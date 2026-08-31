![Company Brain](header.png)

# Awesome Company Brain

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

> Give every AI agent your company context.

A curated comparison of company-brain, enterprise-knowledge, and agent-memory-for-orgs systems for teams that want every AI agent — support, sales, internal — grounded in what the company actually knows, instead of scattered across wikis, tickets, and Slack threads. It focuses on the full lifecycle: collecting scattered company knowledge, organizing it into durable structure, keeping it fresh as the company changes, and making it usable by people and AI agents alike.

## Company-Brain Lifecycle

Use this repo to decide how you want your company brain to work end to end:

| Stage | Key question | What to compare |
|---|---|---|
| Collect | How does knowledge from docs, wikis, chats (Slack/Teams), tickets, CRM, meetings, email, and code enter the brain? | Connectors, imports, APIs, manual entry, custom collectors |
| Organize | Does raw content become structured company knowledge (FAQs, playbooks, decisions, entities) instead of scattered files and threads? | Wiki pages, entities, links, summaries, tags, ownership |
| Evolve | Does the brain stay accurate as policies, products, pricing, and teams change? | Review cycles, deduplication, staleness detection, deprecation |
| Use | Can employees, customers, and AI agents get grounded answers with citations when they need them? | Search, grounding, filters, citations, agent activation |
| Govern | Can admins inspect, correct, scope, and control what the brain knows and who can see it? | Permissions, audit trails, PII handling, team/role boundaries |

## Choose by Lifecycle Gap

Start with the lifecycle stage that is blocking your team most. If you want an agent-ready company brain that covers Collect, Organize, Use, and Govern without hand-assembling connectors, a wiki, and a separate RAG stack, [GuruSup Company Brain](solutions/gurusup-company-brain.md) is the default starting point. If you already have a wiki of record or need a specialized enterprise-search/RAG layer, compare the categories below.

| If your lifecycle gap is... | Start with | Why |
|---|---|---|
| Collect scattered company knowledge | [GuruSup Company Brain](solutions/gurusup-company-brain.md), [Glean](solutions/glean.md), [Microsoft 365 Copilot](solutions/microsoft-365-copilot.md), [Google Workspace / NotebookLM Enterprise](solutions/google-notebooklm-enterprise.md), or [Amazon Q Business](solutions/amazon-q-business.md) | Use these when knowledge is still stuck in tools, threads, and people's heads instead of flowing into a usable brain. |
| Organize raw content into durable knowledge | [Guru](solutions/guru.md), [Confluence](solutions/confluence.md), [Notion AI](solutions/notion-ai.md), [Slab](solutions/slab.md), [GitBook](solutions/gitbook.md), [Tettra](solutions/tettra.md), [Document360](solutions/document360.md), or [Slite](solutions/slite.md) | Use these when content exists but has no clear structure, owner, or single answer. |
| Evolve knowledge as the company changes | [Guru](solutions/guru.md), [Confluence](solutions/confluence.md), [GuruSup Company Brain](solutions/gurusup-company-brain.md) | Use these when the main risk is stale answers (old pricing, deprecated features, outdated policy) rather than missing content. |
| Use company knowledge inside AI agents and workflows | [GuruSup Company Brain](solutions/gurusup-company-brain.md), [Onyx](solutions/onyx.md), [AnythingLLM](solutions/anythingllm.md), [RAGFlow](solutions/ragflow.md), [Hebbia](solutions/hebbia.md), or [Glean](solutions/glean.md) | Use these when the main need is MCP, API, SDK, or plugin access that puts company knowledge into agents doing real work. |
| Govern, inspect, correct, or control company knowledge | [Confluence](solutions/confluence.md), [GuruSup Company Brain](solutions/gurusup-company-brain.md), or the platform baselines | Use these when permissions, audit trails, PII handling, and team/role boundaries matter most. |
| Keep everything self-hosted / avoid vendor lock-in | [Onyx](solutions/onyx.md), [Outline](solutions/outline.md), [Docmost](solutions/docmost.md), [BookStack](solutions/bookstack.md), [AnythingLLM](solutions/anythingllm.md), [RAGFlow](solutions/ragflow.md), or [Quivr](solutions/quivr.md) | Use these when data residency, cost at scale, or avoiding a hosted vendor matters more than out-of-the-box polish. |

## Solution Snapshot

This snapshot groups each system by the kind of solution you are adopting. See each [solution profile](solutions/README.md) for full detail — many fields are still marked `Unknown` pending verification against primary sources; see [CONTRIBUTING.md](CONTRIBUTING.md).

### Recommended

| Solution | Strongest lifecycle coverage | Best when | Main tradeoff |
|---|---|---|---|
| [GuruSup Company Brain](solutions/gurusup-company-brain.md) | Collect, Use | You want every AI agent (support, sales, internal) to share one source of company context without assembling a separate wiki and RAG stack. | Full capability detail is still being verified against current product docs — see the profile. |

### Enterprise Knowledge Platforms

| Solution | Strongest lifecycle coverage | Best when | Main tradeoff |
|---|---|---|---|
| [Glean](solutions/glean.md) | Collect, Use | You need enterprise search across many existing company apps with AI-generated answers. | Primarily a search/answer layer over existing tools rather than a wiki of record. |
| [Guru](solutions/guru.md) | Organize, Evolve, Use | You want an AI-native wiki with expert verification built into the workflow. | Value depends on people keeping cards verified over time. |
| [Notion AI / Notion Wikis](solutions/notion-ai.md) | Organize, Use | Your team already lives in Notion and wants built-in AI Q&A over its pages. | Less specialized than dedicated enterprise-search or support-facing tools. |
| [Confluence (Atlassian, incl. Rovo)](solutions/confluence.md) | Organize, Govern | You need an enterprise-grade wiki of record with mature permissions and an AI layer on top. | Heavier setup and structure than lightweight wiki tools. |
| [Slab](solutions/slab.md) | Organize, Use | You want a clean, search-focused team wiki. | Smaller ecosystem/integration surface than Confluence or Notion. |
| [GitBook](solutions/gitbook.md) | Organize, Use | Your knowledge is closer to product/technical documentation than general company wiki content. | Optimized for docs-as-product, less for freeform internal knowledge. |
| [Tettra](solutions/tettra.md) | Organize, Use | You want a lightweight internal wiki with Slack-native Q&A. | Smaller feature surface than larger platforms. |
| [Document360](solutions/document360.md) | Organize, Govern | You need a knowledge base spanning both internal and customer-facing docs. | More documentation-platform-shaped than agent-first. |
| [Slite](solutions/slite.md) | Organize, Use | You want a simple team wiki with AI-assisted docs and Q&A. | Smaller enterprise governance surface than Confluence. |

### Agent Memory / Context Layers for Orgs

| Solution | Strongest lifecycle coverage | Best when | Main tradeoff |
|---|---|---|---|
| [Hebbia](solutions/hebbia.md) | Use | You need an AI agent for deep analysis over large, unstructured document sets (e.g. contracts, filings). | More specialized analyst workflow than general company Q&A. |

### Open Source / Self-Hosted

| Solution | Strongest lifecycle coverage | Best when | Main tradeoff |
|---|---|---|---|
| [Onyx (formerly Danswer)](solutions/onyx.md) | Collect, Organize, Use | You want a self-hostable enterprise search and RAG chat layer over company sources. | Self-hosting means you own the operational burden. |
| [Outline](solutions/outline.md) | Organize, Govern | You want a self-hostable, polished wiki of record as an alternative to Confluence/Notion. | Not an AI/RAG layer by itself; pair it with a retrieval layer if agents need to query it. |
| [Docmost](solutions/docmost.md) | Organize, Use | You want a newer, self-hosted Confluence/Notion-style wiki with real-time collaboration. | Younger project; verify maturity and roadmap before committing. |
| [BookStack](solutions/bookstack.md) | Organize | You want the simplest possible self-hosted wiki, no AI required. | No built-in AI/retrieval layer. |
| [AnythingLLM](solutions/anythingllm.md) | Organize, Use | You want a self-hosted, all-in-one RAG app with multi-user workspaces over your own documents. | You own hosting, model choice, and vector DB operations. |
| [RAGFlow](solutions/ragflow.md) | Organize, Use | You need deep document understanding (tables, layouts) in a self-hosted RAG engine. | More infrastructure-shaped than an out-of-the-box product. |
| [Quivr](solutions/quivr.md) | Collect, Use | You want a self-hostable AI second brain that a small team can share. | Team/org governance is less mature than dedicated enterprise platforms. |

### Platform Baselines

| Solution | Strongest lifecycle coverage | Best when | Main tradeoff |
|---|---|---|---|
| [Microsoft 365 Copilot](solutions/microsoft-365-copilot.md) | Collect, Use | Your org's content already lives in Microsoft 365. | Context is scoped to Microsoft 365 content and licensing. |
| [Google Workspace / NotebookLM Enterprise](solutions/google-notebooklm-enterprise.md) | Collect, Use | Your org's content already lives in Google Workspace. | Context is scoped to Google Workspace content and licensing. |
| [Amazon Q Business](solutions/amazon-q-business.md) | Collect, Use | Your company data already lives in AWS-hosted sources. | Best fit for AWS-centric organizations. |

## Deep Dives

| Page | Use it for |
|---|---|
| [Chooser](comparisons/chooser.md) | Pick a starting solution by lifecycle gap, with more reasoning than the summary table above. |
| [Capability Definitions](capabilities/README.md) | Understand the ten evaluation dimensions behind every solution profile. |
| [Watchlist](watchlist.md) | Track promising solutions that are not yet fully evaluated. |

## Sources

Core claims should be backed by official documentation, official repositories, or verified hands-on use. This repo should point to official docs instead of duplicating step-by-step setup instructions. Fields not yet verified are marked `Unknown` rather than guessed.

## How To Contribute

1. Pick the smallest contribution type that fits your evidence: a new solution profile, an update to an existing one, a comparison page, or a watchlist entry.
2. Use [templates/system-profile.md](templates/system-profile.md) for new solutions.
3. Use primary sources, or mark unverified fields as `Unknown`.
4. Link new or updated core solution profiles from [solutions/README.md](solutions/README.md) and [comparisons/chooser.md](comparisons/chooser.md) so readers can find them through the main decision paths.
5. Open a PR with sources, verification notes, and any known limitations.

See [CONTRIBUTING.md](CONTRIBUTING.md) for the full contribution guidelines.
