---
type: note
status: active
tags: [ai-coding, theory-building, vibe-coding, senior-engineering, accountability, agents-md, resume-implication]
related: ["[[brunch-cleancode-ownership-ai-era]]"]
created: 2026-06-01
updated: 2026-06-01
---

# Theory Building vs Vibe Coding — 시니어 격차의 진짜 무대

[[brunch-cleancode-ownership-ai-era]] 정독 후 본인 관점에서 한 번 더 풀어쓴 노트. 글의 메시지를 21 년차 시니어 백엔드 입장에서 **실무·인사·이력서 차원으로 확장**.

## 1. Naur 가 40 년 전에 미리 다 말해뒀다

[[Peter Naur]] 의 1985 *Programming as Theory Building* 은 "프로그래밍 본질 = 코드 생산이 아니라 이론(theory) 구축" 이라는 통찰. 그땐 학술적·다소 추상적으로 들렸을 수 있는데, **AI 코드 자동 생성 시대에 정확히 맞아떨어지는 진단**이 된다.

핵심 등식:
> **AI 가 생산한 코드 - 이론 = 즉시 레거시 부채**

코드는 있는데 "왜 이렇게 짰는지 설명·수정 가능한 사람" 이 없으면, 그 코드는 첫 요구 변경 사이클에서 무너진다. 이게 [[Vibe Coding]] 의 진짜 위험이고, [[백명석]] 글의 핵심.

## 2. 시니어 격차가 줄어드는 게 아니라 오히려 벌어진다 (역설)

업계 통념: "AI 가 생산성 격차를 메워준다 → 주니어도 시니어급 코드 생산 가능."

실제 일어나는 일: **이론 보유 격차** 가 더 벌어진다.

| 구분 | AI 출력을 받을 때 | 결과 |
|------|------------------|------|
| 시니어 | 받아들이며 이론을 함께 재구축 (왜 이렇게? 어디 위험? 어떻게 고침?) | 이론 자산 누적, 임팩트 가속 |
| 주니어 | 받아들이고 통과시키면 끝 | 이론 부재, 첫 요구 변경에 무너짐 |

같은 AI 도구가 양쪽에 격차 가속기로 작동한다. **시니어가 AI 시대에 더 가치 있어지는 이유.**

본인 [[self-profile]] 의 "차별점" 항목 보강 후보: *"AI 출력에서 이론을 재구축하는 능력 — AI 가 코드를 만들수록 이 능력의 희소성이 올라간다."*

## 3. Responsibility vs Accountability — AI 시대의 칼날

글의 두 단어 구분이 핵심이다:
- **Responsibility (실행 책임)** — AI 에 위임 가능
- **Accountability (결과 책무)** — 위임 불가, 사람에게 남는다

이건 본인이 이전 [[2026-05-29-ai-product-distribution-thinking]] 노트에서 정리한 [[Air Canada]] 판례의 다른 표현이다. 챗봇이 잘못 답해도 회사가 책무를 진다 — **결과 책무는 AI 가 못 가져간다.** 글의 추상 개념과 판례의 구체 사례가 같은 곳에서 만난다.

## 4. 본인 [[리드플레닛]] 실무 적용 — AGENTS.md 보강 포인트

회사 단위 AGENTS.md 표준 운영 중인데, 이 글을 계기로 보강할 항목:

- **이론 보유자 (theory holder) 명시** — PR 메타에 "이 PR 의 theory holder = 누구" 표기. AI 가 생성한 코드라도 누군가 "왜 이렇게 됐는지 설명할 수 있는 사람" 이 명시되어야 머지
- **PR 셀프체크 1 줄 추가** — "내가 이 코드를 1 년 후 요구 변경 시 직접 고칠 수 있는가?" 가 yes 가 아니면 머지 보류
- **검증 루프에 Naur 인용 1 줄 박기** — "다익스트라: 테스트는 버그의 존재를 보여주지, 부재를 보여주지 않는다" 를 표준 문구로 박아 팀이 [[Eval]] 의 한계를 잊지 않게
- **주니어 멘토링 모듈** — AI 출력 → 이론 재구축 습관을 의식적으로 가르치기. "복붙 → 통과" 가 아니라 "복붙 → 왜? → 위험? → 대안?" 사이클

## 5. 이력서·자기 평가 차원의 함의

본인 이력서 [[resume-master]] 의 핵심 보유 역량 / 차별점에 반영할 후보:

- **"AI 코드의 이론을 재구축할 수 있는 시니어"** — 21 년차의 의미가 "예전 코드 많이 봤다" 가 아니라 "코드를 보고 이론을 빠르게 복원할 수 있다" 로 재정의됨. AI 시대 시니어 가치 명제.
- 4.8 *AI-augmented engineering* 절에 한 줄 보강: "단순 도구 사용이 아니라, AI 출력을 검증·문서화·이론화하는 운영 방식" — 이미 비슷한 문장이 있지만 "이론화" 키워드 명시 가치 있음

다만 [[feedback_resume_no_zero_to_one]] 와 같은 결로, **"이론 구축" 같은 용어를 과사용하면 AI 시대 buzzword 로 식상해질** 위험도 있음. 보강은 신중하게.

## 6. 글에서 더 파볼 만한 지점

- **Mental Model** — 글이 "멘탈 모델" 로 언급. Naur 의 theory 와 거의 같은 개념. 별도 entity 로 분리할지는 다음 이번 다음 출현 때 판단
- **SDD (Spec-Driven Development)** — 글이 잠깐 언급. Vibe Coding 의 대안 흐름 중 하나. 따로 트래킹 가치 있음
- **이전 글 "주말 장애 처리 이야기"** — 같은 저자의 직전 연재. 이론·책임 시리즈의 시작점일 수 있어 다음 ingest 후보

## Action items

- [ ] AGENTS.md 에 theory holder 메타 + Naur 인용 셀프체크 추가 검토
- [ ] [[self-profile]] 차별점 절에 "AI 코드의 이론 재구축 능력" 한 줄 추가 검토
- [ ] [[resume-master]] 4.8 *AI-augmented engineering* 에 "이론화" 키워드 보강 검토 (신중하게)
- [ ] [[백명석]] 이전 글 "주말 장애 처리 이야기" ingest 후보

## Related

- [[brunch-cleancode-ownership-ai-era]] (출처)
- [[Programming as Theory Building]], [[Vibe Coding]], [[Eval]], [[Agentic Engineering]], [[Hallucination]], [[Air Canada]]
- [[2026-05-29-ai-product-distribution-thinking]] — Air Canada 판례·분포 KPI 연결
- [[llm-tool-comparison]], [[ai-market-pulse]], [[self-profile]], [[resume-master]]
