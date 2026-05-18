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
- 2026-05-14 ingest [[yozm-geo-leading-indicators]] (article) — 양용준 / 서치나인 / YozmIT. 신규 entity 5개: [[양용준]], [[서치나인]], [[GEO]], [[SEO]], [[Google Search Console]]. 자동 push 룰 발효 후 첫 ingest.
- 2026-05-14 create [[weekly-workout-routine]] (note) — 47세 관절 보호 컨셉 주 5일 헬스 루틴 작성. Lower A / Upper Push / Mobility / Lower B / Upper Pull 구성
- 2026-05-18 ingest [[yozm-hermes-agent-self-improving]] (article) — 덕파 / YozmIT. 신규 entity 6개: [[덕파]], [[Hermes Agent]], [[Nous Research]], [[OpenRouter]], [[Self-Improving Agent]], [[Procedural Memory]]
- 2026-05-18 setup yozm daily digest — `common/sh/yozm-daily-digest.py` 작성. 첫 실행 시 `meta/digests/yozm-2026-05-18.md` 생성. 개선 백로그는 [[yozm-digest-improvements]]
- 2026-05-18 ingest [[yozm-vibe-coding-real-start]] (article, 번역) — Ahmed Hafdi / Yuna 번역 / YozmIT. 신규 entity 5개: [[Ahmed Hafdi]], [[Yuna]], [[Vibe Coding]], [[Cursor]], [[Simon Willison]]. [[Andrej Karpathy]] 페이지에 Vibe Coding 명명자 정보 추가. 디지스트 #1 상태 마킹 갱신.
- 2026-05-18 create [[resume-master]] — 이력서 PDF → markdown 변환 + P0 수정 (오타/표기/자기 깎기 표현). private/resume-context.md 도 같이 생성 (gitignore)
- 2026-05-18 create [[self-profile]] — 인터뷰 라운드 2 답변 누적 정리. tech stack self-assessment (5단계), 5대 강점, 약점·보완, 차별 포지셔닝, 적합/회피 회사 유형. private 에 면접 답변 초안 분리 정리.
