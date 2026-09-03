# Tettra

## Snapshot

- Website / docs: https://tettra.com (help docs: https://support.tettra.com)
- Company / maintainer: Tettra, Inc. Several secondary sources (Tracxn, Getlatka) report that Tettra was acquired by GSoft (Canadian employee-experience software group, since renamed Workleap) in October 2023. This could not be confirmed on a primary source — Tettra's own site only shows a "Copyright © Tettra, Inc." notice with no parent-company mention, and Tettra does not currently appear in Workleap's public product portfolio (Officevibe, ShareGate, Softstart, Didacte). Tettra also made its own acquisition (Supportman.io, Nov 2024), consistent with it still operating as an independently branded product/company. Ownership status: Unknown with certainty — treat as Tettra, Inc., possibly under a holding company.
- Status: Active commercial product (ongoing feature releases visible in its public changelog as of 2026).
- Open source: No — proprietary, closed-source SaaS.
- Deployment: Cloud-hosted SaaS only. No on-premises or self-hosted option found on the website, pricing page, or help docs.
- Primary users: Small and mid-market companies (per G2 reviewer data: ~53% small business ≤50 employees, ~45% mid-market 51–1,000 employees, ~2% enterprise). Common use cases cited on the site and in reviews: internal company wikis/onboarding docs, customer support teams, HR/ops, agencies and professional-services firms. Heaviest G2 reviewer industries: marketing/advertising, computer software, financial services.
- Best company-brain role: Lightweight, Slack-native internal wiki with an AI Q&A bot ("Kai") that answers employee questions from existing docs and routes unanswered ones to subject-matter experts.
- Last reviewed: 2026-08-31

## One-line Summary

Tettra is a cloud-hosted internal wiki and knowledge-base SaaS product, most notable for its Slack-native AI bot ("Kai") that answers employee questions from company docs and for built-in workflows to keep pages verified and up to date.

## Company-Brain Fit

Tettra covers most of the knowledge lifecycle for a single company wiki, but shallowly outside Slack/Docs/Notion. **Collect**: pages are authored natively or imported from Google Docs, Notion, and markdown files; Kai also scans Slack channels and can turn Q&A threads or whole conversations into new wiki pages with one click. **Organize**: content lives in categories and (newer) freeform "Team Tags," with AI-assisted page tagging and semantic search to aid retrieval. **Evolve**: Tettra's most distinctive feature set is knowledge upkeep — pages have an assigned owner/subject-matter expert, a "Verification" workflow that reminds owners to periodically re-confirm content, and automated reports that surface stale (unviewed/unedited 3+ months), unowned, or publicly-visible pages for cleanup. **Use**: Kai answers questions directly inside Tettra or Slack (via @mention, DM, or automatic in-channel answers) by searching indexed content, and escalates unanswered questions to a designated expert rather than guessing. **Govern**: role-based permissions, private categories restricted to specific teams/groups, and (on the Enterprise tier) SSO/SCIM with directory-group sync for access control and automatic deprovisioning. Overall it's best framed as a well-scoped Slack/Docs-centric team wiki with genuine freshness tooling, not a broad enterprise-wide connector hub pulling from tickets, CRM, or meetings.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Multi-tenant cloud SaaS only; no self-hosted/on-prem option found. You do not own the infrastructure — Tettra, Inc. hosts and operates it. |
| Context capture (docs, wikis, chats, tickets, CRM, meetings) | Narrow but deliberate: native page editor, import from Google Docs/Google Drive folders and Notion, markdown import, and Slack (manual "Summarize & Save" of threads, or automatic capture of Q&A Kai couldn't answer). No native ticketing (Zendesk/Jira), CRM, or meeting-transcript capture; Zapier/API can bridge some of these with custom setup. |
| Knowledge organization | Pages grouped into categories plus newer freeform "Team Tags"; AI-assisted page tagging; semantic search across content. Structure is comparatively flat/simple next to full enterprise wikis (e.g., Confluence). |
| Knowledge evolution (freshness, dedup, review cycles) | A named strength: each page can have an owner/subject-matter expert; scheduled "Verification" workflow reminds owners to re-confirm accuracy; automated "Stale pages" report flags pages unviewed/unedited 3+ months; "Content suggestions" surfaces unowned or publicly-visible pages for cleanup. No explicit automated dedup of near-duplicate pages was found. |
| Retrieval / use (search, grounding, citations) | Kai (AI bot) answers questions in Tettra or Slack by searching indexed content and grounding answers in existing pages; unanswered questions are routed to a human expert rather than the bot guessing. Semantic search is available for manual lookup. Explicit inline source-citation behavior in Kai's answers was not independently verified beyond "searches through your content." |
| Agent activation / write-back (MCP, API, Slack/Teams, support bots) | Slack is the primary chat surface (slash commands, DM, @mention, auto-answers, link previews). A public API exists (described by Tettra as "limited"/experimental) supporting page creation, page requests, search, and asking questions — suited for custom scripts/Zapier-style automation, not a general write-back framework. No official Microsoft Teams app or MCP server was found; Teams connectivity exists only via third-party no-code tools (Zapier). |
| Activation evidence (proof retrieved context is actually used, not just retrievable) | Unknown — Kai is described only as "searches through your content" with no independently verified inline source-citation behavior, so there's no documented trail of what context a given answer actually used. |
| Team / org / role scope | Role-based permissions (e.g., admin, editor, read-only/guest); private categories restricted to specific teams or synced directory groups; a public-facing website-publishing option for external-facing docs. |
| Feedback / correction | Page-request workflow lets teammates request new/updated pages from an owner; Kai can prompt someone to save an answer as new knowledge when it can't answer a question; verification cycles function as a structured correction/refresh loop. No dedicated inline "this answer was wrong" feedback mechanism was independently verified. |
| Privacy / access control | Role-based access control at the category/page level; SSO/SAML and SCIM (with optional directory-group sync) are available but gated to the higher (Enterprise/"Professional") plan; deprovisioned directory users are automatically removed from Tettra. |
| Setup / operations | Self-serve signup with a 30-day free trial; no installation required (pure SaaS); Slack app install plus optional Google Workspace/Notion/GitHub/Zapier connections; SSO/SCIM setup requires the higher-tier plan and is done through Tettra's admin settings (built on WorkOS). |

## Strengths

- Purpose-built freshness tooling (owner-based Verification workflow, Stale-pages report, unowned/public-content surfacing) that many lighter wiki tools lack.
- Deep, genuinely Slack-native workflow: Kai can auto-answer in channel, capture Q&A threads into new pages, and be DMed privately, going beyond a simple "search box in Slack" integration.
- Low setup friction — no infrastructure to run, self-serve trial, and import paths from Google Docs and Notion for migrating existing content.
- Straightforward permissioning (categories, roles, private/public content) that is easy for a small ops or support team to administer without a dedicated admin.

## Limitations

- Content capture is limited to a small set of first-party integrations (Slack, Google Docs/Drive, Notion, GitHub, Zapier); no native connectors for ticketing systems, CRM, or meeting transcripts.
- No official Microsoft Teams app or MCP server; Teams and other tool connectivity depends on third-party automation (Zapier) or the limited/experimental public API.
- SSO/SCIM and other governance features are reserved for the higher-priced (Enterprise/Professional) tier, not available on the entry Scaling plan.
- No self-hosted or private-cloud deployment option — data always lives in Tettra's multi-tenant SaaS.
- Company ownership/parent-entity status is unclear from primary sources (see Snapshot note), which matters for buyers doing vendor-risk diligence.

## Best For

- Small-to-mid-market teams (roughly 10–500 employees) that live in Slack and want a lightweight internal wiki with an AI Q&A layer, without standing up infrastructure.
- Organizations that specifically want a structured process for keeping documentation from going stale (owner-based verification, stale-content reports).
- Support, HR/ops, or agency teams migrating existing docs from Google Docs or Notion into a single Slack-connected knowledge base.

## Not Ideal For

- Enterprises needing a single company brain that natively ingests tickets, CRM records, and meeting transcripts alongside docs and chat — Tettra's capture surface is narrower than that.
- Teams standardized on Microsoft Teams as their primary chat tool, given the lack of an official Teams integration.
- Organizations requiring self-hosted/on-prem deployment or wanting SSO/SCIM without committing to the top pricing tier.

## Tradeoffs

Tettra optimizes for being a well-scoped, low-friction Slack-and-docs wiki with unusually strong content-freshness discipline (ownership, verification cycles, stale-content reports) rather than for being a broad, all-source enterprise knowledge hub. That focus is its main strength for small/mid-market teams that just need reliable, current answers inside Slack, but it also means buyers evaluating it as a general-purpose "company brain" for agentic AI should weigh its narrow integration surface (no native tickets/CRM/meetings, no MCP server, no official Teams app, and a self-described "limited" API) and its SaaS-only, higher-tier-gated governance model against tools built for broader multi-source ingestion.

## Official Setup / Evaluation Links

- Product overview: https://tettra.com
- Pricing: https://tettra.com/pricing/
- Help / setup docs: https://support.tettra.com
- Kai AI features: https://support.tettra.com/kai-ai-features
- API overview: https://support.tettra.com/api-overview/what-is-the-tettra-api
- Integrations list: https://support.tettra.com/integrations
- SSO/SCIM setup: https://support.tettra.com/ssoscim/setting-up-ssoscim-professional-plan-only-1
- Product changelog: https://changelog.tettra.co/

## Sources

- https://tettra.com
- https://tettra.com/pricing/
- https://tettra.com/product/
- https://support.tettra.com/kai-ai-features
- https://support.tettra.com/kai-ai-features/ai-auto-answers-in-slack
- https://support.tettra.com/kai-ai-features/automatically-find-and-save-existing-answers-from-slack
- https://support.tettra.com/ssoscim/setting-up-ssoscim-professional-plan-only-1
- https://support.tettra.com/ssoscim/what-to-expect-from-ssoscim-professional-plan-only-1
- https://support.tettra.com/ssoscim/how-to-set-permissions-based-on-groups
- https://support.tettra.com/api-overview/what-is-the-tettra-api
- https://support.tettra.com/integrations
- https://support.tettra.com/collaborating-on-pages/about-the-knowledge-management-dashboard
- https://changelog.tettra.co/
- https://tettra.com/article/supportman-acquisition/
- https://www.g2.com/products/tettra/reviews
- https://www.g2.com/products/tettra/pricing
- https://tracxn.com/d/companies/tettra/__JVtj9VXILm79nlV_xQ_C6Ulwr24KnAcY1K2QX6uhzco
- https://getlatka.com/companies/tettra
- https://workleap.com/blog/gsoft-becomes-workleap
