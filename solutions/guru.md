# Guru

## Snapshot

- Website / docs: https://www.getguru.com
- Company / maintainer: Guru Technologies, Inc. (founded 2013; headquartered in Philadelphia, PA).
- Status: Active commercial product.
- Open source: No — proprietary SaaS.
- Deployment: Cloud SaaS (multi-tenant); SOC 2 Type II certified with HIPAA/GxP support readiness. No self-hosted/on-premise option identified in official materials.
- Primary users: Customer support, sales, CS, and HR/ops teams that need verified answers surfaced directly in Slack, Teams, browser workflows, and AI agents.
- Best company-brain role: AI-native company wiki with verification workflows.
- Last reviewed: 2026-08-31

## One-line Summary

Guru is a cloud-based AI knowledge platform built around a governed company wiki ("Cards") with structured subject-matter-expert verification workflows, exposed to both employees and AI tools through Slack/Teams integrations, a browser extension, and an official MCP server.

## Company-Brain Fit

Guru is explicitly built around the verification and governance parts of the lifecycle that many wikis leave to chance. It **collects** context through 100+ source connectors with permission-aware ingestion and HRIS/identity sync; **organizes** it into Collections and standardized Card templates; **evolves** it through an automated verification system that Guru says handles roughly 80–90% of review through usage signals, content age, and policy rules, escalating the rest to SME expert review, trust scoring, and auto-archival of stale content; and makes it available for **use** through permission-aware hybrid search, Slack/Teams, a browser extension, a Knowledge Agent chat, and an official MCP server so external AI tools query the same governed answers. **Governance** (RBAC, DLP masking, SSO/SCIM) is enforced consistently across both human and AI access paths, including MCP queries.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Cloud SaaS (multi-tenant), SOC 2 Type II certified, with stated HIPAA/GxP support readiness. No on-premise/self-hosted option found. |
| Context capture (docs, wikis, chats, tickets, CRM, meetings) | 100+ source connectors linking enterprise apps, databases, and file systems into one knowledge layer; permission-aware ingestion (sources inherit their original access controls); HRIS and identity sync to keep org structure/permissions current. |
| Knowledge organization | "Collections" organize knowledge into navigable structures that feed both browsing and AI retrieval; standardized content templates for "Cards" (Guru's knowledge unit). |
| Knowledge evolution (freshness, dedup, review cycles) | Automated verification handles an estimated ~80–90% of review via usage signals, content age, and policy rules; SME expert review workflows with scheduled cycles and reminders; trust scores; auto-archiving of stale/unverified content; continuous refresh as source content changes. |
| Retrieval / use (search, grounding, citations) | Permission-aware hybrid search across all connected sources ("not siloed"); unified knowledge index; answers surfaced with citations and lineage back to the verified source Card. |
| Agent activation / write-back (MCP, API, Slack/Teams, support bots) | Official MCP server (developer.getguru.com) connects Claude, ChatGPT, Cursor, Microsoft Copilot, Sierra, Intercom Fin, and other MCP-compatible tools/agents to search, retrieve, and create/update Guru Cards; separate API and CLI; OAuth 2.0 (recommended, supported for Claude/Cursor) or API-token auth; native Slack and Microsoft Teams apps; browser extension. |
| Activation evidence (proof retrieved context is actually used, not just retrievable) | Documented — answers are surfaced "with citations and lineage back to the verified source Card," and all AI-agent interactions (including MCP queries) are logged in an "AI Agent Center" for auditability, giving a real, checkable trail of what was retrieved and used. |
| Team / org / role scope | RBAC with centralized permissions inheritance from connected sources; HRIS-driven org-structure sync. |
| Feedback / correction | The SME verification/expert-review workflow is itself the correction mechanism — content is fixed once by a verified owner and updates propagate everywhere it's surfaced, with citations and lineage preserved. |
| Privacy / access control | RBAC; DLP masking for PII/PHI redaction; SSO (SAML) and SCIM; encryption at rest and in transit. MCP queries enforce the same RBAC as the web app, and all AI-agent interactions are logged in an "AI Agent Center" for auditability. |
| Setup / operations | Positioned as "a platform and expertise solution, not just a per-seat tool" — onboarding includes a solution-engineer team and knowledge-architecture design rather than pure self-serve signup; not self-serve for pricing (consultation-based). |

## Strengths

- Purpose-built verification workflow (trust scores, SME sign-off, scheduled review, auto-archival) that goes further than most company wikis in enforcing content accuracy.
- Governed MCP server lets multiple AI tools (Claude, ChatGPT, Cursor, Copilot, and support-bot platforms like Intercom Fin and Sierra) reuse the same permissioned, verified answers rather than each tool re-learning content independently.
- Deep, native surfacing in Slack, Microsoft Teams, and a browser extension gets verified answers into existing workflows, not just a separate wiki tab.
- Broad connector footprint (100+ sources) with permission-aware ingestion that respects source-system access controls.
- Access-control stack (RBAC, DLP masking, SSO/SCIM, encryption) suited to regulated or support-heavy organizations.

## Limitations

- No public pricing; positioned as a consultative "platform and expertise" engagement rather than a self-serve SaaS product, which can slow evaluation and add cost for smaller teams.
- Cloud-only; no on-premise/self-hosted deployment option was found in official materials.
- Realizing the platform's value depends on investing in verification workflows and knowledge architecture up front, not just importing existing documents.
- Public materials reviewed do not detail deep analytics or knowledge-gap reporting depth — worth validating directly during evaluation.

## Best For

- Customer support, sales, and CS teams that need verified, trustworthy answers pushed into Slack/Teams and into AI agent/support-bot workflows.
- Organizations that want a formal SME-verification and trust-scoring process built into the knowledge base rather than bolted on afterward.

## Not Ideal For

- Teams wanting fast, free, self-serve setup with transparent public pricing.
- Organizations that require on-premise/self-hosted deployment for data-residency or infrastructure reasons.

## Tradeoffs

Guru trades wiki simplicity for governance rigor: its verification workflows, trust scoring, and RBAC-enforced MCP server make it well suited to support and sales organizations that need provably accurate answers surfaced to both humans and AI agents, but that rigor comes with a sales-led, consultative onboarding model, no public pricing, and no on-premise deployment option.

## Official Setup / Evaluation Links

- [Guru Features](https://www.getguru.com/features)
- [Guru Verification Workflow](https://www.getguru.com/features/verification)
- [Guru MCP Server](https://www.getguru.com/features/mcp-server)
- [Guru MCP Server Overview (Developer Docs)](https://developer.getguru.com/docs/guru-mcp-server-overview)
- [Guru Pricing](https://www.getguru.com/pricing)

## Sources

- [Guru Features](https://www.getguru.com/features)
- [Guru Verification Workflow](https://www.getguru.com/features/verification)
- [Guru MCP Server](https://www.getguru.com/features/mcp-server)
- [Guru MCP Server Overview (Developer Docs)](https://developer.getguru.com/docs/guru-mcp-server-overview)
- [Using Guru as an MCP Server (Help Docs)](https://help.getguru.com/docs/connecting-gurus-mcp-server)
- [Guru Pricing](https://www.getguru.com/pricing)
- [Agentic Knowledge Base | Self-Maintaining Knowledge Base](https://www.getguru.com/solutions/ai-powered-company-wiki)
