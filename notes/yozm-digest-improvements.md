---
type: note
status: active
tags: [improvement, yozm, digest, backlog]
aliases: [yozm 디지스트 개선 백로그]
created: 2026-05-18
updated: 2026-05-18
---

# Yozm Daily Digest — 개선 백로그

`common/sh/yozm-daily-digest.py` 의 첫 실행(2026-05-18) 에서 발견된 이슈와 다음 개선 후보 정리. 이번 주(05-18~05-24) 운영 후 05-25 경 일괄 손볼 예정.

## 1. Title 오염 (Bug)

**증상**: 글 #9 (id 2064) 의 title 이 본문 일부 ("HTTP로 요청을 보냈을 때 서버에서는...") 로 채워짐.

**원인 추정**: list 페이지의 메인 카드 외 영역 (인기글/추천글/관련글) 의 anchor text 가 길게 들어와서 selector 가 잡음.

**개선 방향**:
- title 길이 cap (예: 100 자) 후 제외
- 메인 카드 영역 selector 한정 (예: `section.recent` 또는 `div.magazine-card` 등 실제 구조 확인 후)
- HTML 직접 다운로드 → 구조 확인 → 정밀 selector 작성

## 2. Detail 페이지 본문 추출 불안정 (Bug)

**증상**: 일부 글 요약이 "본문 내용이 충분하지 않아 정확한 요약이 어렵습니다" 메타 응답.

**원인 추정**: yozm detail 페이지가 SPA (JS 로 본문 렌더링) — `requests` 로 받은 HTML 에 본문 텍스트가 비어있음.

**검증 방법**:
```bash
curl -s -A "Mozilla/5.0" https://yozm.wishket.com/magazine/detail/3744/ | grep -c "스프링 부트"
```
0 이면 SPA, > 0 이면 SSR.

**개선 방향**:
- SSR 이면: selector 정확성 문제 → CSS 셀렉터 재확인 (`article.magazine-body` 등)
- SPA 이면: 본문 fetch 를 [[Claude]] WebFetch 패턴(headless browser)으로 전환하거나 메타 description 만으로 만족
- 또는 yozm 공식 메타 (og:description) 활용

## 3. Preview 길이 / 요약 정확도 (Quality)

**증상**: "11명의 바이브 코더" 가 "AI 도구"로 오해됨.

**원인**: preview 가 800 자라 짧고, "바이브 코더" 같은 신조어를 모델이 잘못 추론.

**개선 방향**:
- preview 1500~2000 자로 늘림
- 또는 yozm 의 og:description / 메타 태그 그대로 사용
- prompt 에 "제목의 비유적 표현 주의" 한 줄 추가

## 4. 이미 ingest 된 글 노출 정책 (Decision)

**현재**: 디지스트 본문에 ingest 된 글도 포함 + 마킹.

**대안**:
- A. 그대로 (현재) — context 유지, 그러나 신규 글 식별이 번거로움
- B. 별도 섹션으로 분리 ("이미 ingest 된 글" 섹션 끝에)
- C. 디지스트에서 완전 제외 — frontmatter 카운터에만 표시

**선호**: B (분리). 사용자가 신규 글만 빠르게 훑고, ingest 이력은 끝에서 확인.

## 5. 카테고리 / 키워드 필터 (Feature)

현재는 list 페이지 상위 10 개를 그대로 보여줌. 운영해 보고:

- 자주 무시되는 카테고리 (예: "디자인" 일부) 가 있으면 필터 옵션 추가
- 또는 키워드 화이트리스트 (AI / 에이전트 / Claude / 백엔드 등) 적용

## 6. 다이제스트 retention (housekeeping)

매일 한 파일이 쌓이면 1 년 후 365 개. graph 가 부담될 수 있음:

- A. 30 일 지나면 `meta/digests/archive/` 로 이동
- B. 월별로 통합 디지스트 작성 후 일별 삭제
- C. 그대로 두기 (가장 단순)

운영 1~2 달 후 다시 판단.

## 7. cron 안정성 (Infra)

WSL crontab 의존성:
- WSL 인스턴스 항상 켜져 있어야 cron 동작
- Windows 가 잠자기 모드면 멈춤

옵션 비교:
- **A. WSL crontab** (현재 안내안) — 단순, WSL 켜진 상태에서만
- **B. Windows Task Scheduler → wsl 명령 호출** — PC 부팅 후 자동 실행 가능, 설정 한 번 더 복잡
- **C. systemd timer (WSL 내부)** — 최신 WSL2 systemd 활성화 시 사용 가능

운영 안정성 봐서 결정.

## 8. 디지스트와 vault graph 통합

`type: meta` 인 디지스트가 graph 에서 entity / source 와 어떻게 연결되어 보일지 점검:
- 이미 ingest 된 글은 `[[...]]` 로 backlink 가 자동 잡힘 → OK
- 신규 글은 아직 entity 가 없으므로 grpah 에 단발 노드

추가 검토: 신규 글 URL 만이라도 자리표시 entity 로 만들지? 너무 ingest 부담일 듯. 일단 보류.

## 갱신 이력

- 2026-05-18: 첫 실행 후 백로그 초안 작성
