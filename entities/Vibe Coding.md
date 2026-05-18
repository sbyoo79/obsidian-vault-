---
type: entity
status: active
category: concept
tags: [concept, ai-coding, llm, engineering, productivity, security]
aliases: [vibe coding, 바이브 코딩]
proposed_by: "[[Andrej Karpathy]]"
year_proposed: 2025
created: 2026-05-18
updated: 2026-05-18
---

# Vibe Coding

[[Andrej Karpathy]] 가 2025 년 2 월 명명한 개발 방식. "**AI 가 생성한 코드를 검토 없이 그대로 받아들이는** 코딩" 을 가리킨다.

## 개요

원래 표현은 짧은 트윗에서 시작됐다. "vibe 만 보고 받아들이고 안 돌아가면 다시 시키는" 식의 즉흥적 LLM 협업. [[Cursor]] / [[Lovable]] / [[Bolt]] / [[Replit]] 같은 도구가 보편화되며 빠르게 확산. 2025 년 Collins 사전의 "올해의 단어" 로 선정되기도 했다.

문제는 2026 들어 실측 데이터로 드러나는 중이다 — GitHub 분석에서 AI 공동 작성 코드의 보안 취약점이 사람 코드의 2.74 배. Lovable 앱 1,645 개 중 10 % + 가 Row-Level Security 결함 (CVE-2025-48757). 빠르게 만들지만 더 자주 깨지는 패턴이 정량화됐다.

[[Simon Willison]] 의 재정의가 명확한 기준선이다.

> LLM 이 모든 코드를 썼어도 **전부 리뷰·테스트·이해했다면** 바이브 코딩이 아니라 "타이핑 도우미 활용" 이다.

즉 vibe coding 의 본질은 "AI 가 썼다" 가 아니라 **검증을 건너뛴 것** 이다.

## 본 vault 에서의 의미

본 vault 가 채택한 [[LLM Wiki]] 패턴 (같은 [[Andrej Karpathy]] 제안) 과 흥미로운 대비. LLM Wiki = "외부화 + 검증 가능", vibe coding = "외부화 없음 + 검증 없음". 본 vault 의 작업 룰 (선행 분석 → 티켓 → 브랜치) 과 코드 리뷰·테스트 정책은 vibe coding 의 반대 방향에 있다.

## Key facts

- 명명: [[Andrej Karpathy]], 2025 년 2 월 트윗
- 의미: AI 코드 결과물을 **검토 없이** 그대로 받아들이는 개발 방식
- 영문: vibe coding
- 2025 Collins 올해의 단어
- 2026 실측 데이터에서 보안·품질 문제 명확화

## 원안 / 출처

- [[Andrej Karpathy]] 트윗 (2025-02)
- 비평적 정리: [[yozm-vibe-coding-real-start]] (원문 Ahmed Hafdi)

## 핵심 원리

| 원리 | 설명 |
|------|------|
| 즉흥 | 큰 프롬프트 → 결과물 받아들이기 |
| 검증 생략 | 코드 리뷰 / 테스트 / 보안 스캔 우회 |
| 속도 우선 | 빠른 데모 / MVP 에 적합 |
| 한계 | 프로덕션·보안·복잡 시스템에서 무너짐 |

## 비교 — 인접 패턴

| 항목 | Vibe Coding | "타이핑 도우미" 활용 ([[Simon Willison]]) | [[Agentic Engineering]] |
|------|-------------|-----------------------------------|------------------------|
| AI 코드 생성 | O | O | O |
| 검토·테스트 | X | O | O (독립 검증 루프) |
| 적용 영역 | 빠른 prototype | 일반 개발 | 프로덕션·조직 |

## 채택 사례

- 2025 prototype·해커톤 영역에서 폭발적 확산
- 2026 들어 프로덕션 영역에서 회의론 강해지는 중

## 관련 sources

- [[yozm-vibe-coding-real-start]]

## 관련 entities

- [[Andrej Karpathy]] — 명명자
- [[Simon Willison]] — 비판적 재정의
- [[Ahmed Hafdi]] — 비평글 저자
- [[Agentic Engineering]] — 대안적 흐름
- [[LLM Wiki]] — Karpathy 의 다른 제안, 동일 검증 사상
- [[Cursor]] / [[Claude]] — 주요 도구
