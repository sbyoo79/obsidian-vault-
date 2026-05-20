---
type: entity
status: active
category: tool
tags: [product-analytics, event-tracking, cohort, funnel, retention]
aliases: [Mixpanel]
vendor: Mixpanel Inc.
license: commercial
platform: web / mobile / SaaS
url: https://mixpanel.com/
created: 2026-05-21
updated: 2026-05-21
---

# Mixpanel

상업용 **Product Analytics** SaaS. 이벤트 단위 추적 + **코호트 / 퍼널 / 리텐션 분석** 에 강함. PostHog 의 가장 직접 경쟁 도구. 무료 한도 (월 100 만 이벤트) 있음.

## 개요

GA4 가 마케팅 / 트래픽 분석에 강하다면 Mixpanel 은 **제품 안 사용자 행동 분석** 에 특화. 코호트 정의 / 퍼널 단계 / 리텐션 곡선 같은 SaaS 분석에 자주 채택.

## 본 vault 에서의 의미

[[yozm-analytics-for-vibe-coders]] 에서 코호트·퍼널·리텐션 정밀 분석이 필요할 때 대안으로 추천. self-host 불가라 데이터 외부 전송 정책 검토 필요. [[product-analytics-for-self-built-systems]] 노트의 도구 선택 기준에 포함.

## 핵심 기능

- 이벤트 단위 추적
- 코호트 분석 (가입 시점 / 행동 패턴 기반)
- 퍼널 분석 (단계별 전환율)
- 리텐션 곡선 (Day-N 잔존율)
- A/B 테스트

## Key facts

- 무료 한도: 월 100 만 이벤트 (Growth 플랜)
- 유료: 월 25 USD~ (트래픽 기반)
- self-host 불가 (SaaS 만)
- 데이터 외부 전송 — 회사 정책 / GDPR 검토 필요

## 관련 sources

- [[yozm-analytics-for-vibe-coders]]

## 관련 entities

- [[PostHog]] · [[Umami]] · [[Plausible Analytics]] — 같은 카테고리
- [[Product Analytics]]
