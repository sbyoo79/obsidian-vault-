---
type: source
status: active
format: article
author: "[[김영욱]]"
publisher: "[[YozmIT]]"
url: https://yozm.wishket.com/magazine/detail/3775/
language: ko
published: 2026-05-28
tags: [llm-product, eval, hallucination, pm, ai-product, governance]
created: 2026-05-29
updated: 2026-05-29
---

# AI 는 왜 자꾸 틀리는가

[[김영욱]] 의 [[YozmIT]] 기고. AI 프로덕트가 기존 소프트웨어와 근본적으로 어떻게 다른가를 **결정론 vs 확률론** 의 대비로 풀고, PM (그리고 시스템 설계자) 이 받아들여야 할 사고 전환을 정리한 글.

## 핵심 주장

**기존 SW 의 "같은 입력 = 같은 출력" 전제는 LLM 에서 깨진다.** LLM 은 다음 토큰을 확률적으로 예측하는 시스템이라, 같은 프롬프트도 시점·맥락에 따라 다른 답을 낸다. 이로 인해 세 가지 문제가 동시에 발생.

- **테스트 패러다임 변화**: 기댓값 일치 여부 → 허용 범위 검증 ([[Eval]] 기반)
- **조용한 실패**: 오류가 [[Hallucination|환각]] 형태로 그럴듯하게 발생 — 사용자가 알아채기 어려움
- **비용 예측 불가**: 토큰 단위 과금 + 사용자별 편차 → 사전 SLA 산정 곤란

## PM 대응 (글의 권고)

- "정확도 100 %" KPI 폐기, **오류율 분포** 관찰로 전환
- 답변에 신뢰도·출처·에스컬레이션 경로 명시 (신뢰 설계)
- 출시 이후 지속 모니터링 강화

## 핵심 사례 — [[Air Canada|에어캐나다]] 챗봇 판결

승객 제이크 모팻이 사별 할인을 챗봇에 문의했고, 챗봇은 "여행 후 소급 신청 가능" 이라 답함 (2022.11). 실제 정책은 "여행 전 신청" 이었으나 모팻은 답변을 신뢰해 정가 항공권 구매 후 환불 거절당함. 재판부는 "**챗봇도 회사 웹사이트의 일부**" 이므로 회사 책임이라 판결, 812 달러 환불 + 챗봇 서비스 중단.

## 등장 entity

- 핵심 개념: [[Eval]], [[Hallucination]]
- 사례: [[Air Canada]]
- LLM: [[ChatGPT]], [[Claude]], [[Gemini]]
- 새 직무: Eval Engineer (별도 entity 미신설, [[Eval]] 안에 언급)

## 본 vault 에서의 연결

- [[ai-market-pulse]] — AI 프로덕트 사례 누적
- [[llm-tool-comparison]] — 도구 평가 축
- [[Agentic Engineering]] — 멀티 에이전트 cross-check 가 글의 Eval 권고와 결이 같음
- [[Context Engineering]] — 출력 측 검증의 짝패 (입력 측 품질 관리)
- 본인 관점 노트: [[2026-05-29-ai-product-distribution-thinking]]
