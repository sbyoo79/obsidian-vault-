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
>
> 모델이 바뀌면 또 어떻게 생각이 바뀔지는 모르겠네. — 본인 발화 (2026-05-22, 운영 원칙 3 의 살아있는 표명)

## 운영 원칙

1. **실측만 기록** — 안 써본 도구는 "미검증" 으로 명시. 일반론·벤치마크·언론 평가는 별도 source 로 분리 (`sources/`)
2. **[[ai-market-pulse]] 와 분리** — 시장 관전 (자금력·평가·인재 이동) 과 도구 실측 (본인 작업에서의 성능) 은 별개 트랙. 그 노트의 운영 원칙 그대로 적용
3. **버전·시점 기록** — 평가는 시점에 묶인다. 도구 업데이트 시 기존 평가는 지우지 않고 시점 표시 후 새 평가 추가
4. **단순 요약 아님** — 본인 해석·왜 그렇게 느꼈는지 근거 누적 ([[feedback_curate_with_own_thinking]])

## 도구 풀의 다른 축: IDE

LLM 도구 비교가 본인 전체 dev stack 의 **일부 레이어** 라는 점을 잊지 않기 위해 명시.

| 레이어 | 도구 | 역할 |
|--------|------|------|
| **IDE** | [[IntelliJ]] | 코드 편집·실행·디버깅·리팩터링의 베이스. **LLM 시대에도 막강** (본인 평가) |
| **LLM 보조** | [[Claude Code]] / [[Codex]] / [[ChatGPT]] | 코드 생성·리뷰·문서화 |

**본인 입장**: IDE 와 LLM 도구를 **레이어로 분리 운영**. [[Cursor]] · [[Antigravity]] 같은 IDE+LLM 통합 시도와는 다른 선택 — 분리해야 각 도구의 강점·약점을 따로 평가할 수 있고, 한쪽이 망가져도 다른 쪽 워크플로가 살아남는다. 이 선택의 근거가 [[Antigravity]] 2.0 강제 전환 잡음 같은 사례로 강화됨.

리팩터링·구조 변경 영역에서는 IntelliJ 가 LLM 보다 빠르고 안정적인 경우 많다. 코드 작성·리뷰·문서화는 LLM 도구가 우세. 두 레이어가 서로 대체재가 아니라 **보완재**.

## 본인 실측 비교 (2026-05 시점)

| 도구 | 강점 (본인 실측) | 약점 / 미검증 |
|------|-----------------|--------------|
| [[Claude Code]] | 문서 작성 우세 — 인계 가능 상태 유지에 강함 | 레거시 분석 깊이 ([[Codex]] 대비) |
| [[Codex]] | 레거시 분석력 — 오래된 코드 맥락 파악 우세 | 문서 일관성 ([[Claude]] 대비) |
| [[ChatGPT]] | 설계·아이디어 발산 단계에 적합 | 구현·리뷰는 다른 도구로 위임 |
| [[Gemini]] | (미검증) | 본인 실사용 안 됨. Google 자금력이 도구 우위로 실제 이어졌는지 미확인 |
| [[Antigravity]] (Google 코딩 IDE) | (미검증) | 2.0 강제 전환 잡음 보도 ([[yozm-google-io-2026-gemini-eats-google]]). 직접 검증 시점 아직 없음 |

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

**외부 정보 누적 (2026-05, [[yozm-google-io-2026-gemini-eats-google]])**:
- Gemini 3.5 Flash: Terminal-Bench 2.1 **76.2%** (vs GPT-5.5 78.2%)
- 도구 선택·멀티모달 업계 최상위 평가
- 토큰 가격 **3 배 인상** (Pro 대비 25% 저렴)
- 고객 사례: 다른 최상위 모델 80% 작업 이전 → 연 $10억+ 절감
- 본인 해석: 가격·성능만 보면 진입 검토 가치 있음. 다만 본인 작업 ([[Claude Code]] + [[Codex]] 검증 루프) 의 일관성을 깨면서까지 들여올 이유는 아직 없음. **검증 실험 시점은 본인 워크플로에 빈틈 발견 시**.

### Claude Code 측 외부 정보 (2026-05, [[yozm-codex-vs-claude-code]])

본인 만성 토큰 부족 사례에 대한 객관 데이터 뒷받침 + Codex 의 기능 추격 정보.

**Opus 4.7 측 사고들**:
- **토크나이저 변경** — 같은 텍스트를 1.20 ~ 1.47 배 더 많은 토큰으로 변환 (Vellum, MindStudio). 본인 만성 토큰 부족이 본인만의 문제가 아닌 모델 측 변경 결과
- **성능 저하 측정** (Stella Laurenzo / AMD, 6,852 세션 분석): 사고 깊이 중앙값 67 % 하락, 파일 읽기 6.6 → 2.0
- **벤치마크는 여전히 우세** — SWE-bench Pro 64.3 % (vs GPT-5.4 57.7 %), SWE-bench Verified 87.6 % (vs 74.9 %)

**Codex 측 추격**:
- `/goal` 워크플로우, `/hooks` 브라우저, Vim 모드, remote-control, AWS Bedrock 등 빠른 기능 추가
- 커뮤니티 65 % 가 일상 코딩에서 [[Codex]] 선호

**작업 유형별 우세** (덕파 framing):
- [[Codex]] 우세: 일상 코딩 / 구조적 수정 / PR 리뷰
- [[Claude Code]] 우세: 장기 리팩터링 (8 시간+) / 테스트 작성 / UI·디자인

본인 매트릭스 vs 기사 매트릭스 cross-check:
- 본인 "[[Claude Code]] = 문서 작성 우세" + 기사 "장기 리팩터링·테스트·UI" = 둘 다 **긴 호흡 + 정합성** 결로 일치
- 본인 "[[Codex]] = 레거시 분석력" + 기사 "일상·구조적 코딩·PR 리뷰" = 둘 다 **구조적 코드 파악** 결로 일치

본인 해석: 본인 실측이 외부 데이터로 1 차 검증됨. [[Codex]] 구현 / [[Claude]] 리뷰 의 현 워크플로는 두 도구의 결을 정확히 활용하는 구조. 변경 불필요.

### Antigravity — 미검증, UX 안정성 사례
- [[Google]] 의 코딩 IDE. 2026-05 I/O 에서 2.0 발표
- 사용자 반응: "이전 버전으로 돌아가는 방법" 검색이 1 위 — 에이전트 중심 강제 전환 불만 ([[yozm-google-io-2026-gemini-eats-google]])
- 본인 해석: **UX 안정성 = 새로운 평가 축**. 본인이 [[Claude Code]] · [[Codex]] 를 계속 쓰는 이유 중 하나가 두 도구의 메이저 버전업 시에도 워크플로가 깨지지 않는 점. Antigravity 사례는 그 안정성이 당연하지 않다는 반례.

## 누적 사용 사례

(향후 작업에서 어느 도구가 결정적이었는지 한 줄씩 누적)

- 2026-05-22 [[yozm-karpathy-anthropic-join]] ingest — Claude Code 단독 작업. 외부 자료 fetch + vault schema 따라 다중 entity 신설·갱신 / git 동기화 일관성 유지. 도구 적합 (문서·구조 작업).
- 2026-05-22 [[yozm-google-io-2026-gemini-eats-google]] ingest — Claude Code 단독 작업. 6 개 신규 entity + 2 개 living doc 갱신 + cross-ref 일관성 유지. 도구 적합 재확인 (다중 파일 동시 작업 + 기존 노트 정합성 갱신).

## 평가 축

| 축 | 본인 기준 | 참고 사례 |
|----|---------|----------|
| **성능 (작업별)** | 본인 실측 작업의 결과 품질 | Claude=문서 / Codex=레거시 |
| **UX 안정성** | 메이저 버전업 시 워크플로가 깨지는가 | [[Antigravity]] 2.0 강제 전환 불만 (반례) |
| **가격 인상 추세** | 본인 워크플로 비용 영향 | Gemini Flash 3 배 인상 ([[yozm-google-io-2026-gemini-eats-google]]). **본인 실제 통증**: 최신 모델 쓰느라 만성 토큰 부족 (2026-05) |
| **생태계 통합** | 본인 도구 풀과 협업 가능한가 | (관찰 중) |

## 재평가 트리거

다음 상황에서 본 비교 매트릭스를 재검토:

- Claude 또는 Codex 의 메이저 버전업
- Gemini 본격 사용 시점 (미검증 → 검증으로 전환)
- 회사 멀티 에이전트 워크플로 (역할 배치) 가 실측과 어긋나기 시작할 때
- 새 도구 진입 (예: Anthropic 외 회사의 신규 CLI 에이전트)
- 본인 도구 (Claude / Codex) 가격 인상 발표

## Related

- [[ai-market-pulse]] — 시장 관전 living doc (분리 트랙)
- [[Agentic Engineering]] — 멀티 에이전트 워크플로 사상
- [[Claude]] · [[Codex]] · [[ChatGPT]] — 본인 도구 풀
- [[Anthropic]] · [[OpenAI]] · [[Google]] — 제조사
- [[Gemini]] · [[Antigravity]] — Google 도구 (미검증)
- [[IntelliJ]] — IDE 레이어, 도구 풀의 다른 축
- [[Vibe Coding]] — 회피 사상 (검증 없는 도구 사용)
- [[LLM Wiki]] — 외부화 사상 (본 비교 자체가 외부화)
