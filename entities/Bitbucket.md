---
type: entity
status: active
category: tool
tags: [git, code-hosting, ci-cd, atlassian, dev-tool]
aliases: [Bitbucket]
vendor: "[[Atlassian]]"
license: commercial
platform: cloud
url: https://bitbucket.org
created: 2026-05-22
updated: 2026-05-22
---

# Bitbucket

[[Atlassian]] 의 Git 코드 호스팅 + CI/CD 플랫폼. **본인 회사 사용 중**. CI 측 Bitbucket Pipelines 는 현재 본인 사용 안 함.

## 핵심 기능

- Git 코드 호스팅 + PR 워크플로
- [[Atlassian]] Jira 와 native 통합 (티켓 ↔ 커밋 ↔ PR 자동 연결)
- **Bitbucket Pipelines**: YAML 기반 CI/CD (`bitbucket-pipelines.yml`)
- **Agentic Pipelines**: AI 에이전트가 파이프라인 안에서 작업 수행
  - 기본 제공자: Rovo Dev ([[Atlassian]] 자체 AI)
  - 2026-05-19 부터 [[Claude]] Code 외부 제공자 지원 (`provider: claude`)

## 이 vault 에서의 사용

본인 회사 코드 호스팅으로 사용 중. **Bitbucket Pipelines (CI/CD) 는 현재 미사용** — 별도 CI 환경 또는 수동 배포 사용 중인 것으로 추정. Agentic Pipelines + [[Claude]] Code 지원은 **검토 후보** 로 두되 즉시 적용 대상은 아님.

회사 AGENTS.md 의 멀티 에이전트 워크플로에서 본인은 [[Claude]] Code (리뷰) + [[Codex]] (구현) + [[ChatGPT]] (설계) 조합으로 작업하는데, **CI 측에 [[Claude]] Code 를 끼우는 건 다음 단계로 검토할 만한 옵션** — 단, 제3자 약관 (소스코드·프롬프트·로그가 [[Claude]] 로 전송) 검토 필요.

## Key facts

- 본인 회사 사용 중 (코드 호스팅)
- 본인 사용 안 함: Bitbucket Pipelines (CI/CD)
- 2026-05 Agentic Pipelines [[Claude]] Code 지원 — 검토 후보, 즉시 적용 X
- 제3자 약관: 소스코드·프롬프트·로그가 [[Claude]] 로 전송 + Atlassian 은 프라이버시/보안/비용 책임 없음
- Atlassian 측 제시 유즈케이스: 불안정 테스트 자동 수정 / README 업데이트 / PR 설명 자동 생성 / 보안 보고서 분류 / 기능 플래그 정리

## 관련 sources

- Bitbucket Agentic Pipelines + Claude Code 발표 (2026-05-19): https://www.atlassian.com/blog/bitbucket/agentic-pipelines-now-supports-claude-code

## 관련 entities

- [[Atlassian]] — 제조사
- [[Claude]] — 신규 외부 제공자
- [[Codex]] · [[ChatGPT]] — 본인 도구 풀의 다른 LLM
- [[Agentic Engineering]] — CI 측 에이전트 통합 사상
- [[llm-tool-comparison]] — 도구 적용 검토 시 베이스라인
- [[ai-market-pulse]] — Anthropic ecosystem expansion 추적 변수
