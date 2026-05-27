---
type: entity
status: active
category: tool
tags: [tool, ai, llm, anthropic, assistant]
aliases: [Claude AI, Claude Code]
url: https://claude.com
vendor: Anthropic
license: commercial
platform: [CLI, Desktop, Web, API, VS Code, JetBrains]
created: 2026-05-14
updated: 2026-05-14
---

# Claude

[[Anthropic]] 이 만든 LLM 어시스턴트. 회화부터 코드 편집·파일 시스템 조작까지 다루는 범용 도구.

## 개요

2021 년 OpenAI 출신 연구진이 세운 Anthropic 의 대표 제품. 모델 라인업은 Opus(최대 성능) / Sonnet(균형) / Haiku(속도) 로 나뉘며 4.X 식 정기 버전업을 한다. 안전성·정렬(alignment) 연구 비중이 높고, "Constitutional AI" 라는 학습 접근으로 알려져 있다.

접근 방식은 CLI (`Claude Code`), Desktop, Web, API, IDE extension (VS Code / JetBrains) 등 다양하다. tool use, prompt caching, computer use, file I/O 같은 기능이 API 와 CLI 양쪽에 점진적으로 들어가고 있다.

## 본 vault 에서의 의미

이 vault 의 **active agent**. 모든 ingest / query / lint 작업을 수행한다. `format: discussion` source 의 `author` 가 곧 Claude (특정 모델 버전). 사용자와의 기술 논의가 vault 에 정리될 때마다 이 페이지가 source 들의 hub 가 된다.

## Key facts

- 제조: [[Anthropic]]
- 현재 라인업: Opus / Sonnet / Haiku 4.X (2026 기준 Opus 4.7)
- 접근: Claude Code (CLI), Desktop, Web, API, IDE extension
- 데이터: 일반 텍스트, ADF (Jira 등 통합 시), file system read/write 가능 (Claude Code)
- 컨텍스트 자동 압축 — 긴 세션에서도 작업 지속 가능

## 2026-05 도구 측 시장 신호 ([[yozm-codex-vs-claude-code]])

- **Opus 4.7 토크나이저 변경** — 같은 텍스트를 1.20 ~ 1.47 배 더 많은 토큰으로 변환. 본인 만성 토큰 부족의 객관 데이터 뒷받침.
- **Claude Code 성능 저하 측정** (Stella Laurenzo / AMD, 6,852 세션 / 234,760 도구 호출 분석): 사고 깊이 중앙값 67 % 하락, 파일 읽기 6.6 → 2.0. 원인: Opus 4.7 출시 후 추론 디폴트 변경 + 캐싱 버그 + 텍스트 길이 제한 등.
- **벤치마크는 여전히 우세** — SWE-bench Pro 64.3 % (vs GPT-5.4 57.7 %), SWE-bench Verified 87.6 % (vs 74.9 %). 단 일상·구조적 코딩에서는 [[Codex]] 가 빠르게 추격 (커뮤니티 65 % 선호).
- **설계 철학 측면** — Anthropic 의 "협력 / 인간 옆 안전한 동료" 톤. 위임형 [[Codex]] 와 대비.

## 핵심 기능

- **Tool use** — 외부 도구/함수 호출 (Read/Write/Bash/MCP 등)
- **Prompt caching** — 반복 컨텍스트 토큰 비용 절감 (5분 TTL)
- **File system 직접 접근** — Claude Code 의 핵심 차별점
- **Multi-turn + 자동 컨텍스트 압축**
- **MCP (Model Context Protocol)** — Gmail/Calendar/Drive 등 외부 시스템 통합

## 이 vault 에서의 사용

- WSL 측 file system 으로 `/mnt/c/Users/pc/Documents/Obsidian Vault/` read/write
- 새 source 가 들어오면 ingest 워크플로 (`sources/`, `entities/`, `index.md`, `log.md`) 실행
- 사용자와의 기술 논의는 `sources/discussions/` 로 정리
- 메일링 요약은 `sources/newsletters/` 로 정리

## 관련 sources

- [[karpathy-llm-wiki]] — Claude 가 운영할 PKM 패턴 원안
- [[yozm-codex-vs-claude-code]] — 2026-05 Codex vs Claude Code 비교 분석 (덕파 / YozmIT)

## 관련 entities

- [[Anthropic]] — 제조사
- [[Codex]] — 본인 도구 풀의 짝 (Codex 구현 / Claude 리뷰), 시장 비교 대상
- [[ChatGPT]] — 같은 결의 LLM 비교 대상
- [[LLM Wiki]] — Claude 가 이 vault 에서 실행하는 패턴
- [[Andrej Karpathy]] — 패턴 제안자 + Anthropic 합류 (사이클 시그널)
- [[llm-tool-comparison]] — 본인 도구 실측 living doc
