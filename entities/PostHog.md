---
type: entity
status: active
category: tool
tags: [product-analytics, session-replay, feature-flag, open-source, self-host]
aliases: [PostHog Cloud]
vendor: PostHog Inc.
license: open-source
platform: web / mobile / self-host
url: https://posthog.com/
created: 2026-05-21
updated: 2026-05-21
---

# PostHog

오픈소스 통합 **Product Analytics** 플랫폼. 이벤트 추적 · 세션 리플레이 · 피처 플래그 · 설문 · A/B 테스트를 하나의 도구에 통합. MIT 라이선스 + self-host 무료.

## 개요

이벤트 분석만 다루는 GA4 / Mixpanel 과 달리 **PMF 가설 검증의 전체 사이클** (관찰 → 가설 → 실험 → 측정) 을 한 도구로 운영 가능. self-host 옵션이 있어 데이터 오너십 / 규정 준수 / 비용 통제가 필요한 환경에 적합.

## 본 vault 에서의 의미

[[yozm-analytics-for-vibe-coders]] 의 1 티어 추천 도구. 본인의 광고 플랫폼·DW 같은 [[Vibe Coding]] 회피 워크플로 산출물의 **출시 이후 분석 단계** 후보 — [[product-analytics-for-self-built-systems]] 노트 참조.

## 핵심 기능

- **이벤트 추적** — autocapture + 명시적 capture 둘 다 지원
- **세션 리플레이** — 사용자 화면 재생, 이탈 지점 정확 파악
- **피처 플래그** — 점진 배포 / A/B 테스트 통합
- **설문** — 인앱 또는 이메일로 사용자 피드백 수집
- **퍼널 / 코호트 / 리텐션** 분석

## 이 vault 에서의 사용

직접 사용 X, 단 다음 검토 후보:

- 리드플레닛 광고 플랫폼 (2026.03 구축) — impression / click 외에 사용자 행동까지 추적
- 후속 사이드 프로젝트 — 초기 단계 PMF 가설 검증

self-host 또는 PostHog Cloud 무료 플랜으로 시작 가능.

## Key facts

- 라이선스: MIT (오픈소스)
- self-host: 완전 무료
- Cloud 무료 한도: 월 100 만 이벤트 / 세션 리플레이 5,000 / 피처 플래그 100 만 / 설문 1,500
- 사용자의 90%+ 가 무료 플랜 운영 중
- AI 에이전트 (Cursor / Bolt) 가 PostHog 설치를 자동화하는 사례 등장

## 관련 sources

- [[yozm-analytics-for-vibe-coders]]

## 관련 entities

- [[Product Analytics]] — 카테고리 개념
- [[Vibe Coding]] — 출시 이후 단계 보완 도구
- [[Umami]] · [[Mixpanel]] · [[Plausible Analytics]] — 같은 카테고리 대안
