---
type: note
status: active
tags: [living-doc, ai-market, anthropic, openai, llm-industry, observation]
aliases: [AI 시장 관전, AI Market Pulse]
created: 2026-05-22
updated: 2026-05-22
---

# AI 시장 관전

본인의 AI 산업 변동 관전 living doc. ingest 된 source 들을 본인 관점으로 누적·재해석한다.

> 자기 생각을 넣어서 정리해야 한다. — 본인이 존경하는 분의 가르침

## 운영 원칙

1. **누적형 living doc** — 사건별 source 는 `sources/` 에 따로 ingest 하고, 여기는 본인 해석만 누적
2. **사실과 본인 입장 분리** — 사실은 [[...]] 인용, 본인 입장은 일반 텍스트로 명시
3. **결정점 (도구 선택) 과 분리** — 본인의 일상 도구 (Claude Code + Codex) 선택은 별도 트랙. 시장 관전은 도구 선택을 흔들지 않는다

## 현재 사이클 인식 (2026-05 기준)

- **시작은 [[OpenAI]] 가 끊었다** — ChatGPT (2022) 로 일반 사용자 시장을 열었고, GPT-4 까지 모델 선두 주자.
- **현재는 [[Anthropic]] 이 먹는 분위기** — 시장 평가 ≈ 1조 달러로 [[OpenAI]] (≈ 8,800 억) 추월. 더 결정적인 신호는 [[AI-driven R&D]] 의제 공식화 + [[Andrej Karpathy]] 영입 — "다음 사이클의 모델 개발 방식 자체를 바꾼다" 는 포지션을 선점.

이건 단순한 시장 점유율 역전이 아니라 **사이클의 무대 자체가 바뀌는 신호** 로 본다. OpenAI 가 1막 (대중화) 을 열었다면, 2막 (AI 가 AI 를 개발) 의 주도권은 Anthropic 이 잡으려 하고 있다.

## 추적 신호 2축

| 신호 | 성격 | 본인 해석 |
|------|------|----------|
| **성능 벤치 (엎치락뒤치락)** | 단기 노이즈 | 분기별로 바뀌고, 모델 출시 타이밍에 흔들림. 무게 두지 않는다. |
| **인력 이동 / 전략 발표** | 구조 신호 | 누가 어디로 가는지가 다음 사이클의 무대를 가리킨다. [[Andrej Karpathy]] → [[Anthropic]] 이 대표 사례. |

**왜 인력 이동이 더 무거운가**: 모델 성능은 6 개월 안에 따라잡히지만, 핵심 인력의 의제 합치는 1~2 년 후 결과로 굳어진다. 본인은 후자를 본다.

## 도구 선택 vs 시장 관전

- **도구**: 본인 일상 주력 = [[Claude Code]] + [[Codex]] 병용 (역할 분리). [[ChatGPT]] 설계 보조.
- **시장 관전**: 위 도구 선택과 별개 트랙. 시장 1 위 회사가 누구든 본인 도구 조합은 검증된 워크플로에 따라 유지한다.
- 즉 "Anthropic 우세 분위기" 라는 관전이 곧 "Claude Code 만 쓰자" 가 아니다. 도구는 **검증된 멀티 에이전트 워크플로** 에 의해 선택된다 ([[Agentic Engineering]]).

## 누적 ingest 사례

- 2026-05-22 [[yozm-karpathy-anthropic-join]] — Karpathy 의 Anthropic 합류 + AI-driven R&D 의제 공식화. **본 living doc 의 첫 사례**.

(이후 source ingest 시 한 줄씩 누적)

## 관전 포인트 (앞으로 살펴볼 것)

- [[OpenAI]] 의 대응 — Anthropic 의 AI-driven R&D 의제에 동조 / 반박 / 우회 중 어느 카드?
- 인력 이동 방향성 — Google DeepMind, Meta FAIR 의 인재 유출/유입
- **Google 자금력 ↔ Gemini 실측 부재** — 자금력은 시장 관전 신호로 무게 있는 변수지만 본인이 본격 안 써봤음 (도구 측 평가는 [[llm-tool-comparison]] 의 "미검증" 항목). 자금력이 도구 우위로 실제 이어지는지 별도 추적
- 한국 시장 — [[AI-driven R&D]] 흐름 도착 지연 정도, 본인 이직 후보 회사들의 AI 도구 채택 깊이
- 모델 사이클 단축 — 기존 6~12 개월이 실제로 줄어드는지 (관찰 지표 필요)

## Related

- [[Anthropic]] · [[OpenAI]] — 양대 축
- [[Andrej Karpathy]] · [[Jack Clark]] — 핵심 인물
- [[AI-driven R&D]] — 다음 사이클의 의제
- [[Self-Improving Agent]] — AI-driven R&D 의 사상적 모체
- [[Agentic Engineering]] — 본인 도구 선택의 근거 워크플로
- [[Vibe Coding]] — 회피 대상 사상 (도구 선택의 부정적 기준)
- [[llm-tool-comparison]] — 본인 도구 실측 (분리 트랙)
- [[yozm-karpathy-anthropic-join]] — 첫 누적 사례
