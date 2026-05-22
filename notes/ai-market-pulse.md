---
type: note
status: active
tags: [living-doc, ai-market, anthropic, openai, google, gemini, llm-industry, observation]
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
- **[[Anthropic]] 이 한때 우세** — 시장 평가 ≈ 1조 달러로 [[OpenAI]] (≈ 8,800 억) 추월. 더 결정적인 신호는 [[AI-driven R&D]] 의제 공식화 + [[Andrej Karpathy]] 영입 — "다음 사이클의 모델 개발 방식 자체를 바꾼다" 는 포지션 선점.
- **2026-05 I/O 로 [[Google]] 풀스택 반격 카드 공개** ([[yozm-google-io-2026-gemini-eats-google]]) — [[Gemini]] 가 모델·플랫폼·검색·결제·하드웨어 전반에 침투. **단순 "Anthropic 우세" 가설은 폐기. 3 파전 구도로 재구성** ([[Anthropic]] AI-driven R&D 축 / [[Google]] 풀스택 통합 축 / [[OpenAI]] 대응 미정).

본인 가설 갱신: 2막 (AI 가 AI 를 개발) 의 주도권 다툼이 **두 전선** 에서 동시 진행. (a) 모델 개발 방식 혁신 ([[Anthropic]]), (b) 사용자 접점 전 영역 통합 ([[Google]]). [[OpenAI]] 가 어느 쪽 카드를 들지가 다음 분기점.

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
- 2026-05-22 [[yozm-google-io-2026-gemini-eats-google]] — [[Google]] I/O 2026 풀스택 AI 통합 전략 ([[Gemini]] · [[Antigravity]] · 검색 개편 · [[Agent Payments Protocol]] · Android XR). **사이클 가설을 단순 우세 → 3 파전으로 수정 트리거**. 가격 인상 트렌드 (Flash 3 배) 도 함께 확인.

(이후 source ingest 시 한 줄씩 누적)

## 관전 포인트 (앞으로 살펴볼 것)

- [[OpenAI]] 의 대응 — Anthropic 의 AI-driven R&D 의제에 동조 / 반박 / 우회 중 어느 카드?
- 인력 이동 방향성 — Google DeepMind, Meta FAIR 의 인재 유출/유입
- **[[Google]] 자금력 → 풀스택 카드 가시화 (2026-05)** — 자금력 추상에서 [[Gemini]] · [[Antigravity]] · [[Agent Payments Protocol]] · Android XR 등 구체 카드로 진전. 본인은 여전히 [[Gemini]] 미검증 (도구 측 평가는 [[llm-tool-comparison]]). 다음 단계: 발표된 카드 중 어느 것이 실제로 작동하는지 (Antigravity 2.0 강제 전환 불만 같은 잡음 추적)
- **가격 인상 트렌드** — Gemini 3.5 Flash 토큰 가격 3 배 인상 사례. [[Claude]] · [[Codex]] 가격 인상 가능성 추적 (본인 워크플로 비용 영향)
- **자율 결제 영역** — [[Agent Payments Protocol]] 같은 표준이 정착하면 [[Vibe Coding]] 의 "검증 없는 채택" 사상이 금전 손실로 직결. 본 vault 의 검증 루프 사상이 금전 영역으로 확장되어야 하는지 관찰
- 한국 시장 — [[AI-driven R&D]] 흐름 도착 지연 정도, 본인 이직 후보 회사들의 AI 도구 채택 깊이
- 모델 사이클 단축 — 기존 6~12 개월이 실제로 줄어드는지 (관찰 지표 필요)

## Related

- [[Anthropic]] · [[OpenAI]] · [[Google]] — 3 파전 축
- [[Gemini]] · [[Antigravity]] · [[Agent Payments Protocol]] — Google 풀스택 카드
- [[Andrej Karpathy]] · [[Jack Clark]] — 핵심 인물
- [[AI-driven R&D]] — 다음 사이클의 의제
- [[Self-Improving Agent]] — AI-driven R&D 의 사상적 모체
- [[Agentic Engineering]] — 본인 도구 선택의 근거 워크플로
- [[Vibe Coding]] — 회피 대상 사상 (도구 선택의 부정적 기준)
- [[llm-tool-comparison]] — 본인 도구 실측 (분리 트랙)
- [[yozm-karpathy-anthropic-join]] — 첫 누적 사례
- [[yozm-google-io-2026-gemini-eats-google]] — 사이클 가설 3 파전 재구성 트리거
