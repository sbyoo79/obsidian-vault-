---
type: entity
status: active
category: concept
tags: [concept, ai-agent, engineering, workflow, paradigm]
aliases: [에이전틱 엔지니어링, agentic eng]
created: 2026-05-14
updated: 2026-05-14
---

# Agentic Engineering

AI 에이전트가 실행 주체로 들어온 환경에서, 인간이 결과를 직접 만들기보다 **에이전트의 결과를 검증·조율** 하도록 일을 재설계하는 엔지니어링 패러다임.

## 개요

전통적 엔지니어링이 "기획 → 구현 → 검증" 이라면, agentic engineering 은 구현 단계의 상당 부분을 [[AI Agent]] 가 맡는다. 그래서 사람의 역할은 **분해 / 명세 / 검증 설계** 로 옮겨간다. 도구를 빨리 쓰는 사람이 아니라 **기준을 잘 세우는 사람이 살아남는다** 는 명제가 자주 등장한다.

조직 레벨에서는 공통 컨텍스트 레이어, 권한 경계, 평가 체계 같은 인프라가 새로 필요하다. 단순 자동화와의 차이는 **독립적인 검증 루프** 의 존재 여부다.

## 본 vault 에서의 의미

본 vault 의 schema [[CLAUDE]] · 워크플로 자체가 agentic engineering 의 개인 영역 적용 사례. [[LLM Wiki]] 패턴은 그 한 응용이다. 회사 측 공통 룰 (선행 분석 → 티켓 → 브랜치 → 본 작업) 도 같은 사상의 변형으로 볼 수 있다.

## Key facts

- 사람의 핵심 역량: 분해력 / 명세력 / 검증 설계력
- 조직의 핵심 인프라: 공통 컨텍스트 레이어, 권한 경계, 평가 체계
- 에이전트 실패의 주된 원인: 모델 한계가 아닌 **성공 조건의 모호함**
- 검증 원칙: 에이전트에게 채점을 재위임하지 않는다

## 원안 / 출처

별도의 단일 원안은 없다. 2023~2025 무렵 LLM agent (AutoGPT, Devin, [[Claude]] Code, Cursor 등) 가 등장하면서 자연발생적으로 형성된 담론.

## 핵심 원리

| 원리 | 설명 |
|------|------|
| 결과 ≠ 답 | 에이전트의 산출물은 후보일 뿐, 검증을 통과해야 답이 된다 |
| 기준 우선 | 도구보다 성공 조건이 먼저 |
| 컨텍스트는 자산 | [[Context Engineering]] 으로 누적 |
| 하네스가 인프라 | 환경을 안전하게 반복 실행하는 장치 |

## 채택 사례

- 본 vault 의 [[LLM Wiki]] 패턴 (개인 PKM 영역)
- 회사 측 선행 분석 / 티켓 / 브랜치 / 본 작업 워크플로 (조직 영역)

## 관련 sources

- [[yozm-agentic-engineering-survival]] — DevOwen 의 정리

## 관련 entities

- [[AI Agent]] — 실행 주체
- [[Context Engineering]] — 공통 컨텍스트 만들기
- [[Claude]] — agent 의 한 인스턴스
- [[LLM Wiki]] — 인접 패턴 (개인 영역)
