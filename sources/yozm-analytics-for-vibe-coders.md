---
type: source
status: active
format: article
author: "[[프로덕트 밸리]]"
publisher: "[[YozmIT]]"
url: https://yozm.wishket.com/magazine/detail/3763/
language: ko
published: 2026-05-20
tags: [product-analytics, vibe-coding, free-tools, posthog, ga4, self-hosted]
created: 2026-05-21
updated: 2026-05-21
---

# 감으로 코딩하던 바이브코더를 위한 무료 분석 도구 5개 추천

[[프로덕트 밸리]] 의 [[YozmIT]] 기고. [[Vibe Coding]] 으로 빠르게 출시한 초기 제품의 사용자 행동을 추적하기 위한 **무료 분석 도구 5 개** 와 그 선택 기준을 제시. 핵심 메시지는 "큰 숫자가 아니라 개별 행동을 본다" — 사용자 100 명 미만 단계에서 관찰해야 할 4 가지 지표 (이탈 지점 · 개별 세션 · 활성화 · 재방문) 를 먼저 설계.

## 다루는 도구 (5 개 + 보조)

| 티어 | 도구 | 특징 |
|------|------|------|
| 1티어 | [[PostHog]] | MIT 라이선스, self-host 무료, **세션 리플레이 + 피처 플래그 + 설문** 통합 |
| 1티어 | GA4 | 월 1,000만 이벤트까지 무료, BigQuery 내보내기 무료 |
| 대안 | [[Umami]] | 완전 무료 self-host, 가벼움, GDPR 친화 |
| 대안 | [[Mixpanel]] | 코호트 / 퍼널 / 리텐션 분석 강함 |
| 대안 | [[Plausible Analytics]] | 가볍고 프라이버시 우선, 약간 유료 |
| 보조 | [[Microsoft Clarity]] | 세션 리플레이 / 히트맵 무료 |

## 4 가지 우선 관찰 지표 (사용자 100 명 미만 단계)

| 지표 | 무엇을 보나 |
|------|----------|
| **이탈 지점** | 사용자가 어디서 떠나는가 |
| **개별 세션** | 어떤 행동 흐름을 거치는가 (큰 숫자 X, 1 명씩) |
| **활성화** | [[Aha Moment]] 까지 도달하는가 |
| **재방문** | 한 번 쓴 사용자가 다시 오는가 |

## 도구 선택 기준 (제품 유형별)

본문 인용 정리:

- **콘텐츠 / 마케팅 사이트** → GA4 (검색 / 채널 / 광고 attribution)
- **SaaS / 웹앱** → PostHog (세션 리플레이 + 피처 플래그 = 가설 검증 빠름)
- **프라이버시 강조 제품** → Umami self-host (쿠키리스)
- **광고 비중 큰 제품** → GA4 + Microsoft Clarity 보조
- **퍼널 / 코호트 정밀 분석** → Mixpanel

## 핵심 메시지

> "측정 도구는 절대 답을 주지 않습니다. 답을 찾기에 **좋은 질문이 떠오르게 해주는 도구**입니다."

→ Vibe Coding 으로 빠르게 만든 제품에서 "왜 사용자가 떠났나" 의 가설을 세우는 출발점이 분석 도구. 도구가 PMF 를 보장하진 않는다.

## 통계 / 사실 인용

- PostHog 사용자 90%+ 가 무료 플랜으로 운영 중
- PostHog 무료 한도: 월 100 만 이벤트 / 세션 리플레이 5,000 건 / 피처 플래그 100 만 요청 / 설문 1,500 응답
- GA4 무료: 월 1,000 만 이벤트 (이후 샘플링), 무제한 속성, BigQuery 내보내기 무료

## 본 vault 와의 연결

- 본인의 [[Vibe Coding]] 회피 패턴 (멀티 에이전트 + 검증 루프 + 문서화) 의 **출시 이후 단계** 보완 — "검증된 코드" 와 "검증된 사용자 행동" 은 다른 영역
- 본인 광고 플랫폼 (리드플레닛, 2026.03 1주 내 구축) 의 운영 분석에 [[PostHog]] / [[Umami]] self-host 후보 적용 가능 — [[product-analytics-for-self-built-systems]] 노트 참고
- [[Agentic Engineering]] 흐름의 다음 영역 — AI 에이전트가 코드만 짜는 게 아니라 **PostHog 설치까지 자동화** 한다는 점이 본문에 언급 (Cursor / Bolt 사례)

## Related

- [[프로덕트 밸리]] (저자 / 요즘IT 코너)
- [[YozmIT]]
- [[PostHog]]
- [[Product Analytics]] (개념)
- [[Vibe Coding]]
- [[product-analytics-for-self-built-systems]] (사용자 관점 노트)
