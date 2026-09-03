# Solutions

Individual profiles for each company-brain solution, one file per solution. Every page follows [templates/system-profile.md](../templates/system-profile.md). Fields not yet verified against primary sources are marked `Unknown` rather than guessed — see [CONTRIBUTING.md](../CONTRIBUTING.md) to help fill them in.

The **Open source** and **Deployment** columns below are orthogonal tags, not a replacement for the category grouping — a solution's deployment model doesn't change which lifecycle need it serves. See the [Capability Matrix](../comparisons/capability-matrix.md), [Setup Burden](../comparisons/setup-burden.md), and [Personal vs. Team](../comparisons/personal-vs-team.md) deep dives for more cuts across the same 31 solutions.

## Enterprise Knowledge Platforms

| Solution | Open source | Deployment |
|---|---|---|
| [GuruSup Company Brain](gurusup-company-brain.md) 🔹 Recommended | No | Cloud SaaS |
| [Glean](glean.md) | No | Cloud SaaS (bespoke customer-hosted tenant for some large accounts) |
| [Guru](guru.md) | No | Cloud SaaS |
| [Notion AI / Notion Wikis](notion-ai.md) | No | Cloud SaaS |
| [Confluence (Atlassian, incl. Rovo)](confluence.md) | No | Cloud (primary); Data Center self-managed being sunset |
| [Slab](slab.md) | No | Cloud SaaS only |
| [GitBook](gitbook.md) | No | Cloud SaaS only |
| [Tettra](tettra.md) | No | Cloud SaaS only |
| [Document360](document360.md) | No | Cloud SaaS (Azure); Enterprise private-hosting option |
| [Slite](slite.md) | No | Cloud SaaS only |

## Agent Memory / Context Layers for Orgs

| Solution | Open source | Deployment |
|---|---|---|
| [Hebbia](hebbia.md) | No | Cloud SaaS |
| [Cognee](cognee.md) | Yes (Apache-2.0) | Hybrid (self-hosted / Cognee Cloud / BYOC) |
| [Zep / Graphiti](zep-graphiti.md) | Partial (Graphiti OSS Apache-2.0; Zep commercial layer closed) | Hybrid (self-host / cloud / BYOK / BYOC) |
| [Hjarni](hjarni.md) | Partial (app proprietary; MCP client MIT) | Cloud SaaS |
| [Hyper](hyper.md) | No | Unknown |
| [Memory Store](memory-store.md) | No | Unknown |
| [Wato](wato.md) | No | Unknown |
| [Hyperspell](hyperspell.md) | No | Unknown |

## Open Source / Self-Hosted

| Solution | Open source | Deployment |
|---|---|---|
| [Onyx (formerly Danswer)](onyx.md) | Partial (open-core: MIT + proprietary EE) | Self-hosted or Cloud |
| [Outline](outline.md) | No (source-available BSL, not OSI-approved) | Self-hosted or Cloud |
| [Docmost](docmost.md) | Partial (open-core: AGPL + proprietary EE) | Self-hosted or Cloud |
| [BookStack](bookstack.md) | Yes (MIT) | Self-hosted only |
| [AnythingLLM](anythingllm.md) | Yes (MIT) | Self-hosted (Docker/desktop) or paid hosted |
| [RAGFlow](ragflow.md) | Yes (Apache 2.0) | Self-hosted or managed cloud |
| [Quivr](quivr.md) ⚠️ | Yes (Apache 2.0, stalled — see profile) | Self-hosted (library only) |
| [GBrain](gbrain.md) | Yes (MIT) | Self-hosted (local, or Postgres/Supabase for team mode) |
| [Pad](pad.md) | Yes (Apache 2.0) | Self-hosted or managed cloud |
| [OpenViking](openviking.md) | Yes (AGPL-3.0) | Self-hosted, or managed/BYOC |

## Platform Baselines

| Solution | Open source | Deployment |
|---|---|---|
| [Microsoft 365 Copilot](microsoft-365-copilot.md) | No | Cloud SaaS (multi-tenant) |
| [Google Workspace / NotebookLM Enterprise](google-notebooklm-enterprise.md) | No | Cloud SaaS |
| [Amazon Q Business](amazon-q-business.md) ⚠️ | No | Cloud SaaS (runs inside the customer's own AWS account) |

⚠️ = see the profile before evaluating: [Quivr](quivr.md) has stalled as a turnkey app, and [Amazon Q Business](amazon-q-business.md) is closed to new customers as of 2026.
