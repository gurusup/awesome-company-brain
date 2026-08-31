# Docmost

## Snapshot

- Website / docs: https://docmost.com (docs: https://docmost.com/docs; code: https://github.com/docmost/docmost)
- Company / maintainer: Founded by Philip Okugbe; developed as a commercial open-core product (Docmost / Docmost Inc.) that also sells a hosted Cloud plan and a paid Enterprise Edition on top of the open community core.
- Status: Actively maintained (repo pushed within days of this review; latest tagged release v0.95.0, July 2026); ~21.5k GitHub stars, ~1.5k forks — younger and smaller than Outline but growing quickly.
- Open source: Yes — Community Edition core is licensed AGPL-3.0 (verified via repository LICENSE file). Enterprise features live under a separate proprietary Enterprise license in `ee/`-designated directories, so the full product is open-core rather than 100% AGPL.
- Deployment: Self-hosted (Docker Compose; requires PostgreSQL and Redis) or managed Docmost Cloud; Enterprise Edition supports on-prem/air-gapped deployment with local LLMs (Ollama, vLLM) in addition to cloud LLM providers.
- Primary users: Small-to-midsize teams wanting a self-hosted Confluence/Notion alternative with real-time collaborative editing.
- Best company-brain role: Self-hostable Confluence/Notion-style wiki
- Last reviewed: 2026-08-31

## One-line Summary

Docmost is an AGPL-3.0-licensed, self-hostable Confluence/Notion-style wiki with real-time collaborative editing, diagramming, and (in its paid Enterprise tier) built-in AI chat and semantic search over the wiki's own content.

## Company-Brain Fit

Docmost is primarily an **Organize** and **Collect** tool: it gives teams "Spaces" for departments/projects, nested pages, and real-time CRDT-based co-authoring (including live cursors) with embedded diagramming (Draw.io, Excalidraw, Mermaid) so knowledge gets captured directly where it's written. **Evolve** is supported through page comments and version/revision history rather than automated freshness scoring. For **Use**, the free Community Edition offers standard full-text search; the paid Enterprise Edition adds an "AI Answers" feature (AI chat with citations grounded in wiki content) and semantic search, plus MCP support so external AI tools (Claude, Cursor, etc.) can query the wiki programmatically — meaning the AI-grounded retrieval layer of the "company brain" story is gated behind the commercial license, not part of the free AGPL core. **Govern** is handled via RBAC-style permissions, groups, and Space-level access control in the Community Edition, with SSO (SAML/OIDC/LDAP) reserved for the Enterprise tier. Self-hosting means running Postgres and Redis alongside the app — lighter than Outline's footprint but still a real multi-service deployment, not a single binary.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Self-hosted via Docker Compose (Postgres + Redis + app), or managed Docmost Cloud; Enterprise Edition supports air-gapped/on-prem deployment with local LLMs. |
| Context capture (docs, wikis, chats, tickets, CRM, meetings) | Primarily direct authoring in the editor plus embeds/attachments (Figma, Airtable, Google Drive, Miro, Loom, PDFs, DOCX); no native connectors for pulling in Slack, tickets, or CRM data. |
| Knowledge organization | "Spaces" (per team/department) containing nested pages; groups for access management. |
| Knowledge evolution (freshness, dedup, review cycles) | Page-level comments and version/revision history for tracking changes; no automated dedup or scheduled freshness review. |
| Retrieval / use (search, grounding, citations) | Community Edition: standard full-text search. Enterprise Edition: semantic "AI Search" (intent-aware) and "AI Answers" chat with source citations across pages and attachments (PDF/DOCX). |
| Agent activation / write-back (MCP, API, Slack/Teams, support bots) | REST API (documented); Docmost can act as an MCP server so AI tools like Claude/Cursor can query the wiki programmatically — this MCP/AI layer is part of the Enterprise offering. |
| Team / org / role scope | RBAC-style permissions with Spaces and Groups in the Community Edition (view/edit/admin granularity); SSO (SAML 2.0, OIDC, LDAP) and MFA are Enterprise-only. |
| Feedback / correction | Comments and full page revision history support correction workflows; no dedicated fact-correction/feedback loop beyond normal editing. |
| Privacy / access control | Self-hosting keeps data under company control; granular Space/group permissions in Community Edition; enterprise SSO, audit, and air-gapped LLM deployment available in the paid tier for stricter governance needs. |
| Setup / operations | Docker Compose deployment needing Postgres and Redis; simpler footprint than Outline (no separate object-storage requirement called out) but still a multi-container stack to operate and maintain. |

## Strengths

- Community Edition core is genuinely AGPL-3.0 licensed with no seat limits or feature gates on core wiki functionality.
- Real-time CRDT-based collaborative editing with live cursors, plus native diagramming (Draw.io, Excalidraw, Mermaid) built into the page editor.
- Clear, affordable upgrade path to Enterprise (from $5/user/month) for SSO and AI features without a rip-and-replace migration.
- MCP server support lets external AI coding/assistant tools query the wiki directly — useful for agent write-back into a "company brain" workflow.
- Active, fast-shipping project with a straightforward Docker Compose deployment.

## Limitations

- AI chat/semantic search ("AI Answers," "AI Search") and enterprise SSO are gated behind the paid Enterprise Edition — the free AGPL core is a wiki without built-in AI grounding.
- No native connectors to ingest knowledge from Slack, ticketing systems, or CRM; content only enters via authoring or file embeds/attachments.
- Smaller, younger project (founded 2023, ~21.5k stars) than Confluence-class incumbents — fewer third-party integrations and community plugins to date.
- AGPL-3.0's copyleft terms are more restrictive than permissive licenses (MIT/Apache) if a company wanted to build and distribute a modified/derivative product.

## Best For

- Small-to-midsize teams wanting a modern, real-time collaborative wiki with Confluence/Notion-like UX that they fully control.
- Teams that want a clear, affordable path to AI-grounded wiki search/chat and SSO without switching products (Enterprise upgrade).
- Companies comfortable with AGPL licensing and a lightweight Docker Compose deployment.

## Not Ideal For

- Teams that need built-in AI chat/RAG search but want to stay on the free, unmodified community edition.
- Organizations needing native connectors into Slack/tickets/CRM for automatic knowledge capture (better paired with, or replaced by, a dedicated ingestion/search tool like Onyx).
- Companies with legal/procurement policies that disallow AGPL-licensed software in their stack.

## Tradeoffs

Docmost delivers a modern, real-time collaborative wiki with genuinely open (AGPL) core functionality and diagramming built in, and it has a clean commercial path to AI-grounded search/chat and enterprise SSO — but that AI layer, MCP write-back, and SSO all sit behind the paid Enterprise Edition, and like Outline it has no native connectors, so it excels as the authoring/organization layer of a company brain rather than as an aggregator of knowledge already scattered across other tools.

## Official Setup / Evaluation Links

- Docs: https://docmost.com/docs
- GitHub repo: https://github.com/docmost/docmost
- License and editions: https://docmost.com/docs/editions
- Pricing (Community vs Enterprise vs Cloud): https://docmost.com/pricing

## Sources

- https://github.com/docmost/docmost (repo metadata, README)
- https://raw.githubusercontent.com/docmost/docmost/main/LICENSE
- https://docmost.com/
- https://docmost.com/pricing
- https://docmost.com/docs/editions
- https://wz-it.com/en/blog/docmost-community-vs-enterprise-edition/
