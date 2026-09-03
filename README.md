![header](https://capsule-render.vercel.app/api?type=waving&color=0:0D1117,100:00FFA3&height=200&section=header&text=VazquezDev&fontSize=60&fontColor=ffffff&animation=fadeIn&fontAlignY=35&desc=AI+Systems+Architect+%2F+Developer&descAlignY=55&descSize=20)

<div align="center">

[![Typing SVG](https://readme-typing-svg.demolab.com/?font=JetBrains+Mono&size=21&pause=1000&color=00FFA3&center=true&vCenter=true&width=800&lines=RAG.+AGENTS.+AUTOMATION.;Build+AI+systems+a+CTO+can+trust.;44+tools+in+one+MCP+server%2C+fully+shipped.;Architecture-first.+Production-first.+Shipped+not+demoed.)](https://vazquezdev.pro)

📍 **Barcelona, Spain** (GMT+1) &nbsp;·&nbsp; 🌍 **Remote-first**, available worldwide &nbsp;·&nbsp; 🇪🇺 **EU citizen** — no visa sponsorship &nbsp;·&nbsp; 🗣️ **English** (B2)

![Experience](https://img.shields.io/badge/Production_AI-3%2B_Years-0D1117?style=for-the-badge&labelColor=0D1117&color=00FFA3)

![Architecture-First](https://img.shields.io/badge/Architecture--First-A855F7?style=for-the-badge)
![Production-First](https://img.shields.io/badge/Production--First-A855F7?style=for-the-badge)
![End-to-End Ownership](https://img.shields.io/badge/End--to--End_Ownership-A855F7?style=for-the-badge)
![Team & Delivery](https://img.shields.io/badge/Team_%26_Delivery-A855F7?style=for-the-badge)

</div>

<br>

Below: a voice note that becomes a filled corporate report in seconds, a Qdrant vector database exposed as a full toolset for any MCP client, and a lab notebook built so research data never has to leave a university's own server. Three systems, three different hard problems — all shipped, all public. Scroll past the badges — **the repos do the talking.**

Sole AI engineer at **CSR Online** since March 2026, reporting directly to the co-founder/CTO, owning three production AI systems end-to-end: infrastructure, vector database, backend, deployment. In parallel, I run **VazquezDev**, my own AI architecture practice.

```bash
adrian@vazquezdev:~$ whoami
> AI Systems Architect & Developer

adrian@vazquezdev:~$ cat mission.md
> I design AI that works where it has to work — your servers or the cloud.
> Architecture follows your security and compliance requirements.
> RAG pipelines, autonomous agents, and orchestration flows —
> deployed to production, not stuck in demo mode.

adrian@vazquezdev:~$ _
```

<div align="center">

![Skills](https://skillicons.dev/icons?i=python,fastapi,docker,postgres,redis,vue,nuxt,tailwind,git&theme=dark)

</div>

---

## `$ ls repos/flagship`

ReportAI and Qdrant-MCP are the two deployed case studies on [vazquezdev.pro](https://www.vazquezdev.pro). NotaBene rounds out the public repos — a production-grade platform in its own right. All three: public, read the code.

### 📋 [ReportAI](https://github.com/avaazquezz/ReportAI) · [live →](https://reportai.vazquezlabs.com/)

![Status](https://img.shields.io/badge/Status-Deployed-00FFA3?style=for-the-badge&labelColor=0D1117)

**The pitch:** a field rep sends a 90-second voice note to a Telegram bot. A finished report lands in the right inbox seconds later — filled into **the company's own Word template**, not a generic AI summary.

**The architecture call:** chat-native, zero install — runs on the chat app the team already has open. FastAPI backend, LangGraph orchestrating the agent, Claude doing structured extraction via tool-calling, Groq Whisper transcription, self-hosted Postgres, docxtpl + self-hosted Gotenberg for rendering.

**The hard part:** bring-your-own-template. Every client defines their own document types and field schema from an admin panel — onboarding a new report type is configuration, not a code change.

**Why it matters:** Otter, Fireflies, Fathom, Notion AI Meeting Notes — all of them assume a scheduled video call and output their own generic summary format. Most fieldwork isn't a Zoom call. ReportAI targets the in-person recap and fills the client's actual template.

<br>

### 🔎 [Qdrant-MCP](https://github.com/avaazquezz/Qdrant-MCP) · [live →](https://mcp-qdrant-web.vazquezlabs.com/)

![Status](https://img.shields.io/badge/Status-Deployed-00FFA3?style=for-the-badge&labelColor=0D1117)
![License](https://img.shields.io/badge/License-MIT-00FFA3?style=for-the-badge&labelColor=0D1117)
![Tools](https://img.shields.io/badge/Tools-44_across_6_toolsets-00FFA3?style=for-the-badge&labelColor=0D1117)
![Requires](https://img.shields.io/badge/Requires-Qdrant_v1.19%2B-00FFA3?style=for-the-badge&labelColor=0D1117)

**The gap:** the official Qdrant MCP server ships 2 tools — store and find. This one ships 44, across core CRUD, hybrid/grouped/recommend/discover search, payload & vector editing, snapshots, and full observability (Prometheus metrics, quotas, self-diagnosed issues).

**The architecture call:** toolsets are opt-in — a client isn't handed all 44 tools by default — and a read-only mode strips every mutating tool from the registry entirely, not just from the docs.

**The hard part:** "bring your own Qdrant" mode. It runs as one public deployment with no database of its own — every caller supplies their own instance. That only works if isolation is real, so every request goes through an SSRF guard that rejects private/internal/cloud-metadata addresses and **re-resolves DNS on every call** to defeat rebinding — hands-on verified, not assumed.

**Ships as:** `uvx mcp-qdrant` on PyPI · a Docker image · a one-click Claude Desktop `.mcpb` bundle. Fully typed, strict mypy, ruff, pytest with integration tests against a real Qdrant in CI.

<br>

### 🧬 [NotaBene-App](https://github.com/avaazquezz/NotaBene-App) · [live →](https://www.notabene.click/)

![Status](https://img.shields.io/badge/Status-Deployed-00FFA3?style=for-the-badge&labelColor=0D1117)
![License](https://img.shields.io/badge/License-Proprietary-00FFA3?style=for-the-badge&labelColor=0D1117)
![Deployment](https://img.shields.io/badge/Deployment-Self--Hosted-00FFA3?style=for-the-badge&labelColor=0D1117)
![Languages](https://img.shields.io/badge/Languages-EN_%2F_FR_%2F_ES-00FFA3?style=for-the-badge&labelColor=0D1117)

**The origin:** conceived at the **University of Liège** (Belgium), rebuilt from scratch.

**The architecture call:** fully self-hosted, zero third-party cloud dependency — Postgres, Redis, MinIO, and Traefik, all designed to run on the institution's own infrastructure. GDPR-compliant by design, not by policy document.

**The hard part:** real-time collaboration without polling. Multiple researchers editing the same experiment simultaneously, synced via **WebSocket + Redis pub/sub**, no page reload, no stale state. The backend is async all the way down — FastAPI, SQLAlchemy 2.0, asyncpg, no synchronous I/O blocking the event loop under real concurrent load.

**Also shipped:** 3,612 translation keys across English/French/Spanish (1,204 each), reagent & inventory tracking with automatic low-stock and expiry alerts, animal facility records, an immutable versioned protocol library, per-module team permissions, an idempotent APScheduler alert engine, bcrypt-12 password hashing, 60-minute JWT access tokens with 7-day rotating refresh (DB-backed revocation), an append-only admin audit log, and full network isolation — DB/Redis/MinIO reachable only by the backend container.

<br>

**Also on the side:** [**InakaMoments**](https://github.com/avaazquezz/InakaMoments) · [live →](https://inakamoments.com/) — a freelance build for a balloon and event decoration business in Abrera, Barcelona: public site + SaaS admin panel (`Nuxt 4` `Supabase` `Docker`).

---

## `$ cat career.log`

| Period | Role | Where |
|---|---|---|
| Mar 2026 – Present | AI Engineer | **CSR Online**, Barcelona — sole engineer of the AI department, reporting directly to the co-founder/CTO |
| Oct 2025 – Present | AI Systems Architect & Developer | **VazquezDev** — freelance AI architecture & proprietary products, built in parallel with CSR Online |
| Sep 2023 – Sep 2025 | Full Stack Product Engineer | Full-stack web — before specializing in AI architecture |

---

## `$ ssh adrian@vazquezdev.pro`

**Read the code. That's the pitch.** Every claim above links to something you can actually open and run. Or skip the README — **[talk to Cortex AI](https://brain.vazquezdev.pro)**, the RAG system that already knows this portfolio cold.

<div align="center">

[![Portfolio](https://img.shields.io/badge/PORTFOLIO-vazquezdev.pro-0D1117?style=for-the-badge&labelColor=0D1117&color=00FFA3)](https://www.vazquezdev.pro)
[![Cortex AI](https://img.shields.io/badge/CORTEX_AI-Talk_to_it-0D1117?style=for-the-badge&labelColor=0D1117&color=A855F7)](https://brain.vazquezdev.pro)
[![LinkedIn](https://img.shields.io/badge/LINKEDIN-adriiivaaazz-0D1117?style=for-the-badge&logo=linkedin&logoColor=00FFA3&labelColor=0D1117)](https://linkedin.com/in/adriiivaaazz)
[![Email](https://img.shields.io/badge/EMAIL-adrian%40vazquezdev.pro-0D1117?style=for-the-badge&logo=gmail&logoColor=A855F7&labelColor=0D1117)](mailto:adrian@vazquezdev.pro)
[![Instagram](https://img.shields.io/badge/INSTAGRAM-vazquezdev.ai-0D1117?style=for-the-badge&logo=instagram&logoColor=00FFA3&labelColor=0D1117)](https://instagram.com/vazquezdev.ai)
[![GitHub](https://img.shields.io/badge/GITHUB-avaazquezz-0D1117?style=for-the-badge&logo=github&logoColor=C9D1D9&labelColor=0D1117)](https://github.com/avaazquezz)

**Build AI systems a CTO can trust.**

</div>
