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

**Status**: 시범 진입 준비 (선행 작업 완료, 첫 PR 발생 시점부터 시범 시작)

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
- **단위**: 레포지토리 1 개 시범 — **`leadplanet-common-api` 선정** (2026-05-22)
- **선정 근거 (갱신)**:
  - 본인 active 작업 영역, 운영 핵심에서 한 단계 떨어진 위치
  - **최근 작업 거의 없음 / 배포 거의 없음** → 분 비용 부담 낮음 (가격 확인의 사실상 답)
  - **Read 전용** → 데이터 손상 위험 없음, 인터페이스 변경 가능성 낮음 → 확장 단계 주의도 일부 완화
- **첫 job**: PR 설명 자동 생성 (가장 안전, 코드 변경 없음, 잘못돼도 영향 적음)
- **다음 후보 (1 단계 평가 후)**: 불안정 테스트 자동 수정 → README/문서 자동 업데이트
- **시범 기간**: 1~2 개월 (**첫 PR 발생 시점부터 카운트**. 작업 빈도 낮은 repo 라 데이터 수집 속도 느릴 수 있음. "동작 / 비동작" 은 PR 1~2 건이면 판단 가능, "효과 / 가치" 는 시간 더 필요)
- **평가 후 결정**: 확장 / 보류 / 철수
- **확장 단계 주의 (갱신)**: 본 repo 는 Read 전용이라 인터페이스 변경 가능성 낮지만, 공통 API 라 의존 repo 영향 ↑ 라는 구조 자체는 유지. 불안정 테스트 자동 수정 같은 코드 변경 단계 진입 시 의존 repo 영향 재평가 필요

### 시범 전 선행 작업

- [x] **시범 레포지토리 선정** → `leadplanet-common-api` (2026-05-22 완료)
- [x] **가격 확인** → 본인 판단으로 사전 해소 (시범 repo 가 작업·배포 거의 없음 → 분 비용 부담 거의 없음, 2026-05-22). Atlassian 측 청구 모델 자체는 본격 확장 시 재확인
- [x] **온프레미스 연결 필요성 평가** → 시범 단계 (PR 설명 자동 생성) 는 코드·PR 만 다루므로 **self-hosted runner 불필요**. 배포 자동화 확장 시 재검토

### 온프레미스 서버 ↔ Cloud Pipelines 옵션
| 옵션 | 설명 | 평가 |
|------|------|------|
| **Self-hosted runner** | 사내 서버에 runner 띄움. Pipelines job 이 사내 환경 실행 | **권장** — 클라우드↔온프레미스 직접 연결 불필요 |
| SSH / VPN / 터널링 | 클라우드 runner 에서 온프레미스 inbound 허용 | 보안·네트워크 부담 큼 |

### 구조 설계

#### 현재 CI/CD 구조

```
개발자 → Bitbucket (push/PR)
            ↓ (webhook/polling)
         Jenkins (사내 빌드 서버)
            ↓ build → test
            ├─ 테스트: 동일 서버에서 sh 실행
            └─ 상용: SSH 로 jar 이동 + 원격 sh 실행
```

#### 시범 1~2 단계 후 구조 (두 라인 병렬)

```
개발자 → Bitbucket (push/PR)
            │
            ├─ [라인 1: 기존] webhook → Jenkins
            │                            ↓ build → test → deploy
            │                            (변경 없음)
            │
            └─ [라인 2: 신규] Bitbucket Pipelines (Atlassian Cloud 컨테이너)
                                ↓ provider: claude
                              Claude Code 실행 → PR 설명 자동 생성 등
                                ↓
                              Bitbucket PR 에 댓글/설명 갱신
```

**핵심**: 두 라인은 **동일한 시작점** (Bitbucket push/PR 이벤트) 에서 갈라져 **다른 끝점** 으로 감. 본인 사내 인프라 (Jenkins / 상용 서버) 에 들어오는 트래픽 없음. Pipelines 는 Atlassian Cloud 의 컨테이너를 자동으로 띄워 그 안에서 [[Claude]] Code 를 실행.

#### 단계별 구조 변화

| 시범 단계 | Pipelines 가 하는 일 | Jenkins 와의 관계 | self-hosted runner |
|----------|---------------------|------------------|-------------------|
| **1 단계 (시범 진입)** PR 설명 자동 생성 | PR 메타데이터 수정만 | **무관** | 불필요 |
| **2 단계** 불안정 테스트 자동 수정 | 코드 수정 PR 을 새로 만듦 | **간접 연결** — 새 PR 이 Jenkins 빌드 라인 다시 트리거 (기존 흐름 그대로) | 불필요 |
| **3 단계** 배포 자동화까지 확장 | 사내 서버 접근 필요 | **직접 연결** 필요 | **필요** |

#### 3 단계 진입 시 빌드 결과물 사내 전달 옵션

배포까지 확장하면 "빌드 결과물 (jar) 을 사내 상용 서버로 어떻게 보낼 것인가" 가 핵심 의사결정 포인트. 3 가지 옵션:

| 옵션 | 흐름 | 평가 |
|------|------|------|
| **A. Self-hosted runner** | Pipelines job 자체를 사내 runner 에서 실행 → 빌드 결과물이 처음부터 사내 망 안 → 사내 → 사내 SSH (현 Jenkins 흐름과 동일) | **권장** — 인터넷 노출 없음. 단점: runner 운영 추가 |
| **B. Artifact 저장소 경유** | Pipelines (Cloud) 빌드 → jar 를 Bitbucket Downloads / Nexus / S3 push → 사내 서버 pull → 배포 sh | 저장소 운영 추가, Pipelines ↔ 사내 분리 운영 |
| **C. Cloud → 사내 SSH 직접** | Pipelines 컨테이너에서 SSH 로 사내 상용 서버 직접 접속 | **비권장** — 사내 서버에 inbound 허용 필요, 보안 부담 큼 |

**3 단계 진입 시 가장 깔끔한 미래 그림 = A 안 (self-hosted runner)**. Jenkins 가 하던 "사내 빌드·배포" 흐름을 그대로 유지하면서 Pipelines 의 Agentic 기능만 끼우는 형태. 단, **이 결정은 시범 1~2 단계 결과가 좋을 때만 진입**. 지금 깊이 결정할 필요 없음.

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
