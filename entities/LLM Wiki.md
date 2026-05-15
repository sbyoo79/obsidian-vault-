---
type: entity
status: active
tags: [pkm, pattern, llm, wiki]
created: 2026-05-14
---

# LLM Wiki

[[Andrej Karpathy]] 가 제안한 PKM 패턴. LLM 이 markdown 위키를 점진적으로 빌드·유지하고, 사람은 큐레이션·방향·비판적 사고를 담당한다.

## 구조

- **Raw Sources** — 원본 (불변)
- **The Wiki** — LLM 이 만든 markdown (summary, entity, cross-ref)
- **The Schema** — 위키 구조/컨벤션 정의 (예: `CLAUDE.md`)

## 작업 3 가지

- Ingest / Query / Lint

## 보조 파일

- `index.md` — 카테고리 카탈로그
- `log.md` — append-only 이력

## 채택 이력

- 2026-05-14: 본 vault 에 schema [[CLAUDE]] 로 채택

## 관련

- [[karpathy-llm-wiki]] — 원안 gist
- [[Obsidian]] — browser 도구
