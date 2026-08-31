# Slab

## Snapshot

- Website / docs: https://slab.com (help center: https://help.slab.com)
- Company / maintainer: Slab, Inc. — founded 2016, headquartered in San Francisco, CA (founders include Jason Chen, CEO).
- Status: Active commercial product, subscription SaaS.
- Open source: No — proprietary SaaS.
- Deployment: Cloud-hosted, multi-tenant SaaS only. No official on-premises or self-hosted deployment option is documented on slab.com, the pricing page, or the help center (all tiers, including Enterprise, are described as hosted subscriptions). Note: a couple of third-party listing/directory sites claim on-prem/private-cloud support, but this could not be corroborated against any official Slab source, so treat those claims as unverified.
- Primary users: Small-to-midsize and growing companies (Startup/Business tiers scale per-user; Enterprise requires a 100-user minimum) wanting a company-wide wiki/knowledge base for both technical and non-technical staff — use cases cited by Slab include onboarding, engineering docs/postmortems, and general team knowledge sharing. Named customers referenced in marketing material include Asana.
- Best company-brain role: Team wiki / knowledge base for authoring, organizing, and searching internal documentation, with basic built-in AI (Q&A, autofix, freshness flagging) layered on top.
- Last reviewed: 2026-08-31

## One-line Summary

Slab is a proprietary, cloud-hosted team wiki and knowledge base for writing, organizing, and searching internal documentation, with unified search across integrated tools and optional AI features (Ask, Predict, Autofix) on paid tiers.

## Company-Brain Fit

Slab's core strength is the "Organize" and "Use" stages of the knowledge lifecycle: it's a structured wiki (Topics, real-time collaborative editor, templates, permissions) with a built-in unified search that also indexes content from 50+ connected tools (Slack, Google Workspace, GitHub, Jira, Confluence, etc.), so it can act as a single search surface over scattered docs. For "Collect," Slab itself is primarily a manual-authoring tool — content gets into Slab mostly by people writing or embedding it, plus lightweight integrations that surface external content in search rather than deep ingestion pipelines for chats/tickets/CRM/meeting transcripts. For "Evolve," Slab has a genuine mechanism: post owners can set verification/reverification intervals, and AI can flag stale-looking content for owner review — this is a real freshness workflow, though it depends on manual reverification rather than automated content diffing. For "Use," Business/Enterprise plans add AI Ask (natural-language Q&A over the knowledge base) on top of unified search. For "Govern," Slab has topic/post-level permissions, guest accounts, SSO/SCIM (Business+), and audit logs (Enterprise), which cover access control reasonably well. Where Slab is comparatively weak as an "AI agent's brain" is agent activation/write-back: there is no official MCP server or first-party AI-agent connector — API/webhook access (GraphQL, Business+) lets you read/write posts and get publish notifications, and third-party AI platforms (e.g., Glean, Dust) offer connectors to index Slab content, but Slab does not ship its own agent-facing tool layer.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Cloud-hosted, multi-tenant SaaS. No official self-hosted or on-premises option found. |
| Context capture (docs, wikis, chats, tickets, CRM, meetings) | Primarily manual document/wiki authoring plus a real-time collaborative editor; integrations (Slack, Google Workspace, GitHub, Jira, Asana, etc.) let you embed/reference external content and surface it in unified search, but there is no described deep pipeline for ingesting chat threads, support tickets, CRM records, or meeting transcripts as first-class knowledge. |
| Knowledge organization | Structured around "Topics" (with multi-topic tagging per post), templates, and admin tools to surface popular vs. stale content; no evidence of automated clustering or knowledge-graph features. |
| Knowledge evolution (freshness, dedup, review cycles) | Built-in "Post verification" lets owners set reverification intervals (e.g., monthly/annually) with expiration banners and reverify prompts; AI can flag posts that look stale for owner review. No documented automated de-duplication. |
| Retrieval / use (search, grounding, citations) | Fast, as-you-type "unified search" ranks by reads/views/links/mentions and also surfaces results from connected integrations. AI Ask (Business/Enterprise) provides natural-language Q&A over the knowledge base; Slab's public materials do not document explicit inline source citations for AI Ask answers. |
| Agent activation / write-back (MCP, API, Slack/Teams, support bots) | GraphQL API and webhooks (Business/Enterprise only) allow programmatic post creation/updates and publish-event notifications via a bot-user token, scoped to whatever that bot user can access. No official MCP server was found from Slab; at least one unofficial, community-built MCP server for Slab exists on GitHub. Slack integration exists for embedding/notifications, not a full read/write bot framework. |
| Team / org / role scope | Free tier caps at 10 users + guests; Startup/Business are unlimited users (per-seat pricing) with guest allowances; Enterprise requires a 100-user minimum. Roles include standard users, guests, and admins; topic-level owner/editor/viewer permissions. |
| Feedback / correction | Posts support comments, reactions, and author feedback; verification requests let teammates flag content they believe is outdated, routing to the post's maintainer/verifier. |
| Privacy / access control | Two-level post permissions (Editor/Viewer), three-level topic edit permissions (All/Posts/None), guest accounts scoped to specific topics, SAML-based SSO and SCIM provisioning (Business+), audit logs (Enterprise). No independent SOC 2 or other compliance certification could be verified from official sources during this review. |
| Setup / operations | Self-service signup with a free tier (no credit card required) up to 10 users; paid tiers are billed per user/month (monthly or annual); Enterprise is sales-assisted with a 100-user minimum and custom terms; 30-day money-back guarantee stated on the pricing page. |

## Strengths

- Free tier (up to 10 users) and clear, publicly listed per-seat pricing for Startup/Business tiers, unusual transparency for this category.
- Purpose-built freshness workflow (post verification with reverification intervals and expiration banners) rather than a purely static wiki.
- Unified search spans both native Slab content and 50+ connected third-party tools.
- Fine-grained permissions (post- and topic-level) plus SSO/SCIM and audit logs on higher tiers for access governance.
- Broad integration catalog (Slack, Google Workspace, GitHub, Jira, Asana, Figma, Zendesk, and more) for embedding external content into docs.

## Limitations

- No official on-premises/self-hosted deployment option — data lives in Slab's multi-tenant cloud.
- AI features (Ask, Predict, full Autofix) and API/webhooks are gated behind the Business tier ($12.50/user/month billed annually) or higher; the free and Startup tiers have limited or no AI/API access.
- No official MCP server or first-party AI-agent connector was found; agent-facing access currently relies on the general-purpose GraphQL API or unofficial/community tooling.
- Content capture is primarily manual authoring and embeds rather than automated ingestion from chats, tickets, CRM, or meeting recordings.
- No independently verifiable compliance certification (e.g., SOC 2) could be confirmed from Slab's own site during this review.

## Best For

- Small-to-midsize teams that want a clean, easy-to-adopt company wiki with real-time collaborative editing and clear pricing, including a usable free tier.
- Organizations whose main need is unified search across a growing set of SaaS tools plus a central place to author docs, onboarding material, and postmortems.
- Teams that want a lightweight, built-in content-freshness process (owner-driven verification) without adopting a separate governance tool.

## Not Ideal For

- Organizations that require self-hosting, data residency control, or on-premises deployment.
- Teams that want to give AI agents deep, automated write-back or MCP-native access to company knowledge out of the box.
- Companies needing automated ingestion of unstructured sources (support tickets, CRM records, meeting transcripts) into the knowledge base rather than manual authoring/embedding.

## Tradeoffs

Slab trades deep, automated knowledge-lifecycle machinery for simplicity and approachability: it is a well-executed, easy-to-use team wiki with genuinely useful freshness (verification) and search features, priced transparently and reachable by very small teams via its free tier — but it is a closed, cloud-only SaaS with AI and programmatic access locked behind higher-priced tiers, and it currently lacks the agent-native interfaces (an official MCP server, deep automated ingestion pipelines) that would make it a first-class "brain" for AI agents rather than a human-facing wiki that agents can only reach through a general API or third-party connectors.

## Official Setup / Evaluation Links

- Product homepage: https://slab.com
- Pricing: https://slab.com/pricing
- Features overview: https://slab.com/features/
- Integrations catalog: https://slab.com/integrations
- Help Center — API & Webhooks: https://help.slab.com/en/articles/6545629-developer-tools-api-webhooks
- Help Center — Post verification: https://help.slab.com/en/articles/4136379-post-verification
- Help Center — Post permissions: https://help.slab.com/en/articles/6390693-post-permissions / Topic permissions: https://help.slab.com/en/articles/2677456-topic-permissions

## Sources

- https://slab.com
- https://slab.com/pricing
- https://slab.com/features/
- https://slab.com/integrations
- https://help.slab.com/en/articles/8810973-ai-predict
- https://help.slab.com/en/articles/6545629-developer-tools-api-webhooks
- https://help.slab.com/en/articles/6390693-post-permissions
- https://help.slab.com/en/articles/2677456-topic-permissions
- https://help.slab.com/en/articles/3904505-user-types
- https://help.slab.com/en/articles/2849252-guest-accounts
- https://help.slab.com/en/articles/4136379-post-verification
- https://github.com/russwyte/slabby (unofficial, community-built MCP server — cited only to support the claim that no official one was found)
