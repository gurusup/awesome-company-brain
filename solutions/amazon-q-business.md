# Amazon Q Business

## Snapshot

- Website / docs: https://aws.amazon.com/q/business/
- Company / maintainer: AWS (Amazon Web Services)
- Status: Closed to new customers as of 2026. AWS continues bug fixes and security updates for existing customers only; new feature development has stopped. AWS is directing prospective and existing customers to migrate to Amazon Quick, described by AWS as "the next evolution of Amazon Q Business."
- Open source: No — proprietary AWS managed service.
- Deployment: Fully managed AWS service; the application and its index run inside the customer's own AWS account and chosen AWS Region, built on Amazon Bedrock.
- Primary users: Enterprise employees at organizations already on AWS — from frontline/help-desk style Q&A (Lite tier) to broader knowledge-worker productivity (Pro tier).
- Best company-brain role: Platform baseline: AI grounded in AWS-hosted company data sources
- Last reviewed: 2026-08-31

## One-line Summary

Amazon Q Business is AWS's fully managed enterprise generative-AI assistant that indexes content from 40+ connected data sources and answers natural-language questions with citations while respecting source-system permissions — now closed to new customers and being superseded by Amazon Quick.

> [!WARNING]
> Closed to new customers as of 2026. AWS is directing prospective and existing customers to its successor, "Amazon Quick." Do not start a new evaluation here — see [Tradeoffs](#tradeoffs) below.

## Company-Brain Fit

Amazon Q Business's context is scoped to an AWS-managed index built from connected data sources inside the customer's own AWS account/region — an AWS-ecosystem-centric baseline, though it reaches many non-AWS SaaS sources via connectors. Collect: 40+ built-in connectors (S3, SharePoint, Confluence, Salesforce, ServiceNow, Slack, Jira, Google Drive, Gmail, Zendesk, GitHub, and more) plus a custom-connector API and a web crawler. Organize: automatic content indexing and metadata extraction on ingest, with document-level ACLs crawled from source systems and enabled by default. Evolve: per-connector sync schedules (full or incremental) configurable via console or API — no separate "review cycle" concept. Use: a chat interface with citations, "Q Apps" for building lightweight no-code AI apps, and plugins/actions that can act in connected third-party systems, with chat orchestration auto-routing requests across data sources and plugins. Govern: IAM Identity Center-based identity, permissions-aware responses that respect source-system access controls, and admin guardrails (blocked phrases, response-scope restriction). Because deployment, identity, and the index all live inside a single AWS account/region, it is best understood as an AWS-native layer over an organization's content rather than a cloud-agnostic company brain — and, as of this review, it is a legacy product being wound down in favor of Amazon Quick.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Fully managed AWS service; app and index deployed in the customer's AWS account; region choice determines data residency; 3-AZ availability for the Enterprise index tier, single-AZ for Starter. |
| Context capture (docs, wikis, chats, tickets, CRM, meetings) | 24+ named native connectors documented, including S3, SharePoint (Cloud and Server), Confluence (Cloud and Server), OneDrive, Exchange, Salesforce, ServiceNow, Jira, Slack, Microsoft Teams, Google Drive, Gmail, Google Calendar (preview), GitHub (Cloud and Server), Box, Dropbox, Zendesk, Smartsheet, Asana (preview) — plus a custom connector API and web crawler. |
| Knowledge organization | Automatic indexing and metadata extraction on ingest; no manual wiki-curation step; admins can apply metadata/relevance boosting to tune ranking. |
| Knowledge evolution (freshness, dedup, review cycles) | Configurable per-connector sync run schedules (full vs. incremental) via console or the CreateDataSource API. |
| Retrieval / use (search, grounding, citations) | Natural-language chat with source citations; admins can restrict responses to enterprise data only or allow LLM fallback; "Q Apps" (Pro tier only) let users build lightweight AI apps from a natural-language description, shareable via an org-wide app library; chat orchestration auto-routes a request across data sources and plugins. |
| Agent activation / write-back (MCP, API, Slack/Teams, support bots) | Amazon Q Business API (console, API, CLI, SDKs); built-in plugins take actions in Jira, Salesforce, ServiceNow, PagerDuty, Asana, Confluence, Google Calendar, and Microsoft Exchange/Teams, with custom plugins via a CreatePlugin API; Slack, Microsoft Teams, and Outlook/Word integrations plus browser extensions on the Pro tier. Native MCP support is not documented for Q Business itself — MCP appears only as a bridging mechanism in AWS's migration guide to the successor product, Amazon Quick. |
| Activation evidence (proof retrieved context is actually used, not just retrievable) | Strong — chat responses include source citations, and admins can restrict responses to enterprise data only or allow LLM fallback, giving a visible, user-facing signal of whether an answer is actually grounded in retrieved content. |
| Team / org / role scope | IAM Identity Center (or IAM federation) for SSO/identity; document-level ACLs crawled from source systems, on by default. Two subscription tiers: Lite (Q&A only, no plugins) and Pro (adds Q Apps, plugins, and Slack/Teams integrations); the Pro tier ships with a reduced feature set in at least two regions (Europe/Ireland, Asia Pacific/Sydney). |
| Feedback / correction | Thumbs-up/thumbs-down on every chat response, with a reason prompt on negative feedback (harmful, not accurate, not useful/incomplete, other); admin-configurable blocked phrases with a custom fallback message; built-in hallucination mitigation for text-based RAG responses (mutually exclusive with chat orchestration). |
| Privacy / access control | Responses respect the requesting user's source-system permissions; encryption at rest via AWS KMS and TLS in transit; formal compliance validation cited for HIPAA, SOC 1/2/3, PCI, and ISO 42001; AWS states Amazon Q Business does not use customer data to improve the service or to train underlying LLMs; standard AWS shared-responsibility model applies. |
| Setup / operations | Set up via the AWS Management Console, API, CLI, or SDKs; requires an AWS account and, for full functionality, IAM Identity Center configuration. Pricing is two-part — per-user subscription plus separately billed index capacity — with a documented 60-day free trial (up to 50 users and 1,500 index hours). Exact prices below are as published on AWS's pricing page as of 2026-08-31 and should be reverified before quoting. |

## Strengths

- Very broad native connector catalog (24+ named connectors spanning cloud storage, wikis, CRM/ITSM, chat, calendar, and code hosting) plus a custom-connector API and web crawler.
- Permissions-aware retrieval with ACL crawling on by default, and an explicit AWS statement that customer data is not used to train underlying models.
- Two-tier pricing separates a low-cost, broad-seat "answers only" tier (Lite) from a higher-cost "acts on your behalf" tier (Pro) rather than one-size-fits-all licensing.
- Built-in hallucination mitigation and admin-configurable guardrails (blocked phrases, response-scope restriction) are part of the managed service.
- Formal third-party compliance validation (HIPAA, SOC 1/2/3, PCI, ISO 42001) inherited from AWS infrastructure.

## Limitations

- The product is closed to new customers and in maintenance-only mode, with AWS actively steering customers toward Amazon Quick — this is the single most important fact for anyone evaluating it today.
- Significant feature gating behind the Pro tier: Q Apps, all plugins, and third-party chat integrations (Slack/Teams) are unavailable on the Lite tier, effectively requiring the higher-priced tier for any agentic use case.
- Chat orchestration (the auto-routing/agentic layer) is documented as optimized for English-language content, implying weaker support for other languages.
- Pro-tier feature set is reduced in at least two regions (Europe/Ireland, Asia Pacific/Sydney).
- Index capacity is unit-based and capped per index unit, so cost and operational complexity scale directly with content volume; setup also requires AWS account/console fluency and, for full features, IAM Identity Center configuration.

## Best For

- Existing Amazon Q Business customers who want continuity while planning a phased migration to Amazon Quick.
- Organizations already standardized on AWS that want a permissions-aware Q&A layer over existing enterprise content without building custom RAG infrastructure.
- Enterprise IT/HR/benefits help-desk style Q&A at broad employee scale via the lower-cost Lite tier.

## Not Ideal For

- Any organization evaluating a brand-new deployment today — AWS itself directs prospective new customers to Amazon Quick instead.
- Multi-cloud or non-AWS-centric organizations, since deployment, identity, and the index all live inside a single AWS account/region.
- Teams needing action/agent capability (plugins, Q Apps) on a budget, since that functionality is Pro-tier only.

## Tradeoffs

Amazon Q Business trades broad, natively-integrated data access and strong out-of-the-box governance (ACL-aware indexing, IAM Identity Center SSO, formal compliance certifications, an explicit no-training-on-customer-data stance) for deep AWS lock-in and a two-tier pricing structure that pushes any real agentic capability (Q Apps, plugins, third-party integrations) into the pricier Pro tier. Its most consequential tradeoff today, however, is temporal: AWS has stopped accepting new customers and is steering the product toward Amazon Quick, so what otherwise reads as a mature, well-documented enterprise-AI-memory platform is, as of this review, a legacy path — evaluating it today means evaluating a bridge to a different, less-documented successor product rather than a platform with its own forward roadmap.

## Official Setup / Evaluation Links

- [Product overview](https://aws.amazon.com/q/business/)
- [Pricing](https://aws.amazon.com/q/business/pricing/)
- [Features](https://aws.amazon.com/q/business/features/)
- ["What is Amazon Q Business" (user guide)](https://docs.aws.amazon.com/amazonq/latest/qbusiness-ug/what-is.html)
- [Availability change / migration guide to Amazon Quick](https://docs.aws.amazon.com/amazonq/latest/qbusiness-ug/qbusiness-availability-change.html)

## Sources

- [Amazon Q Business product page](https://aws.amazon.com/q/business/)
- [Amazon Q Business pricing](https://aws.amazon.com/q/business/pricing/)
- [Amazon Q Business features](https://aws.amazon.com/q/business/features/)
- ["What is Amazon Q Business" user guide](https://docs.aws.amazon.com/amazonq/latest/qbusiness-ug/what-is.html)
- [Availability change / migration guide to Amazon Quick](https://docs.aws.amazon.com/amazonq/latest/qbusiness-ug/qbusiness-availability-change.html)
- [Supported connectors](https://docs.aws.amazon.com/amazonq/latest/qbusiness-ug/supported-connectors.html)
- [Connectors list](https://docs.aws.amazon.com/amazonq/latest/qbusiness-ug/connectors-list.html)
- [Guardrails and global controls](https://docs.aws.amazon.com/amazonq/latest/qbusiness-ug/guardrails-global-controls.html)
- [Data protection](https://docs.aws.amazon.com/amazonq/latest/qbusiness-ug/data-protection.html)
- [Service improvement / data-use statement](https://docs.aws.amazon.com/amazonq/latest/qbusiness-ug/service-improvement.html)
- [Compliance validation](https://docs.aws.amazon.com/amazonq/latest/qbusiness-ug/compliance-validation.html)
- [Subscription tiers](https://docs.aws.amazon.com/amazonq/latest/qbusiness-ug/tiers.html)
