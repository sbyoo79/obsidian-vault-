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

## 검토 메모 (2026-05)

**Status**: 검토 중 (시범 진입 직전)

### 본인 컨텍스트
- 현재 CI: **Jenkins + 수동 빌드**
- 빌드 빈도: 수시 → 무료 분 (월 50 분) 내 안 들어옴, 유료 전환 비용 검토 필수
- 회사 보안팀 = **본인**. 소스코드는 이미 Bitbucket 에 있어서 추가 노출 없음. 정책 결정 자유도 높음
- 서버: **온프레미스** — 배포 측 연결은 self-hosted runner 등 별도 검토 필요
- 멀티 에이전트 워크플로 CI 확장 의향: 있음 ("되면 좋긴 하겠네")

### 도입 안 비교
| 안 | 내용 | 평가 |
|----|------|------|
| A. 완전 이전 | Jenkins 의 모든 job 이관 | 이전 비용 큼, 분 비용 폭증, 부담 ↑ — **보류** |
| B. 공존 (광범위) | Jenkins + Pipelines 다수 신규 영역 | 이중 운영 복잡도 ↑ |
| **C. Agentic 만 부분 도입** | Jenkins 그대로 + Pipelines Agentic 만 신규 영역 시범 | **추천** — Strangler Fig 의 CI 버전, 회사 AGENTS.md 사상과 일치 |

### 시범 계획
- **단위**: 레포지토리 1 개 시범 — **`leadplanet-common-api` 선정** (2026-05-22). 선정 근거: 본인 active 작업 영역 / PR 단위 작업 잦음 / 운영 핵심에서 한 단계 떨어진 위치
- **첫 job**: PR 설명 자동 생성 (가장 안전, 코드 변경 없음, 잘못돼도 영향 적음)
- **다음 후보 (1 단계 평가 후)**: 불안정 테스트 자동 수정 → README/문서 자동 업데이트
- **시범 기간**: 1~2 개월
- **평가 후 결정**: 확장 / 보류 / 철수
- **확장 단계 주의**: `leadplanet-common-api` 는 **공통 API** 라 다른 서비스 의존도 ↑. 불안정 테스트 자동 수정 같은 코드 변경 단계 진입 시 영향 범위 재평가 필요 (시범 단일 repo 가 아닌 의존 repo 들도 함께 영향)

### 시범 전 선행 작업
1. **가격 확인** — Atlassian Pipelines Agentic + [[Claude]] Code 외부 제공자 사용 시 실제 청구 모델. 본인 만성 토큰 부족 상태에서 추가 부담 가늠 ([[llm-tool-comparison]] 가격 평가축과 연계)
2. **시범 레포지토리 선정** — 영향 격리 가능 + PR 워크플로 빈도 적정 + 본인이 owner 인 repo
3. **온프레미스 연결 필요성 평가** — 시범 단계 (PR 설명 / 테스트 자동 수정) 는 코드·PR 만 다루므로 self-hosted runner 불필요. 배포 자동화 확장 시 self-hosted runner 검토

### 온프레미스 서버 ↔ Cloud Pipelines 옵션
| 옵션 | 설명 | 평가 |
|------|------|------|
| **Self-hosted runner** | 사내 서버에 runner 띄움. Pipelines job 이 사내 환경 실행 | **권장** — 클라우드↔온프레미스 직접 연결 불필요 |
| SSH / VPN / 터널링 | 클라우드 runner 에서 온프레미스 inbound 허용 | 보안·네트워크 부담 큼 |

### 보류 조건
다음 중 하나라도 해당하면 도입 보류:
- 가격 확인 결과 본인 워크플로 비용에 부담 큼
- 시범 1~2 개월 후 실측 효과가 본인 로컬 멀티 에이전트 워크플로 대비 미미함
- [[Claude]] Code CI 측 동작이 로컬 환경 대비 일관성 떨어짐 (UX 안정성 = [[llm-tool-comparison]] 평가축)

## 관련 sources

- Bitbucket Agentic Pipelines + Claude Code 발표 (2026-05-19): https://www.atlassian.com/blog/bitbucket/agentic-pipelines-now-supports-claude-code

## 관련 entities

- [[Atlassian]] — 제조사
- [[Claude]] — 신규 외부 제공자
- [[Codex]] · [[ChatGPT]] — 본인 도구 풀의 다른 LLM
- [[Agentic Engineering]] — CI 측 에이전트 통합 사상
- [[llm-tool-comparison]] — 도구 적용 검토 시 베이스라인
- [[ai-market-pulse]] — Anthropic ecosystem expansion 추적 변수
