# OpenViking

## Snapshot

- Website / docs: https://openviking.ai (code: https://github.com/volcengine/OpenViking, docs: https://docs.openviking.ai)
- Company / maintainer: Volcengine (ByteDance's cloud/AI platform). Backed by a published paper (VikingMem, arXiv:2605.29640, accepted VLDB 2026).
- Status: Very actively maintained — 34.6k+ GitHub stars, 2.6k+ forks, commits as recent as the day this profile was reviewed. Open-source edition described by the maintainers as "still in its early stages."
- Open source: Yes, fully — AGPL-3.0. The maintainers explicitly state "the open-source edition is not crippled": no feature gates, no account required, no activation key for self-managed production use.
- Deployment: Self-hosted (pip install, Docker, or standalone HTTP service) by default. Commercial tiers layer on top: a Volcano Engine-managed SaaS (Personal and Enterprise), and a self-managed "Online" (your VPC/BYOC) or "Offline" (air-gapped) edition with distributed deployment and support, activated by license key.
- Primary users: Developers and teams building AI agents (Claude Code, Codex, Cursor, OpenClaw, Hermes, and others) that need persistent, inspectable context rather than a black-box vector store.
- Best company-brain role: Open-source "context database" that unifies agent memory, knowledge RAG, and skills as one browsable filesystem, with an enterprise tier for team-level permissions.
- Last reviewed: 2026-08-31

## One-line Summary

OpenViking is an open-source (AGPL-3.0) context database for AI agents that stores memories, resources, and skills as a browsable `viking://` virtual filesystem with tiered (abstract/overview/detail) loading, instead of a black-box vector index.

## Company-Brain Fit

OpenViking is squarely an Agent Memory / Context Layer building block rather than an end-user wiki: it gives agents (Claude Code, Codex, Cursor, and others) a structured, inspectable place to store and retrieve resources, per-user memories, and skills, with every retrieval leaving a debuggable trajectory. Per-user namespaces (`user/{user_id}/...`) are built into the core data model, and the commercial "Enterprise" managed tier adds "multi-user context management, team collaboration and permissions" on top — so the path from single-developer tool to team/company deployment is a real, documented upgrade path rather than a hack. It fits Collect (via `ov add-resource` ingesting repos/docs/web pages), Organize (the L0/L1/L2 tiered structure), and Use (native integrations across many agent CLIs and MCP) well; Govern-level team permissions are a paid add-on, not part of the open-source core.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Self-hosted by default (pip/Docker/standalone service), fully functional per the maintainers' "not crippled" open-source claim. Managed SaaS and self-managed (BYOC/air-gapped) commercial tiers are optional. |
| Context capture (docs, wikis, chats, tickets, CRM, meetings) | `ov add-resource` ingests repos, docs, and web pages; capture is resource-centric (whatever you point it at) rather than pre-built connectors to specific SaaS tools like Slack or a CRM. |
| Knowledge organization | Every entry is processed into three tiers on write — L0 abstract (~100 tokens), L1 overview (~2k tokens), L2 full detail — organized as a `viking://` virtual filesystem agents browse with `ls`/`tree`/`find`. |
| Knowledge evolution (freshness, dedup, review cycles) | Sessions are asynchronously distilled into long-term memory after commit; no dedicated staleness/deprecation workflow beyond that documented. |
| Retrieval / use (search, grounding, citations) | Directory-recursive retrieval: vector search locates the highest-scoring directory, then drills down layer by layer, preserving surrounding context; every query keeps an inspectable browsing trajectory. |
| Agent activation / write-back (MCP, API, Slack/Teams, support bots) | Native integrations for Claude Code, Codex, OpenClaw, Hermes, Cursor, TRAE, OpenCode, plus generic MCP clients and LangChain/LangGraph; a CLI (`ov`) and HTTP server for direct use. |
| Team / org / role scope | Per-user memory/resource/skill namespaces exist in the open-source core; multi-user context management, team collaboration, and permissions are explicitly gated to the commercial Enterprise/self-managed tiers. |
| Feedback / correction | Unknown — no dedicated correction/verification workflow found beyond the session-to-memory distillation process. |
| Privacy / access control | Self-hosted deployment keeps data local by default; the self-managed "Offline" tier targets fully air-gapped, regulated environments. Fine-grained access control is part of the paid tiers. |
| Setup / operations | Low to moderate for the open-source edition (`pip install openviking`, an interactive `init` wizard, a `doctor` health check); production deployment (Docker, distributed) requires more operational ownership. |

## Strengths

- Genuinely full-featured open-source core (AGPL-3.0), not a crippled trial of a paid product.
- Published, peer-reviewed research backing (VikingMem paper, accepted at VLDB 2026) with concrete benchmark results (LoCoMo, tau2-bench) rather than only marketing claims.
- Wide, well-documented agent integration surface (Claude Code, Codex, Cursor, OpenClaw, Hermes, TRAE, OpenCode, MCP, LangChain/LangGraph).
- Transparent, inspectable retrieval (browsable filesystem plus per-query trajectory) instead of an opaque vector store.
- Very active development and a large, fast-growing community (34.6k+ stars in roughly seven months).

## Limitations

- Team/company-level permissions and collaboration are commercial add-ons, not part of the open-source core — a company deployment needing real governance will likely need the paid Enterprise or self-managed tier.
- No pre-built connectors to common company SaaS tools (Slack, ticketing, CRM) — capture is generic ("point it at a resource") rather than turnkey enterprise ingestion.
- Very young project (created January 2026); self-described as "still in its early stages."
- AGPL-3.0 licensing has real copyleft implications for anyone building a commercial product on top of the open-source core.

## Best For

- Technical teams building custom AI agents that want an open-source, inspectable memory/context layer instead of assembling their own vector-store plumbing.
- Organizations already using Claude Code, Codex, Cursor, or similar agent CLIs who want persistent, shared context across sessions.
- Teams that may later want a managed or self-managed enterprise tier without switching context-layer technology.

## Not Ideal For

- Non-technical teams wanting a turnkey, connector-rich enterprise knowledge platform out of the box.
- Organizations that need team permissions and governance today, on the free open-source tier alone.

## Tradeoffs

OpenViking trades pre-built enterprise connectors and out-of-the-box team governance for a fully open, inspectable, research-backed context layer that developers can wire into almost any agent — strong as an infrastructure building block, less turnkey than a dedicated enterprise-knowledge SaaS product.

## Official Setup / Evaluation Links

- https://docs.openviking.ai/en/getting-started/01-introduction
- https://docs.openviking.ai/en/getting-started/02-quickstart
- https://docs.openviking.ai/en/agent-integrations/01-overview
- https://openviking.ai/studio (live hosted demo, no installation required)
- https://www.volcengine.com/product/openviking-service (commercial tiers)

## Sources

- https://github.com/volcengine/OpenViking (README, GitHub API for stars/license/activity)
- https://openviking.ai
- https://docs.openviking.ai
- https://blog.openviking.ai/post/openviking-benchmark-results/
- https://arxiv.org/abs/2605.29640 (VikingMem paper, VLDB 2026)
