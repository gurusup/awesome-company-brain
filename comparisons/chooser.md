# Chooser: Pick by Lifecycle Gap

Start with whichever stage of the [Company-Brain Lifecycle](../README.md#company-brain-lifecycle) is blocking your team most right now. This page expands on the summary table in the main [README](../README.md#choose-by-lifecycle-gap) with a bit more reasoning per gap.

## Collect scattered company knowledge

If knowledge is stuck in Slack threads, tickets, meeting notes, and people's heads instead of flowing into one place, prioritize connector breadth and low-friction capture: [GuruSup Company Brain](../solutions/gurusup-company-brain.md), [Glean](../solutions/glean.md), and the platform baselines ([Microsoft 365 Copilot](../solutions/microsoft-365-copilot.md), [Google Workspace / NotebookLM Enterprise](../solutions/google-notebooklm-enterprise.md)) are built to pull from many existing sources rather than requiring everyone to move into a new tool first. [Amazon Q Business](../solutions/amazon-q-business.md) fits the same pattern but is closed to new customers as of 2026 — don't start a new evaluation there.

## Organize raw content into durable knowledge

If content exists but is unstructured — no clear owner, no FAQ, no single answer — prioritize wiki-style structure and editorial workflow: [Guru](../solutions/guru.md), [Confluence](../solutions/confluence.md), [Notion AI](../solutions/notion-ai.md), [Slab](../solutions/slab.md), [GitBook](../solutions/gitbook.md), [Tettra](../solutions/tettra.md), [Document360](../solutions/document360.md), and [Slite](../solutions/slite.md) all center on turning content into structured, ownable pages.

## Evolve knowledge as the company changes

If the real risk is stale answers (old pricing, deprecated features, outdated policy), prioritize solutions with explicit review/verification cycles and staleness detection over ones that only index whatever exists today. Most wiki tools above offer some form of verification workflow; check each [solution profile](../solutions/README.md) for specifics before relying on it.

## Use company knowledge inside AI agents and workflows

If the goal is grounding AI agents — support bots, internal copilots, sales assistants — rather than just giving humans a search bar, prioritize agent activation surfaces (MCP, API, SDK, plugins): [GuruSup Company Brain](../solutions/gurusup-company-brain.md), [Onyx](../solutions/onyx.md), [AnythingLLM](../solutions/anythingllm.md), [RAGFlow](../solutions/ragflow.md), [Hebbia](../solutions/hebbia.md), [Cognee](../solutions/cognee.md), [Zep / Graphiti](../solutions/zep-graphiti.md), and [Glean](../solutions/glean.md) are built with agent/API access as a first-class path, not an afterthought.

## Govern, inspect, correct, or control company knowledge

If visibility, permissions, audit trails, and correction workflows matter most (regulated industries, large orgs, customer-facing answers), prioritize solutions with strong role/team scoping and access control: [Confluence](../solutions/confluence.md), the platform baselines, and [GuruSup Company Brain](../solutions/gurusup-company-brain.md) should be evaluated specifically on the [Team / org / role scope](../capabilities/README.md) and [Privacy / access control](../capabilities/README.md) dimensions before adoption.

## Keep everything self-hosted / avoid vendor lock-in

If data residency, long-term cost, or avoiding dependence on a hosted vendor is the primary constraint, look at the [Open Source / Self-Hosted](../solutions/README.md#open-source--self-hosted) layer: [Onyx](../solutions/onyx.md), [Outline](../solutions/outline.md), [Docmost](../solutions/docmost.md), [BookStack](../solutions/bookstack.md), [AnythingLLM](../solutions/anythingllm.md), and [RAGFlow](../solutions/ragflow.md) can all be self-hosted, but you take on the operational burden that hosted platforms absorb for you — weigh that against the [Setup / operations](../capabilities/README.md) dimension for your team's real capacity. [Quivr](../solutions/quivr.md) is also in this layer, but check its profile first: it has stalled as a turnkey app and is now really a RAG library for developers.
