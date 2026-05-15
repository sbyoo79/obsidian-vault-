---
type: entity
status: active
category: concept
tags: [pkm, pattern, llm, wiki, workflow]
aliases: [LLM-driven wiki, Karpathy wiki pattern]
proposed_by: "[[Andrej Karpathy]]"
year_proposed: 2025
url: https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f
created: 2026-05-14
updated: 2026-05-14
---

# LLM Wiki

[[Andrej Karpathy]] 가 제안한 PKM 패턴. LLM 이 markdown 위키를 점진적으로 빌드·유지하고, 사람은 큐레이션·방향·비판적 사고를 담당한다.

## 개요

기존 RAG / "원본을 매 질문마다 다시 읽는다" 식 접근의 한계를 정면으로 비튼다. 위키 자체를 LLM 이 누적해 가는 **컴파일된 산출물** 로 본다 — 매 query 마다 원본 PDF/article 을 토큰 비용 들여 재해석하는 대신, 위키에 이미 정리된 요약·entity·cross-ref 를 우선 활용한다.

핵심 통찰은 한 문장: "지식 베이스 유지의 어려움은 읽기/사고가 아니라 부기(bookkeeping) 다." 사람이 매번 포기하는 bookkeeping 영역을 LLM 에게 위임한다.

[[Zettelkasten]], [[Digital Garden]], [[Building a Second Brain]] 같은 인간 중심 PKM 흐름의 자연스러운 다음 단계로 볼 수 있다.

## 본 vault 에서의 의미

이 vault 의 schema [[CLAUDE]] 가 채택한 운영 패턴. 본 vault 의 폴더 구조 / ingest·query·lint 워크플로 / `index.md` · `log.md` 보조 파일이 모두 이 패턴에서 직접 파생된다.

## Key facts

- 제안자: [[Andrej Karpathy]]
- 원안: gist 한 편 ([[karpathy-llm-wiki]])
- 3 계층: Raw Sources / The Wiki / The Schema
- 3 작업: Ingest / Query / Lint
- 보조: `index.md`, `log.md`

## 원안 / 출처

[[karpathy-llm-wiki]] gist 1 편이 사실상 유일한 1 차 자료. 후속 토론은 트위터/HN 댓글로 분산되어 있다.

## 핵심 원리

| 항목 | 설명 |
|------|------|
| Compile 된 위키 | 위키 자체가 산출물. 원본 재해석 비용을 영구히 줄인다 |
| LLM = 사서 | 부기, cross-ref, summary 유지가 LLM 강점 |
| 사람 = 큐레이터 | 무엇을 받아들이고 무엇을 버릴지 사람이 결정 |
| Schema = 헌법 | `CLAUDE.md` 가 LLM 동작을 묶는다 |

## 채택 사례

- **본 vault** (2026-05-14): [[CLAUDE]] 로 schema 정의, 첫 ingest 로 [[karpathy-llm-wiki]] 처리

## 관련 sources

- [[karpathy-llm-wiki]] — 원안 gist

## 관련 entities

- [[Andrej Karpathy]] — 제안자
- [[Obsidian]] — 브라우저로 권장된 도구
- [[Zettelkasten]] (페이지 미생성) — 인간 중심 비교 대상
- [[Digital Garden]] (페이지 미생성) — 인접 패턴
