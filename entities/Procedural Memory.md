---
type: entity
status: active
category: concept
tags: [concept, memory, cognition, ai-agent, llm, workflow]
aliases: [절차적 기억, procedural memory]
created: 2026-05-18
updated: 2026-05-18
---

# Procedural Memory

"어떻게 하는지" 를 기억하는 메모리. 자전거 타기, 도구 사용 같은 절차적 스킬. AI 에이전트 영역에서는 **반복적으로 성공한 작업 절차를 외부 저장하고 재사용** 하는 구조를 가리킨다.

## 개요

인지심리학의 분류에서 [[Declarative Memory]] (사실/사건 기억) 와 대비되는 개념. 사람의 procedural memory 는 신경 회로에 새겨지지만 LLM 에이전트 영역에서는 weight 가 아닌 **외부 markdown / DB** 로 저장된다. 그래서 AI 의 procedural memory 는 **외부화된 형태로만 존재** — 검증 / 갱신 / 삭제가 가능하다는 장점.

## 본 vault 에서의 의미

본 vault 의 sources 와 entities 가 **declarative memory** 라면, 운영 룰 / ingest 워크플로 / 자동 commit 패턴 같은 schema 룰이 **procedural memory** 에 해당한다. [[CLAUDE]] 파일 자체가 vault 의 procedural memory.

## Key facts

- 인지심리학 분류: declarative ↔ procedural 의 한 축
- 사람: 신경 회로 (자동화)
- LLM 에이전트: 외부 markdown / DB (명시적)
- 장점: 검증 가능, 갱신 가능, 사용자에게 공유 가능

## 원안 / 출처

용어 자체는 인지심리학 (Anderson 의 ACT-R 같은 인지 모델). LLM 에이전트로의 전유는 2024~ 흐름.

## 핵심 원리

- **반복 성공 → 저장 트리거**
- **외부 저장소** — 사람이 읽을 수 있는 형식
- **호출 시점 retrieval** — 검색·인덱싱 필요
- **갱신·삭제 메커니즘** — 무효해진 절차 처리

## 채택 사례

- [[Hermes Agent]] — 도구 호출 5 회 이상 성공 시 자동 저장
- [[Claude]] memory 기능 (Anthropic) — 폐쇄형 사용자 메모리
- 본 vault — schema ([[CLAUDE]]) 가 procedural memory 의 사용자 주도 형태

## 관련 sources

- [[yozm-hermes-agent-self-improving]]

## 관련 entities

- [[Self-Improving Agent]] — procedural memory 가 핵심 자원
- [[Hermes Agent]] — 대표 구현
- [[Context Engineering]] — 상위 흐름
