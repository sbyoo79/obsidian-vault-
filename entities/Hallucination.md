---
type: entity
status: active
category: concept
tags: [llm, failure-mode, ai-safety, ai-product]
aliases: [환각, 할루시네이션, LLM Hallucination]
created: 2026-05-29
updated: 2026-05-29
---

# Hallucination

LLM 이 사실과 다른 내용을 **그럴듯한 어조로** 생성하는 실패 모드. 한국어로 보통 **환각** 으로 옮긴다.

## 개요

LLM 은 다음 토큰을 확률 분포에서 추출하는 시스템이라, **확신(high probability) 과 정확성(factual correctness) 이 분리** 되어 있다. 모델 입장에서 가장 그럴듯해 보이는 출력이 사실과 어긋날 수 있고, 이때 사용자 입장에서는 톤·문법이 자연스러워 오류를 알아채기 어렵다. 이것이 "**조용한 실패**" 의 본질.

## 본 vault 에서의 의미

[[Agentic Engineering]] 워크플로의 가장 큰 위험 요소. 단일 LLM 출력을 검토 없이 받아들이는 [[Vibe Coding]] 패턴이 깨지는 지점이고, 멀티 에이전트 cross-check + [[Eval]] 의 존재 이유.

본인 리드플레닛 멀티테넌트 ERP 같이 LLM 출력을 고객 응대·보고서 산출에 직접 노출시키는 시스템에선, 환각은 단순 오류가 아니라 **법적·운영 책임** 으로 직결 ([[Air Canada]] 판례).

## Key facts

- 원인: 학습 분포 외 입력, 부족한 컨텍스트, 모델 over-confidence
- 사용자 인지 한계: 자연스러운 어조 때문에 오류 탐지 곤란
- 법적 함의: [[Air Canada]] 챗봇 판결 — 환각 답변도 회사 발화로 인정
- 완화 기법: RAG, citation forcing (출처 인용 강제), 신뢰도 표기, [[Eval]] 기반 모니터링, 위험 등급별 휴먼 게이트

## 관련 sources

- [[yozm-ai-why-wrong]] — 환각이 "조용한 실패" 인 이유

## 관련 entities

- [[Eval]] — 완화·탐지 도구
- [[Air Canada]] — 환각의 법적 책임 선례
- [[Context Engineering]] — 입력 측 완화 (RAG, 컨텍스트 위생)
- [[Vibe Coding]] — 환각을 무비판 수용하는 안티패턴
- [[Claude]], [[ChatGPT]], [[Gemini]] — 주요 LLM 모두 해당
