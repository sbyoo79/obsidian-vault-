---
type: entity
status: active
category: tool
tags: [coding-agent, llm, openai, gpt, cli, ide, terminal]
aliases: [OpenAI Codex, Codex CLI]
vendor: "[[OpenAI]]"
license: commercial
platform: [CLI, Desktop, Mobile, AWS Bedrock]
url: https://openai.com/codex
created: 2026-05-27
updated: 2026-05-27
---

# Codex

[[OpenAI]] 의 코딩 에이전트. [[Claude]] Code 와 함께 본인 멀티 에이전트 워크플로의 구현 담당.

## 개요

[[OpenAI]] 가 GPT-5 시리즈 기반으로 만든 코딩 에이전트. CLI 중심의 도구로, 터미널·IDE·모바일·데스크톱 등 다양한 환경에서 동작한다. 2026-04 ~ 05 사이 `/goal`·`/hooks`·remote-control·AWS Bedrock 지원 등 빠른 기능 추격으로 [[Claude]] Code 의 독점 우위를 흔든 도구로 평가받고 있다 ([[yozm-codex-vs-claude-code]]).

## 핵심 기능

- **`/goal` 워크플로우** (2026-04-30) — 여러 턴·세션에 걸친 목표 관리
- **`/hooks` 브라우저, Vim 모드, 플러그인 공유** (2026-05-07)
- **`codex remote-control`** (2026-05-08) — 모바일·데스크톱 간 원격 제어
- **AWS Bedrock 지원** (2026-05-08)
- **커널 레벨 격리** — Seatbelt + Landlock / seccomp 로 PR 리뷰 등 안전성 확보

## 이 vault 에서의 사용

본인 멀티 에이전트 워크플로의 **구현 (Implementation) 담당**:

- GPT (ChatGPT) → 설계·문서화
- **Codex → 구현**
- [[Claude]] Code → 단위 리뷰

회사 공통 AGENTS.md 의 cross-LLM 검증 매트릭스에서 Codex 가 구현 → [[Claude]] 가 리뷰 (또는 반대) 의 한 축.

## Key facts

- 제조사: [[OpenAI]]
- 본인 평가 ([[llm-tool-comparison]]):
  - **강점**: 레거시 분석력 (오래된 코드, 비표준 패턴, 흩어진 의존성 파악) — 본인 실측
  - **외부 평가** (덕파 2026-05): 일상 코딩 / 구조적 수정 / PR 리뷰 우세, 커뮤니티 65 % 선호
- 회사 [[Agentic Engineering]] 워크플로의 핵심 도구 중 하나
- 2026-04 ~ 05 빠른 기능 추격으로 [[Claude]] Code 독점 구도에 균열

## 관련 sources

- [[yozm-codex-vs-claude-code]] — Codex vs Claude Code 비교 분석 (덕파 / YozmIT, 2026-05-26)

## 관련 entities

- [[OpenAI]] — 제조사
- [[ChatGPT]] — 같은 회사 LLM (본인 도구 풀의 설계·문서 담당)
- [[Claude]] (Code) — 본인 도구 풀의 리뷰 담당 + 시장 비교 대상
- [[Antigravity]] — Google 측 비교 도구
- [[llm-tool-comparison]] — 본인 도구 실측 living doc
- [[Agentic Engineering]] — 본인 멀티 에이전트 워크플로 사상
