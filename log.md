# Log

vault 작업 이력. append-only. 절대 과거 항목을 수정하지 않는다.

- 2026-05-14 init — LLM Wiki 패턴 적용. [[CLAUDE]], [[index]] 생성, `notes/` `entities/` `sources/` `meta/` 디렉토리 신설
- 2026-05-14 cleanup — `Leadplanet/` 폴더 삭제, 빈 디렉토리(`notes/` `entities/` `sources/` `meta/`) 제거. schema 갱신(폴더는 첫 콘텐츠 생성 시 자동 생성)
- 2026-05-14 ingest [[karpathy-llm-wiki]] → created [[Andrej Karpathy]], [[LLM Wiki]], [[Obsidian]]; updated [[index]]
- 2026-05-14 schema refine — [[CLAUDE]] frontmatter superset + entity 표준 섹션 추가. 기존 entity 3개([[Andrej Karpathy]], [[LLM Wiki]], [[Obsidian]]) 표준 섹션 따라 두텁게 재작성
- 2026-05-14 schema extend — discussion / newsletter source 타입 추가 (`sources/discussions/`, `sources/newsletters/`), [[Claude]] entity 신설
- 2026-05-14 ingest [[2026-05-14-vault-setup-and-llm-wiki-adoption]] (discussion) — 첫 dogfood discussion. 새 entity 없음, 기존 [[Claude]] [[LLM Wiki]] [[Obsidian]] [[Andrej Karpathy]] 참조
- 2026-05-14 ingest [[yozm-agentic-engineering-survival]] (article) — DevOwen / YozmIT. 신규 entity 5개: [[DevOwen]], [[YozmIT]], [[Agentic Engineering]], [[AI Agent]], [[Context Engineering]]
- 2026-05-14 ingest [[yozm-solomon-paradox-ai]] (article) — Dinon / YozmIT. 신규 entity 5개: [[Dinon]], [[Solomon's Paradox]], [[Self-Distancing]], [[Role-Reversal Dialogue]], [[ChatGPT]]
- 2026-05-14 schema decision — [[2026-05-14-vault-setup-and-llm-wiki-adoption]] 미해결 질문 사후 정리. [[CLAUDE]] 에 "Git 동기화" 섹션 신설 (자동 commit/push), `obsidian-git` plugin read-only view 정책 명시
