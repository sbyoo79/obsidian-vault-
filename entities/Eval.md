---
type: entity
status: active
category: concept
tags: [llm, evaluation, ai-product, testing, methodology]
aliases: [이밸, LLM Eval, AI Eval]
created: 2026-05-29
updated: 2026-05-29
---

# Eval

LLM 출력의 품질·신뢰도를 **분포 기반** 으로 검증하는 방법론·시스템. 단일 정답을 기댓값 일치로 판단하는 기존 단위 테스트와 달리, 다양한 입력에 대한 출력의 **허용 범위** 와 **품질 분포** 를 평가한다.

## 개요

LLM 은 확률적 시스템이라 "같은 입력 = 같은 출력" 이 성립하지 않는다. 이로 인해 기존 QA 의 "테스트 케이스 통과/실패" 모델이 무너지고, **출력의 분포** 자체를 평가해야 한다. Eval 은 이를 위한 데이터셋·메트릭·자동화 파이프라인을 가리킨다.

대표 패턴:
- **Reference-based**: 정답이 명확한 입력 (factual QA / code) → 정확도·BLEU·ROUGE
- **Reference-free / LLM-as-judge**: 평가에 LLM 동원 (helpfulness, harmlessness, faithfulness)
- **Human-in-the-loop**: 도메인 전문가 spot-check
- **Adversarial / red-team**: 의도적 깨기 시도로 tail risk 측정

## 본 vault 에서의 의미

본인의 [[Agentic Engineering]] 멀티 에이전트 워크플로 (Codex 구현 → Claude 리뷰) 가 Eval 의 실무 한 형태. **단일 LLM 의존 회피 + cross-check 매트릭스** 는 LLM-as-judge 패턴이며, 회사 단위 표준 (AGENTS.md) 의 검증 루프 단계로 정착시키는 중. 단순 출력 비교를 넘어 **에이전트의 의사결정 과정 자체** 를 다른 에이전트가 검증하는 trajectory-level Eval 로 진화 가능.

## Key facts

- 새 직무 **Eval Engineer** 등장 (2024~), 데이터셋·메트릭·자동화 담당
- 기존 QA 와의 본질적 차이: 단일 정답 → 분포 평가
- 프로덕션 운영 시 사후 모니터링도 Eval 의 연장 (drift 탐지)
- KPI 재정의 필요: 정확도 단일 숫자 → p50 / p95 / p99 / tail risk 분포

## 관련 sources

- [[yozm-ai-why-wrong]] — Eval 이 기존 테스트를 대체하는 이유 정리
- [[yozm-vibe-coding-real-start]] — vibe coding 한계 → Eval·검증 시대로의 전환

## 관련 entities

- [[Hallucination]] — Eval 이 잡으려는 대표 실패 모드
- [[Agentic Engineering]] — 실무 적용 형태
- [[Context Engineering]] — 입력 측 짝패
- [[Vibe Coding]] — Eval 의 반대편 (검증 없는 수용)
- [[Claude]], [[Codex]], [[ChatGPT]] — judge 또는 검증 대상 도구
