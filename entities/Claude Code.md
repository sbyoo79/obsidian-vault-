---
type: entity
status: active
category: tool
tags: [tool, ai, cli, coding-agent, anthropic, agentic-engineering, mcp]
aliases: [claude-code]
url: https://claude.com/claude-code
vendor: Anthropic
license: commercial
platform: [CLI, VS Code, JetBrains, Web]
created: 2026-06-07
updated: 2026-06-07
---

# Claude Code

[[Anthropic]] 의 공식 에이전트 코딩 도구. [[Claude]] 모델을 백엔드로 사용하며, 파일 시스템 / shell / MCP 외부 시스템에 직접 접근할 수 있는 CLI·IDE 통합 환경.

## 개요

기존 챗 인터페이스 (Web / Desktop / API) 가 "대화" 중심이라면, Claude Code 는 **에이전틱 실행** 에 최적화. 사용자가 자연어로 지시하면 도구 호출 (Read / Edit / Bash / WebFetch / MCP …) 을 직접 실행하고, 결과를 보고 다음 단계를 결정한다. 본 vault 의 모든 ingest / query / lint 작업이 이 도구 위에서 돌아간다.

[[Claude]] 모델 패밀리 (Opus / Sonnet / Haiku) 와 분리 추적할 가치가 있는 이유: **도구 자체의 변동성** (메이저 버전업 / 디폴트 변경 / 캐싱 동작 / 토크나이저) 이 모델 성능과 별개로 사용자 실측에 큰 영향을 주는 게 2026-05 시점에 명확해졌기 때문 ([[yozm-codex-vs-claude-code]]).

## 본 vault 에서의 의미

본 vault 의 **실제 active agent**. [[Claude]] entity 가 "모델 패밀리" 라면 본 entity 는 그 모델을 운영하는 도구 자체. ingest 워크플로 ([[CLAUDE]] schema) 가 돌아가는 실행 환경이고, 본인 도구 풀의 한 축 ([[Codex]] 와 짝, [[llm-tool-comparison]] 참고).

본인 멀티 에이전트 워크플로 (설계 [[ChatGPT]] / 구현 [[Codex]] / 리뷰·문서 Claude Code) 의 **리뷰·문서화** 담당. [[Agentic Engineering]] 사상의 본인 일상 구현체.

## 핵심 기능

- **파일 시스템 직접 접근** — Read / Edit / Write / Glob / Grep
- **Shell 실행** — Bash (sandbox 모드 / 권한 모드 분리)
- **Tool use** — MCP (Model Context Protocol) 기반 외부 시스템 통합 (Gmail / Calendar / Drive / Jira 등)
- **자동 컨텍스트 압축** — 긴 세션에서도 작업 지속 (기존 메시지 요약 후 다음 윈도우로 이월)
- **세션 영구 메모리** — 프로젝트별 memory 디렉토리 + frontmatter 식별자 패턴 (`feedback_*` / `project_*` / `user-profile`)
- **Hooks / Slash commands / Subagents** — 사용자 정의 자동화 / 권한 / 작업 분기
- **Settings.json 기반 권한 / 허용 명령 관리** — 보안과 실용성 분리
- **IDE 통합** — VS Code / JetBrains extension

## 이 vault 에서의 사용

- WSL 측 file system 으로 `/home/sbyoo/work-space/obsidian-vault-/` 직접 read/write
- 새 source → `sources/` ingest, 등장 entity → `entities/` 신설·갱신, 사용자 관점 → `notes/`
- 사용자와의 기술 논의는 `sources/discussions/` 로 정리 — 본 entity 가 `author=[[Claude]]` 의 실제 실행자
- yozm 일일 디지스트 등 정기 작업은 hooks / cron 단위로 자동화 후보
- 본 vault 의 git 동기화 ([[CLAUDE]] schema "Git 동기화" 절) 도 본 도구로 수행

## 2026-05 도구 측 외부 정보 ([[yozm-codex-vs-claude-code]])

- **사고 깊이 중앙값 67 % 하락 측정** (Stella Laurenzo / AMD, 6,852 세션 / 234,760 도구 호출). 원인 추정: Opus 4.7 출시 후 추론 디폴트 변경 + 캐싱 버그 + 텍스트 길이 제한
- **파일 읽기 횟수 6.6 → 2.0** — 같은 작업 단위에서 컨텍스트 수집 빈도 자체가 줄어듦
- **토크나이저 변경 (Opus 4.7)** — 같은 텍스트를 1.20 ~ 1.47 배 더 많은 토큰으로 변환 → 본인 만성 토큰 부족의 객관적 원인
- **벤치마크는 여전히 우세** — SWE-bench Pro 64.3 % / SWE-bench Verified 87.6 % (vs [[Codex]] / GPT-5.4 각각 57.7 % / 74.9 %)
- **작업 유형별 우세** (덕파 framing): Claude Code = 장기 리팩터링 (8 시간+) / 테스트 작성 / UI·디자인. [[Codex]] = 일상 / 구조적 수정 / PR 리뷰
- **설계 철학 측면** — "협력 / 인간 옆 안전한 동료" 톤. 위임형 [[Codex]] 와 대비

## Key facts

- 제조: [[Anthropic]]
- 백엔드 모델: [[Claude]] 패밀리 (Opus / Sonnet / Haiku 4.X)
- 접근: CLI, VS Code extension, JetBrains extension, web (claude.ai/code)
- 핵심 차별점: 파일 시스템 / shell / MCP 직접 접근 → 진정한 에이전틱 실행
- 비용 모델: 모델 사용량 기반 (구독 또는 API 토큰)
- "Fast mode" — Opus 출력 가속 옵션 (Opus 4.6 / 4.7)

## 관련 sources

- [[yozm-codex-vs-claude-code]] — 덕파 / YozmIT. Claude Code 의 시장 위치 변동 분석 (Codex 추격 + 본인 토크나이저 영향)
- [[karpathy-llm-wiki]] — Claude Code 가 본 vault 에서 실행하는 PKM 패턴 원안

## 관련 entities

- [[Claude]] — 백엔드 모델 패밀리. 본 entity 와 모델/도구 레이어로 분리
- [[Anthropic]] — 제조사
- [[Codex]] — 짝 도구. 본인 멀티 에이전트 워크플로의 구현 담당, 2026-05 시장 추격 사례
- [[ChatGPT]] — 설계·발산 담당 (본인 도구 풀의 다른 축)
- [[Cursor]] · [[Antigravity]] — IDE + LLM 통합 시도. 본인은 IDE ([[IntelliJ]]) 와 분리 운영
- [[Agentic Engineering]] — Claude Code 가 일상 구현하는 사상
- [[Atlassian]] · [[Bitbucket]] — Agentic Pipelines 에서 Claude Code 외부 제공자 지원 (2026-05-19)
- [[llm-tool-comparison]] — 본인 도구 실측 living doc
- [[ai-market-pulse]] — 시장 관전 living doc
