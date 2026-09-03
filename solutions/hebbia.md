# Hebbia

## Snapshot

- Website / docs: https://www.hebbia.com (product docs behind login; trust/security portal at trust.hebbia.ai)
- Company / maintainer: Hebbia, Inc. — founded 2020 by George Sivulka (Stanford), HQ New York City. Closed-source, VC-backed (a16z, Index Ventures, GV, among others).
- Status: Actively developed, GA enterprise product. Flagship product "Matrix" (launched 2022) was upgraded/rebranded into "Max" in 2026 ("the first AI team member built for the way your firm works").
- Open source: No. Proprietary SaaS; no public source code or repository.
- Deployment: Cloud-hosted SaaS (search.hebbia.ai / app). No public evidence of a self-hosted or on-prem option — deployment details for large enterprise contracts are only available via sales.
- Primary users: Investment/asset managers, investment banks, private equity, law firms, and corporate finance/strategy teams doing document- and data-room-heavy research.
- Best company-brain role: AI knowledge-work agent for large, unstructured document sets
- Last reviewed: 2026-08-31

## One-line Summary

Hebbia is a proprietary enterprise AI platform (product: Matrix/Max) that runs LLM-driven agents over large, unstructured document sets — filings, data rooms, contracts, transcripts — to return structured, citation-backed analysis for finance, legal, and professional-services workflows.

## Company-Brain Fit

Hebbia is best understood as a vertical AI application, not a general-purpose company-brain infrastructure layer. It shines at the "Use" stage of the lifecycle — turning a firm's document corpus (SEC filings, data rooms, PDFs, spreadsheets, CRM/alt-data feeds) into agent-driven, citation-backed answers inside a spreadsheet-like interface — and it does real "Collect" work by connecting to 40+ external data sources (SharePoint, Box, Dropbox, FactSet, PitchBook, etc.). It does much less for "Organize" and "Evolve": there is no public evidence of a persistent, queryable knowledge graph, versioned entity model, or freshness/dedup pipeline that other agents (Slack bots, support bots, custom MCP agents) can read from or write back to — Matrix/Max is designed to be worked inside directly by analysts, not embedded as a memory layer under arbitrary internal agents. Firms wanting Hebbia as part of a broader "give every agent company context" architecture should expect it to sit as a specialized research/analysis endpoint (accessed by people, and via its own agents) rather than as shared infrastructure other tools plug into — this would require custom integration work and is not something the public materials describe.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Cloud SaaS only; no public self-hosted/on-prem/VPC option documented. |
| Context capture (docs, wikis, chats, tickets, CRM, meetings) | Strong for documents/data: connects 40+ sources (SharePoint, OneDrive, Box, Dropbox, AWS, Egnyte, FactSet, S&P Capital IQ, PitchBook, Preqin, SEC filings, earnings transcripts, DealCloud, Salesforce). No evidence of chat/ticket/meeting ingestion (Slack, Teams, Zendesk, calendar). |
| Knowledge organization | Unknown — no public documentation of a persistent knowledge graph or structured entity model; the product surfaces answers per-query in a spreadsheet-style grid ("Matrix") rather than a browsable organized knowledge base. |
| Knowledge evolution (freshness, dedup, review cycles) | Unknown — not documented publicly. |
| Retrieval / use (search, grounding, citations) | Core strength: multi-agent "ISD" (Information/Synthesis/Decomposition) pipeline decomposes queries and returns citation-backed, source-linked answers over large unstructured corpora. |
| Agent activation / write-back (MCP, API, Slack/Teams, support bots) | Unknown — no public MCP server or open API documented; access appears to be primarily through Hebbia's own web app. |
| Activation evidence (proof retrieved context is actually used, not just retrievable) | Partial — its own multi-agent ISD pipeline returns citation-backed, source-linked answers, real evidence that retrieved content is used inside Hebbia's own product. No public MCP/API surface exists to show the same pattern holding for third-party agents. |
| Team / org / role scope | Seat-based licensing (e.g., Professional vs. Lite seats per third-party pricing reports) implies per-user/per-seat access; no public detail on team/role-based knowledge scoping. |
| Feedback / correction | Unknown — not documented publicly. |
| Privacy / access control | SOC 2 Type II and ISO certified per Hebbia's security page; states it does not train on customer data; AES-256 at rest, TLS 1.3 in transit; GDPR compliant, CCPA "coming soon" per site (as reviewed). |
| Setup / operations | Enterprise sales-led onboarding; custom seat-based contracts (reported ~$10K/seat/year Professional, ~$3-3.5K/seat/year Lite per third-party pricing trackers, not confirmed on Hebbia's own site). |

## Strengths

- Purpose-built for deep analysis over very large, messy unstructured document sets (data rooms, filings, contracts) — a workload general RAG tools often struggle with at scale.
- Citation-backed, source-traceable answers via its multi-agent decomposition pipeline, which matters heavily in finance/legal where provenance is a requirement, not a nice-to-have.
- Broad set of pre-built connectors into financial/data-room ecosystems (FactSet, PitchBook, Preqin, SharePoint, Box, etc.) that reduce integration effort for its target industries.
- Strong enterprise security posture (SOC 2 Type II, ISO certification, no training on customer data) suited to regulated finance/legal customers.
- Credible customer base in institutional finance (reported to include major asset managers and advisory firms), suggesting real production usage at scale.

## Limitations

- Closed-source, cloud-only SaaS — no self-hosting, no code to audit, and customers are dependent on Hebbia's roadmap and infrastructure.
- No public evidence of an underlying persistent knowledge graph, MCP server, or open API for other agents/tools to read from or write into — it is not documented as a pluggable "memory layer" for a broader company-brain architecture.
- Narrow ingestion scope: strong on documents/data feeds, but no visible support for chat, ticketing, or meeting-transcript ingestion, which limits its use as a general org-wide knowledge hub.
- Pricing is opaque and enterprise-sales-gated (no public pricing page); third-party estimates suggest a high per-seat cost, positioning it for large institutional budgets rather than small teams.
- Vertical focus on finance/legal/professional-services workflows means it is less suited to general internal knowledge-management use cases (engineering docs, product wikis, support content).

## Best For

- Investment banks, asset managers, PE/VC firms, and law firms that need agent-driven analysis across large sets of filings, contracts, and data-room documents.
- Deal teams and research analysts who need fast, citation-backed synthesis across dozens or hundreds of documents simultaneously.

## Not Ideal For

- Teams looking for an open-source or self-hostable memory/knowledge layer they can audit or embed into a custom agent stack.
- Organizations wanting a general-purpose, org-wide company brain spanning chat, tickets, wikis, and meetings rather than document-heavy financial/legal research.
- Budget-constrained teams — pricing is enterprise-only and reportedly high per seat.

## Tradeoffs

Hebbia trades openness and general-purpose flexibility for depth: it is a highly specialized, closed, cloud-only application optimized for one hard problem — synthesizing answers with citations across huge unstructured document sets in finance and legal contexts — rather than a general infrastructure layer that other agents can plug into. Teams evaluating it as part of a "company brain" strategy should treat it as a best-in-class vertical research tool that people (and its own internal agents) use directly, not as shared memory infrastructure; wiring it into a broader agent ecosystem (Slack bots, support bots, MCP-based agents) is not something the public documentation supports today, and pricing/deployment details require a direct sales conversation.

## Official Setup / Evaluation Links

- https://www.hebbia.com — main site / product overview
- https://www.hebbia.com/security — security and compliance overview
- https://trust.hebbia.ai — security/trust documentation portal
- https://www.hebbia.com/blog/introducing-matrix-the-interface-to-agi — product background (Matrix)
- https://www.hebbia.com/blog/introducing-max — product background (Max)

## Sources

- https://www.hebbia.com
- https://www.hebbia.com/security
- https://www.hebbia.com/blog/introducing-matrix-the-interface-to-agi
- https://www.hebbia.com/blog/introducing-max
- https://www.hebbia.com/blog/divide-and-conquer-hebbias-multi-agent-redesign
- https://en.wikipedia.org/wiki/Hebbia
- https://www.getguru.com/reference/what-is-hebbia
- https://metronome.com/pricing-index/hebbia (third-party pricing estimate, not confirmed by Hebbia)
