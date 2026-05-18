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
- 2026-05-18 update [[self-profile]] — 인터뷰 라운드 3 답변 반영. 매칭 기준 (희망 조건) 섹션 추가: 50~200명 / SaaS·ERP·커머스 / 리더십 50:50 / 하이브리드 / 통근 1시간 이내. 연봉 하한은 private 에 보관.
- 2026-05-18 update [[self-profile]] — 통근 한계 1시간 → 1시간 30분으로 현실 반영. 매칭 가능 지역 표를 2 단계로 분리 (1h 이내 편안 / 1h~1h30 현실)
- 2026-05-18 update [[self-profile]] — 회사 규모 50~200 항목을 "선호하되 그 이상도 OK" 로 유연 조정. 첫 매칭 시범 (무신사 / private) 진행하며 발견된 사용자 실제 기준 반영.
- 2026-05-18 update [[self-profile]] — 두 번째 매칭 시범 (InSpline) 결과 self-profile 정교화: (1) 회사 규모 하한 명시 (5~30명 초기 단계 배제, 안정성 우선), (2) 자금 단계 항목 신설 (Series A+ 또는 안정 흑자 우선), (3) 글로벌/외국계 입장 갱신 (영어 약점 보완 기회로 적극), (4) 회피 영역에 0→1·초기 단계 추가
- 2026-05-18 update [[self-profile]] — 언어/프레임워크 표 정교화: TypeScript/JavaScript/Node.js 분리, React/GraphQL/Hasura 항목 추가. Fieldguide 매칭 시 발견된 빈틈 보완.
- 2026-05-18 third match (private) — Fieldguide / Software Engineer (Korea) 매칭 분석. **9.0/10, 본격 검토 1호 후보**. Customized resume 작성 (~/work-space/이력서_유승보_fieldguide_2026-05.md, vault 외부).
- 2026-05-19 Fieldguide 영문 지원 자료 작성 — 채용 페이지 영문 확인 후 영문 이력서 1p / 2p + cover letter 작성 (~/work-space/resume_seungbo-yoo_fieldguide_2026-05_{1page,2page}.md, ~/work-space/cover-letter_seungbo-yoo_fieldguide_2026-05.md, vault 외부). 한글 customized resume 베이스로 미국 컨벤션 적용 (요약·강조 differentiator·과거형 동사·정량 메트릭·1페이지 압축).
- 2026-05-19 Fieldguide 매칭 정보 갱신 (private) — 지원 양식에서 확인: 오피스 위치 대치동 → **여의도** (부평 통근 1h 이내), 근무 시간 **KST 06:00 시작** (미국 본사 overlap, 이른 시간 remote 허용 + 오전 중 오피스 출근). 통근 평가는 더 좋아짐, 단 06:00 시작이 본인 생활 패턴과 호환되는지 점검 항목으로 추가.
