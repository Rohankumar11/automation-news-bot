# ⚡ PGDM Daily News Bot — Intelligent News Automation Pipeline

> Stop scrolling. Start receiving.
> A production-grade automation pipeline that thinks, filters,
> and delivers financial intelligence — before your day begins.

---

## 🔄 What This Really Is

This is not just a news bot.

This is a fully automated **data ingestion → AI processing → delivery pipeline**
built on event-driven architecture — triggered on a schedule, requiring
zero human interaction from start to finish.

Every morning, while you sleep:

7 nodes. 1 trigger. 0 manual effort.

---

## 🏗 Pipeline Architecture

### Stage 1 — Ingestion
Parallel RSS feed readers pull live articles simultaneously from
3 curated financial sources. Each feed runs independently,
ensuring one failure doesn't break the pipeline.

### Stage 2 — Aggregation
A Merge node appends all feed outputs into a unified data stream.
A Wait buffer prevents API rate-limit collisions downstream.

### Stage 3 — Transformation
A JavaScript Code node bundles 100+ raw RSS items into a single
clean payload — stripping noise, structuring title + summary + link
for optimal AI token usage.

### Stage 4 — AI Processing
Google Gemini (gemini-1.5-flash-8b) receives the bundled payload
and applies domain-specific instructions to:
- Categorize news into 4 finance-relevant sections
- Generate 2-line plain-English summaries
- Add MBA-lens insights per article
- Append relevant finance hashtags

### Stage 5 — Delivery
Telegram Bot API receives the structured output and pushes
a formatted Markdown message directly to the target chat —
no app, no login, no friction.

---

## ⚙️ Automation Stack

| Layer | Tool | Role |
|-------|------|------|
| Orchestration | n8n Cloud | Workflow engine & scheduler |
| Ingestion | RSS Feed Nodes | Live data pull |
| Aggregation | Merge Node | Multi-source unification |
| Rate Control | Wait Node | API collision prevention |
| Transformation | JavaScript Node | Payload bundling |
| Intelligence | Google Gemini AI | Summarization & structuring |
| Delivery | Telegram Bot API | End-user notification |

---

## 🔁 Workflow Design Principles

**Event-Driven**
Triggered by a time-based schedule event — no polling,
no manual execution required.

**Fault Tolerant**
Each RSS node runs independently. If one feed fails,
the rest of the pipeline continues unaffected.

**Rate-Limit Aware**
Wait node and item limiting prevent 429 quota errors
on free-tier AI APIs — making this production-stable
without any paid plan.

**Token Optimized**
The JavaScript bundler compresses multi-item RSS output
into a single AI call — minimizing API usage while
maximizing context quality sent to Gemini.

**Zero Infrastructure**
Runs entirely on n8n Cloud + free-tier APIs.
No servers. No Docker. No DevOps overhead.

---

## 📊 Pipeline Metrics

| Metric | Value |
|--------|-------|
| News Sources | 3 RSS feeds |
| Articles Processed | ~105 per run |
| AI Input (after bundling) | 1 optimized payload |
| Telegram Messages Sent | 1 structured brief |
| Daily Runs | 1 (7:30 AM, Mon–Sat) |
| Manual Steps Required | 0 |
| Infrastructure Cost | $0 |

---

## 🧠 Why Automation, Not Manual Reading

| Manual Approach | This Pipeline |
|----------------|---------------|
| Open 3+ apps daily | 0 apps to open |
| Read 50+ headlines | 1 structured brief |
| No consistent format | Always same structure |
| Easy to skip on busy days | Runs regardless |
| No MBA-lens filter | Finance insights per article |
| Time cost: 20–30 min/day | Time cost: 0 min/day |

---

## 🔧 Extensibility

This pipeline is designed to be modular and extendable:

- **Add sources** → Plug in new RSS nodes into Merge
- **Change AI model** → Swap Gemini for OpenAI or Claude in 1 click
- **Add channels** → Fork output to WhatsApp, Email, or Slack
- **Add filters** → Insert IF node to filter by keyword or category
- **Log to sheets** → Add Google Sheets node for daily article archive
- **Weekly digest** → Clone workflow with 7-day aggregation logic

---

## 📁 Respository Structure
---

## 🚀 Get Started

See [docs/setup_guide.md](docs/setup_guide.md) for full setup.
Import `workflow/pgdm_news_bot.json` into any n8n instance
and you're running in under 20 minutes.

---

## 👤 Author

**Rohan**
PGDM Finance | Automation & FinTech Enthusiast
Building systems that eliminate repetitive decisions.

---

> *"The best workflow is the one you never have to think about."*
