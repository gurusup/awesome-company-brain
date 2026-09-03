# Capability Matrix

A single-glance view of all 31 solutions against the [ten... now eleven evaluation dimensions](../capabilities/README.md). Ratings are the maintainers' synthesis of what's documented in each [solution profile](../solutions/README.md) — `Strong` (well-documented and robust), `Partial` (present but limited or partially documented), `Weak` (present but noticeably thin), `Unknown` (not documented in the profile). This is not an independent audit; click through to a profile for the primary sources behind any rating before relying on it.

Columns (abbreviated — see [Capability Definitions](../capabilities/README.md) for full text): **Deploy** = Deployment/ownership, **Capture** = Context capture, **Organize** = Knowledge organization, **Evolve** = Knowledge evolution, **Retrieve** = Retrieval/use, **Activate** = Agent activation/write-back, **Evidence** = Activation evidence, **Scope** = Team/org/role scope, **Feedback** = Feedback/correction, **Privacy** = Privacy/access control, **Setup** = Setup/operations.

## Enterprise Knowledge Platforms

| Solution | Deploy | Capture | Organize | Evolve | Retrieve | Activate | Evidence | Scope | Feedback | Privacy | Setup |
|---|---|---|---|---|---|---|---|---|---|---|---|
| [GuruSup Company Brain](../solutions/gurusup-company-brain.md) 🔹 | Partial | Partial | Partial | Partial | Partial | Partial | Unknown | Partial | Partial | Partial | Weak |
| [Glean](../solutions/glean.md) | Strong | Strong | Strong | Partial | Strong | Strong | Partial | Strong | Unknown | Strong | Weak |
| [Guru](../solutions/guru.md) | Partial | Strong | Strong | Strong | Strong | Strong | Strong | Strong | Strong | Strong | Weak |
| [Notion AI](../solutions/notion-ai.md) | Weak | Partial | Strong | Weak | Strong | Strong | Unknown | Partial | Weak | Strong | Strong |
| [Confluence](../solutions/confluence.md) | Partial | Strong | Partial | Weak | Strong | Partial | Partial | Strong | Unknown | Partial | Strong |
| [Slab](../solutions/slab.md) | Weak | Weak | Partial | Strong | Partial | Weak | Unknown | Partial | Partial | Partial | Strong |
| [GitBook](../solutions/gitbook.md) | Weak | Weak | Partial | Partial | Partial | Strong | Unknown | Partial | Weak | Partial | Strong |
| [Tettra](../solutions/tettra.md) | Weak | Weak | Partial | Strong | Partial | Weak | Unknown | Partial | Partial | Partial | Strong |
| [Document360](../solutions/document360.md) | Partial | Weak | Strong | Strong | Strong | Partial | Partial | Strong | Partial | Strong | Partial |
| [Slite](../solutions/slite.md) | Weak | Strong | Partial | Strong | Strong | Strong | Partial | Partial | Partial | Strong | Strong |

## Agent Memory / Context Layers for Orgs

| Solution | Deploy | Capture | Organize | Evolve | Retrieve | Activate | Evidence | Scope | Feedback | Privacy | Setup |
|---|---|---|---|---|---|---|---|---|---|---|---|
| [Hebbia](../solutions/hebbia.md) | Partial | Strong | Weak | Weak | Strong | Weak | Partial | Weak | Weak | Strong | Weak |
| [Cognee](../solutions/cognee.md) | Strong | Partial | Strong | Partial | Strong | Strong | Unknown | Partial | Weak | Partial | Partial |
| [Zep / Graphiti](../solutions/zep-graphiti.md) | Strong | Weak | Strong | Strong | Strong | Strong | Partial | Partial | Weak | Strong | Partial |
| [Hjarni](../solutions/hjarni.md) | Weak | Weak | Partial | Weak | Partial | Strong | Weak | Partial | Weak | Weak | Strong |
| [Hyper](../solutions/hyper.md) | Unknown | Unknown | Unknown | Unknown | Unknown | Unknown | Unknown | Unknown | Unknown | Unknown | Unknown |
| [Memory Store](../solutions/memory-store.md) | Unknown | Unknown | Unknown | Unknown | Unknown | Unknown | Unknown | Unknown | Unknown | Unknown | Unknown |
| [Wato](../solutions/wato.md) | Unknown | Unknown | Unknown | Unknown | Unknown | Unknown | Unknown | Unknown | Unknown | Unknown | Unknown |
| [Hyperspell](../solutions/hyperspell.md) | Unknown | Unknown | Unknown | Unknown | Unknown | Unknown | Unknown | Unknown | Unknown | Unknown | Unknown |

## Open Source / Self-Hosted

| Solution | Deploy | Capture | Organize | Evolve | Retrieve | Activate | Evidence | Scope | Feedback | Privacy | Setup |
|---|---|---|---|---|---|---|---|---|---|---|---|
| [Onyx](../solutions/onyx.md) | Strong | Strong | Partial | Partial | Strong | Strong | Partial | Partial | Weak | Partial | Weak |
| [Outline](../solutions/outline.md) | Strong | Weak | Strong | Partial | Partial | Partial | Unknown | Strong | Partial | Partial | Weak |
| [Docmost](../solutions/docmost.md) | Strong | Weak | Strong | Partial | Partial | Partial | Partial | Partial | Partial | Partial | Partial |
| [BookStack](../solutions/bookstack.md) | Strong | Weak | Strong | Partial | Weak | Weak | Unknown | Strong | Partial | Strong | Strong |
| [AnythingLLM](../solutions/anythingllm.md) | Strong | Partial | Partial | Weak | Strong | Strong | Partial | Weak | Weak | Weak | Strong |
| [RAGFlow](../solutions/ragflow.md) | Partial | Strong | Partial | Weak | Strong | Strong | Strong | Weak | Weak | Weak | Weak |
| [Quivr](../solutions/quivr.md) | Weak | Weak | Unknown | Unknown | Partial | Unknown | Unknown | Weak | Unknown | Weak | Partial |
| [GBrain](../solutions/gbrain.md) | Partial | Weak | Strong | Partial | Strong | Strong | Partial | Partial | Weak | Weak | Partial |
| [Pad](../solutions/pad.md) | Strong | Weak | Partial | Weak | Weak | Strong | Unknown | Strong | Weak | Partial | Partial |
| [OpenViking](../solutions/openviking.md) | Strong | Partial | Strong | Partial | Strong | Strong | Strong | Weak | Weak | Partial | Strong |

## Platform Baselines

| Solution | Deploy | Capture | Organize | Evolve | Retrieve | Activate | Evidence | Scope | Feedback | Privacy | Setup |
|---|---|---|---|---|---|---|---|---|---|---|---|
| [Microsoft 365 Copilot](../solutions/microsoft-365-copilot.md) | Partial | Strong | Strong | Partial | Strong | Strong | Strong | Strong | Partial | Strong | Partial |
| [Google Workspace / NotebookLM Enterprise](../solutions/google-notebooklm-enterprise.md) | Partial | Partial | Partial | Partial | Strong | Weak | Strong | Partial | Partial | Strong | Partial |
| [Amazon Q Business](../solutions/amazon-q-business.md) ⚠️ | Strong | Strong | Partial | Partial | Strong | Strong | Strong | Strong | Strong | Strong | Partial |

⚠️ Closed to new customers as of 2026 — see the [profile](../solutions/amazon-q-business.md) before evaluating.

## Reading this matrix

- A row full of `Unknown` (Hyper, Memory Store, Wato, Hyperspell) means the vendor hasn't published enough for us to rate it yet, not that the product is weak — these are very early-stage (YC Spring 2026) and worth re-checking as they publish more.
- `Evidence` (Activation evidence) is the newest and thinnest column on purpose: most vendors document that retrieval/citations exist, but few publish proof that retrieved context is actually loaded and used by an agent (an audit log, a lineage trail) rather than just retrievable. Guru, RAGFlow, OpenViking, Microsoft 365 Copilot, Google NotebookLM Enterprise, and Amazon Q Business are the only `Strong` ratings here — check their profiles for what specifically counts as evidence.
- Don't sum ratings into a single "score" — a `Weak` on Setup often reflects a deliberate self-hosted/DIY tradeoff (see the [Setup Burden](setup-burden.md) page), not a flaw.
