---
type: source
status: active
format: article
author: "[[미어캣]]"
publisher: "[[YozmIT]]"
url: https://yozm.wishket.com/magazine/detail/3765/
language: ko
published: 2026-05-21
tags: [google, gemini, google-io, ai-agent, ai-platform, antigravity, agent-payments, android-xr]
created: 2026-05-22
updated: 2026-05-22
---

# Gemini가 구글을 먹어치우는 중입니다: 구글 I/O 2026 총정리

[[미어캣]] 의 [[YozmIT]] 기고. 구글 I/O 2026 컨퍼런스에서 발표된 [[Gemini]] 의 전방위 확대를 정리한 분석 기사. 저자 진단: **"[[Gemini]] 가 [[Google]] 의 모든 것을 먹어치우고 있으며, [[Google]] 은 IT 의 모든 것을 먹어치우려는 중"**.

## 핵심 주장

[[Google]] 의 **풀스택 AI 통합 전략** — 모델·플랫폼·서비스·하드웨어를 [[Gemini]] 로 재편성. CEO Sundar Pichai 발언: "차별화된 풀스택 방식으로 AI 혁신 추구".

## 모델 라인업

| 모델 | 핵심 사실 |
|------|----------|
| **Gemini 3.5 Flash** | Terminal-Bench 2.1 **76.2%** (GPT-5.5 78.2%). 도구 선택·멀티모달 업계 최상위. **토큰 가격 직전 대비 3배 인상** (Pro 대비 25% 저렴) |
| **Gemini Omni** | 영상 생성 모델. 커뮤니티 평가: "Sora 수준의 우위 불명확" |
| **AI Ultra $100/월** | 개발자·크리에이터용 구독제, 사용량 기반 청구 |

고객 사례 인용: "다른 최상위 모델에서 하던 80% 수준의 작업을 Flash 로 이전 → **연 $10억+ 절감**".

## 에이전트 플랫폼

- **[[Antigravity]] 2.0**: 코딩 IDE 에서 통합 도구로 확장. 사용자 반응 = **"이전 버전으로 돌아가는 방법" 검색이 1위**. VS Code 스타일이 사라지고 에이전트 중심으로 강제 전환되면서 인증·실행 문제 발생.
- **Gemini Spark**: 클라우드 기반 자율 실행 에이전트. 지메일·구글 독스 기본 통합. 여름에 자율 문자/이메일 발송 + 로컬 브라우저 제어 추가 예정.

## 검색 개편 (25년 만의 대규모 변화)

- 검색창 = 키워드 입력 → **AI 에이전트 대화 공간** 전환
- **Information Agents**: 24시간 백그라운드 모니터링 + 변화 시 푸시
- AI 검색 모드 월 사용자 **10억 명** 돌파, 분기 쿼리 **2배+** 증가

## 쇼핑·결제

- **Universal Cart**: 검색·Gemini 앱 상품 한 곳에서 결제
- **[[Agent Payments Protocol]]** (AP2): 자율 결제 규칙 표준 공개

## 하드웨어

- **Android XR 안경**: 삼성·퀄컴·젠틀몬스터·와비파커 협력. 음성 모델 가을, 화면 모델 추후
- **XREAL Project Aura**: 2026 년 내 출시 확정 유선 XR 글래스

## 약점·잡음 (저자 지적)

- [[Antigravity]] 2.0 강제 전환 불만 (이전 버전 회귀 검색 1위)
- Gemini Pro 출시 지연
- Gemini Omni 의 미적지근한 시장 반응
- → "속도와 사용자 경험의 간극" 노출

## 가격 인상 트렌드

- Gemini 3.5 Flash 토큰 가격 **3배 인상**
- 기사 저자 진단: [[Google]] · [[OpenAI]] · [[Anthropic]] 모두 **가격 인상 한계 시험 중**

## 본 vault 와의 연결

- **[[ai-market-pulse]] 가설 수정 트리거**: "[[Anthropic]] 우세" 단순 가설 → **[[Anthropic]] + [[Google]] + [[OpenAI]] 3 파전** 으로 재구성 필요. [[Anthropic]] 의 [[AI-driven R&D]] 의제는 여전히 차별점이지만, [[Google]] 은 "풀스택 통합" 이라는 다른 축으로 대응 카드를 들고 나옴.
- **"Google 자금력 ↔ Gemini 실측 부재"** 관전 포인트 ([[ai-market-pulse]]) 가 한 단계 진전 — 자금력이 풀스택 카드로 가시화. 본인이 [[Gemini]] 를 직접 안 써본 빈틈이 점점 더 명확.
- **[[llm-tool-comparison]] 외부 정보 누적**: Gemini 3.5 Flash 벤치 (Terminal-Bench 2.1 76.2%) / Antigravity 2.0 강제 전환 불만 / 가격 3배 인상. 본인 실측은 여전히 미검증.
- **도구 평가 축 추가 후보**: [[Antigravity]] 의 강제 전환 사례는 **UX 안정성** 도 평가 축이 되어야 함을 보여줌. 현재 [[llm-tool-comparison]] 은 성능 강점·약점만 보고 있는데, "버전업 시 UX 안정성" 도 본인 도구 풀 (Claude Code / Codex) 평가에 들어가야 함.
- **가격 트렌드 영향**: 본인 워크플로 비용에 직접 영향. [[Claude]] · [[Codex]] 가격 인상 가능성 추적 필요.

## Related

- [[Google]] (주인공)
- [[Gemini]] (제품 라인)
- [[Antigravity]] (에이전트 IDE)
- [[Agent Payments Protocol]] (AP2)
- [[Anthropic]] · [[OpenAI]] (경쟁 축)
- [[Claude]] · [[Codex]] · [[ChatGPT]] (본인 도구 풀 비교 대상)
- [[ai-market-pulse]] (시장 관전 living doc)
- [[llm-tool-comparison]] (도구 실측 living doc)
- [[미어캣]] (필자)
- [[YozmIT]]
