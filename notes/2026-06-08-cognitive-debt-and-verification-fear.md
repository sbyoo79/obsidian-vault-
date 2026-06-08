---
type: note
status: active
tags: [ai-coding, cognitive-debt, verification, mental-model, agents-md, senior-engineering, theory-building]
related: ["[[brunch-cleancode-ai-no-silver-bullet]]", "[[2026-06-01-theory-building-vs-vibe-coding]]"]
created: 2026-06-08
updated: 2026-06-08
---

# 인지적 부채와 검증 두려움 — 98 화 본인 적용 노트

[[brunch-cleancode-ai-no-silver-bullet]] (98 화, 2026-06-08) 정독 + 본인이 평소 가지고 있던 "AI 가 짠 코드를 상용에 보낼 때의 두려움" 을 같이 풀어쓴 노트. 97 화 노트 [[2026-06-01-theory-building-vs-vibe-coding]] 와는 thesis 가 다름 — 그쪽은 *이론 보유 격차의 외부 효과 (시니어 가치·이력서)*, 이쪽은 *본인 워크플로에서 검증을 어떻게 자리 잡힐 것인가* 의 내부 운영.

## 1. 98 화가 새로 가져온 것

97 화 (주인의식·Responsibility vs Accountability) 가 **"AI 시대 책임의 위치"** 를 정의했다면, 98 화는 **"그 책임을 실제로 어떻게 보전하는가"** 의 두 축 (명세·검증) 으로 실행 가이드를 제시.

가장 큰 기여: **인지적 부채(cognitive debt)** framing.

- 기술 부채 = 코드 품질의 미래 비용. 리팩터로 해소 가능
- [[인지적 부채]] = **이해 부재의 누적**. 코드를 고쳐야 할 때 비로소 드러나고, 그때는 이미 늦음

AWS 2025-10 장애 (베테랑 퇴직 → 트라이벌 지식 소실, 복구 75 분) 가 인지적 부채의 조직 버전 사례로 인용된 점이 인상적. 이건 **개인 AI 코딩의 문제만이 아니라 조직 차원의 동일 패턴**이라는 뜻 — 우리 회사 AGENTS.md 가 다뤄야 할 영역.

## 2. 본인의 "검증 두려움" 을 재해석

평소 본인이 가지고 있던 감정: *"코드는 잘 짜주는데, 내가 직접 짠 게 아닌지라 이게 맞나? 상용 나가도 되나? 두려움이 항상 크다."*

98 화 framing 으로 다시 보면 이 두려움의 정체가 명확해진다:

**두려움 자체가 verification 이 작동 중이라는 신호.**

- 두려움이 있다 = 본인의 멘탈 모델과 AI 출력 사이에 gap 이 있다는 인지 = 인지적 부채를 막는 1 차 게이트
- 두려움이 없다 = 무비판 수용 = 인지적 부채가 누적되어도 본인이 모름 = [[Vibe Coding]] 상태

즉 두려움을 **없애야 할 감정** 으로 보지 말고, **계속 살려둬야 할 게이트** 로 명시화하는 게 맞다. 두려움이 사라지는 시점 ≠ 안전. 두려움이 **합당한 verification 절차에 의해 해소되는 시점** = 안전.

## 3. 검증의 기준선 — "내가 짰는가" 가 아니라 "차갑게 다시 봐도 설명 가능한가"

상용에 내보내도 되는지의 판정 기준은 코드의 출처 (본인 손 vs AI) 가 아니라 본인의 멘탈 모델 상태:

1. **차갑게 다시 봐도 왜 이 접근인지 설명 가능한가** — 1 년 후 컨텍스트 잊고 PR 만 봐도 OK
2. **입력 X 들어왔을 때 어떻게 동작할지 예측 가능한가** — 핵심 분기·엣지 케이스
3. **새벽 장애 시 어디부터 볼지 즉시 안가는가** — 본인이 디버깅 진입점 알고 있는가

세 개 다 yes 면 코드의 출처는 무관. 세 개 중 하나라도 no 면 본인이 직접 짠 코드라도 인지적 부채.

## 4. 본인 워크플로에 자리매김 — docs 단계의 재정의

본인 멀티 에이전트 워크플로: **Codex 구현 → Claude 리뷰 → 본인 docs**.

지금까지 docs 단계의 정의가 모호했음 — "AI 출력 정리 / 문서화" 정도. 98 화 framing 으로 다시 보면:

> **docs 단계 = 본인 말로 다시 쓸 수 있는가의 시험. 못 쓰면 reject.**

이 정의로 바꾸면 docs 단계가 자동으로 인지적 부채 방지 게이트가 된다. AI 가 만든 코드를 머지하기 전 무조건 통과해야 하는 layer.

AGENTS.md 에 박을 한 줄 (97 화 노트의 AGENTS.md action 보강과 연계):

> "AI 가 생성한 코드는 본인이 자기 말로 다시 설명할 수 있을 때까지 docs 가 완성된 것으로 보지 않는다. 설명이 안 되면 (a) AI 에게 본인 수준으로 재설명 요청, (b) 스크래치 리팩터로 직접 만져보기, (c) 그래도 안 되면 reject."

## 5. 검증은 코드 리뷰만이 아니다 — layered verification

98 화의 한계 (혹은 본인이 채워야 할 부분): 글이 검증을 주로 **이해 차원** 으로 다룬다. 21 년차 시니어 입장에서 보면 그건 verification 의 한 layer 일 뿐. 본인이 평소 운영하는 production verification 은 layered:

| Layer | 목적 | AI 코드여서 추가될 게 있나 |
|------|------|--------------------------|
| 본인 docs (이해) | 인지적 부채 방지 | **본 글의 핵심. 항상 필수.** |
| 코드 리뷰 (동료) | 본인 사각 보완 | AI 코드일수록 더 필요 — "왜 이렇게?" 질문에 본인이 답 가능해야 함 |
| 자동화 테스트 | 명시 요구의 회귀 방지 | AI 가 같이 만든 테스트라도, 본인이 케이스 의도 설명 가능해야 함 |
| Staging / canary | 미명시 시나리오 노출 | AI 코드일수록 명시되지 않은 행동이 더 있을 가능성 → 점진 롤백 가치 ↑ |
| Observability | 미지의 실패 모드 탐지 | 핵심 path 에 alert·dashboard·로그 + rollback 한 방 |

**핵심 인사이트**: AI 코드라서 verification 이 더 필요한 게 아니라, **"이해도 ↓ × stakes ↑" 조합** 이 위험. AI 코드여도 stakes 낮은 곳 (스크립트·내부 도구) 은 layer 1~2 까지, stakes 높은 곳 (결제·고객 데이터) 만 5 layer 다 받게 하면 운영 부하·verification 효과의 균형이 맞는다.

## 6. 97 화 노트 ([[2026-06-01-theory-building-vs-vibe-coding]]) 와의 관계

97 화 노트는 **외부 효과** 에 집중 — 시니어 격차·이력서·자기 평가.
98 화 노트는 **내부 운영** 에 집중 — 본인 워크플로의 docs 단계 재정의·검증 layer 의 적용 기준.

같은 article 시리즈에 두 노트가 분리된 이유: thesis 가 다름. 합치면 한쪽이 흐려진다.

97 화 노트의 AGENTS.md action 항목 (theory holder 명시 / PR 셀프체크) 은 본 노트의 docs 단계 재정의와 한 묶음으로 다음 AGENTS.md 개정 사이클에서 같이 반영 후보.

## 7. Action items

- [ ] AGENTS.md docs 단계 재정의 — "본인 말로 다시 쓸 수 있어야 docs 완료" 한 줄 박기 (97 화 노트의 theory holder / PR 셀프체크와 묶어 일괄 반영)
- [ ] stakes × 이해도 매트릭스 — 어떤 작업에 어떤 verification layer 까지 거는지 본인 기준 문서화 후보 (지금은 implicit, 명시화 가치)
- [ ] "검증 두려움 게이트" 문장 self-profile 보강 검토 — *"AI 출력에 두려움을 가지는 것을 verification 의 일부로 운영하는 능력"* 같은 표현. 단, 97 화 노트와 같은 buzzword 우려 — 신중하게
- [ ] [[Eval]] entity 에 인지적 부채 연결 한 줄 추가 (기존 "이론 재구축의 한 형태" 결을 본 노트로 확장)

## Related

- [[brunch-cleancode-ai-no-silver-bullet]] (출처, 98 화)
- [[brunch-cleancode-ownership-ai-era]] (97 화)
- [[2026-06-01-theory-building-vs-vibe-coding]] (97 화 본인 노트)
- [[인지적 부채]] — 본 글이 도입한 개념
- [[Programming as Theory Building]], [[Peter Naur]], [[Vibe Coding]], [[Eval]], [[Agentic Engineering]]
- [[self-profile]], [[llm-tool-comparison]]
