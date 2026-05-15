---
type: source
status: active
format: article
author: "[[Dinon]]"
publisher: "[[YozmIT]]"
url: https://yozm.wishket.com/magazine/detail/3753/
language: ko
tags: [psychology, self-distancing, ai, decision-making, metacognition, role-reversal, llm-use]
created: 2026-05-14
updated: 2026-05-14
---

# 조언은 쉽고 행동은 어려운 이유, AI로 극복하기

[[Dinon]] 이 [[YozmIT]] 에 기고한 글. 자기 문제에는 결정이 안 되면서 남 문제에는 술술 조언이 나오는 [[Solomon's Paradox]] 를 LLM 활용 기법 [[Role-Reversal Dialogue]] 로 극복한다는 제안.

## 솔로몬의 역설

솔로몬 왕이 타인에게는 지혜로웠지만 자기 가정 문제에는 실패했다는 일화에서 따온 인지 편향. **자기 문제 → 감정·맥락 압박으로 시야 좁아짐**. 타인의 문제 → 한 발 떨어진 위치에서 분석 가능. 워털루대 [[Igor Grossmann]] 의 [[Self-Distancing]] 연구가 이론적 근거를 제공한다.

## 역할 반전 대화 (Role-Reversal Dialogue)

기존 LLM 활용 패턴은:
```
사용자 → AI 에게 질문 → 답변 받는다
```
저자가 제안하는 반전:
```
AI 가 사용자 클론처럼 고민을 제시 → 사용자가 조언자 역할
```

[[Claude]], [[ChatGPT]] 같은 도구에 본인의 맥락을 충분히 준 뒤 "내 입장에서 너가 고민을 말해줘. 나는 친구처럼 조언할게" 라고 역할을 뒤집는다. [[Base44]] 같은 노코드 빌더로 자기 전용 대화 앱을 만드는 방법도 언급.

## 두 가지 효과

1. **내 안의 해결책 발견** — 이미 알고 있던 답을 외부화해서 자연스럽게 꺼낼 수 있다
2. **부정적 사고 패턴 인식** — 무의식적으로 반복하던 사고가 클론 AI 의 입을 통해 시각화 → 근본 원인이 보인다

## 인상적인 인용

> 이미 어디선가 다 들었던 말이지만, 역할을 바꿔 제시하니 훨씬 빠르고 쉽게 납득할 수 있었다.

> 해결책은 이미 우리 모두 알고 있다. AI 를 통해 우리 안의 지혜를 꺼내는 도구로 삼으면, 현재의 문제에 더 쉽게 접근할 수 있다.

## 본 vault 와의 연결

- [[LLM Wiki]] 패턴이 "LLM 은 부기, 사람은 큐레이션" 으로 역할을 나눈다면, 이 article 은 "LLM 은 self-mirror, 사람은 외부 조언자" 라는 또 다른 역할 분담을 제안한다. [[Agentic Engineering]] 의 task 자동화 흐름과 결이 다른, 개인 심리/의사결정 영역의 LLM 활용.
- 회사 작업 룰의 **선행 분석** 단계도 비슷한 효과가 있다 — 작업 직전에 객관 시각을 강제하니까, 본인이 너무 깊이 들어가기 전에 거리두기가 된다.
- vault 의 자기 ingest 자체가 약한 형태의 self-distancing — 머릿속 생각을 위키 페이지로 외부화하면 다시 읽을 때 한 발 물러서서 보게 된다.

## Related

- [[Dinon]]
- [[YozmIT]]
- [[Solomon's Paradox]]
- [[Self-Distancing]]
- [[Role-Reversal Dialogue]]
- [[ChatGPT]]
- [[Claude]]
- [[LLM Wiki]]
- [[Agentic Engineering]]
