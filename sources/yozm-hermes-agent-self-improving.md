---
type: source
status: active
format: article
author: "[[덕파]]"
publisher: "[[YozmIT]]"
url: https://yozm.wishket.com/magazine/detail/3756/
language: ko
tags: [ai-agent, self-improving, procedural-memory, hermes, nous-research, openrouter, llm-tools]
created: 2026-05-18
updated: 2026-05-18
---

# '쓸수록 나아진다'는 그 AI, Hermes Agent 제대로 알아보기

[[덕파]] 가 [[YozmIT]] 에 기고. [[Nous Research]] 의 [[Hermes Agent]] 가 [[OpenRouter]] 토큰 사용 랭킹 1 위에 오른 흐름을 짚으면서, "self-improving" 이 마케팅 슬로건인지 실제 메커니즘인지를 뜯어본다.

## 핵심 논지

Hermes 의 self-improving 은 **모델 자체가 똑똑해진다** 가 아니라 **사용자의 워크플로에 맞춰진다** 는 의미다. [[Procedural Memory]] 를 영구 저장하고 다음 호출에서 재사용하는 식. 혁신적 데모용이 아니라 **장기 사용에서의 워크플로 최적화** 가 진짜 경쟁력.

> 곧바로 똑똑해진다 보다 **쓸수록 워크플로에 맞춰진다** 가 더 정확한 표현.

## Self-Improving 의 네 기둥

| # | 메커니즘 | 설명 |
|---|---------|------|
| 1 | **스킬 자동 저장** | 도구 호출 5 회 이상 작업 성공 시 절차를 마크다운으로 기록 |
| 2 | **메모리 검색** | SQLite FTS5 기반 경량 검색. 10 ms 안 문서 lookup |
| 3 | **동적 개선** | 세션 중 메모리 도구로 저장된 절차 직접 수정 |
| 4 | **사용자 모델링** | Honcho 기반으로 사용자 패턴 누적 → 장기 기억 |

핵심은 **저장이 명시적 동작** 이라는 점. "자동으로 학습된다" 가 아니라 "특정 조건에서 명시적으로 markdown 으로 저장한다" — 검증 가능하고 사용자가 들여다볼 수 있는 형태.

## 사용 환경

- 플랫폼: 텔레그램, 디스코드, 슬랙, 로컬 CLI, Docker, SSH
- 백엔드: [[OpenRouter]] 경유로 다양한 LLM 호출 가능
- 학습 인프라: Atropos RL 환경 ([[Nous Research]] 자체 RL 프레임워크)

## 현실적 한계

- **개인 개발자 중심** — 팀 환경에서 권한/공유 모델 제약
- **보안** — 자격증명/시크릿이 자동 절차에 흘러들 가능성
- **규제·감사** — 엔터프라이즈 도입에 필요한 거버넌스 부족

## 본 vault 와의 연결

흥미로운 직접 연결:

- **저장이 명시적 동작** = 본 vault 의 [[LLM Wiki]] 패턴과 정확히 같은 사상. "자동 학습" 의 블랙박스가 아니라 **markdown 으로 외부화**.
- Hermes 의 "스킬 자동 저장" = vault 의 ingest 자동화와 동일 컨셉. 도구 호출 5 회 이상 성공 시 ↔ ingest 신호 받았을 때
- Hermes 의 "메모리 검색" = vault 의 `index.md` 카탈로그 + Obsidian graph 검색
- 차이: Hermes 는 **에이전트가 스스로 저장**, vault 는 **사용자/Claude 가 명시적으로 ingest**. 후자가 더 보수적이지만 신뢰성 높음.

이 article 은 본 vault 가 추구하는 [[Context Engineering]] 의 또 다른 응용 사례를 보여준다.

## Related

- [[덕파]]
- [[YozmIT]]
- [[Hermes Agent]]
- [[Nous Research]]
- [[OpenRouter]]
- [[Self-Improving Agent]]
- [[Procedural Memory]]
- [[LLM Wiki]] — 동일 사상 (저장 = 명시적 동작)
- [[Context Engineering]] — 상위 흐름
