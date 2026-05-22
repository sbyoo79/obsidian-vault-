---
type: note
status: active
tags: [living-doc, llm-tools, claude-code, codex, chatgpt, gemini, agentic-engineering, observation]
aliases: [LLM 도구 비교, 본인 도구 실측]
created: 2026-05-22
updated: 2026-05-22
---

# LLM 도구 비교 (본인 실측)

본인이 직접 부딪혀 본 LLM 도구별 강점·약점 living doc. 시간 누적으로 워크플로 재평가 시 베이스라인이 된다.

> 기록을 해놔야 안 까먹어. — 본인 발화 (2026-05-22)

## 운영 원칙

1. **실측만 기록** — 안 써본 도구는 "미검증" 으로 명시. 일반론·벤치마크·언론 평가는 별도 source 로 분리 (`sources/`)
2. **[[ai-market-pulse]] 와 분리** — 시장 관전 (자금력·평가·인재 이동) 과 도구 실측 (본인 작업에서의 성능) 은 별개 트랙. 그 노트의 운영 원칙 그대로 적용
3. **버전·시점 기록** — 평가는 시점에 묶인다. 도구 업데이트 시 기존 평가는 지우지 않고 시점 표시 후 새 평가 추가
4. **단순 요약 아님** — 본인 해석·왜 그렇게 느꼈는지 근거 누적 ([[feedback_curate_with_own_thinking]])

## 본인 실측 비교 (2026-05 시점)

| 도구 | 강점 (본인 실측) | 약점 / 미검증 |
|------|-----------------|--------------|
| [[Claude]] Code | 문서 작성 우세 — 인계 가능 상태 유지에 강함 | 레거시 분석 깊이 ([[Codex]] 대비) |
| [[Codex]] | 레거시 분석력 — 오래된 코드 맥락 파악 우세 | 문서 일관성 ([[Claude]] 대비) |
| [[ChatGPT]] | 설계·아이디어 발산 단계에 적합 | 구현·리뷰는 다른 도구로 위임 |
| Gemini | (미검증) | 본인 실사용 안 됨. Google 자금력이 도구 우위로 실제 이어졌는지 미확인 |

## 도구별 메모

### Claude Code — 문서 우세
- 인계 가능 상태 (회사 AGENTS.md 의 "문서화-as-deliverable") 와 결이 맞음
- 본 vault 의 active agent. ingest / note 작성에서 일관된 문체·구조 유지
- 회사 멀티 에이전트 워크플로에서 **리뷰 / 통합** 담당으로 배치된 것과 일치

### Codex — 레거시 분석 우세
- 오래된 코드, 비표준 패턴, 흩어진 의존성을 읽는 데 강함
- maxvisor 계열 fade-out 작업 ([[project_maxvisor_batch_fadeout]]) / countInfoJob 이관 ([[project_countinfojob_migration]]) 같은 레거시 맥락에서 체감
- 회사 워크플로에서 **구현** 담당으로 배치된 것과 일치

### ChatGPT — 설계·발산
- 외부 자료 검색 + 설계 단계 아이디어 정리
- 회사 워크플로에서 **기초 설계 / 문서 작성** 보조로 배치

### Gemini — 미검증
- 본인이 본격적으로 안 써봤음. 평가 보류
- [[Anthropic]] / [[OpenAI]] 와 같은 축에서 비교 가능한 또 하나의 프론티어 모델인데, 검증 부재가 본인 도구 풀에 빈틈
- Google 의 자금력 자체는 시장 관전 신호로 [[ai-market-pulse]] 에 별도 추적 — 자금력이 도구 우위로 이어졌는지는 본인이 직접 써봐야 답 가능

## 누적 사용 사례

(향후 작업에서 어느 도구가 결정적이었는지 한 줄씩 누적)

- 2026-05-22 [[yozm-karpathy-anthropic-join]] ingest — Claude Code 단독 작업. 외부 자료 fetch + vault schema 따라 다중 entity 신설·갱신 / git 동기화 일관성 유지. 도구 적합 (문서·구조 작업).

## 재평가 트리거

다음 상황에서 본 비교 매트릭스를 재검토:

- Claude 또는 Codex 의 메이저 버전업
- Gemini 본격 사용 시점 (미검증 → 검증으로 전환)
- 회사 멀티 에이전트 워크플로 (역할 배치) 가 실측과 어긋나기 시작할 때
- 새 도구 진입 (예: Anthropic 외 회사의 신규 CLI 에이전트)

## Related

- [[ai-market-pulse]] — 시장 관전 living doc (분리 트랙)
- [[Agentic Engineering]] — 멀티 에이전트 워크플로 사상
- [[Claude]] · [[Codex]] · [[ChatGPT]] — 본인 도구 풀
- [[Anthropic]] · [[OpenAI]] — 제조사
- [[Vibe Coding]] — 회피 사상 (검증 없는 도구 사용)
- [[LLM Wiki]] — 외부화 사상 (본 비교 자체가 외부화)
