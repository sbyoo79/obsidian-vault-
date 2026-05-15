---
type: entity
status: active
category: concept
tags: [concept, ai-agent, llm, workflow, context]
aliases: [컨텍스트 엔지니어링, context eng]
created: 2026-05-14
updated: 2026-05-14
---

# Context Engineering

LLM/에이전트에게 줄 컨텍스트를 **충돌·중복 없이 체계적으로 정리** 하는 작업.

## 개요

프롬프트 엔지니어링이 "한 번 잘 쓰는 문장" 에 집중한다면, context engineering 은 **재사용·누적되는 자산 으로서의 컨텍스트** 를 설계한다. 용어 사전, API 계약, 운영 정책, 도메인 지식 같은 것들이 시간 누적되어 한 곳에 정리된 형태. 같은 정보가 여러 곳에 분산·모순되면 agent 의 결과가 불안정해진다는 진단에서 출발한다.

## 본 vault 에서의 의미

본 vault 자체가 작은 context engineering 산출물. schema [[CLAUDE]] 는 "Claude 가 이 vault 에서 어떻게 행동할지" 를 박아둔 헌법이고, `index.md` 는 vault 콘텐츠의 목차, entity 페이지들은 도메인 지식의 단위다. [[LLM Wiki]] 패턴은 결국 context engineering 의 PKM 영역 적용 방식.

회사 측에서도 동일한 사상이 적용 중이다 — `common/agents/AGENTS.md` (공통 룰), 프로젝트별 `CLAUDE.md`, knowledge-base 리포가 모두 같은 layer.

## Key facts

- 결과물: 단일 prompt 가 아니라 **누적된 문서·entity·룰 집합**
- 핵심 가치: 충돌 없는 정합성 (= 같은 사실은 한 곳에서만 정의)
- 도구: markdown 위키, vector DB, MCP, custom retrieval 등 다양

## 원안 / 출처

용어 자체는 2024~2025 무렵 LLM agent 담론과 함께 보편화. [[Andrej Karpathy]] 의 [[LLM Wiki]] gist 도 같은 흐름의 한 응용.

## 핵심 원리

- **Single source of truth** — 같은 사실은 한 곳
- **누적·진화** — 매 작업이 컨텍스트를 조금씩 풍성하게 만든다
- **충돌 검출** — lint / health check 로 모순을 잡는다
- **layer 분리** — schema, 데이터, 결정 이력을 분리 보관

## 채택 사례

- 본 vault: schema [[CLAUDE]] + `index.md` + `entities/`
- 회사: 공통 룰 (`common/agents/AGENTS.md`) + 프로젝트별 `CLAUDE.md` + knowledge-base

## 관련 sources

- [[yozm-agentic-engineering-survival]] — 조직 레벨 context layer 설명
- [[karpathy-llm-wiki]] — PKM 영역 적용 사례

## 관련 entities

- [[Agentic Engineering]] — 상위 흐름
- [[AI Agent]] — context 의 소비자
- [[LLM Wiki]] — 적용 패턴 한 예
