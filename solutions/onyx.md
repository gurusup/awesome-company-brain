# Onyx (formerly Danswer)

## Snapshot

- Website / docs: https://onyx.app (docs: https://docs.onyx.app; code: https://github.com/onyx-dot-app/onyx)
- Company / maintainer: DanswerAI, Inc. (dba Onyx) — VC-backed startup (Y Combinator W24, ~$10M seed co-led by Khosla Ventures and First Round Capital), founded by Yuhong Sun and Chris Weaver; actively developed (194+ GitHub contributors, ~31.8k GitHub stars, frequent releases — latest v4.6.5 as of Aug 2026).
- Status: Actively maintained, fast-moving (commits pushed same day as this review).
- Open source: Yes, mixed license — core "Community Edition" is MIT ("MIT Expat" per LICENSE file), but code under `ee/` directories (backend/ee, web/src/ee, web/src/app/ee) is covered by the proprietary "Onyx Enterprise License," not MIT. So Onyx is open core, not 100% open source.
- Deployment: Self-hosted (Docker Compose, Kubernetes/Helm, Terraform templates for major clouds); also offered as managed "Onyx Cloud." Two self-hosted modes: lightweight "Lite" (<1GB RAM) and full "Standard."
- Primary users: Engineering, IT, and ops-heavy companies wanting a self-hosted ChatGPT-style assistant grounded in internal tools (Slack, Confluence, Jira, Drive, GitHub, Salesforce, etc.).
- Best company-brain role: Open-source enterprise search and RAG chat over company sources
- Last reviewed: 2026-08-31

## One-line Summary

Onyx is an open-core (MIT community edition + proprietary enterprise add-ons), self-hostable AI search and chat platform that indexes 40+ workplace tools with permission-aware retrieval and answers questions with citations.

## Company-Brain Fit

Onyx is squarely a **Use** and **Retrieval** layer: it does not create or edit source content itself, it connects to and continuously indexes existing systems of record (Slack, Confluence, Jira, Drive, GitHub, Salesforce, SharePoint, and 30+ others) for **Collect**, applies hybrid search + LLM-based knowledge graphs to structure retrieval for **Organize**, and re-syncs on a schedule so answers reflect **Evolve**-ing source content rather than a stale snapshot. It is explicitly designed for the **Use** stage — chat, cited answers, agents/actions, and a Slack bot — more than for authoring or governing knowledge directly. Self-hosting means the team owns the full stack (Postgres/Vespa/Redis, ingestion workers, and an LLM of choice — including local models via Ollama/vLLM), which buys data residency and control but requires real DevOps investment; the enterprise-licensed tier (RBAC, SSO, audit/query history) is what most companies need for governance at scale, and that tier is not MIT-licensed.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Self-hosted via Docker Compose or Kubernetes/Helm (Terraform for AWS/GCP/Azure), or use hosted Onyx Cloud. Full data ownership when self-hosted; works with any LLM provider including local models. |
| Context capture (docs, wikis, chats, tickets, CRM, meetings) | 40+ native connectors (Slack, Google Drive, Confluence, Jira, GitHub, Salesforce, SharePoint, Gmail, Notion, Zendesk, and more), with continuous/incremental re-indexing. |
| Knowledge organization | Hybrid keyword + vector search plus LLM-based knowledge graph construction over indexed content; document sets and connector-based grouping. |
| Knowledge evolution (freshness, dedup, review cycles) | Scheduled/continuous re-sync per connector keeps the index current with source systems; no manual dedup/review workflow beyond re-indexing. |
| Retrieval / use (search, grounding, citations) | Hybrid search, contextual retrieval, and RAG chat with inline citations back to source documents. |
| Agent activation / write-back (MCP, API, Slack/Teams, support bots) | Slack bot (OnyxBot) answers in channels/threads; REST API; "Actions & MCP" lets Onyx agents call external tools/APIs and Onyx can itself act as an MCP-connected assistant. |
| Team / org / role scope | Document-level permission sync inherited from source systems (Confluence, Jira, GitHub, Drive, Gmail, Slack, Salesforce, SharePoint) so users only see what they already have access to; RBAC for admin-level access control is an Enterprise Edition feature. |
| Feedback / correction | In-chat thumbs up/down style feedback on answers is supported; no dedicated knowledge-correction workflow beyond re-indexing source of truth. |
| Privacy / access control | Self-hosted deployment keeps data and LLM calls under company control; permission-aware retrieval limits answers to documents a user can already access; SSO/RBAC/audit (query history) are Enterprise Edition (non-MIT) features. |
| Setup / operations | Requires running and operating Postgres, a vector/search index, Redis, and background indexing workers; "Lite" mode targets small deployments (<1GB RAM), "Standard" mode is production-scale — real DevOps effort either way. |

## Strengths

- Fully self-hostable core (MIT) with no seat-based licensing for the community edition.
- Broad, mature connector library (40+) covering most common enterprise SaaS tools with permission-aware sync.
- Works with any LLM provider, including fully local/offline models (Ollama, vLLM), which supports strict data-residency requirements.
- Native Slack bot and MCP/Actions support make it usable as an in-workflow assistant, not just a search UI.
- Well-funded, active development (YC-backed, frequent releases, large contributor base).

## Limitations

- Not 100% open source: enterprise features (SSO, RBAC, audit logging, query history) live under a proprietary "Onyx Enterprise License," not MIT — read the LICENSE file's per-directory carve-outs before assuming full OSS coverage.
- Self-hosting is operationally heavy: Postgres, a search/vector index, Redis, and indexing workers all need to be run and maintained.
- Primarily a retrieval/chat layer, not a content-authoring or wiki tool — it does not replace a wiki, it searches across your existing ones.
- As a fast-moving, relatively young VC-backed startup, long-term roadmap and licensing terms could shift (e.g., which features move behind the Enterprise license).

## Best For

- Engineering-led teams that already have DevOps capacity and want a self-hosted "ask my company's tools" assistant with source-permission-aware answers.
- Organizations needing to keep both data and LLM inference on-prem or in a private cloud.
- Teams that want a Slack-native Q&A bot grounded in Confluence/Jira/Drive/GitHub without adopting a proprietary SaaS search product.

## Not Ideal For

- Teams wanting a zero-ops, fully managed product with no infrastructure to run (use Onyx Cloud instead, or a SaaS competitor).
- Teams that need enterprise governance features (SSO, RBAC, audit) but want to stay strictly on the MIT-licensed community edition.
- Teams looking for a wiki/authoring tool rather than a search-and-chat layer over existing sources.

## Tradeoffs

Onyx trades the ease of a SaaS enterprise-search product for self-hosted control, deep connector coverage, and LLM flexibility — but that control comes with real infrastructure ownership (multiple stateful services, indexing workers) and a licensing model where the free MIT tier stops short of the governance features (SSO, RBAC, audit) many companies need at scale, pushing them toward the proprietary Enterprise Edition or Onyx Cloud.

## Official Setup / Evaluation Links

- Docs: https://docs.onyx.app
- GitHub repo: https://github.com/onyx-dot-app/onyx
- Connectors list: https://onyx.app/connectors
- Slack bot setup: https://docs.onyx.app/admins/getting_started/slack_bot_setup
- License and editions: https://github.com/onyx-dot-app/onyx/blob/main/LICENSE

## Sources

- https://github.com/onyx-dot-app/onyx (repo metadata, README, LICENSE)
- https://raw.githubusercontent.com/onyx-dot-app/onyx/main/LICENSE
- https://onyx.app/
- https://onyx.app/connectors
- https://docs.onyx.app/admins/getting_started/slack_bot_setup
- https://techcrunch.com/2025/03/12/why-onyx-thinks-its-open-source-solution-will-win-enterprise-search/
- https://techfundingnews.com/onyx-lands-10m-to-build-ai-powered-24-7-coworker-that-instantly-finds-what-you-need/
- https://www.ycombinator.com/companies/onyx
