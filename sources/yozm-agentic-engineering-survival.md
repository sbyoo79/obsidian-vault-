---
type: source
status: active
format: article
author: "[[DevOwen]]"
publisher: "[[YozmIT]]"
url: https://yozm.wishket.com/magazine/detail/3752/
language: ko
tags: [agentic-engineering, ai-agent, llm, context-engineering, verification, workflow, productivity]
created: 2026-05-14
updated: 2026-05-14
---

# 에이전틱 엔지니어링 시대에서 살아남기

[[DevOwen]] 이 [[YozmIT]] 에 기고한 글. AI 에이전트가 일상화되는 시점에서 개인과 조직이 살아남기 위해 무엇이 필요한지 짚는다.

## 핵심 논지

생산성의 병목이 "결과 생성" 에서 "검증과 조율" 로 이동한다. 그래서 살아남는 사람은 **프롬프트를 빨리 쓰는 사람이 아니라 업무를 설계할 줄 아는 사람** 이다. 도구보다 기준이 먼저다.

> 에이전트가 실패하는 이유는 모델의 한계가 아니라 **성공 조건의 모호함** 이다.

## 개인 수준의 세 가지 능력

| 능력 | 의미 |
|------|------|
| **분해력** | 일을 기계가 처리 가능한 단위로 나눈다 |
| **명세력** | 성공/실패 조건과 기준을 명시한다 |
| **검증 설계력** | 결과 신뢰성을 확보하는 메커니즘을 만든다 |

## 조직/리더 수준의 설계

- **공통 컨텍스트 레이어** — 용어 사전, API 계약, 운영 정책 (= [[Context Engineering]] 의 실천)
- **권한·책임 경계** — 읽기/쓰기 분리, 승인 게이트
- **평가 체계** — 채택률, 수정 시간, 롤백률 같은 운영 지표

## 인상적인 통찰

- "에이전트는 채점을 재위임받으면 안 된다" — 생성기와 독립된 **검증 루프** (테스트, 샌드박스, 휴먼 리뷰) 가 있어야 단순 자동화가 아닌 진정한 협업이 된다
- "환경을 안전하게 반복 실행하게 만드는 장치 (= 하네스)" 가 생산성의 새 인프라
- [[Claude]] Opus 4.7 의 1M 토큰 컨텍스트 같은 모델 진화는 그 자체로 답이 아니다 — 컨텍스트를 무엇으로 채우느냐가 결과를 좌우

## 본 vault 와의 연결

- 본 vault 의 schema [[CLAUDE]] 자체가 [[Context Engineering]] 의 작은 사례 — LLM 에게 "어떻게 정리할지" 를 미리 헌법으로 박아두는 방식
- [[LLM Wiki]] 패턴은 글의 "공통 컨텍스트 레이어" 와 사상이 같다. 다른 점은 LLM Wiki 가 PKM 개인 영역, agentic engineering 은 조직·제품 개발 영역이라는 스코프 차이
- 회사 작업의 공통 룰(선행 분석 → 티켓 → 브랜치 → 본 작업)도 글의 "기준 먼저" 원칙과 같은 방향

## Related

- [[DevOwen]]
- [[YozmIT]]
- [[Agentic Engineering]]
- [[AI Agent]]
- [[Context Engineering]]
- [[Claude]]
- [[LLM Wiki]]
