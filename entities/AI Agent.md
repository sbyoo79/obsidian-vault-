---
type: entity
status: active
category: concept
tags: [concept, ai, agent, llm, automation]
aliases: [AI 에이전트, LLM agent, autonomous agent]
created: 2026-05-14
updated: 2026-05-14
---

# AI Agent

문서 해석·코드 수정·도구 호출·결과 평가를 스스로 수행하는 LLM 기반 실행 주체.

## 개요

LLM 단독이 단발성 출력에 가깝다면, agent 는 거기에 **루프, 도구 사용, 환경과의 상호작용** 이 더해진 형태다. 한 요청 안에서 여러 단계를 자율 결정한다 (예: 파일 읽기 → 분석 → 수정 → 테스트). [[Claude]] Code, Cursor, Devin 같은 도구가 구체적 인스턴스.

[[Agentic Engineering]] 흐름은 agent 가 사람의 손을 대체하기보다 사람과 같이 일하는 환경 설계 쪽을 강조한다.

## 본 vault 에서의 의미

본 vault 의 active agent 는 [[Claude]] (특히 Claude Code CLI). agent 가 vault 의 read/write/ingest/lint 를 수행하는 동안 사용자는 큐레이션과 비판적 판단을 담당한다 — [[LLM Wiki]] 패턴의 역할 분담과 동일.

## Key facts

- 구성 요소: LLM + tool use + 환경 (file system, browser, API)
- 핵심 차이 (vs 단순 LLM 호출): 다단계 자율 결정, 도구 활용, 환경 상태 변경
- 한계: 검증 없는 자율 실행은 신뢰 어려움 → 독립 검증 루프 필요
- 대표 도구: [[Claude]] Code, Cursor, Devin, AutoGPT 류

## 원안 / 출처

명확한 원안은 없으나 2022~2024 LLM 발전과 tool use API 도입을 거치며 사실상의 카테고리로 굳어졌다.

## 핵심 원리

- **Loop** — 한 번에 답을 내지 않고 반복 시도·관찰
- **Tool use** — LLM 이 외부 도구를 호출해서 환경과 상호작용
- **State** — 컨텍스트와 외부 상태를 함께 다룬다
- **Verification** — 채점은 별개 메커니즘이 맡는다

## 채택 사례

- 본 vault: [[Claude]] 가 vault 의 agent
- 회사 작업: [[Claude]] Code 가 분석/구현/문서 작성/git 작업 수행

## 관련 sources

- [[yozm-agentic-engineering-survival]]

## 관련 entities

- [[Agentic Engineering]] — agent 를 전제로 한 엔지니어링 변화
- [[Context Engineering]] — agent 에게 좋은 컨텍스트 제공하기
- [[Claude]] — 대표 instance
- [[LLM Wiki]] — agent 친화 PKM 패턴
