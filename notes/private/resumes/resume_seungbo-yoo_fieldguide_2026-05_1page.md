<!-- Customized for Fieldguide — Software Engineer (Korea). 2026-05-18. English, 1-page. -->

# Seungbo Yoo

Backend Engineering Lead · Seoul Metro Area, South Korea
sbyoo79@gmail.com · +82 10-2843-2239

---

## Summary

Backend engineer with 21 years of experience in B2B SaaS, leading the modernization of document-heavy and multi-tenant systems. Owned the 0→1 design of an ERP SaaS backend, then returned 7–9 years later to lead its modernization at the successor company — an unusually long feedback loop for a single engineer. Currently operating an AI-augmented engineering practice (multi-agent role separation across GPT / Codex / Claude with verification loops and documentation), not vibe coding.

---

## Why Fieldguide

- **ML-driven document understanding (preferred)** → Daily practitioner of AI-augmented engineering; built ad platform and data warehouse end-to-end in one week each, fully documented for handoff
- **Documentation-heavy workflows (preferred)** → Personal vault + company knowledge base operated as living documentation, treated as a first-class deliverable
- **B2B SaaS domain** → LeadPlanet (ERP SaaS, current), MAXVISOR (Franchise SaaS, founding designer), Tmon and Ktown4u (commerce)
- **Korea team build phase** → 0→1 design and team-leadership experience across three companies

---

## Selected Experience

### LeadPlanet — Team Lead, Backend (Dec 2024 – Present)
Multi-tenant ERP SaaS for franchise operators. Leading the AI and Data Analytics backend team (renamed from Office Development team in Jun 2026; scope and headcount unchanged).

- Consolidated a per-tenant deployment topology into a single multi-tenant application: **~200 instances at 256–512 GB / 90%+ memory → one instance at 128 GB / 10–15%**, cutting infrastructure cost significantly.
- Upgraded **Java 1.8 + Spring Boot 1.4.2 → Java 17 + Spring Boot 2.7.18** across a ~250K-LOC / ~2,000-file codebase; migrating toward Java 21 + Boot 3.5.
- Re-architected bulk file ingestion into **Python parser microservice + MQ + worker** with Outbox pattern, removing the main system from the failure path and enabling replay.
- Built an internal data warehouse (Python + FastAPI) and an in-product ad platform (Spring Boot, Java 21) **end-to-end in roughly one week each** using a multi-agent AI workflow (GPT design / Codex implementation / Claude review); ad platform currently serves **12K–15K impressions/day** in production.

### Tmon — Team Lead, Service Development (Aug 2020 – Jun 2023)
Backend lead across common service areas (deal detail, GNB, category, automated storefront).

- Led a team of up to 13 backend engineers (later 8 after reorganization), running planning, mentoring, and cross-team alignment.
- Designed and shipped **incremental ES indexing for an automated storefront** over a catalog of ~100M items (previously 3-hour full reindex), dramatically reducing operational load.
- Drove the **product DB migration and SKU restructuring** for ~5M products, including downstream join and API cleanup.

### MAXVISOR — Backend Engineer (Nov 2016 – Jul 2019)
Founding backend designer for a Franchise B2B SaaS. **This is the predecessor system that I am now modernizing at LeadPlanet** — the same person owns the 0→1 design *and* the long-arc consequences.

- Defined the backend stack and architecture from scratch; built REST APIs, batch jobs, ELK-based observability, and the build/deploy automation pipeline.
- Implemented external integrations (POS vendors KICC / Smartro / Metacity, Kiwoom virtual accounts) and the franchise ordering subsystem (Spring Boot + Vue.js).

*(Earlier roles: Loen / Melon, SK Communications / Cyworld, Wiz, NeoMtel — full history available in the long-form CV.)*

---

## Technical Skills

5-level self-assessment: 1 heard of / 2 with a guide / 3 hands-on / 4 deep + troubleshooting / 5 expert.

- **Languages**: Java **4** · TypeScript / JavaScript 3 / 3 · Node.js 3 · Python 3 · C# 3 · PHP 3
- **Frameworks**: Spring / Spring Boot **4** · React 3 · GraphQL 3 · FastAPI / Flask 3 · JPA 3 · Hasura 1 (short learning curve on Postgres + GraphQL)
- **Data / Infra**: **DB design + tuning 4** · MySQL 4 (Postgres learnable) · AWS (EC2 / Lambda / RDS / S3) 3 · Docker 3 · CI/CD 3 · RabbitMQ / SQS 3 · Redis / ES / CouchBase 3
- **AI-augmented engineering**: Multi-agent workflow (GPT / Codex / Claude), context engineering, verification loops, documentation-as-deliverable

---

## Education

- **M.S., Information & Communication Engineering** — Soonchunhyang University, 2002–2004 · GPA 4.02 / 4.5
- **B.S., Information & Communication Engineering** — Soonchunhyang University, 1998–2002 · GPA 3.2 / 4.5
