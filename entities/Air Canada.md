---
type: entity
status: active
category: org
tags: [airline, ai-legal-precedent, chatbot, case-study]
aliases: [에어캐나다]
industry: airline
created: 2026-05-29
updated: 2026-05-29
---

# Air Canada

캐나다 국적 항공사. 본 vault 에서는 **챗봇 환각 답변 책임 판결** 사례로 등록.

## 개요

2022 년 11 월 승객 제이크 모팻(Jake Moffatt) 이 사별 할인 정책을 챗봇에 문의했고, 챗봇은 "여행 후 소급 신청 가능" 이라 답변. 실제 정책은 "여행 전 신청 필요" 였다. 모팻은 챗봇 답변을 신뢰해 정가 항공권을 구매 후 환불 거절당하자 소송 제기.

재판부는 "**챗봇도 회사 웹사이트의 일부**" 이므로 회사가 책임진다고 판결. Air Canada 는 812 달러 환불 + 챗봇 서비스를 중단했다.

## 본 vault 에서의 의미

LLM 출력에 대한 **회사 발화 책임** 의 선례. "참고용 면책" 표기로 책임을 회피하려 해도 인정되지 않는다는 강력한 신호. AI 프로덕트 거버넌스 설계의 출발선이며, 본인이 멀티테넌트 ERP 에 LLM 기능을 도입할 때 항상 떠올려야 하는 사례.

함의: **LLM 출력에 회사 정책 권한을 위임하는 순간, 그 출력은 회사 발화로 간주된다.** 향후 모든 LLM 기반 고객 응대 시스템 거버넌스의 출발 원칙.

## Key facts

- 사건 발생: 2022 년 11 월
- 환불 금액: 812 캐나다 달러
- 후속 조치: Air Canada 챗봇 서비스 중단
- 핵심 함의: LLM 답변 = 회사 공식 답변, "AI 가 그랬다" 면책 불성립

## 관련 sources

- [[yozm-ai-why-wrong]] — 결정론 vs 확률론 글의 핵심 사례

## 관련 entities

- [[Hallucination]] — 사고 원인
- [[Eval]] — 사후 예방책
