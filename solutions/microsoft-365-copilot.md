# Microsoft 365 Copilot

## Snapshot

- Website / docs: https://www.microsoft.com/microsoft-365/copilot
- Company / maintainer: Microsoft Corporation
- Status: Generally available (GA since November 2023). Sold in tiers: Copilot Chat (Basic, included with eligible M365 licenses), Microsoft 365 Copilot (Basic, standard in-app access), and Microsoft 365 Copilot (Premium, full grounded add-on).
- Open source: No — proprietary SaaS.
- Deployment: Cloud SaaS, multi-tenant, Microsoft-hosted; logically isolated per tenant via Microsoft Entra ID authorization/RBAC. No self-hosting option.
- Primary users: Enterprise/business/education/government Microsoft 365 users — knowledge workers inside a Microsoft 365 tenant.
- Best company-brain role: Platform baseline: AI grounded in Microsoft 365 org content
- Last reviewed: 2026-08-31

## One-line Summary

Microsoft 365 Copilot is a per-seat, tenant-scoped generative-AI assistant that grounds responses in a user's permitted Microsoft Graph content (email, files, chats, meetings) and surfaces them inside Word, Excel, PowerPoint, Outlook, Teams, and a standalone chat/search experience, extendable to some non-Microsoft data via connectors.

## Company-Brain Fit

Copilot's context is scoped to a single Microsoft 365 tenant's Microsoft Graph — it is a platform baseline, not a universal company brain. Collect: native content is Outlook mail/calendar, Teams chats and meeting transcripts, SharePoint/OneDrive files, and Office documents, extended by 100+ prebuilt Graph connectors (Confluence, ServiceNow, Salesforce, Jira, Box, Dropbox, Google Drive, SAP, Workday, Zendesk, Dynamics 365, SQL/Oracle) and federated MCP-based connectors for live, non-indexed queries. Organize: an automatically-built semantic (vector) index over Graph content, with no manual wiki/taxonomy required. Evolve: near-real-time reindexing tied to content changes (authored docs index almost immediately; shared SharePoint content reindexes daily); there is no explicit "review cycle" or staleness-governance feature — freshness relies on continuous re-crawling. Use: Copilot Chat, in-app Copilot panes across Word/Excel/PowerPoint/Outlook/Teams/OneNote, and Copilot Search, with citations back to source content. Govern: no separate access-control layer — Copilot only surfaces content a user already has at least view permission on, inheriting existing SharePoint/Exchange/Teams RBAC and Purview sensitivity labels. Everything is bounded to one Microsoft 365 tenant; non-Microsoft knowledge must be explicitly connected via Graph connectors.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Cloud SaaS, Microsoft-hosted, per-tenant logical isolation via Entra ID/RBAC; no self-hosting option. |
| Context capture (docs, wikis, chats, tickets, CRM, meetings) | Native: SharePoint, OneDrive, Exchange/Outlook, Teams chats and meetings, Word/Excel/PowerPoint/OneNote/Forms. Extended via Graph connectors (100+ prebuilt: Confluence, ServiceNow, Salesforce, Jira, Box, Dropbox, Google Drive, SAP, Workday, Zendesk, SQL/Oracle, Dynamics 365) and federated (MCP-based, read-only) connectors for live third-party queries. |
| Knowledge organization | Microsoft Graph plus an automatically-generated semantic (vector) index; no manual wiki/taxonomy — indexing is automatic, admin involvement limited to exclusions. |
| Knowledge evolution (freshness, dedup, review cycles) | Near-real-time reindexing tied to content changes; grounding always checks live permissions. No explicit staleness-flagging or review-cycle feature is documented — freshness is a function of crawl cadence, not curated review. |
| Retrieval / use (search, grounding, citations) | Copilot Chat (web and work-based), in-app Copilot across Word/Excel/PowerPoint/Outlook/Teams/OneNote/Forms, and Copilot Search (a universal AI search layer), with citations back to source documents/emails/records. |
| Agent activation / write-back (MCP, API, Slack/Teams, support bots) | Copilot Studio is the low-code builder for custom agents/workflows on top of M365 Copilot and Teams, with connectors for write-back actions. Federated Graph connectors explicitly use a Model Context Protocol (MCP) model to fetch data in real time, but are read-only by design; write-back requires additional Power Platform connectors/plugins. Also extensible via the Microsoft 365 Agents Toolkit. |
| Activation evidence (proof retrieved context is actually used, not just retrievable) | Strong — Copilot responses cite back to source documents, emails, and records inside Word/Excel/PowerPoint/Outlook/Teams and Copilot Search, a documented, user-visible citation mechanism rather than silent retrieval. |
| Team / org / role scope | No new access layer — inherits the existing tenant permission model (SharePoint/Exchange RBAC, sensitivity labels, Information Rights Management). Licensing and access are per-user, per-tenant. |
| Feedback / correction | Thumbs up/down on Copilot responses with an optional detail pane (logs, screenshots, contact email); admins can enable/disable via policy; an "Agent feedback sharing" admin setting routes end-user feedback to agent developers. |
| Privacy / access control | Respects existing M365 permissions (no separate ACL); integrates with Microsoft Purview (sensitivity labels, DLP, retention, eDiscovery for Copilot interaction logs); supports the EU Data Boundary; Microsoft states prompts, responses, and Graph-accessed data are not used to train foundation LLMs, including third-party models used by Copilot. |
| Setup / operations | Sold as a per-seat add-on requiring a qualifying base license (M365 E3/E5/E7/F1/F3, Business Basic/Standard/Premium, Apps for business/enterprise, GCC/GCC-High/DoD, academic A1/A3/A5). Setup via the Microsoft 365 admin center (Copilot setup guide, license assignment, Copilot Control System for governance). Pricing is an add-on layered on base M365 licensing and changes over time; as of 2026-08-31, official/near-official sources cite roughly $30/user/month (annual commitment) for the enterprise add-on and a lower SMB "Business" add-on tier — verify current figures directly on Microsoft's pricing page before quoting exact numbers. |

## Strengths

- Deep, native integration inside the Office apps users already work in daily (Word, Excel, PowerPoint, Outlook, Teams, OneNote) rather than a separate destination tool.
- Grounding and citations are drawn automatically from Microsoft Graph — no manual document upload required once licensed.
- Reuses existing SharePoint/Exchange/Teams permissions rather than requiring a parallel access-control system to maintain.
- Broad, actively maintained connector ecosystem (100+ prebuilt Graph connectors) plus a federated/MCP mode for live queries against dynamic third-party systems without indexing.
- Mature, explicit enterprise compliance posture: GDPR, EU Data Boundary, Purview integration, and an explicit no-training-on-tenant-data commitment.
- Copilot Studio provides a low-code path to build custom agents/workflows that extend Copilot with organization-specific knowledge and actions.

## Limitations

- Context is scoped to a single Microsoft 365 tenant/Graph by design — not a cross-cloud or cross-organization universal company brain.
- Requires a qualifying Microsoft 365 base license plus, for the full grounded (Premium) experience, a separate per-seat add-on — a real cost layer on top of core M365 licensing.
- Non-Microsoft data sources require Graph connector setup, licensing, and (for synced connectors) ongoing sync/indexing maintenance — no first-class support for arbitrary external systems out of the box.
- No documented staleness-governance or review-cycle feature — freshness relies on automatic crawl cadence rather than an explicit content-lifecycle workflow.
- Per-seat licensing can become costly at scale, and feature/performance differs between Basic and Premium license tiers.

## Best For

- Organizations already standardized on Microsoft 365 wanting AI assistance embedded directly in Word/Excel/PowerPoint/Outlook/Teams/SharePoint.
- Enterprises needing strict compliance guarantees (GDPR, EU Data Boundary, Purview DLP/labels) without building a separate data-governance system.
- Teams that want to extend Microsoft Graph data with third-party systems (Salesforce, ServiceNow, Confluence, etc.) via a supported connector rather than custom integration.

## Not Ideal For

- Organizations wanting a single company brain spanning multiple clouds/ecosystems (e.g., Google Workspace, Slack, Notion, AWS) without heavy connector work.
- Teams wanting a lightweight, low-cost pilot — the fully grounded experience is a paid per-seat add-on on top of qualifying base licensing.
- Use cases needing agent write-back to arbitrary external systems by default — federated connectors are read-only; write-back needs additional connectors/plugins.

## Tradeoffs

Microsoft 365 Copilot's core tradeoff is depth-within-ecosystem versus breadth-across-ecosystems: because it grounds every response in the tenant's own Microsoft Graph and inherits the tenant's existing permission model, it avoids building a second access-control or indexing system and gives users citation-backed answers natively inside the apps they already use — but that same design makes it fundamentally tenant- and Microsoft-ecosystem-scoped, so any non-Microsoft knowledge must be explicitly connected through Graph connectors or federated MCP connectors, each with its own setup and (for synced connectors) ongoing maintenance overhead. Organizations get strong compliance and governance guarantees largely "for free" because Copilot piggybacks on Microsoft's existing enterprise data-protection commitments, but pay for that in per-seat licensing costs stacked on top of base M365 subscriptions and in the practical limitation that Copilot is, by design, not a neutral, cross-platform company memory.

## Official Setup / Evaluation Links

- [Product page](https://www.microsoft.com/en-us/microsoft-365/copilot)
- [Overview docs](https://learn.microsoft.com/en-us/copilot/microsoft-365/microsoft-365-copilot-overview)
- [Licensing / plans](https://learn.microsoft.com/en-us/microsoft-365/copilot/microsoft-365-copilot-licensing)
- [Admin setup guide](https://learn.microsoft.com/en-us/microsoft-365/copilot/microsoft-365-copilot-setup)
- [Copilot Studio (build custom agents)](https://learn.microsoft.com/en-us/microsoft-copilot-studio/fundamentals-what-is-copilot-studio)
- [Pricing](https://www.microsoft.com/en/microsoft-365-copilot/pricing)

## Sources

- [Microsoft 365 Copilot product page](https://www.microsoft.com/en-us/microsoft-365/copilot)
- [Microsoft 365 Copilot overview](https://learn.microsoft.com/en-us/copilot/microsoft-365/microsoft-365-copilot-overview)
- [Microsoft 365 Copilot privacy](https://learn.microsoft.com/en-us/microsoft-365/copilot/microsoft-365-copilot-privacy)
- [Semantic index for Copilot](https://learn.microsoft.com/en-us/microsoftsearch/semantic-index-for-copilot)
- [Microsoft 365 Copilot connectors overview](https://learn.microsoft.com/en-us/microsoft-365/copilot/connectors/overview)
- [Microsoft 365 Copilot licensing](https://learn.microsoft.com/en-us/microsoft-365/copilot/microsoft-365-copilot-licensing)
- [Copilot Studio overview](https://learn.microsoft.com/en-us/microsoft-copilot-studio/fundamentals-what-is-copilot-studio)
- [Enabling users for Copilot (feedback settings)](https://learn.microsoft.com/en-us/microsoft-365/copilot/microsoft-365-copilot-enable-users)
- [Agent settings (admin center)](https://learn.microsoft.com/en-us/microsoft-365/admin/manage/agent-settings)
- [Microsoft 365 Copilot pricing](https://www.microsoft.com/en/microsoft-365-copilot/pricing)
- [Microsoft Tech Community: Copilot Business bundle pricing](https://techcommunity.microsoft.com/blog/microsoft365copilotblog/act-now-lock-in-current-pricing-on-microsoft-365-copilot-business-bundles/4502628)
