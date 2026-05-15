---
type: entity
status: active
category: tool
tags: [tool, markdown, pkm, app, notes]
aliases: [Obsidian.md]
url: https://obsidian.md
vendor: Obsidian
license: freemium
platform: [macOS, Windows, Linux, iOS, Android]
created: 2026-05-14
updated: 2026-05-14
---

# Obsidian

로컬 markdown 파일 기반 PKM 앱. `[[wiki link]]` 와 graph view 가 핵심 식별자.

## 개요

Dynalist 를 만든 Shida Li / Erica Xu 가 2020 년에 출시했다. 데이터는 평범한 markdown 파일로 사용자의 로컬 디스크에 저장된다. 그 결과 vendor lock-in 이 거의 없고, 다른 도구 (vim, VS Code, Claude Code 등) 가 같은 파일을 함께 다루기 쉽다.

bidirectional link, backlink, graph view, canvas, daily note, template, dataview 같은 플러그인 등 PKM 에 필요한 기능이 거의 다 모여 있다. 개인 사용은 무료, 동기화 서비스 `Sync` 와 공개 서비스 `Publish` 는 유료, 그리고 후원 등급 `Catalyst` 가 별도로 있다.

## 본 vault 에서의 의미

[[LLM Wiki]] 패턴의 **browser / editor** 역할. Claude Code 는 WSL 측에서 file system 으로 직접 read/write 하고, Obsidian 은 사람이 vault 를 시각적으로 탐색·편집하는 GUI 역할을 한다. graph view 로 entity 간 연결을 빠르게 점검할 수 있어 LLM 이 만든 cross-ref 의 품질을 사람이 한눈에 검증하기 좋다.

## Key facts

- 출시: 2020
- 제작: Shida Li, Erica Xu (Dynalist 출신)
- 저장 형식: 로컬 markdown — vendor lock-in 없음
- 핵심 기능: `[[wiki link]]`, backlink, graph view
- 무료 (개인), 유료: Sync / Publish / Catalyst
- 플랫폼: macOS / Windows / Linux / iOS / Android

## 핵심 기능

- **Bidirectional `[[...]]`** — 양방향 링크와 backlink panel
- **Graph view** — 페이지를 노드로 시각화
- **Canvas** — 자유 배치 보드
- **Daily notes / Templates** — 반복 노트 자동화
- **Plugin 생태계** — core + community plugin 다수 (`obsidian-git`, `dataview`, `templater`, ...)

## 이 vault 에서의 사용

- 브라우저 역할 (편집은 Claude Code 가 더 자주 함)
- graph view 로 ingest 직후 연결 품질 검증
- 설치 plugin: `obsidian-git` (현재 비활성 — WSL git 으로 동기화), `mermaid-tools`

## 관련 sources

- [[karpathy-llm-wiki]] — LLM Wiki 의 browser 로 Obsidian 언급

## 관련 entities

- [[LLM Wiki]] — 본 vault 가 채택한 패턴
- [[Andrej Karpathy]] — LLM Wiki 제안자
