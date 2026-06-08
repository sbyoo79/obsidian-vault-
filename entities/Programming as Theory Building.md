---
type: entity
status: active
category: concept
tags: [software-engineering, mental-model, knowledge-work, ai-coding, theory, naur]
aliases: [Theory Building, 프로그래밍은 이론 구축, Naur 1985]
proposed_by: "[[Peter Naur]]"
year_proposed: 1985
created: 2026-06-01
updated: 2026-06-08
---

# Programming as Theory Building

[[Peter Naur]] 가 1985 년 발표한 에세이 *"Programming as Theory Building"* 의 핵심 주장. **프로그래밍의 본질은 코드 생산이 아니라 "이론(theory) 의 구축"** 이라는 통찰.

## 개요

"이론" 은 단순히 무엇이 참인지 아는 것이 아니라:
1. **왜 그렇게 했는지 설명할 수 있고**
2. **새로운 요구에 맞춰 고칠 수 있는** 지식

코드·문서·테스트는 이론의 산물(artifact) 일 뿐, 이론 자체는 **개발자의 머릿속에 산다.** 같은 코드라도 이론을 가진 사람과 못 가진 사람에게 의미가 완전히 다르다.

길버트 라일 (Gilbert Ryle) 의 *knowing-how vs knowing-that* 구분과 결이 같다 — 코드는 knowing-that (사실), 이론은 knowing-how (할 줄 앎).

## 본 vault 에서의 의미

40 년 전 통찰이 [[AI Agent]] 코드 자동 생성 시대에 정확히 다시 떠오른다. AI 가 코드를 만들 때 **이론은 누가 보유하는가** 가 핵심 질문:

- **이론 없는 코드 = 즉시 레거시 부채.** AI 가 만든 코드를 검토 없이 받아들이면 누구도 "왜 이렇게 짰는지" 설명 못 함 → 첫 요구 변경에서 무너짐
- 본인 [[Agentic Engineering]] 워크플로 (Codex 구현 → Claude 리뷰 → 본인 docs) 의 docs 단계가 이론을 외부화·재구축하는 메커니즘
- [[Eval]] 의 출력 검증 → 이론 재구축의 일부 형태 (왜 이 출력이 옳은가를 다른 에이전트가 reasoning)
- [[Vibe Coding]] 안티패턴 = "이론 구축 단계 생략" 의 다른 이름

21 년차 시니어 입장에서: AI 가 생산성 격차를 메워주는 게 아니라 오히려 **이론 보유 능력 격차** 를 더 벌릴 가능성. AI 출력을 받아들이며 이론을 재구축할 줄 아는 시니어와, 받아들이고 끝인 주니어의 차이가 임팩트로 직결.

## Key facts

- 발표: 1985, *Microprocessing and Microprogramming* 학술지
- Naur 의 다른 업적: BNF (Backus-Naur Form), ALGOL 60 명세
- 현대적 재조명: AI 코딩 시대 (2023~) 에 다시 광범위하게 인용 [[백명석]] / DHH / GeePawHill 등
- 함의: 코드베이스 인수인계 = 이론 인수인계, 단순 파일 전달 X
- 멘탈 모델 (Mental Model) 개념과 사실상 같은 영역

## 관련 sources

- [[brunch-cleancode-ownership-ai-era]] — 백명석, AI 시대 이론 보유의 의미 재조명
- [[brunch-cleancode-ai-no-silver-bullet]] — 백명석 후속, 검증 = 멘탈 모델 구축 = 이론 재구축으로 재명시. **인지적 부채** 라는 새 framing 도입
- [[yozm-vibe-coding-real-start]] — Vibe Coding 한계 비판도 같은 결

## 관련 entities

- [[Peter Naur]] — 원안 저자
- [[Vibe Coding]] — 이론 없는 코드의 대표 안티패턴
- [[Eval]], [[Agentic Engineering]] — 이론 재구축의 실무 메커니즘
- [[Hallucination]] — 이론 없이 받아들였을 때의 위험
- [[Context Engineering]] — 입력 측 이론 관리
