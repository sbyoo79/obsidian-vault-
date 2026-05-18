---
type: entity
status: active
category: tool
tags: [tool, ai, llm, code-editor, vibe-coding, ide]
aliases: [Cursor AI]
url: https://cursor.com
vendor: Anysphere
license: freemium
platform: [macOS, Windows, Linux]
created: 2026-05-18
updated: 2026-05-18
---

# Cursor

VS Code 기반의 AI 통합 코드 에디터. Anysphere 가 만들었으며 [[Vibe Coding]] 시대의 대표 도구 중 하나로 자리잡았다.

## 개요

기존 VS Code 의 fork 위에 LLM 자율 편집·코드베이스 인덱싱·에이전트 모드를 묶은 IDE. [[Claude]] / [[ChatGPT]] / 자체 모델 등을 백엔드로 쓸 수 있다. 2023~2024 무렵 등장해 2025 년 [[Vibe Coding]] 붐과 함께 사용자 폭발.

다른 AI 도구와의 차별점은 **에디터 통합 깊이**. autocomplete 보다 한 수 위인 "Composer" / "Agent" 같은 모드로 다중 파일 동시 편집·refactor 가 가능. 단점은 [[Vibe Coding]] 의 가장 큰 통계적 문제 (보안 취약점 2.74 배) 가 이런 도구들의 빠른 결과물에서 비롯됨.

## 본 vault 에서의 의미

[[Claude]] Code 와 같은 결의 IDE 친화 LLM 도구. 본 vault 는 Claude Code 를 active agent 로 쓰지만 cursor 는 외부 source 에서 자주 등장하는 비교 reference.

## Key facts

- 제조: Anysphere
- 기반: VS Code fork
- 모델: Claude / GPT / 자체 모델 등 선택 가능
- 라이선스: freemium (Pro 유료)
- 핵심 기능: 코드베이스 인덱싱, 멀티파일 편집, agent 모드

## 핵심 기능

- **Composer** — 자연어로 여러 파일 동시 편집
- **Agent** — 자율 multi-step 코딩
- **Tab autocomplete** — 강화된 자동완성
- **Codebase chat** — 전체 코드베이스 컨텍스트로 질문
- **Cursor Rules** — `.cursorrules` 파일로 프로젝트별 규칙 박기

## 이 vault 에서의 사용

직접 사용 안 함 ([[Claude]] Code 가 vault 의 active agent). 외부 source 에서 vibe coding / AI 코딩 도구 언급 시 reference.

## 관련 sources

- [[yozm-vibe-coding-real-start]] — vibe coding 도구로 언급

## 관련 entities

- [[Vibe Coding]] — 시대의 대표 도구
- [[Claude]] — 직접 비교 대상 (IDE 통합 vs CLI)
- [[ChatGPT]] — 백엔드 모델 옵션
- [[AI Agent]] — 카테고리상 상위
