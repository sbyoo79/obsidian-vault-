---
type: source
status: active
tags: [pkm, llm, wiki, obsidian, pattern]
url: https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f
author: [[Andrej Karpathy]]
created: 2026-05-14
updated: 2026-05-14
---

# LLM Wiki: A Pattern for Personal Knowledge Management

[[Andrej Karpathy]] 의 gist. LLM 이 markdown 위키를 점진적으로 빌드·유지하는 PKM(개인 지식 관리) 패턴을 제안한다. 위키 자체를 "compile 된 산출물"로 본다 — 매 query 마다 원본을 재해석하는 대신 위키에 누적된 결과를 우선 활용한다.

## 3 계층 구조

| 계층 | 역할 |
|------|------|
| Raw Sources | 원본 (article, PDF, video 등) — 불변 |
| The Wiki | LLM 이 만든 markdown — summary, entity, cross-ref |
| The Schema | 위키 구조/컨벤션 정의 (예: `CLAUDE.md`) |

## 핵심 작업 3 가지

- **Ingest** — 새 source 를 처리하고 관련 위키 페이지를 갱신, log 에 append
- **Query** — 위키 페이지에서 합성·인용. 가치 있는 결과는 다시 위키에 정리
- **Lint** — 상호 참조 / orphan / 모순 점검

보조 파일: `index.md`(카테고리 카탈로그), `log.md`(append-only 이력).

## 통찰

> "지식 베이스 유지의 어려움은 읽기/사고가 아니라 부기(bookkeeping)."

LLM 은 사람이 결국 포기하는 유지·정리 작업을 잘 수행한다. 사람은 큐레이션·방향·비판적 사고에 집중한다.

## 언급된 도구

- [[Obsidian]] — browser
- Web Clipper — article 수집
- Dataview — 동적 query plugin
- Marp — markdown slide
- qmd — local 검색

## Related

- [[Andrej Karpathy]]
- [[LLM Wiki]]
- [[Obsidian]]
- [[CLAUDE]] (본 vault schema 도 이 패턴을 채택)
