# Zep / Graphiti

## Snapshot

- Website / docs: https://www.getzep.com (docs: https://help.getzep.com; code: https://github.com/getzep/graphiti)
- Company / maintainer: Zep Software, Inc., founded 2023. Zep is the commercial managed platform; Graphiti is Zep's open-source temporal knowledge-graph engine that powers it.
- Status: Actively maintained — Graphiti repo shows a commit pushed the day before this review, latest tagged release v0.29.3 ("FalkorDB and other Optimizations"); Zep Cloud is a GA commercial product with published pricing.
- Open source: Graphiti — Yes, Apache License 2.0 (confirmed via repo LICENSE/GitHub metadata). Zep itself (the managed platform's proprietary Context Graph Engine, governance layer, and hosted service) is closed-source/commercial.
- Deployment: Graphiti — self-hosted, bring-your-own graph database (Neo4j 5.26+, FalkorDB 1.1.2+, Amazon Neptune, or deprecated Kuzu) plus a choice of LLM providers. Zep — Zep Cloud (managed SaaS), Cloud + BYOK (customer-controlled encryption keys), or BYOC (self-hosted in customer's own VPC).
- Primary users: AI/agent developers building conversational or autonomous agents that need persistent, time-aware memory; enterprise teams (Zep cites Fortune 500 customers, e.g. Samsung, Zscaler, per its site) needing managed agent-memory infrastructure with compliance guarantees.
- Best company-brain role: Temporal graph memory and Graph RAG infrastructure for orgs
- Last reviewed: 2026-08-31

## One-line Summary

Zep is a commercial agent-memory platform built on Graphiti, its open-source (Apache-2.0) engine for temporal knowledge graphs that track how facts and relationships change over time, giving AI agents fact-level, provenance-tracked, continuously updated memory.

## Company-Brain Fit

Zep/Graphiti sits squarely at the infrastructure layer of a company brain, specifically strong on Organize and Evolve: its core differentiator is treating knowledge as a temporal graph, where every fact carries a validity window and is automatically invalidated or superseded as new information arrives, rather than being a static snapshot. This directly serves the "Evolve" stage (freshness, contradiction handling, audit trail back to source) better than most memory tools reviewed here. Collect is supported generically (ingest any structured or unstructured "episode" — conversation turns or business data) but there are no documented pre-built connectors to specific enterprise systems (Slack, ticketing, CRM) beyond what a developer builds themselves. Use is well covered via hybrid retrieval (semantic + BM25 keyword + graph traversal) exposed through SDKs (Python, TypeScript, Go), a REST API, and native MCP server support. Govern is addressed at the commercial Zep layer (SOC 2 Type II, HIPAA BAA, attribute-based access control, policy-driven retention, audit logging) rather than in the open-source Graphiti core. As with the other tools in this category, this is memory infrastructure for developers to build agents on top of — not a ready-made, non-technical company wiki or search app — so realizing a "give every agent company context" architecture with Zep/Graphiti still requires application-level integration work.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Graphiti: fully self-hosted, own graph DB (Neo4j/FalkorDB/Neptune) and LLM provider choice — full data ownership. Zep: Cloud (managed), Cloud+BYOK (customer-held encryption keys), or BYOC (self-hosted in customer VPC) — spectrum from convenience to full control. |
| Context capture (docs, wikis, chats, tickets, CRM, meetings) | Generic "episode" ingestion (chat history and arbitrary business data) rather than named pre-built connectors; developers integrate specific sources themselves. No documented native Slack/Teams/CRM connector. |
| Knowledge organization | Temporal knowledge graph (Context Graph) with prescribed ontology (Pydantic models) or emergent/learned patterns; entities, relationships, and facts explicitly modeled with validity windows. |
| Knowledge evolution (freshness, dedup, review cycles) | Core strength: facts carry validity windows and are automatically invalidated when contradicted by new information ("temporal fact management"); incremental graph updates without full batch recomputation. |
| Retrieval / use (search, grounding, citations) | Hybrid retrieval combining semantic embeddings, BM25 keyword search, and graph traversal; every fact traces back to its source episode for provenance/citation. Zep Cloud advertises sub-200ms retrieval at scale (10K–100M+ graphs, per vendor claim — not independently benchmarked here). |
| Agent activation / write-back (MCP, API, Slack/Teams, support bots) | Native MCP server (episode/entity management, semantic search, graph ops), REST API (FastAPI-based), and SDKs in Python/TypeScript/Go; framework-agnostic (works standalone or with any agent framework). No dedicated Slack/Teams bot product observed. |
| Team / org / role scope | Zep Cloud plans are scoped by "projects" and seats (e.g., Free: 2 projects; Flex Plus: 10 projects/15 seats; Enterprise: unlimited/custom), implying project- and seat-based org scoping rather than fine-grained internal role modeling out of the box. |
| Feedback / correction | Zep describes "Observations" that analyze graph patterns to surface recurring behaviors/trends; explicit user-facing fact correction/edit workflows were not independently verified beyond this. |
| Privacy / access control | Zep Enterprise: SOC 2 Type II and HIPAA BAA certified (per vendor site), attribute-based access control, policy-driven retention, legal holds, audit logging. Graphiti (self-hosted OSS) inherits whatever access control the operator's own infrastructure provides — no built-in enterprise ACL layer in the open-source core itself. |
| Setup / operations | Graphiti: pip-installable (`graphiti-core`), Docker Compose for self-hosting, requires standing up a supported graph DB. Zep: managed cloud with published usage-based pricing (credits consumed per "episode" ingested/processed; storage/retrieval unmetered) — free tier (10,000 credits/month) up through paid Flex ($125/mo) and Flex Plus ($375/mo) plans, and custom Enterprise contracts. |

## Strengths

- Genuinely open-source core (Graphiti, Apache-2.0) with a large, active GitHub project (~30k stars, ~3k forks, commits pushed within a day of this review) — auditable and self-hostable independent of the Zep commercial product.
- Temporal-graph design is a real differentiator for company-brain use cases where facts change over time (org changes, project status, pricing, personnel) and stale/contradicted information needs to be automatically superseded rather than silently coexisting with the truth.
- Provenance built into the data model: every fact links back to its source episode, which supports auditability and trust in agent-surfaced answers.
- Multiple supported graph-database backends (Neo4j, FalkorDB, Amazon Neptune) avoid single-vendor database lock-in for the open-source path.
- Zep's commercial layer adds concrete enterprise governance (SOC 2 Type II, HIPAA BAA, attribute-based access control, audit logs) and a flexible deployment spectrum (Cloud / BYOK / BYOC) for teams that need compliance guarantees without building it themselves.
- Native MCP server support on both the open-source and commercial sides eases integration into modern agent tooling.

## Limitations

- Ingestion is generic ("episodes") rather than backed by a library of pre-built enterprise connectors (Slack, ticketing systems, CRM, meeting transcription) — teams must build their own ingestion pipelines for those sources.
- Zep Cloud pricing is usage/credit-based and can become a meaningful recurring cost at scale; the free tier (10,000 credits/month, no rollover) is limited to prototyping.
- The open-source Graphiti core does not itself include enterprise-grade access control or governance — that is reserved for the commercial Zep product, so self-hosted deployments must build their own governance layer.
- Sub-1.0 versioning on the Graphiti library (v0.29.x as of this review) signals the API/behavior may still evolve, which matters for teams building long-term dependencies on it.
- As with comparable tools in this category, this is agent-memory infrastructure requiring developer integration, not a ready-to-use knowledge-base application for non-technical staff.

## Best For

- Engineering teams building conversational or autonomous agents that need memory of evolving, time-sensitive facts (e.g., account status, project state, personnel changes) rather than a static document index.
- Organizations wanting an auditable, self-hostable open-source graph-memory core (Graphiti) with the option to upgrade to a managed, compliance-certified commercial layer (Zep) as needs grow.
- Teams already standardizing on MCP for agent tool integration who want native, low-friction memory access.

## Not Ideal For

- Teams wanting an out-of-the-box, connector-rich enterprise knowledge base without building custom ingestion pipelines.
- Budget-sensitive teams with high-volume ingestion needs who are sensitive to Zep's usage-based credit pricing.
- Non-technical teams needing a ready-made search/chat UI rather than a memory engine to build agents on top of.

## Tradeoffs

Zep/Graphiti's central tradeoff is that its temporal, fact-level graph model is genuinely more sophisticated at handling changing organizational knowledge than a flat document-RAG approach, but that sophistication comes with more integration surface: teams must build their own ingestion connectors and, on the open-source path, their own access-control layer, whereas the commercial Zep product trades some of that flexibility (and adds usage-based cost) for managed infrastructure, compliance certifications, and a flexible cloud/BYOK/BYOC deployment spectrum. It is a strong choice for teams that specifically need time-aware, provenance-tracked agent memory and are willing to either self-host the open-source core or pay for the managed layer — less so for teams wanting a connector-rich, no-code company knowledge tool.

## Official Setup / Evaluation Links

- https://github.com/getzep/graphiti — Graphiti open-source repository (README, LICENSE, quickstart)
- https://help.getzep.com/graphiti/getting-started/welcome — Graphiti getting-started docs
- https://help.getzep.com/graph-overview — Zep Graph overview docs
- https://www.getzep.com/pricing/ — Zep Cloud pricing
- https://github.com/getzep/graphiti/releases — release history

## Sources

- https://github.com/getzep/graphiti
- https://help.getzep.com/graphiti/getting-started/welcome
- https://help.getzep.com/graphiti/getting-started/overview
- https://help.getzep.com/graph-overview
- https://www.getzep.com
- https://www.getzep.com/pricing/
- https://blog.getzep.com/graphiti-knowledge-graphs-for-agents/
- https://api.github.com/repos/getzep/graphiti (GitHub API — stars, forks, license, last push, latest release)
