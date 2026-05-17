---
type: entity
status: active
category: tool
tags: [tool, llm, api, router, gateway, infrastructure]
aliases: [Open Router]
url: https://openrouter.ai
vendor: OpenRouter
license: commercial
platform: [API, Web]
created: 2026-05-18
updated: 2026-05-18
---

# OpenRouter

다양한 LLM 공급자 (OpenAI / Anthropic / Google / 오픈소스 모델 등) 를 **단일 API 로 라우팅** 해주는 게이트웨이 서비스.

## 개요

LLM 마다 별도 SDK·인증·요금 체계를 가지는 불편을 한 곳에 합치는 broker. 한 endpoint 에서 모델 이름만 바꿔 호출 가능. 토큰 사용량 통계와 모델별 인기 랭킹을 공개해서 시장 동향 신호 (어떤 모델이 실제로 쓰이는가) 의 1 차 자료 역할도 한다.

[[Hermes Agent]] 같은 도구가 [[OpenRouter]] 랭킹에 등장하면 실제 사용자 트래픽이 붙고 있다는 의미가 된다.

## 본 vault 에서의 의미

LLM 도구·에이전트 source 에서 자주 등장하는 인프라. 시장 신호 (어느 모델이 진짜 쓰이는가) 의 reference 출처.

## Key facts

- 역할: LLM API 게이트웨이 / 라우터
- 지원 모델: 오픈/폐쇄 양쪽 다수
- 부가 가치: 모델별 토큰 사용량 통계, 랭킹 공개
- 비즈니스: 마진 + 인프라 편의성

## 핵심 기능

- 단일 endpoint 로 여러 LLM 호출
- 자동 fallback (모델 장애 시 대체)
- 사용량 집계 / 비용 통계
- 모델 랭킹 공개

## 관련 sources

- [[yozm-hermes-agent-self-improving]] — Hermes 의 랭킹 1 위 신호 출처

## 관련 entities

- [[Hermes Agent]] — OpenRouter 위에서 호출
- [[Claude]] / [[ChatGPT]] — OpenRouter 가 라우팅하는 대표 LLM
