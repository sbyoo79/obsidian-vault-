---
type: source
status: active
format: discussion
author: "[[Claude]]"
model: claude-opus-4-7
session_date: 2026-05-14
tags: [pkm, vault-setup, llm-wiki, schema-design, obsidian, dogfood]
created: 2026-05-14
updated: 2026-05-14
---

# Vault setup & LLM Wiki adoption

본 vault 의 초기 셋업과 [[LLM Wiki]] 패턴 채택 과정을 정리한 첫 discussion source. dogfood 검증 사례.

## 맥락

사용자가 [[Andrej Karpathy]] 의 gist ([[karpathy-llm-wiki]]) 를 제시하고 본인 [[Obsidian]] vault 와의 연동 가능성을 검토 요청했다. 시점의 vault 상태:

- 경로: `/mnt/c/Users/pc/Documents/Obsidian Vault/` (WSL 접근 가능)
- 콘텐츠: `Leadplanet/` 폴더 (회사 관련 노트 3 개) + `환영합니다!.md` 만 존재
- `.obsidian/plugins/`: `obsidian-git`, `mermaid-tools` 설치, 단 git 자체 미초기화

회사 KB 리포 (`knowledge-base/`) 와 별개 영역으로 개인 학습/연구 자산을 운영하려는 의도가 명확했다.

## 핵심 결론

- LLM Wiki 패턴이 본 vault 에 적합 — 회사 자료와 분리하면 부담 없이 즉시 시작 가능
- 도입 방식은 **최소 시작 (안 A)**: schema 와 보조 파일만 먼저 만들고 하위 폴더는 첫 콘텐츠 시 자동 생성. 빈 폴더는 vault 에 두지 않는다.
- dogfood 검증: 첫 ingest 로 패턴 원안 gist 자체 ([[karpathy-llm-wiki]]) 를 처리
- entity 페이지는 **표준 6 섹션 (한 줄 요약 / 개요 / vault 의미 / Key facts / sources / entities)** 으로 두텁게
- frontmatter 는 **카테고리별 superset** (person 이면 roles/affiliation, tool 이면 vendor/license/platform, concept 이면 proposed_by/year_proposed)
- 파일명은 **영문 유지** — 사용자의 영어 학습 의도와 일치
- discussion / newsletter 도 정식 source 타입으로 등록. 누적되면 가치 큼.

## 결정

### Vault 운영
- Schema 위치: vault 루트 `CLAUDE.md`
- 글로벌 `~/.claude/CLAUDE.md` 에 vault 작업 시 schema 를 먼저 Read 하도록 한 줄 추가
- 회사 정보는 vault 에 ingest 하지 않는다 (schema 안전 규칙으로 명시)
- 회사 노트 (`Leadplanet/`) 와 빈 폴더들은 정리 (삭제)

### Vault git
- 원격: GitHub **private** repo `git@github.com:sbyoo79/obsidian-vault-.git`
- 인증: SSH (`~/.ssh/id_ed25519`), GitHub Settings 에 키 등록 완료
- 동기화 책임: **WSL git 직접** (Claude 가 commit/push). `obsidian-git` plugin 은 비활성
- `.gitignore`: `.env*`, `.obsidian/workspace*`, `.obsidian/cache`, `.obsidian/plugins/*/data.json`, `.trash/`, OS/editor 메타
- `core.autocrlf = input` 설정 (Windows vault + WSL git 조합)

### Schema 컨벤션
- 디렉토리: `sources/` (`discussions/`, `newsletters/` 하위), `entities/`, `notes/`, `meta/`
- 보조 파일: `index.md` (카테고리 카탈로그, 1 줄/페이지), `log.md` (append-only)
- Entity 표준 6 섹션 정식화
- Frontmatter superset 정식화

### discussion / newsletter 정식 추가
- `format: discussion` — `sources/discussions/YYYY-MM-DD-{slug}.md`, 5 섹션 (맥락 / 핵심 결론 / 결정 / 미해결 질문 / Related)
- `format: newsletter` — `sources/newsletters/YYYY-MM-DD-{publisher}-{slug}.md`, 4 섹션 (발행 정보 / 핵심 요약 / 인사이트 / Related)
- 광고·PR 성 메일은 ingest 거부 (사용자 확인 필터)
- [[Claude]] entity 사전 신설 — 앞으로 discussion source 의 author 로 hub 역할

### Memory
- `~/.claude/projects/-home-sbyoo-work-space/memory/reference_obsidian_vault.md` 추가
- 다음 세션에서 vault 작업 시 빠르게 컨텍스트 잡기

## 미해결 질문 → 사후 결정 (2026-05-14 정리)

- **Plugin 정책** — `obsidian-git` 을 완전 비활성으로 둘지, read-only view 용도로 유지할지
  → **결정**: read-only view 로 활성 유지. plugin 자체의 auto-commit/push 기능은 OFF. 실제 동기화는 WSL git ([[Claude]]) 이 단일하게 담당. [[Obsidian]] entity 페이지에 반영.
- **자동 commit/push** — ingest 직후 git push 까지 Claude 가 자동으로 처리하도록 schema 에 명시할지
  → **결정**: 자동 처리. [[CLAUDE]] schema 에 "Git 동기화" 섹션 신설 — vault 변경이 발생한 모든 작업 직후 `git add/commit/push` 까지 자동 실행.
- **Entity 카테고리** — `model` 또는 별도 LLM 카테고리를 만들지. 현재 [[Claude]] 는 `tool` 로 분류
  → **보류**: 현재는 `tool` 로 충분. 모델 인스턴스가 다수 누적되어 카테고리 재정의 필요해질 때 다시 본다.
- **검색 부하** — discussion source 가 누적되면 graph/검색이 무거워질 가능성. Dataview plugin 도입 시점 판단 필요
  → **보류**: 아직 부하 없음. 향후 source 수십 개 누적 시 재검토.
- **Newsletter 운영 디테일** — 발행처 entity 의 추가 필드 (rss/site/cadence 등) 운영 룰
  → **해소**: 이미 [[YozmIT]] ingest 시 publisher entity 신설 + frontmatter superset 적용으로 별도 룰 없이 작동. 추가 필드는 필요 시점에 자연 추가.
- **편집 충돌** — WSL 측 git 작업 중 Obsidian 이 동일 파일 편집 중일 때의 충돌 처리
  → **해소**: 인프라적 해결책 없음. 사용자 주의로 운영. Claude 작업 중에는 Obsidian 의 동일 파일 편집을 피하거나, push 후 Obsidian 에서 명시적 새로고침 권장.

## Related

- [[Andrej Karpathy]] — 패턴 제안자
- [[LLM Wiki]] — 채택한 패턴
- [[Obsidian]] — vault 의 browser
- [[Claude]] — vault 의 active agent (본 discussion 의 author)
- [[karpathy-llm-wiki]] — 패턴 원안 gist
- [[CLAUDE]] — vault schema
