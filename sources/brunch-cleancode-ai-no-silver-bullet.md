---
type: source
status: active
format: article
author: "[[백명석]]"
publisher: "[[Brunch]]"
url: https://brunch.co.kr/@cleancode/98
language: ko
published: 2026-06-08
tags: [ai-coding, spec-driven-development, mental-model, theory-building, cognitive-debt, verification, senior-engineering, no-silver-bullet]
created: 2026-06-08
updated: 2026-06-08
---

# AI와 함께 개발하기 - 은탄환은 없다

[[백명석]] 의 [[Brunch]] @cleancode 연재 글 (98 화). 앞 글 [[brunch-cleancode-ownership-ai-era]] (97 화, "딸깍의 시대") 의 후속. AI 가 구현을 가져간 상황에서 **개발자에게 남는 일은 무엇인가** 를 명세(spec) 와 검증(verification) 두 축으로 정리하고, 새 위험 개념 **"인지적 부채(cognitive debt)"** 를 도입한다.

## 핵심 주장

1. **프로그래밍의 본질 = 명세 → 구현 → 검증.** AI 가 구현을 담당하게 되면서 개발자에게 남는 일은 **명확한 문제 정의** 와 **엄격한 검증**. 본질적으로 "구현만 다른 사람(=AI)에게 맡겨왔을 뿐."
2. **명세는 결정론적·반복 가능해야 한다.** 같은 명세에서 비슷한 결과가 나와야 함 — 코드의 deterministic / repeatable 요건이 명세 단계로 이동.
3. **검증 = 멘탈 모델 구축.** [[Peter Naur]] 의 정의를 다시 끌어옴 — "프로그래밍의 주된 목적은 그 문제가 프로그램 실행을 통해 어떻게 해결되는지에 대한 이론을 구축하는 것."
4. **인지적 부채(cognitive debt) — AI 시대의 새 위험.** 이해 없이 쌓인 부채는 단순 기술 부채와 다르다. **문제 발생 시 대처 자체가 불가능**해진다.
5. **결론** — "위임은 하되, 이해만큼은 내 몫으로 남겨 두어야 한다."

## 구조 — 명세 / 검증 두 축

### 1단계: 명세 — 문제 정의와 설계도
- AI 도구의 brainstorming / planning 모드 적극 활용
- 명세는 코드처럼 **deterministic / repeatable** 해야 함
- 같은 명세 입력에서 비슷한 출력 (구현) 이 재현되어야 함 → [[SDD]] (Spec-Driven Development) 의 기본 요구

### 2단계: 검증 — 이해를 통한 멘탈 모델 구축
- 검증의 목적은 단순한 출력 확인이 아니라 **본인이 이해할 수 있는 수준의 멘탈 모델** 을 확보하는 것
- 방법:
  - AI 에게 "내가 이해할 수 있는 수준으로" 설명 요청
  - 직접 코드를 만지고 테스트하는 **스크래치 리팩토링**
  - 리팩토링으로 **개념적 일관성(conceptual integrity)** 확보 → 멘탈 모델 강화

## 새 개념 — 인지적 부채 (Cognitive Debt)

- 기술 부채와 구분되는 AI 시대 특유의 부채
- 기술 부채 = 코드 품질의 미래 비용
- 인지적 부채 = **이해 없이 받아들인 코드의 누적** → 문제 발생 시 대처 자체가 불가능
- 사례: **AWS 2025-10 장애** — 베테랑 엔지니어들의 퇴직으로 "트라이벌 지식(tribal knowledge)" 이 사라져 복구에 약 75 분 소요
  - 인지적 부채의 조직 버전. 코드는 있어도 이론을 가진 사람이 없으면 동일한 결과

## Key quotes (저자 인용 발췌)

> 프로그래밍의 주된 목적은 그 문제가 프로그램 실행을 통해 어떻게 해결되는지에 대한 이론을 구축하는 것 — [[Peter Naur]] (저자가 본 글에서 다시 인용)

> 위임은 하되, 이해만큼은 내 몫으로 남겨 두어야 한다. 그 이해, 곧 멘탈 모델을 놓는 순간, 우리는 인지적 부채에 잠기게 될 테니까. — 저자, 결론

## 시리즈 / 연결 글

- 직전 글: [[brunch-cleancode-ownership-ai-era]] (97 화, 2026-05-31) — 주인의식 / Responsibility vs Accountability / Naur 이론 재조명. 본 글은 그 후속편으로 "이해 / 멘탈 모델 구축" 측면을 더 구체화.

## 등장 entity

- 인물: [[백명석]] (저자), [[Peter Naur]]
- 개념: [[Programming as Theory Building]], 인지적 부채(cognitive debt), 멘탈 모델, [[SDD]] (Spec-Driven Development), 스크래치 리팩토링, 트라이벌 지식, 개념적 일관성
- 사례: AWS 2025-10 장애

## 본 vault 에서의 연결

- [[Programming as Theory Building]] — 본 글의 이론적 토대 (저자가 직접 다시 인용)
- [[Vibe Coding]] — "이해 없이 받아들이는 코드" 의 대표 안티패턴, 인지적 부채의 주된 발생원
- [[Eval]] — 검증 단계의 구체 메커니즘
- [[Agentic Engineering]] — 본인의 멀티 에이전트 워크플로 (Codex 구현 → Claude 리뷰 → 본인 docs) 는 명세·검증 두 축을 외부화한 형태
- [[Hallucination]] — 검증을 건너뛰었을 때의 직접적 결과
- [[2026-06-01-theory-building-vs-vibe-coding]] — 97 화 기반 본인 관점 노트. 본 글 (98 화) 후속 노트는 별도 검토 필요
