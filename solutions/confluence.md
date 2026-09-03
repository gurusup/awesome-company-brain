# Confluence (Atlassian, incl. Rovo)

## Snapshot

- Website / docs: https://www.atlassian.com/software/confluence
- Company / maintainer: Atlassian (Atlassian Corporation; Nasdaq: TEAM), founded 2002 in Sydney, Australia by Mike Cannon-Brookes and Scott Farquhar, with dual operations centered in Sydney and the US.
- Status: Active commercial product; core Atlassian product line with continued investment (Rovo AI layer actively expanding).
- Open source: No — proprietary.
- Deployment: Cloud (Atlassian-hosted, primary go-forward path with public per-seat pricing). Data Center (self-managed, on-prem or IaaS) exists but is being phased out: no new subscriptions after March 30, 2026, license expansion ends March 2028, full end-of-life March 28, 2029. The fully self-hosted "Server" edition was discontinued previously.
- Primary users: Organizations already standardized on Jira/Atlassian tooling, and broader enterprise/IT/cross-functional teams needing a documentation wiki.
- Best company-brain role: Enterprise wiki of record with AI assistant layer.
- Last reviewed: 2026-08-31

## One-line Summary

Confluence is Atlassian's team workspace/wiki product; Rovo is Atlassian's AI layer — search, chat, content generation, and agents — now bundled into paid Confluence Cloud plans and grounded in a cross-product "Teamwork Graph" spanning Confluence, Jira, and connected apps.

## Company-Brain Fit

Confluence's brain-fit comes largely through its ecosystem rather than a purpose-built knowledge-governance layer. It **collects** context from native Confluence pages/spaces and, via Rovo's Teamwork Graph, from Jira issues, meeting notes, and connected third-party apps like Slack. It **organizes** content into spaces and pages, with whiteboard-to-page and whiteboard-to-Jira-item conversion. Its **evolution** mechanisms are largely standard version history and space ownership rather than a dedicated verification/trust workflow. It is **used** through Rovo Search (cross-tool AI search with citations), Rovo Chat (conversational Q&A that can also take actions like creating Jira issues or Slack messages), and pre-built or custom AI agents (via Rovo Studio). **Governance** relies on Confluence's existing space/page permission model plus Atlassian's broader enterprise identity and security tooling (Atlassian Access/Guard), rather than an AI-specific governance layer built for external agent access.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Cloud (Atlassian-hosted) is the primary, actively developed path with public per-seat pricing for Free/Standard/Premium. Data Center (self-managed) is in phased retirement (no new subscriptions after March 30, 2026; full EOL March 2029); the fully self-hosted "Server" edition was already discontinued. |
| Context capture (docs, wikis, chats, tickets, CRM, meetings) | Native Confluence pages/spaces; Rovo's "Teamwork Graph" connects Jira issues, Confluence pages, meeting notes, and third-party apps (e.g., Slack) into unified AI context. |
| Knowledge organization | Spaces/pages hierarchy; whiteboard-to-page and whiteboard-to-Jira-item conversion; inline definitions surface organizational terminology in context. |
| Knowledge evolution (freshness, dedup, review cycles) | Standard page version history and space-level ownership. No dedicated content-verification, staleness-scoring, or dedup workflow comparable to purpose-built knowledge platforms was found in official materials — Unknown/limited. |
| Retrieval / use (search, grounding, citations) | Rovo Search — AI-powered search with cited answers spanning Confluence, Jira, and connected apps; Rovo Chat for conversational Q&A over the same sources; AI content generation, editing, and tone adjustment inline on pages. |
| Agent activation / write-back (MCP, API, Slack/Teams, support bots) | Rovo Chat can create Jira issues, generate Google Docs, send Slack messages, and create calendar events from a single natural-language command. Pre-built agents include a Meeting Insights Reporter and a Brainstorm Facilitator; custom agents can be built via Rovo Studio; a "Rovo Dev" code-intelligence capability is in early access for developer teams. Specifics on an external MCP server or public API for third-party AI tools to query Confluence/Rovo directly were not confirmed in the sources reviewed — Unknown. |
| Activation evidence (proof retrieved context is actually used, not just retrievable) | Partial — Rovo Search is described as returning "cited answers," which is some evidence of source attribution in the response itself, but no audit log or usage-tracking mechanism proving retrieved context was actually loaded (beyond the citation) is documented. |
| Team / org / role scope | Space-level and page-level permissions native to Confluence; organization-wide administration, identity, and security policy via Atlassian Access/Guard. |
| Feedback / correction | Not clearly documented in the sources reviewed — Unknown. |
| Privacy / access control | Space/page permissions enforced natively; enterprise-tier identity and security controls (SSO, data residency, centralized policy) available via Atlassian Access/Guard. Specific data-handling controls for Rovo AI processing were not independently verified in the sources reviewed. |
| Setup / operations | Self-serve signup with public per-user pricing for Free, Standard, and Premium Cloud tiers; Enterprise is custom/sales-led. Rovo is included at no additional list price in paid Cloud plans (Premium/Enterprise since April 2025, Standard since October 2025), but AI usage is metered by a monthly credit allowance. |

## Strengths

- Deep integration with Jira and the broader Atlassian suite — valuable for teams whose tickets, plans, and docs already live in Atlassian products.
- Rovo AI (search, chat, content generation, agents) is bundled into paid Cloud plans rather than sold as a separate product, lowering the barrier to trying AI features.
- Transparent, public per-user Cloud pricing for the Free, Standard, and Premium tiers (only Enterprise is custom).
- Cross-product "Teamwork Graph" gives Rovo context spanning tickets and docs, not just wiki pages, plus connections to some third-party apps.
- Large, established enterprise customer base and mature admin/security tooling (Atlassian Access/Guard) built over two decades.

## Limitations

- Atlassian is actively retiring self-managed Data Center (no new subscriptions after March 30, 2026; full EOL March 2029), and the fully self-hosted Server edition is already gone — organizations wanting on-premise deployment are being pushed toward Cloud-only.
- Rovo AI usage is metered by monthly credit allowances even on paid plans, which can create unpredictable costs or throttling at scale.
- No dedicated content-verification or trust-scoring workflow comparable to purpose-built knowledge platforms (e.g., Guru) was found in official materials.
- Confluence's page/space model can become sprawling and hard to keep organized at scale without strong internal governance discipline.
- Public documentation of external write-back and MCP-style third-party agent integration is less clear than for AI-agent-first platforms like Glean or Guru.

## Best For

- Organizations already standardized on Jira/Atlassian tooling that want AI search and content assistance layered directly onto their existing wiki.
- Teams that want transparent, public per-seat Cloud pricing rather than a sales-led custom quote, at least below the Enterprise tier.

## Not Ideal For

- Organizations that require long-term on-premise/self-hosted deployment — Data Center is being sunset.
- Teams wanting a dedicated, AI-agent-first knowledge platform with a mature, publicly documented external MCP/agent write-back ecosystem out of the box.

## Tradeoffs

Confluence's core tradeoff is breadth-via-ecosystem versus AI specialization: it leverages deep Jira/Atlassian integration and now bundles Rovo AI directly into Cloud plans at transparent per-seat pricing, but it lacks the verification workflows of purpose-built knowledge platforms, meters AI usage by credits, and is phasing out its self-managed deployment path in favor of Cloud-only delivery.

## Official Setup / Evaluation Links

- [Confluence](https://www.atlassian.com/software/confluence)
- [Rovo in Confluence: AI features](https://www.atlassian.com/software/confluence/ai)
- [Rovo (AI Agents, Chat & Enterprise Search)](https://www.atlassian.com/software/rovo)
- [Confluence Data Center (deployment/EOL info)](https://www.atlassian.com/enterprise/data-center/confluence)
- [Confluence Pricing](https://www.atlassian.com/software/confluence/pricing)

## Sources

- [Confluence](https://www.atlassian.com/software/confluence)
- [Rovo in Confluence: AI features](https://www.atlassian.com/software/confluence/ai)
- [Rovo (AI Agents, Chat & Enterprise Search)](https://www.atlassian.com/software/rovo)
- [Confluence Data Center](https://www.atlassian.com/enterprise/data-center/confluence)
- [Atlassian — Wikipedia, for company founding/HQ/ticker facts](https://en.wikipedia.org/wiki/Atlassian)
- [Confluence Pricing 2026 (ONES.com, secondary corroboration of per-seat pricing)](https://ones.com/blog/confluence-pricing/)
- [Atlassian Confluence Data Center End of Life (docmost.com, secondary corroboration of EOL timeline)](https://docmost.com/blog/atlassian-confluence-data-center-eol/)
