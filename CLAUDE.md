# Vault Schema — LLM Wiki

이 vault 는 [Karpathy 의 LLM Wiki 패턴](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f) 을 따른다.
LLM 이 markdown 위키를 점진적으로 빌드/유지하고, 사용자는 큐레이션·방향·비판적 사고를 담당한다.

## 적용 범위

- 이 vault 는 **개인 학습/연구/메모** 영역이다.
- 회사 작업물(maxvisor, leadplanet, 운영 이슈 등)은 회사 `knowledge-base` 리포로 가고, 이쪽으로 흘러들지 않게 한다.
- Claude Code 가 이 vault 에서 작업할 때는 항상 이 파일을 먼저 Read 한다.

## 디렉토리

```text
Obsidian Vault/
├── CLAUDE.md     ← 본 파일 (schema)
├── index.md      ← 카테고리별 카탈로그
├── log.md        ← append-only chronological 이력
├── notes/        ← 자유 노트 (concept, daily, fleeting → permanent)
├── entities/     ← 명사 페이지 (사람/회사/도구/개념 1개당 1 파일)
├── sources/      ← 원본 metadata (article/paper/video/podcast)
└── meta/         ← 운영 메타 (template, schema 부속, lint 결과)
```

각 하위 폴더는 첫 콘텐츠가 생성될 때 자동으로 만들어진다. 빈 폴더는 vault 에 남기지 않는다.

## 페이지 컨벤션

### 파일명
- kebab-case 또는 한국어 자연어 둘 다 허용.
- entity 페이지는 고유명사 그대로: `Andrej Karpathy.md`, `Obsidian.md`.
- 날짜성 노트는 `YYYY-MM-DD-{slug}.md`.

### Frontmatter (선택)
```yaml
---
type: note | entity | source
status: draft | active | archived
tags: [tag1, tag2]
created: YYYY-MM-DD
updated: YYYY-MM-DD
---
```

### Wiki link
- 다른 페이지 참조는 `[[페이지 이름]]` 형식.
- 미존재 페이지로 링크해도 OK — 향후 채울 자리 표시로 둔다.
- 핵심 명사가 본문에 등장하면 가능한 한 `[[...]]` 으로 감싼다.

## 핵심 작업 (LLM 역할)

### Ingest — 원본 → 위키 반영

사용자가 새 source(article, 영상, 책 등) 를 제시하면:

1. `sources/{slug}.md` 생성 — 출처 메타데이터(제목/저자/URL/일자/태그) + 1 문단 요약
2. 본문에서 핵심 entity / concept 를 추출 → 각 `entities/{name}.md` 갱신 또는 신설 (관련 source 를 `[[...]]` 로 역참조)
3. 필요 시 `notes/{slug}.md` 에 사용자 관점의 정리 노트 작성
4. `log.md` 에 한 줄 추가: `- YYYY-MM-DD ingest [[source/slug]] → updated [[entity-a]], [[entity-b]]`
5. `index.md` 의 해당 카테고리 섹션에 신규 페이지 포인터 추가 (기존이면 갱신)

### Query — 위키에서 합성

사용자가 질문하면:

1. `index.md` 와 관련 페이지를 먼저 검색 — 외부 검색보다 vault 우선
2. 답변에 사용한 페이지를 `[[...]]` 로 인용
3. 답변 과정에서 새로 알게 된 사실/연결은 해당 페이지에 반영 (사용자 확인 후)
4. `log.md` 에 한 줄: `- YYYY-MM-DD query "{질문 요약}" → cited [[a]], [[b]]; updated [[c]]`

### Lint — 건강도 점검 (요청 시)

- orphan 페이지(아무도 링크 안 한 페이지) 식별
- 깨진 `[[...]]` (대상 미존재) 식별 → 신규 페이지 자리 표시인지 미스타이프인지 분류
- 같은 entity 가 다른 이름으로 여러 페이지에 존재(중복) 식별
- 결과를 `meta/lint-{YYYY-MM-DD}.md` 로 저장 + `log.md` 한 줄

## index.md / log.md 규칙

- **index.md**: 카테고리별 섹션 + 페이지 포인터. 1 페이지당 1 줄, 100 자 이내.
- **log.md**: 가장 최근 항목이 맨 아래(append-only). 날짜 역순으로 정렬하지 않는다. 절대 과거 항목을 수정하지 않는다.

## 안전 규칙

- `CLAUDE.md` (본 파일) 변경 시 항상 사용자에게 보고한다.
- 회사 정보(고객/매출/내부 기획) 가 우연히 source 로 들어오면 ingest 하지 않고 사용자에게 분리 보관을 권고한다.
- `.obsidian/` 폴더는 건드리지 않는다.
