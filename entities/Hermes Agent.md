---
type: entity
status: active
category: tool
tags: [tool, ai-agent, self-improving, llm, procedural-memory]
aliases: [Hermes]
url: https://hermes.nousresearch.com
vendor: "[[Nous Research]]"
license: open-source
platform: [Telegram, Discord, Slack, CLI, Docker, SSH]
created: 2026-05-18
updated: 2026-05-18
---

# Hermes Agent

[[Nous Research]] 의 AI 에이전트 도구. "쓸수록 워크플로에 맞춰지는" 점진적 학습이 특징. 2026 년 [[OpenRouter]] 토큰 사용 랭킹에서 Openclaw 를 제치고 1 위에 오른 시점에 주목받았다.

## 개요

LLM 단독 호출이 아닌 **명시적 [[Procedural Memory]]** 를 갖춘 에이전트. 한 번 성공한 작업 절차를 markdown 으로 저장해두고 다음 호출에 재사용한다. self-improving 의 의미는 "모델이 더 똑똑해진다" 가 아니라 "**사용자 워크플로에 맞춰 진화한다**".

다양한 surface (Telegram / Discord / Slack / CLI / Docker / SSH) 에서 사용 가능하다. 백엔드는 [[OpenRouter]] 를 통해 여러 LLM 을 선택 가능.

## 본 vault 에서의 의미

본 vault 의 [[LLM Wiki]] 패턴과 동일 사상 — "자동 학습 블랙박스" 가 아니라 **markdown 으로 외부화된 명시적 저장**. 본 vault 가 사용자/Claude 의 의식적 ingest 라면, Hermes 는 에이전트의 자율적 저장. 둘 다 산출물은 검증 가능한 markdown.

## Key facts

- 제조: [[Nous Research]]
- 등장: 2026 년 OpenRouter 토큰 사용 랭킹 1 위
- 핵심: 명시적 procedural memory + RL 학습 환경 (Atropos)
- 검색: SQLite FTS5 기반 (10 ms 내 lookup)
- 메모리 stack: 단기 (세션 컨텍스트) + 장기 (저장된 절차) + 사용자 모델 (Honcho)

## 핵심 기능

### Self-Improving 4 기둥

1. **스킬 자동 저장** — 도구 호출 5 회 이상 성공 시 절차를 markdown 으로 기록
2. **메모리 검색** — SQLite FTS5 로 10 ms 내 문서 lookup
3. **동적 개선** — 세션 중 메모리 도구로 저장된 절차 직접 수정
4. **사용자 모델링** — Honcho 기반 사용자 패턴 누적

### 부속 컴포넌트

- **Skills Hub** — 저장된 스킬 관리
- **Atropos** — [[Nous Research]] 의 RL 학습 환경

## 이 vault 에서의 사용

직접 사용은 아님. **참조 비교 대상**. [[Claude]] (현재 vault 의 active agent) 와 다른 자율 저장 모델로 학습 가치.

## 한계

- 개인 개발자 중심 — 팀 권한·공유 모델 부족
- 보안 — 자격증명/시크릿이 자동 절차에 흘러들 위험
- 거버넌스 — 규제·감사 환경에 부적합

## 관련 sources

- [[yozm-hermes-agent-self-improving]]

## 관련 entities

- [[Nous Research]] — 제조사
- [[OpenRouter]] — 백엔드 LLM 라우터
- [[Self-Improving Agent]] — 상위 개념
- [[Procedural Memory]] — 핵심 메커니즘
- [[AI Agent]] — 상위 카테고리
- [[Claude]] — 비교 대상 (자율 저장 vs 명시적 ingest)
- [[LLM Wiki]] — 동일 사상 (markdown 외부화)
