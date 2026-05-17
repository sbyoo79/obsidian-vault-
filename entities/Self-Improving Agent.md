---
type: entity
status: active
category: concept
tags: [concept, ai-agent, learning, memory, llm, paradigm]
aliases: [자가 학습 에이전트, self-improving AI]
created: 2026-05-18
updated: 2026-05-18
---

# Self-Improving Agent

사용 과정에서 누적된 경험을 **다음 호출에 재사용** 함으로써 점진적으로 성능·개인화가 향상되는 [[AI Agent]] 패턴.

## 개요

"self-improving" 이라는 표현은 두 가지 의미가 섞여 쓰인다.

| 의미 | 설명 | 현실성 |
|------|------|--------|
| **모델 자체가 똑똑해진다** | weight 업데이트, online RL | 사용자 환경에서는 거의 불가 |
| **워크플로에 맞춰진다** | 절차/선호를 외부 저장 후 재사용 | 실제 가능, 대다수 도구의 의미 |

마케팅 슬로건은 1 번처럼 들리지만 실제 메커니즘은 2 번. 핵심은 **명시적 외부 저장** — 모델은 그대로지만 호출 시 매번 풍부한 context (저장된 절차 + 선호 + 사용자 패턴) 가 함께 들어가는 구조.

## 본 vault 에서의 의미

본 vault 의 [[LLM Wiki]] 패턴이 정확히 이 사상의 **사용자 주도** 버전. Hermes 같은 도구가 **에이전트 주도** 버전이라면, vault 는 **사용자/Claude 의 명시적 ingest** 로 같은 효과를 낸다. 둘 다 [[Context Engineering]] 의 사례.

## Key facts

- 진짜 메커니즘: weight 변경이 아닌 **외부 컨텍스트 누적**
- 핵심 자원: [[Procedural Memory]] 저장소
- 한계: 저장이 자동일 경우 잘못된 절차도 누적될 위험 → 검증 루프 필요
- 검증 방식: markdown 등 사람이 읽을 수 있는 형식 권장

## 원안 / 출처

특정 단일 원안 없음. 2024~2026 LLM 에이전트 흐름에서 자연 발생. 인지심리학의 [[Procedural Memory]] 개념을 차용.

## 핵심 원리

| 원리 | 설명 |
|------|------|
| **저장은 명시적** | 자동이되 조건 명확 (예: 성공한 절차) |
| **검증 가능** | markdown 같은 사람이 읽을 형식 |
| **검색 가능** | FTS / 벡터 / wiki link 등 |
| **갱신 가능** | 시간이 지나 무효해진 절차는 수정·삭제 |

## 채택 사례

- [[Hermes Agent]] — 에이전트 자율 저장 형태
- 본 vault — 사용자/Claude 명시적 ingest 형태
- ChatGPT memory / Claude memory — 폐쇄형 빅랩 버전

## 관련 sources

- [[yozm-hermes-agent-self-improving]]

## 관련 entities

- [[Hermes Agent]] — 대표 구현
- [[Procedural Memory]] — 핵심 자원
- [[AI Agent]] — 상위 카테고리
- [[Context Engineering]] — 상위 흐름
- [[LLM Wiki]] — 사용자 주도 버전 패턴
