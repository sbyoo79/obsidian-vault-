---
type: source
status: active
format: article
author: "[[Ahmed Hafdi]]"
translator: "[[Yuna]]"
publisher: "[[YozmIT]]"
url: https://yozm.wishket.com/magazine/detail/3746/
original_url: https://medium.com/@ahmed.hafdi/vibe-coding-is-over-what-comes-next-is-much-harder
original_title: "Vibe Coding Is Over. What Comes Next Is Much Harder."
language: ko
published: 2026-05-08
tags: [vibe-coding, ai-coding, code-review, security, llm-tools, engineering]
created: 2026-05-18
updated: 2026-05-18
---

# 바이브 코딩의 진짜 시작은 이제부터다

[[Ahmed Hafdi]] 의 Medium 글 "Vibe Coding Is Over. What Comes Next Is Much Harder." 의 [[YozmIT]] 번역본. AI 코딩 도구가 단기간에 끌어올린 속도의 대가로 보안과 품질을 크게 훼손했고, **이제는 거대한 프롬프트 한 방이 아니라 작게 쪼개고 검증하는 시대로 돌아간다** 는 주장.

## 핵심 논지

"바이브 코딩 끝났다" 는 도발적 제목이지만 본질은 명확하다.

> 거대한 프롬프트 하나로 밀어붙이던 시대는 끝났다. 이제는 작업을 잘게 쪼개 설계하고 각 단계를 검증하는 시대다.

[[Andrej Karpathy]] 가 2025 년 2 월 명명한 [[Vibe Coding]] — "AI 가 생성한 코드를 검토 없이 그대로 받아들이는 개발 방식" — 은 빠른 데모에는 좋았지만 프로덕션에서는 무너지고 있다.

## 보안·품질 실측 데이터

| 출처 | 수치 |
|------|------|
| GitHub 분석 | AI 공동 작성 코드의 보안 취약점 = 사람 코드의 **2.74 배** |
| Lovable 플랫폼 (1,645 개 앱 조사) | **10 %+** 가 Row-Level Security 결함 (CVE-2025-48757) |
| Tenzai 테스트 (5 개 주요 도구 × 15 개 앱) | **69 개 취약점** |

빠른 코드는 더 자주 깨진다 — 통계로 확인된 사실.

## Simon Willison 의 정의 (인용)

> [[Simon Willison]]: LLM 이 모든 코드를 썼어도 **전부 리뷰·테스트·이해했다면** 바이브 코딩이 아니라 "타이핑 도우미 활용" 이다.

즉 바이브 코딩의 핵심은 **검증 없이** 받아들이는 것이지 "AI 가 코드를 썼다" 자체가 아니다. 의미를 명확히 다시 박는 인용.

## 새로운 엔지니어 가치

- "가장 많은 줄을 짜는 사람" → **AI 를 지휘하고 결과물을 평가할 수 있는 사람**
- 필수 역량: 아키텍처 판단력 / 보안 직관 / 복잡한 시스템의 분해 능력
- [[Agentic Engineering]] 흐름과 정확히 같은 메시지: 도구가 아닌 **기준** 이 가치를 만든다

## 언급된 도구

[[Cursor]] / [[Lovable]] / [[Bolt]] / [[Replit]] / [[Devin]] / [[Claude]] Code / GitHub / Snyk / Semgrep

## 본 vault 와의 연결

- 본 글의 핵심 주장은 [[Agentic Engineering]] 의 "독립 검증 루프" 와 동일 사상. **에이전트에게 채점을 재위임하지 않는다** 가 보안 문제로 실측된 사례.
- [[Andrej Karpathy]] 가 vibe coding 을 명명했고, 같은 인물이 [[LLM Wiki]] 도 제안했다 — **명시적 외부화·검증 가능** 이라는 공통 사상. 본 vault 가 그 흐름에 있다.
- 본 vault 의 작업 룰(선행 분석 → 티켓 → 브랜치 → 본 작업) 도 같은 사상의 회사 워크플로 버전. 검증 루프가 룰에 박혀 있다.
- "거대한 프롬프트 한 방" 의 반대 = vault 의 ingest sub-패턴 (sources → entities → notes 분리) 도 같은 결의 작게 쪼개기.

## Related

- [[Ahmed Hafdi]] (원저자)
- [[Yuna]] (번역가)
- [[YozmIT]]
- [[Vibe Coding]]
- [[Andrej Karpathy]] (명명자)
- [[Simon Willison]] (인용)
- [[Cursor]]
- [[Claude]]
- [[Agentic Engineering]] — 동일 사상
- [[LLM Wiki]] — 동일 사상 (Karpathy 제안)
