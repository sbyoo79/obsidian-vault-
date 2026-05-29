---
type: note
status: active
tags: [ai-product, llm, eval, distribution-kpi, system-design, backend, multi-tenant]
related: ["[[yozm-ai-why-wrong]]"]
created: 2026-05-29
updated: 2026-05-29
---

# AI 프로덕트 — 분포 사고로의 전환과 백엔드 엔지니어 보강 시야

[[yozm-ai-why-wrong]] 정독 후 본인 관점에서 한 번 더 다듬은 노트. 글은 PM 시야로 잘 정리됐지만, 21 년차 백엔드·시스템 설계자 입장에서 **글에 없는 결을 더해두려고** 작성.

## 1. 결정론 → 분포론은 KPI 자체의 재정의

글의 "정확도 100 % KPI 버려라" 는 절반의 진실이다. 진짜 본질은 KPI 가 **단일 숫자 → 분포** 로 바뀌는 것:

- 기존 시스템 KPI: 정확도 = 0.99 같은 단일 평균
- LLM 시스템 KPI: **p50 / p95 / p99 + tail risk** 분포 추적

p50 만 빛나는 시스템과 p99 에서 [[Air Canada|에어캐나다]] 사고가 터지는 시스템은 다르게 관리해야 한다. SLO·SLA 도 분포 기준으로 다시 짜야 한다. 이건 백엔드의 latency p50/p95/p99 관측과 같은 마인드셋을 출력 품질에도 적용하는 것 — 이미 익숙한 사고를 결국 적용처만 옮기는 것이라 어렵지 않다.

## 2. 에어캐나다 판결의 진짜 교훈

글은 "AI 답변에 책임진다" 로 요약했는데, 한 발 더 들어가면:

> **LLM 출력에 회사 정책 권한을 위임하는 순간, 그 출력은 회사 발화로 간주된다.**

"참고용" 면책 문구는 통하지 않는다는 게 핵심. 향후 모든 LLM 기반 고객 응대 시스템 거버넌스의 출발 원칙이 될 것. 본인이 [[리드플레닛]] ERP 에 LLM 응답 기능 (보고서 산출·고객 응대 보조 등) 을 붙일 때 잊지 말 자리.

## 3. 백엔드 엔지니어 보강 시야 — 글에 없는 것

### 3-1. LLM 은 외부 API 처럼 다뤄야 + α

기존 외부 API 호출 패턴 (retry / timeout / circuit breaker / fallback) 은 기본이다. 거기에 **"성공한 호출의 결과가 틀릴 수 있음"** 이라는 새 차원이 추가된다. HTTP 200 + 본문 그럴듯한데 사실은 [[Hallucination|환각]] — 이건 기존 외부 API 에는 없던 모드.

대응:
- 출력 검증 레이어 ([[Eval]] 기반) 를 호출 다음 단에 강제로 둠
- 신뢰도 점수 / 출처 인용 강제 (citation-forced prompting)
- 위험 등급별 휴먼 게이트 (자동 / 보조 / 휴먼 확인 필수 3 단계)

### 3-2. 비용 관측성 — 멀티테넌트의 새 차원

토큰 단위 과금은 **per-tenant · per-feature · per-request** 추적이 필수. 본인 [[리드플레닛]] 케이스 (멀티테넌트 ERP) 에서:

- 한 테넌트가 의도 (악의 / 무지) 적으로 무한 루프성 프롬프트를 돌리면 비용 폭발
- SLO 에 **비용 budget** 을 정식 변수로 넣어야 함 ("응답 시간" / "정확도" 옆에 "비용 / 요청")
- 비용 alert · circuit breaker · 테넌트별 quota 가 신규 모듈로 필요

이건 글에서 "비용 예측 불가" 로 한 줄 처리된 부분의 백엔드 측 구현 디테일이다. 단순 모니터링이 아니라 **테넌트 격리 + 운영 제어** 까지 가야 한다.

### 3-3. Eval 은 출력 검증을 넘어 의사결정 과정 검증으로

본인 [[Agentic Engineering]] 워크플로 (GPT 설계 → Codex 구현 → Claude 리뷰) 는 [[Eval]] 의 실무 한 형태다. 단순 출력 비교가 아니라 **에이전트의 의사결정 과정 자체** 를 다른 에이전트가 검증하는 방식. 회사 단위 AGENTS.md 표준화 작업에 이걸 명문화해 둘 가치 있음.

## 4. 글에서 빠진 (그러나 곧 따라올) 주제

- **[[Context Engineering]]** — Eval 못지않게 입력 측 품질 관리가 결과를 결정. RAG 품질 · 프롬프트 버전 관리 · 컨텍스트 위생 (sensitive info filter) 까지. 출력 검증만 강조하면 절반의 솔루션.
- **에이전트 chained call 시 오류 누적** — single-shot Eval 만 보면 multi-step agent 의 누적 오류는 못 잡음. trajectory-level Eval 이 다음 화두.
- **모델 교체 시 회귀 평가** — Claude 3.5 → 4.7 같은 업그레이드도 KPI 분포가 바뀜. [[yozm-codex-vs-claude-code]] 가 본인 토큰 부족이 모델 변경의 결과였음을 객관 검증한 것과 같은 결.

## 5. Action items (본인 회사 적용)

- [ ] 리드플레닛 LLM 기능 (보고서 산출·DW 분석 등) 에 신뢰도 표기 / 출처 인용 컨벤션 정립
- [ ] 멀티테넌트 비용 budget SLO 변수 신설 검토
- [ ] AGENTS.md 에 Eval 단계 명시 (multi-agent cross-check = LLM-as-judge 패턴 설명 추가)
- [ ] [[Air Canada]] 케이스를 팀 공유 — LLM 출력 거버넌스 출발선으로

## Related

- [[yozm-ai-why-wrong]] (출처)
- [[Eval]], [[Hallucination]], [[Air Canada]]
- [[Agentic Engineering]], [[Context Engineering]]
- [[llm-tool-comparison]], [[ai-market-pulse]]
