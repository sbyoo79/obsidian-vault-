---
type: entity
status: active
category: concept
tags: [concept, technique, llm-use, prompting, metacognition, self-distancing]
aliases: [역할 반전 대화, role reversal, role-swap prompting]
proposed_by: "[[Dinon]]"
created: 2026-05-14
updated: 2026-05-14
---

# Role-Reversal Dialogue

LLM 에게 사용자의 페르소나(고민자) 를 부여하고 사용자가 외부 조언자 역할을 하는 대화 패턴. [[Self-Distancing]] 의 LLM 활용 변형.

## 개요

기존 LLM 활용은 사용자가 묻고 AI 가 답한다. 반전은 그 반대 — AI 가 사용자의 클론처럼 고민을 토로하고 사용자가 친구·코치처럼 조언한다. 이때 사용자는 자기 문제를 외부에서 바라보게 되어 [[Solomon's Paradox]] 의 자기-타인 비대칭이 완화된다.

핵심은 **충분한 컨텍스트 + 역할 명시** 다. 본인의 상황·감정·맥락을 LLM 에게 충분히 준 뒤 "내 입장에서 너가 말해줘. 나는 친구처럼 조언할게" 라고 시점을 박는다.

## 본 vault 에서의 의미

LLM 활용을 "자동화" 가 아닌 "메타인지 보조" 로 확장하는 패턴. [[Agentic Engineering]] / [[LLM Wiki]] 같은 작업 자동화 흐름과 결이 다른, 개인 의사결정·심리 영역의 적용 사례.

## Key facts

- 제안자: [[Dinon]] (요즘IT 기고)
- 도구: [[Claude]], [[ChatGPT]] 같은 LLM 챗 + 노코드 wrapper ([[Base44]] 등)
- 효과:
  1. 내 안의 해결책 외부화
  2. 부정적 사고 패턴 시각화

## 원안 / 출처

- [[yozm-solomon-paradox-ai]] — Dinon 의 정리 글

## 핵심 원리

| 단계 | 동작 |
|------|------|
| 1 | LLM 에게 본인 상황 / 감정 / 맥락 충분히 제공 |
| 2 | "내 페르소나로 너가 고민을 말해줘" 로 역할 박기 |
| 3 | 사용자는 외부 조언자처럼 응답 |
| 4 | 반복 — 새로운 답이 나오는지, 같은 패턴이 보이는지 관찰 |

## 채택 사례

- 개인 의사결정·고민 정리
- 부정적 사고 패턴 진단

## 관련 sources

- [[yozm-solomon-paradox-ai]]

## 관련 entities

- [[Solomon's Paradox]] — 완화 대상
- [[Self-Distancing]] — 상위 원리
- [[ChatGPT]] / [[Claude]] — 실행 도구
- [[Dinon]] — 제안자
