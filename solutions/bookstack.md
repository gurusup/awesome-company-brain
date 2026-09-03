# BookStack

## Snapshot

- Website / docs: https://www.bookstackapp.com (docs: https://www.bookstackapp.com/docs; primary source repo: https://codeberg.org/bookstack/bookstack, mirrored at https://github.com/BookStackApp/BookStack)
- Company / maintainer: Community project led and primarily maintained by creator Dan Brown, with community contributors (186+ contributors); no commercial company or dual-licensing model behind it.
- Status: Actively maintained (latest release v26.05.4, August 2026; ~19k GitHub stars on the mirror, primary development and issue tracking now on Codeberg rather than GitHub).
- Open source: Yes — MIT License (verified via repository LICENSE file), fully permissive, no enterprise/proprietary carve-outs.
- Deployment: Self-hosted only (Docker or manual LAMP-stack install: PHP/Laravel + MySQL/MariaDB). No official BookStack-run cloud/hosted plan; several unaffiliated third parties (e.g., PikaPods) offer managed hosting.
- Primary users: Small-to-midsize teams and self-hosting/homelab users wanting a simple, no-frills internal wiki/documentation tool.
- Best company-brain role: Simple self-hosted wiki, no AI built in
- Last reviewed: 2026-08-31

## One-line Summary

BookStack is a simple, MIT-licensed, community-maintained self-hosted wiki organized around Books/Chapters/Pages, with no built-in AI features and no official hosted offering.

## Company-Brain Fit

BookStack covers the **Organize** and **Collect** stages in the most minimal way among these four tools: content is authored directly (Markdown or WYSIWYG) into a strict Books → Chapters → Pages hierarchy (with Shelves grouping Books), which enforces a clean, predictable structure but offers none of the automated ingestion, real-time co-editing CRDT, or AI-assisted organization the other products have. **Evolve** is handled through page revision history and simple version comparison, with no automated freshness/dedup tooling. **Use** relies on straightforward full-text search (per-book or global) and a REST API — there is no AI chat, semantic search, or RAG layer built into the product at all, open-source or paid, since BookStack has no paid tier to fund such features. **Govern** is handled through a genuinely full role/permission system (page-, chapter-, book-, and shelf-level permissions) plus LDAP/SAML2/OIDC SSO support, which is unusually complete for a project with no commercial backer. Self-hosting BookStack is comparatively simple — a single PHP/Laravel app plus a MySQL/MariaDB database, no Redis/object-storage/search-index services required — making it the lowest-operational-overhead option of the four, at the cost of having no path to AI-grounded retrieval without bolting on a separate tool (e.g., pairing it with Onyx as a connector/source).

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Self-hosted only; Docker or manual install (PHP/Laravel + MySQL/MariaDB); no official cloud/SaaS plan, only unaffiliated third-party managed hosting. |
| Context capture (docs, wikis, chats, tickets, CRM, meetings) | Direct authoring only (Markdown/WYSIWYG editor), plus image uploads and built-in diagrams.net (draw.io) integration; no connectors to external systems like Slack, tickets, or CRM. |
| Knowledge organization | Strict hierarchy: Shelves → Books → Chapters → Pages, with cross-book linking and paragraph-level deep links. |
| Knowledge evolution (freshness, dedup, review cycles) | Full page revision history with diff/comparison; no automated freshness scoring or dedup workflow. |
| Retrieval / use (search, grounding, citations) | Full-text search scoped to a single book or across the whole instance; no AI/semantic search or RAG chat — none is planned as part of the project's stated minimalist philosophy. |
| Agent activation / write-back (MCP, API, Slack/Teams, support bots) | Documented REST API (token-based auth) supports reading/writing content and exporting pages/chapters/books as PDF, HTML, plain text, or Markdown; no official MCP server, Slack bot, or support-bot integration. |
| Activation evidence (proof retrieved context is actually used, not just retrievable) | Unknown — not documented beyond the retrieval/citation features described above. |
| Team / org / role scope | Full role-and-permission system with granular access control down to individual pages/chapters/books/shelves, role-based MFA enforcement, and multi-language UI (10+ languages via Crowdin). |
| Feedback / correction | Comments on pages and full revision history support correction and rollback; no dedicated feedback-loop tooling. |
| Privacy / access control | Self-hosted-only, so data never leaves the company's infrastructure by default; supports LDAP, SAML2, and OIDC SSO for enterprise auth alongside built-in email/password and social login. |
| Setup / operations | Lightweight stack: single PHP/Laravel application plus MySQL/MariaDB — no Redis, object storage, or search-index services required, making it simpler to operate than Outline or Docmost. |

## Strengths

- Fully MIT-licensed with no enterprise carve-outs, dual licensing, or feature gating of any kind.
- Simple operational footprint (PHP/Laravel + MySQL/MariaDB) — easiest of the four to self-host and maintain.
- Genuinely complete role/permission system and LDAP/SAML2/OIDC SSO support despite having no commercial backer.
- Built-in export to PDF/HTML/Markdown/plain text, including via the REST API, useful for downstream ingestion by other tools.
- Long-running, stable project (since 2015) with a clear, disciplined "stay simple" philosophy that limits scope creep.

## Limitations

- No AI features at all — no semantic search, RAG chat, or summarization; would need to be paired with a separate tool for AI-grounded retrieval.
- No native connectors to Slack, tickets, CRM, or meeting tools — purely a manual-authoring wiki.
- No official cloud/hosted plan; teams without self-hosting capacity must rely on unaffiliated third-party hosts.
- Community-maintained by essentially one lead maintainer plus contributors — no company-backed SLA or dedicated support to fall back on.
- Rigid Books/Chapters/Pages hierarchy is simple but less flexible than freeform nested-page or database/table structures (e.g., Notion-style) offered by Outline/Docmost.

## Best For

- Small-to-midsize teams or homelab/self-hoster users wanting a dead-simple, low-maintenance internal wiki with no AI or SaaS dependency.
- Organizations that value a fully permissive (MIT) license and minimal infrastructure footprint over feature breadth.
- Teams that already have (or plan to pair with) a separate AI search/RAG layer and just need a clean, well-organized documentation source to feed it.

## Not Ideal For

- Teams wanting built-in AI chat or semantic search over their wiki content — not offered by BookStack at any tier.
- Teams wanting real-time multi-user collaborative editing (Google-Docs-style simultaneous editing) — BookStack's editing model is more traditional/page-lock oriented.
- Organizations that want an officially supported managed/cloud hosting option from the vendor itself.

## Tradeoffs

BookStack trades feature breadth (no AI, no real-time collaborative editing, no external connectors) for simplicity, stability, and a genuinely unencumbered MIT license with the lightest self-hosting footprint of the four — it's the right choice when the goal is a clean, well-permissioned documentation source of truth to author and organize knowledge, not a platform to also capture, retrieve via AI, or automatically evolve that knowledge.

## Official Setup / Evaluation Links

- Docs / installation: https://www.bookstackapp.com/docs/admin/installation
- Primary source repo (Codeberg): https://codeberg.org/bookstack/bookstack
- GitHub mirror: https://github.com/BookStackApp/BookStack
- API documentation (live demo): https://demo.bookstackapp.com/api/docs
- Feature overview: https://www.bookstackapp.com/

## Sources

- https://github.com/BookStackApp/BookStack (repo metadata, mirror)
- https://raw.githubusercontent.com/BookStackApp/BookStack/development/LICENSE
- https://raw.githubusercontent.com/BookStackApp/BookStack/development/readme.md
- https://www.bookstackapp.com/about/project-faq/
- https://demo.bookstackapp.com/api/docs
- https://codeberg.org/bookstack/bookstack
