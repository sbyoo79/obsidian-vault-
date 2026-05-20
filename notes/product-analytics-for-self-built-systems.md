---
type: note
status: active
tags: [product-analytics, posthog, vibe-coding, ad-platform, side-project]
created: 2026-05-21
updated: 2026-05-21
---

# Self-built 시스템의 Product Analytics 도입 검토

[[yozm-analytics-for-vibe-coders]] ingest 후 정리한 **본인 작업 연결 노트**. 멀티 에이전트 워크플로로 빠르게 빌드한 산출물의 **출시 이후 분석 단계** 를 어떻게 채울지.

## 출발 인식

본인의 [[Vibe Coding]] 회피 패턴 = GPT 설계 / Codex 구현 / Claude 리뷰 + 검증 루프 + 문서화. 그러나 이건 **"검증된 코드"** 까지의 영역. **"검증된 사용자 행동"** 은 별개 — 분석 도구가 필요.

본인 [[self-profile]] 의 "실패 경험" 항목 (private):
- 티몬 브랜드 홈 (2022): 기획 단계부터 무리, 5 개 브랜드 stop
- 티몬 구독 서비스 (2021~2022): 구독자 100 명 미만, "하지 말았어야 했던 프로젝트"

→ "엔지니어가 잘 만들어도 비즈니스 결과는 별개" 라는 학습. 분석 도구로 일찍 신호를 잡았으면 다른 결정이 가능했을 수도.

## 적용 후보 (본인 작업)

### 1. 리드플레닛 광고 플랫폼 (2026.03 구축)

- 현재: impression / click 단순 집계 (일 12,000~15,000 impression)
- 부족: 가맹점 본사 입장에서 광고 효과의 정성 신호 (이탈 / 활성화 / 재방문) 미확인
- 후보: **[[PostHog]] self-host** — MIT 라이선스, 데이터 회사 내부 보관, 광고 클릭 후 행동 추적
- 효과: 광고 효과 가설 검증 사이클 단축 + 가맹점 본사 보고 자료 강화

### 2. 향후 사이드 프로젝트

- 초기 단계 PMF 가설 검증 — [[Product Analytics]] 의 100 명 미만 단계 4 지표 (이탈 / 개별 세션 / 활성화 / 재방문)
- 후보: [[PostHog]] Cloud 무료 플랜 (월 100 만 이벤트) 또는 [[Umami]] self-host
- 가치: 멀티 에이전트로 빠르게 빌드한 후 → 빠르게 측정 → 빠르게 결정

## 도입 시 검토 항목

| 항목 | 결정 필요 |
|------|---------|
| 회사 정책 | 외부 분석 도구 사용 가능 여부 (개인정보 / 데이터 외부 전송) |
| self-host vs Cloud | 회사 데이터는 self-host 우선 / 사이드는 Cloud 무료 |
| Cookie / GDPR | 가맹점 본사 → 한국 KISA 가이드 |
| 이벤트 설계 | autocapture vs 명시적 capture — autocapture 가 빠른 시작에 유리 |
| AI 에이전트 자동 설치 | Cursor / Bolt 가 PostHog 설치 자동화한다는 본문 인용 — 본인 워크플로에도 적용 가능 |

## 다음 행동 후보

- [ ] 광고 플랫폼에 PostHog self-host POC — 1 주 내 구축 가능성 평가
- [ ] 사이드 프로젝트 시 PostHog Cloud 무료 플랜으로 시작 (PMF 검증 사이클 단축)
- [ ] [[Agentic Engineering]] 패턴에 "출시 이후 분석 자동화" 보강 검토 — 회사 [[멀티 에이전트 워크플로 decision|AGENTS.md 의 멀티 에이전트 워크플로]] 회고 시점 (6 개월 후) 의 외부 노출 자료 후보

## Related

- [[yozm-analytics-for-vibe-coders]] — 원문 source
- [[PostHog]] · [[Product Analytics]] · [[프로덕트 밸리]]
- [[Vibe Coding]] — 출발 사상
- [[Agentic Engineering]] — 다음 영역 (분석 자동화)
- [[self-profile]] — 본인 실패 경험 (분석 도구 부재의 학습)
