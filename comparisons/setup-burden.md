# Setup Burden

How much friction stands between you and a working company brain, before you've evaluated anything else. Grouped by the fastest path to a first working instance — many solutions offer a second, heavier path at higher tiers (noted in parens). Extracted from each [solution profile](../solutions/README.md)'s own `Setup / operations` and `Status` fields — see the profile for specifics before committing.

## Self-serve (sign up and go, no sales call for an entry tier)

| Solution | Entry path | Heavier path at scale |
|---|---|---|
| [Notion AI](../solutions/notion-ai.md) | Free/Plus/Business self-serve signup | Enterprise plan is sales-led |
| [Confluence](../solutions/confluence.md) | Self-serve below Enterprise | Enterprise tier is sales-led |
| [Slab](../solutions/slab.md) | Self-serve (Free/Startup/Business) | Enterprise requires 100-user minimum, sales-led |
| [GitBook](../solutions/gitbook.md) | Self-serve free tier | Enterprise tier is sales-led |
| [Tettra](../solutions/tettra.md) | Self-serve, 30-day trial | — |
| [Document360](../solutions/document360.md) | Self-serve entry plan | Higher tiers are custom-quote |
| [Slite](../solutions/slite.md) | Self-serve, 14-day trial | Enterprise tier is sales-led |
| [Hjarni](../solutions/hjarni.md) | Self-serve, low setup | — |
| [AnythingLLM](../solutions/anythingllm.md) | Self-serve (Docker or desktop install) | — |
| [GBrain](../solutions/gbrain.md) | Self-serve for personal use | Team mode requires DIY infra (Postgres/Supabase + OAuth) |
| [Pad](../solutions/pad.md) | Self-serve managed cloud | DIY if self-hosting |
| [OpenViking](../solutions/openviking.md) | Self-serve OSS | Enterprise (team permissions) is sales-led |
| [Microsoft 365 Copilot](../solutions/microsoft-365-copilot.md) | Self-serve add-on to existing M365 | Enterprise-scale rollout is sales-assisted |
| [Amazon Q Business](../solutions/amazon-q-business.md) ⚠️ | Self-serve via AWS Console | **Closed to new customers as of 2026 — see [profile](../solutions/amazon-q-business.md)** |

## Sales-assisted only (demo/consultation required, no public self-serve path)

| Solution | Notes |
|---|---|
| [GuruSup Company Brain](../solutions/gurusup-company-brain.md) 🔹 | Primary CTA is "Book a live demo"; no self-serve signup or public pricing found. |
| [Glean](../solutions/glean.md) | Enterprise, sales-led onboarding; connectors and permissions configured by admins. |
| [Guru](../solutions/guru.md) | Positioned as "a platform and expertise solution," with a solution-engineer team involved in onboarding. |
| [Hebbia](../solutions/hebbia.md) | Enterprise sales process; pricing not public. |
| [Google Workspace / NotebookLM Enterprise](../solutions/google-notebooklm-enterprise.md) | NotebookLM Enterprise specifically is sales-assisted (Gemini for Workspace add-on is self-serve). |

## DIY self-hosted (you own the operational burden, regardless of price)

| Solution | Notes |
|---|---|
| [Onyx](../solutions/onyx.md) | Self-hosting is real DevOps work; a hosted Cloud option also exists. |
| [Outline](../solutions/outline.md) | Self-host or use the self-serve Cloud option. |
| [Docmost](../solutions/docmost.md) | Lighter footprint than Onyx/RAGFlow; Cloud option also exists. |
| [BookStack](../solutions/bookstack.md) | Lightest self-hosted footprint in this list — no AI/retrieval layer to operate. |
| [RAGFlow](../solutions/ragflow.md) | Resource-heavy self-hosted deployment; managed cloud option also exists. |
| [Quivr](../solutions/quivr.md) ⚠️ | Not turnkey at all — a Python library (`pip install quivr-core`) you build an app around. |
| [Cognee](../solutions/cognee.md) | Infra/SDK layer — self-host or use Cognee Cloud/BYOC. |
| [Zep / Graphiti](../solutions/zep-graphiti.md) | Graphiti (OSS) is DIY; Zep (commercial) has a self-serve cloud free tier. |

## Unknown

[Hyper](../solutions/hyper.md), [Memory Store](../solutions/memory-store.md), and [Wato](../solutions/wato.md) are too early-stage (YC Spring 2026) to have documented setup paths yet. [Hyperspell](../solutions/hyperspell.md) is an infra/API layer — "setup burden" for it really means the engineering work of building the user-facing surface on top, not signing up.

## Reading this page

Self-serve isn't automatically "better" — it usually trades governance depth (SME verification, formal compliance certs) for speed. Sales-assisted tools in this list (Guru, Glean, GuruSup Company Brain) lean into that tradeoff deliberately. DIY self-hosted trades ops burden for data residency and control — see [Keep everything self-hosted / avoid vendor lock-in](../README.md#choose-by-lifecycle-gap) in the chooser for when that tradeoff makes sense.
