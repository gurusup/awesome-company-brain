# Personal vs. Team

This repo is scoped to company/team knowledge, not individual note-taking (see [Related Lists](../README.md#related-lists) for the personal-scale counterpart). But several entries here are infrastructure layers rather than finished team products — worth knowing before you evaluate them as if they were a turnkey "company brain." Extracted from each [solution profile](../solutions/README.md)'s `Primary users` and `Team / org / role scope` fields.

## Team/Org product (built for teams from day one)

All ten [Enterprise Knowledge Platforms](../solutions/README.md#enterprise-knowledge-platforms), all three [Platform Baselines](../solutions/README.md#platform-baselines), and most of the [Open Source / Self-Hosted](../solutions/README.md#open-source--self-hosted) wikis/RAG apps ship a team-facing product out of the box — multi-user accounts, role/permission scoping, and a UI meant for more than one person: [GuruSup Company Brain](../solutions/gurusup-company-brain.md) 🔹, [Glean](../solutions/glean.md), [Guru](../solutions/guru.md), [Notion AI](../solutions/notion-ai.md), [Confluence](../solutions/confluence.md), [Slab](../solutions/slab.md), [GitBook](../solutions/gitbook.md), [Tettra](../solutions/tettra.md), [Document360](../solutions/document360.md), [Slite](../solutions/slite.md), [Hebbia](../solutions/hebbia.md), [Hjarni](../solutions/hjarni.md), [Microsoft 365 Copilot](../solutions/microsoft-365-copilot.md), [Google Workspace / NotebookLM Enterprise](../solutions/google-notebooklm-enterprise.md), [Amazon Q Business](../solutions/amazon-q-business.md) ⚠️, [Onyx](../solutions/onyx.md), [Outline](../solutions/outline.md), [Docmost](../solutions/docmost.md), [BookStack](../solutions/bookstack.md), [RAGFlow](../solutions/ragflow.md), and [Pad](../solutions/pad.md).

## Scales from personal to team

- **[AnythingLLM](../solutions/anythingllm.md)** — a personal desktop app and a multi-user Docker deployment are both first-class; you choose the mode at setup.
- **[GBrain](../solutions/gbrain.md)** — personal-first agent memory, with a documented (but young, ~5-month-old) "company brain" team mode that needs its own Postgres/Supabase + OAuth setup.

## Infra/building-block (not a finished team product)

These require application or workflow integration on top before a team gets a usable surface — evaluate them as components, not as something you hand a non-technical team on day one:

- **[Cognee](../solutions/cognee.md)** — graph-oriented memory infra via SDK/MCP/API.
- **[Zep / Graphiti](../solutions/zep-graphiti.md)** — temporal graph memory and Graph RAG under an application.
- **[Quivr](../solutions/quivr.md)** ⚠️ — a Python RAG library (`quivr-core`); no team workspace UI exists in the current open-source core.
- **[Hyperspell](../solutions/hyperspell.md)** — a memory/context API for builders, not an end-user app.
- **[OpenViking](../solutions/openviking.md)** — open-source core is a context database agent CLIs plug into; team/company permissions are a separate paid Enterprise layer on top.

## Unknown

[Hyper](../solutions/hyper.md), [Memory Store](../solutions/memory-store.md), and [Wato](../solutions/wato.md) all market themselves as team/org "company brain" products, but are too early-stage to confirm what the team surface actually looks like today — check each profile before assuming team-readiness.

## Reading this page

"Infra/building-block" isn't a knock — [Hyperspell](../solutions/hyperspell.md) and [Cognee](../solutions/cognee.md) are exactly what you want if you're building your own agent product and need a memory layer underneath. It's a mismatch only if you're a non-technical team looking for something to adopt directly — for that, start with the [Team/Org product](#teamorg-product-built-for-teams-from-day-one) list or the [chooser](chooser.md) instead.
