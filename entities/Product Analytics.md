---
type: entity
status: active
category: concept
tags: [analytics, product, pmf, user-behavior]
aliases: [product analytics, 제품 분석]
created: 2026-05-21
updated: 2026-05-21
---

# Product Analytics

사용자 행동 데이터를 통해 제품의 [[PMF]] · 활성화 · 리텐션 가설을 검증하는 분석 영역. **"큰 숫자가 아니라 개별 행동"** 을 보는 데서 출발해, 사용자 100 명 미만 단계에서는 **이탈 지점 / 개별 세션 / 활성화 / 재방문** 4 가지 우선 관찰 지표가 핵심.

## 개요

전통 웹 분석 (페이지뷰 / 세션 / 직접·간접 트래픽) 의 한계 — "사용자가 왜 떠났는지 모른다" — 를 보완하기 위해 등장. 이벤트 단위 / 사용자 단위 / 코호트 단위 추적이 핵심.

대표 프레임워크: **[[AARRR]]** (Acquisition / Activation / Retention / Revenue / Referral), **[[North Star Metric]]**, **퍼널 / 코호트 / 리텐션** 분석.

## 본 vault 에서의 의미

본인의 [[Vibe Coding]] 회피 패턴 (멀티 에이전트 워크플로 + 검증 루프) 의 **출시 이후 단계** 를 채우는 영역. 코드 검증만으로는 PMF 가 검증되지 않음 ([[티몬-구독-서비스-회고|티몬 구독 서비스]] · [[티몬-브랜드홈-회고|브랜드 홈]] 같은 본인 실패 경험 — private memory) — 사용자 행동 측정이 동반되어야 함.

## Key facts

- 도구 카테고리: 통합형 ([[PostHog]]) / 이벤트 ([[Mixpanel]]) / 가벼움 ([[Umami]], [[Plausible Analytics]]) / 마케팅 통합 (GA4) / 세션 리플레이 보조 ([[Microsoft Clarity]])
- 100 명 미만 단계: 큰 숫자보다 개별 세션 관찰이 우선
- AI 코딩 도구 (Cursor / Bolt) 가 분석 도구 설치까지 자동화하는 흐름 ([[yozm-analytics-for-vibe-coders]])
- [[Aha Moment]] = 사용자가 제품 가치를 처음 체감하는 순간. 활성화 지표의 기준점

## 채택 사례

- [[yozm-analytics-for-vibe-coders]] — 프로덕트 밸리, 무료 도구 5 개 + 선택 기준
- (개인 검토) 본인 광고 플랫폼·후속 사이드 프로젝트 — [[product-analytics-for-self-built-systems]]

## 관련 sources

- [[yozm-analytics-for-vibe-coders]]

## 관련 entities

- [[PostHog]] — 통합 1 티어
- [[Vibe Coding]] — 출시 이후 단계의 보완 영역
- [[Agentic Engineering]] — AI 에이전트의 다음 영역 (코드 → 분석 자동화)
