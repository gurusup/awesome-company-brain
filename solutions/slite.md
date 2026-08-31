# Slite

## Snapshot

- Website / docs: https://slite.com (developer docs: https://developers.slite.com)
- Company / maintainer: Slite, Inc. (Delaware, US, with a Paris-founded team); founded 2016/2017 by Christophe Pasquier (CEO); backed by Y Combinator, Index Ventures, Spark Capital, eFounders.
- Status: Active commercial product.
- Open source: No — proprietary SaaS.
- Deployment: Cloud-hosted SaaS only, on Google Cloud Platform (EU region, Belgium); no self-hosted/on-prem/VPC option found.
- Primary users: Growing/mid-size companies building an AI-native team wiki, used cross-functionally by Engineering, Product, Support, and Sales teams to centralize docs and give AI agents grounded company context.
- Best company-brain role: AI-native team wiki that pairs document authoring with an AI Q&A layer ("Slite Agent"/Ask) and a doc-verification workflow to keep the knowledge base current.
- Last reviewed: 2026-08-31

## One-line Summary

Slite is a cloud-hosted, AI-native team wiki that combines a collaborative doc/wiki editor with an AI Q&A search layer and doc-freshness verification workflows, and exposes that knowledge to external AI agents via a hosted MCP server and REST API.

## Company-Brain Fit

Slite covers most of the knowledge lifecycle inside one product rather than as a headless layer. **Collect**: content originates in Slite's own doc/wiki editor (with tables, nested docs, embeds) and is supplemented by 50+ integrations (Slack, GitHub, Jira, Linear, Google Drive, HubSpot, Salesforce, Confluence, SharePoint, Asana, Grain, BigQuery, and more); on Pro/Enterprise, the "Slite Agent" can search connected tools directly rather than requiring everything to be copied into docs. **Organize**: docs are grouped into collections/channels with a "Knowledge Management Panel" for admins and structured tables for semi-structured data. **Evolve**: a native verification workflow lets anyone mark a doc "verified" or "flag as outdated" with notes, or request verification from a named subject-matter expert; Pro/Enterprise add AI-assisted "doc fact-checking with suggested fixes" and drift detection against connected tools. **Use**: the "Ask"/Slite Agent feature answers questions by searching the knowledge base (and, on higher tiers, connected tools), citing source documents and surfacing gaps or outdated content; the same knowledge is exposed to external AI clients (Claude, ChatGPT, Cursor, Windsurf, LangChain/LlamaIndex) through a hosted, OAuth-authenticated MCP server with 40+ read/write tools, plus a REST API. **Govern**: access is enforced server-side at the document level (workspace-wide, restricted, or public), search results are permission-filtered for both humans and agents, and Enterprise adds SSO (Okta/Azure AD/OneLogin/Auth0), SCIM provisioning, and audit logs, on top of SOC 2 Type II and GDPR compliance (HIPAA BAAs available for Enterprise).

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Cloud-hosted SaaS only, run by Slite on Google Cloud Platform (EU region, Belgium). No self-hosted, on-prem, or private-VPC option found. |
| Context capture (docs, wikis, chats, tickets, CRM, meetings) | Native doc/wiki editor is the primary source; 50+ integrations (Slack, GitHub, Jira, Linear, Google Drive, HubSpot, Salesforce, Confluence, SharePoint, Asana, Loom, Grain meeting recordings, BigQuery, Attio, Intercom) let content be embedded in docs or, on Pro/Enterprise, searched live by the Slite Agent without being copied in. |
| Knowledge organization | Docs are grouped into collections/channels, can be nested, and support structured tables; admins get a "Knowledge Management Panel" for oversight. |
| Knowledge evolution (freshness, dedup, review cycles) | Manual verification workflow: any doc can be marked "verified" or "flagged as outdated" with a note, or routed to a named subject-matter expert for review. Pro/Enterprise add AI "doc fact-checking with suggested fixes" and drift detection that drafts updates from connected-tool changes for human approval. No explicit dedup feature found. |
| Retrieval / use (search, grounding, citations) | "Ask" / Slite Agent answers questions by searching the knowledge base (and connected tools on Pro/Enterprise), returns cited source documents, and surfaces gaps or likely-outdated answers. Results are filtered by the querying user's permissions. |
| Agent activation / write-back (MCP, API, Slack/Teams, support bots) | Hosted, OAuth-authenticated MCP server (api.slite.com/mcp) with 40+ tools for search, doc/table create-update, and collection management, for Claude, ChatGPT, Cursor, Windsurf, and custom LangChain/LlamaIndex agents; write actions can be queued for human approval. Also a REST API (OpenAPI v3, developers.slite.com). No native Teams bot found; Slack integration is primarily for content ingestion/notifications. |
| Team / org / role scope | Seat-based pricing (Basic, Pro, Enterprise); Enterprise adds reader-only (viewer) seats and custom agent sources. Marketed for cross-functional use (Engineering, Product, Support, Sales) rather than a single team. |
| Feedback / correction | Doc-level flag-as-outdated and verification-request workflow, with unlimited AI-assisted edits on Pro. No public documentation found of inline thumbs-up/down feedback on individual Ask/Agent answers. |
| Privacy / access control | Document-level permissions (workspace-wide, restricted to users/groups, or public), enforced server-side for both humans and agents. SSO (Okta, Azure AD, OneLogin, Auth0 via OAuth2/OIDC) on higher tiers, SCIM provisioning and audit logs on Enterprise. SOC 2 Type II and GDPR compliant; HIPAA BAAs available for Enterprise. TLS in transit; provider-managed (GCP) encryption at rest; no end-to-end encryption. |
| Setup / operations | Self-serve signup with a 14-day free trial (no credit card); fully managed, no infrastructure to operate. Enterprise tier adds dedicated migration and onboarding support. |

## Strengths

- Combines doc authoring, structured tables, and AI Q&A in one product rather than a bolted-on chatbot; rated highly for ease of use on third-party review sites (G2 lists a 9.3/10 "Ease of Use" score across 265 reviews).
- Native, purpose-built verification workflow (verify / flag-outdated / request-verification-from-SME) directly targets documentation staleness rather than treating freshness as an afterthought.
- Hosted, OAuth-authenticated MCP server exposes 40+ read/write tools to Claude, ChatGPT, Cursor, and Windsurf, with permission inheritance from the signed-in user and human-approval queuing for writes — a real agent-activation layer, not just a search widget.
- Broad integration catalog (50+ tools including Slack, GitHub, Jira, Salesforce, HubSpot, Confluence, SharePoint), with Ask/Slite Agent able to search several of these connected tools directly on Pro/Enterprise.
- SOC 2 Type II and GDPR compliance, with HIPAA BAAs available on Enterprise, and server-side, document-level permission enforcement.

## Limitations

- Fully proprietary, cloud-only SaaS hosted in a single EU (Belgium/GCP) region — no self-hosted, on-prem, or private-VPC option for organizations with stricter data-residency or air-gap requirements.
- AI usage is metered: the Basic plan caps AI search/answers at 30 questions/month, and Pro allocates a fixed "50 monthly credits per seat" for Agent features.
- Cross-tool Agent search, automated drift detection, and AI fact-checking are gated to Pro and Enterprise — not available on the entry tier.
- SSO, SCIM provisioning, audit logs, and other enterprise security controls require the custom-priced Enterprise tier.
- No end-to-end encryption; data protection relies on TLS in transit plus provider-managed (GCP) encryption at rest.

## Best For

- Growing or mid-size companies wanting a single AI-native wiki with built-in freshness/verification workflows instead of a static docs tool plus a separate AI layer.
- Teams that want to expose internal knowledge to AI coding/chat agents (Claude, ChatGPT, Cursor) through a permissioned, hosted MCP server without building custom retrieval infrastructure.
- Cross-functional orgs (Engineering, Product, Support, Sales) consolidating knowledge scattered across Slack, Jira, HubSpot, Salesforce, and GitHub into one searchable, cited answer layer.

## Not Ideal For

- Organizations that require self-hosted, on-prem, or private-VPC deployment, or data residency outside Slite's EU (GCP Belgium) hosting.
- Teams wanting unlimited AI Q&A usage on an entry-level plan without hitting question/credit caps.
- Organizations needing enterprise security controls (SSO, SCIM, audit logs) without moving to custom Enterprise pricing.

## Tradeoffs

Slite trades deployment flexibility for product cohesion: it is a fully managed, cloud-only SaaS wiki that bundles authoring, freshness verification, and an agent-facing MCP/API layer into one opinionated product rather than a headless retrieval layer that can be self-hosted or wired into arbitrary infrastructure. That makes it fast to adopt and genuinely differentiated on "AI keeps docs fresh," but its AI features are metered by plan and per-seat credits, its deepest capabilities (cross-tool Agent search, automated drift detection, enterprise security controls) sit behind Pro/Enterprise tiers, and organizations needing self-hosting or data residency beyond its single EU region will find it a poor fit.

## Official Setup / Evaluation Links

- https://slite.com/pricing
- https://slite.com/mcp
- https://slite.com/security
- https://developers.slite.com/

## Sources

- https://slite.com
- https://slite.com/pricing
- https://slite.com/about
- https://slite.com/security
- https://slite.com/mcp
- https://slite.com/ask
- https://slite.com/integrations
- https://developers.slite.com/
- https://www.capterra.com/p/171199/Slite/reviews/
- https://www.g2.com/products/slite/features
