# Outline

## Snapshot

- Website / docs: https://www.getoutline.com (docs: https://docs.getoutline.com; code: https://github.com/outline/outline)
- Company / maintainer: General Outline, Inc. — a company-backed open-core product (not a community-governed project); maintains both the codebase and the hosted Outline Cloud offering.
- Status: Actively maintained (repo pushed within days of this review; latest tagged release v1.9.2, July 2026); ~40.4k GitHub stars, ~3.5k forks.
- Open source: Source-available, not OSI-approved open source — licensed under the Business Source License (BSL) 1.1. You may self-host and modify freely, but you may not use it to offer a competing "Document Service" (a commercial product letting third parties create their own teams/documents on top of it). The license converts to Apache 2.0 four years after each version's release (change date for the reviewed version: 2030-07-13).
- Deployment: Self-hosted (Docker; requires PostgreSQL 12+, Redis 4+, and object storage) or managed Outline Cloud (hosted SaaS, from $19/user/month on the Team plan).
- Primary users: Product, engineering, and ops teams wanting a fast, Notion-like team wiki with real-time collaborative editing.
- Best company-brain role: Self-hostable company wiki of record
- Last reviewed: 2026-08-31

## One-line Summary

Outline is a fast, real-time collaborative team wiki with a polished editor and strong search, available self-hosted under a source-available Business Source License or as a paid managed cloud service.

## Company-Brain Fit

Outline sits mainly in the **Organize** and **Use** stages of the company-brain lifecycle: it gives teams a structured place (collections, nested documents) to write and maintain source-of-truth knowledge, with strong full-text search and a clean editor for the **Collect**/authoring step, but it has no built-in connectors to pull knowledge in from other systems (Slack, tickets, CRM, meetings) — content only enters Outline through people writing or importing it. **Evolve** is handled via document revision history, comments, and manual review rather than automated freshness/dedup tooling. Self-hosting Outline means owning a horizontally-scalable stack (Postgres, Redis, object storage, and the app itself) — the docs explicitly note it requires DevOps experience to run in production — which buys full data ownership and no per-seat SaaS fee, but at real operational cost; the alternative is the vendor's own hosted Outline Cloud, which trades that ops burden for a subscription and less infrastructure control. Because the code is BSL-licensed rather than a permissive/copyleft OSI license, companies considering forking it into a competing hosted wiki product cannot do so under the license terms — self-hosting for internal use is fine, but that restriction is worth knowing before treating it as fully "open source."

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Self-hosted via Docker (needs Postgres 12+, Redis 4+, object storage, a Unix host — Windows unsupported), or managed Outline Cloud (SaaS). |
| Context capture (docs, wikis, chats, tickets, CRM, meetings) | No native connectors to external systems; content is created by users directly in the editor or via import (Markdown, Word, Confluence exports, etc.); a Slack integration exists for notifications/unfurling, not knowledge ingestion. |
| Knowledge organization | Collections (top-level wikis) containing nested documents in a tree structure, with drag-and-drop reorganization and cross-document linking/backlinks. |
| Knowledge evolution (freshness, dedup, review cycles) | Full document revision history and comments; no automated freshness scoring, dedup, or scheduled review workflow. |
| Retrieval / use (search, grounding, citations) | Fast full-text search across documents; no LLM-based RAG/grounding built into the core self-hosted product. |
| Agent activation / write-back (MCP, API, Slack/Teams, support bots) | Public REST API for reading/writing documents; Slack app integration; no official MCP server or support-bot integration in the open self-hosted core. |
| Activation evidence (proof retrieved context is actually used, not just retrievable) | Unknown — the core has no built-in AI/RAG chat or citation mechanism, so there is nothing that shows retrieved content being loaded into an agent's answer; the API only confirms documents are readable/writable. |
| Team / org / role scope | Team/workspace-based with collection-level and document-level permissions (view/edit), plus user groups; suitable for company-wide or team-scoped wikis. |
| Feedback / correction | Inline comments and suggestions on documents, plus full version history for corrections and rollbacks. |
| Privacy / access control | Self-hosting keeps data under company control; supports SSO (OIDC/SAML depending on plan/edition) and granular collection/document permissions; audit logging is more built out on paid Cloud plans. |
| Setup / operations | Requires running Postgres, Redis, and object storage alongside the app; docs explicitly describe it as a horizontally-scalable service needing DevOps experience to run in production — non-trivial compared to single-binary wikis. |

## Strengths

- Best-in-class editor UX: fast, real-time collaborative editing that feels close to Notion.
- Strong full-text search and clean information architecture (collections → nested documents).
- Genuinely self-hostable with source access and no per-seat fee if you run it yourself.
- Backed by a company actively developing and supporting it (frequent releases, responsive maintainers), unlike many purely community-run wikis.
- Public API and Slack integration support basic workflow automation.

## Limitations

- BSL 1.1 license is not OSI-approved open source; redistributing/offering it as a competing hosted document service is explicitly disallowed.
- No native connectors for ingesting knowledge from Slack, tickets, CRM, or meetings — it is an authoring tool, not an aggregator.
- No built-in AI/RAG chat in the self-hosted core as of this review; the company's revenue model centers on the hosted Cloud plans.
- Self-hosting requires meaningful operational investment (Postgres, Redis, object storage, scaling), more than single-server wiki alternatives.

## Best For

- Teams that want a fast, Notion-like authoring and collaboration experience for internal docs and want to self-host it.
- Companies comfortable running a multi-service stack (Postgres/Redis/object storage) in exchange for full data ownership.
- Teams already using Slack who want lightweight wiki-Slack integration without needing AI search built in.

## Not Ideal For

- Teams needing an AI-grounded search/chat layer out of the box (pair Outline with a separate RAG tool, or consider Onyx/Docmost's AI tier instead).
- Teams that need a strictly OSI-licensed open-source codebase for legal/procurement reasons.
- Small teams without DevOps resources who want a true single-container "just works" self-hosted wiki (BookStack or Docmost may be simpler to operate).

## Tradeoffs

Outline offers arguably the best writing/collaboration UX among self-hostable wikis, backed by a real company that keeps shipping — but that comes with a source-available (BSL) license rather than a fully permissive open-source one, a multi-service self-hosting footprint that requires real DevOps effort, and no built-in knowledge-ingestion or AI-retrieval layer, so it best serves as the authoring/wiki-of-record piece of a company brain rather than the whole stack.

## Official Setup / Evaluation Links

- Docs / hosting guide: https://docs.getoutline.com/s/hosting/doc/hosting-outline-nipGaCRBDu
- Self-hosting requirements: https://docs.getoutline.com/s/hosting/doc/requirements-ULdYnwi4wG
- GitHub repo: https://github.com/outline/outline
- Pricing (Cloud vs self-hosted): https://www.getoutline.com/pricing

## Sources

- https://github.com/outline/outline (repo metadata)
- https://raw.githubusercontent.com/outline/outline/main/LICENSE
- https://docs.getoutline.com/s/hosting/doc/hosting-outline-nipGaCRBDu
- https://docs.getoutline.com/s/hosting/doc/requirements-ULdYnwi4wG
- https://www.getoutline.com/pricing
- https://www.getoutline.com/
