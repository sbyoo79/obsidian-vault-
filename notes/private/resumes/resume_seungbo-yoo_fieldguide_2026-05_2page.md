<!-- Customized for Fieldguide — Software Engineer (Korea). 2026-05-18. English, 2-page (senior full version). -->

# Seungbo Yoo

Backend Engineering Lead · Seoul Metro Area, South Korea
sbyoo79@gmail.com · +82 10-2843-2239

---

## Summary

Backend engineer with **21 years** of experience in B2B SaaS and commerce platforms, with a track record of leading the modernization of document-heavy and multi-tenant systems. Founded the backend of a Franchise ERP SaaS in 2016 and — 7–9 years later — returned to lead its modernization at the successor company, an unusually long feedback loop on a single engineer's own design decisions. Currently operating an **AI-augmented engineering** practice (multi-agent role separation across GPT / Codex / Claude with verification loops and documentation-as-deliverable) — explicitly the opposite of vibe coding.

---

## Why Fieldguide

| Fieldguide signal | Match |
|---|---|
| **ML-driven document understanding** (preferred) | Daily practitioner of AI-augmented engineering — multi-agent workflow with verification and documentation |
| **Documentation-heavy workflows** (preferred) | Personal vault + company knowledge base operated as living documentation; "handoff-ready" is an explicit deliverable |
| **B2B SaaS domain** (preferred) | LeadPlanet (ERP SaaS, current) + MAXVISOR (Franchise SaaS, founding designer) + Tmon / Ktown4u (commerce) |
| Korea team build phase | 0→1 design and team-leadership experience across three companies |
| TypeScript / React / Node.js / Python / GraphQL / AWS | Hands-on at production level |
| Postgres | Strong MySQL background (DB design + tuning level 4) — short learning curve |

---

## Differentiators

1. **0→1 + long-arc ownership** — Designed and built MAXVISOR's B2B SaaS backend from scratch (2016–2019), then returned to LeadPlanet to lead the modernization of *the same system* (2024–present). The same person owns the architectural decisions and their multi-year consequences.
2. **Risky migrations done safely** — Java 1.8 → 17 (Spring Boot 1.4.2 → 2.7.18) across 250K LOC, ASP → .NET → Java rewrites at Cyworld, Windows storage → Linux conversion at **3.2 PB / 3.2M file metadata / 300 storage servers**.
3. **AI-augmented engineering as a paradigm, not a tool** — Multi-agent role separation (GPT for design and documentation, Codex for implementation, Claude for review), context engineering, explicit verification loops. Two production systems shipped end-to-end in roughly one week each using this workflow.
4. **Team leadership track record** — Lead / squad lead at Tmon (up to 13 engineers), Ktown4u (squad of 4), and LeadPlanet.

---

## Experience

### LeadPlanet — Team Lead, Backend (Dec 2024 – Present)
Multi-tenant ERP SaaS for franchise operators. Leading the office-development backend team.

- Lead **multi-tenant backend system design and operations** across many tenant organizations.
- Build aggregation, reconciliation, and audit-adjacent processes for revenue, settlement, and logistics data.
- Drive a gradual rewrite from a misapplied layered architecture into **Vertical Slice Architecture (VSA)** for domain cohesion.

**Project — Legacy modernization (Jan 2025 – present).** This is the predecessor of MAXVISOR (which I founded in 2016) — the same system, same person, returning to address its accumulated debt.

- **Codebase scope**: ~2,000 Java files, ~250K LOC.
- Consolidated a per-tenant deployment topology into a single multi-tenant application: **~200 instances at 256–512 GB / 90%+ memory → one instance at 128 GB / 10–15% memory**, cutting infrastructure cost significantly.
- Migrated self-hosted file storage to S3, relieving disk pressure.
- Upgraded **Java 1.8 + Spring Boot 1.4.2 → Java 17 + Spring Boot 2.7.18**; final target is Java 21 + Boot 3.5+.
- Maintained handoff-ready documentation throughout, with analysis and plan documents kept inside the project repository.
- **Tech**: MySQL, Java 17, Spring Boot, Claude CLI / Codex / IntelliJ / ChatGPT.

**Project — Ad platform (Mar 2026, one-week build).**

- Built an MVP banner ad platform inside LeadUS (the franchise ordering app), end-to-end in one week.
- **AI-only delivery**: design + documentation with GPT, implementation with Codex, review with Claude.
- Currently serves **12K–15K impressions/day** in production with stable impression/click ingestion.
- **Tech**: MySQL, Java 21, Spring Boot.

**Project — Data warehouse (Mar 2026, one-week build).**

- Consolidated revenue data from third-party logistics, POS, and in-house ordering into a unified warehouse.
- Built POS and logistics aggregation up to a gold layer; validated reporting via Claude integration.
- Same multi-agent AI workflow as above; one-week delivery with thorough documentation.
- **Tech**: MySQL, Python, FastAPI.

**Operational improvements.**

- Re-architected bulk file ingestion into **Python parser microservice + MQ + worker**, decoupling the main system and enabling replay on failure.
- Introduced **Outbox pattern** for cross-service messaging to prevent data loss and enable retries and state tracking.
- Tuned DB connections and batch concurrency to remove multi-tenant bottlenecks.

---

### Ktown4u — Manager, Backend (Jul 2023 – Dec 2024)
Squad lead for the back-office team (4 backend engineers) at a global K-culture commerce platform.

- Led back-office squad — execution + work distribution + cross-functional coordination.
- Shipped new back-office features and operational fixes; handled CS-driven data corrections at **multi-million-record scale** (event data uploads, order corrections).
- Contributed to the **SKU / catalog restructuring** initiative (separation of logistics SKU from display product), including AS-IS analysis and migration planning.
- **Tech**: Linux, MySQL, Redis, ES, CouchBase, Python 3.7, Java 21, Spring Boot, React-Redux.

---

### Tmon — Team Lead, Service Development (Aug 2020 – Jun 2023)
Backend lead across common service areas — deal detail, GNB, category, automated storefront, microsites.

- Managed a team of up to 13 engineers (later 8 after the post-acquisition reorganization), running 1-on-1s, mentoring, planning, and cross-team alignment.
- Owned the full stack across the common service area including legacy PHP zones.

**Project — Incremental ES indexing for automated storefront (Apr 2023).**

- Catalog of ~100M items previously required a 3-hour full reindex; designed and shipped incremental indexing to spread the load and reduce operational risk.
- **Tech**: MySQL, Redis, ES, Java 8, Spring Batch.

**Project — Product DB migration + SKU restructuring (Oct 2020 – ongoing).**

- ~5M products migrated and restructured; followed by API and join-path cleanup across affected domains.
- **Tech**: MySQL, Redis, ES, Python 3.7, Java 8, Spring / Spring Boot.

**Projects — Brand Home (2022), Subscription service (2021–2022).**

- Participated in initial design, scheduling, and cross-team alignment; built parts of the PHP-based legacy area (Mighty-Tmon).

---

### Influential (Welaaa) — Senior Backend Engineer (Nov 2019 – Jun 2020)

- Operated the Welaaa audiobook service on AWS; led backend, batch, and external-integration work.
- Built **Samsung Bixby integration** for Welaaa using OAuth 2.0 for member linking.
- Shipped the **Samsung Galaxy A-series promotion module** including device-check.
- **Tech**: AWS EC2 + Lambda + RDS, MySQL 5.7, Python 3.7, Flask.

---

### MAXVISOR — Backend Engineer (Nov 2016 – Jul 2019)

> **0→1 ownership.** This is the predecessor system I am now modernizing at LeadPlanet — the same person owns the original architecture and its long-term consequences.

- Defined the backend technology stack and overall architecture from scratch for a Franchise B2B SaaS.
- Built the main system: Spring Boot + JPA + Spring Batch + Spring Security + ELK Stack.
- Built the franchise ordering subsystem (Spring Boot + Vue.js).
- Built external integrations: POS vendors (KICC / Smartro / Metacity) and Kiwoom virtual accounts.
- Set up **end-to-end automation from build to customer deployment**.
- **Tech**: CentOS 7, Nginx, MySQL 5.7, Java 8, Spring Boot 2.0.1, JPA, Spring Batch, Spring Security, ELK Stack, Vue.js.

---

### Loen Entertainment (Melon) — Project Lead, Ticket Team (Nov 2014 – Oct 2016)

- Built the **Melon Ticket global booking site** — global member system, real-time sales monitoring, payment integration.
- Co-designed the architecture and database for the **Melon Shopping** service; acted as project manager and backend/frontend engineer.
- **Tech**: Linux, Apache + Tomcat, MariaDB / Oracle 10, Java 8, Melon framework (custom Spring 4.0), MemCached, MyBatis.

---

### SK Communications (Cyworld) — Manager, Social Infrastructure (Apr 2011 – Dec 2013)

- Owned Cyworld's member, file, and common-infrastructure systems.
- **Cyworld file system conversion (Windows → Linux)** — **3.2 PB scale, 3.2M file metadata records, 300 Windows storage servers** converted. Major Windows licensing cost reduction.
- Modernized Cyworld common UI from **ASP REST API → .NET MVC**; built the Ilchon RESTful API for the social graph.
- **Tech**: Linux, Resin 3.0, SQLite, Java 5 / C# / .NET, IIS, MS-SQL, MemCached, AMQP.

---

### Earlier roles

- **Wiz Communications** — Backend Engineer (Sep 2009 – Oct 2010). Shipped Android ringtone app for KT, plus WAP services (KT Show widget, SKT / KT YouTube).
- **NeoMtel** — Research Engineer (Nov 2004 – Aug 2009). Built backend / CMS for China Telecom Screen Media service on BREW phones; ran on-site pilot installations.

---

## Technical Skills

5-level self-assessment: 1 heard of / 2 with a guide / 3 hands-on / 4 deep + troubleshooting / 5 expert.

### Languages
Java **4** · TypeScript / JavaScript 3 / 3 · Node.js 3 · Python 3 · C# 3 · PHP 3

### Frameworks & Libraries
Spring / Spring Boot **4** · React 3 · GraphQL 3 · FastAPI / Flask 3 · JPA 3 · Spring Batch 3 · Spring Security 3 · Hasura 1 (short learning curve, runs on Postgres + GraphQL)

### Data & Infrastructure
**DB design + tuning 4** · MySQL 4 (Postgres learnable) · AWS (EC2 / Lambda / RDS / S3) 3 · Docker 3 · CI/CD 3 · RabbitMQ / SQS 3 · Redis 3 · Elasticsearch 3 · CouchBase 3 · Data warehouse / analytics pipelines 3

### AI-augmented Engineering
Multi-agent role separation (GPT / Codex / Claude) · context engineering · verification loops · documentation-as-deliverable · Karpathy-style LLM Wiki pattern applied to personal PKM

---

## Education

| Period | School | Degree / Major | GPA |
|---|---|---|---|
| 2002 – 2004 | Soonchunhyang University | M.S., Information & Communication Engineering | 4.02 / 4.5 |
| 1998 – 2002 | Soonchunhyang University | B.S., Information & Communication Engineering | 3.2 / 4.5 |
