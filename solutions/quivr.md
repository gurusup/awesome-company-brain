# Quivr

## Snapshot

- Website / docs: https://core.quivr.com (library docs) — the original `www.quivr.app` product site is unreachable (dead domain, not linked here); https://www.quivr.com now hosts a separate, unrelated commercial customer-support-agent SaaS product from the same company — code: https://github.com/QuivrHQ/quivr
- Company / maintainer: Quivr (GitHub org QuivrHQ; founder/lead maintainer StanGirard)
- Status: Open-source repo is not formally archived but shows a stalled maintenance pattern — last commit 2025-06-19 (last push 2025-07-09), last release `core-0.0.33` published 2025-02-04, no release since — over a year stale as of this review (2026-08-31). The company's commercial focus has visibly shifted to a separate, unrelated paid customer-support-agent SaaS product at quivr.com.
- Open source: Yes — Apache License 2.0 (verified by reading the raw LICENSE file content, which is standard Apache 2.0 text). Note: GitHub's automated license detector flags the repo as "Other / NOASSERTION," almost certainly because the copyright line's placeholder brackets (`[2023-2024] [Quivr]`) were never filled in — the license text itself is unambiguously Apache 2.0.
- Deployment: Self-hosted only, distributed as a Python package (`pip install quivr-core`) that developers embed in their own application — current docs frame it as a lightweight RAG library, not a turnkey full-stack app with a ready UI. No Docker Compose quickstart is documented in the current README, and there is no free/OSS-equivalent hosted option (the only hosted product at quivr.com is the separate commercial support-agent SaaS).
- Primary users: Developers embedding RAG into their own applications as a library; no longer positioned for end-user teams wanting a ready-made, self-hosted "second brain" app with a UI.
- Best company-brain role: Self-hostable AI second-brain, usable at team level — **caveat: this describes the project's earlier full-stack-app positioning; see Company-Brain Fit below for its current state.**
- Last reviewed: 2026-08-31

## One-line Summary

Quivr is an Apache-2.0-licensed Python RAG library (`quivr-core`) that historically shipped as a full self-hosted "second brain" web app, but has since been reduced to a bare embeddable library with no recent releases (last: Feb 2025), while its maintaining company's commercial attention has moved to an unrelated customer-support-agent SaaS product.

> [!WARNING]
> Stalled as a turnkey app: no release since February 2025, no commits since mid-2025, and the maintaining company has shifted its commercial focus to a separate, unrelated SaaS product. Treat this as a RAG library for developers, not a self-hosted "second brain" app — see [Tradeoffs](#tradeoffs) below.

## Company-Brain Fit

Quivr's current shape does not map well onto the standard company-brain lifecycle as a turnkey product. **Collect** is possible at the library level (PDF, TXT, Markdown ingestion, extensible parsers, an advanced "Megaparse" parser), but there is no documented workspace UI, so **Organize**, **Evolve**, and **Govern** are left entirely to whatever application a team builds around `quivr-core` — none of these are provided out of the box. **Use** works at the retrieval/chat level (multi-LLM support, vector stores, reranking), but again only inside a custom-built application, not a ready product. Critically, self-hosting Quivr today means adopting an early-stage-feeling library with a stalled release cadence (last release February 2025) from a company that has publicly pivoted its commercial roadmap to a different, unrelated product — a real maintenance-risk signal for any team considering it as the foundation of a durable company-brain system. Teams evaluating it should treat it as a components library to build with, not a product to deploy.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Self-hosted only, as a Python library (`pip install quivr-core`) embedded into a custom application — not a turnkey full-stack app with Docker Compose and a ready UI in its current form (that architecture existed in earlier project versions). No official OSS hosted/cloud option exists; the original quivr.app marketing/product site is unreachable. |
| Context capture (docs, wikis, chats, tickets, CRM, meetings) | File ingestion for PDF, TXT, Markdown, with extensible parsers and an advanced "Megaparse" parser for complex documents. No dedicated native connectors for wikis, tickets, CRM, or meeting platforms were found. |
| Knowledge organization | Unknown — as a library, structuring and organization are left to the implementing application; no documented workspace or folder model was found in current docs. |
| Knowledge evolution (freshness, dedup, review cycles) | Unknown — not documented in current sources. |
| Retrieval / use (search, grounding, citations) | Multi-LLM support (OpenAI, Anthropic, Mistral, Gemma, local via Ollama), vector stores (PGVector, Faiss), reranking via Cohere, and multi-turn conversation handling. |
| Agent activation / write-back (MCP, API, Slack/Teams, support bots) | Unknown for the open-source core — no MCP, Slack/Teams, or support-bot write-back integration was confirmed in fetched docs. (Note: the separate commercial quivr.com SaaS product does offer support-bot agents and MCP/webhook integrations, but that is a distinct, non-open-source product line, not this repository.) |
| Team / org / role scope | No evidence found of a multi-user/team workspace UI, role-based permissions, or an admin console in the current open-source core. |
| Feedback / correction | Unknown — not documented in current sources. |
| Privacy / access control | Self-hosting the library keeps data under the implementer's control by design, but no built-in authentication, RBAC, or SSO layer was found — any access control must be built by the adopting application. |
| Setup / operations | `pip install quivr-core` with a minimal quickstart (a few lines of code); no Docker Compose quickstart currently documented. Requires meaningful development effort to turn into a usable end-user product, since it ships as a library rather than a ready application. |

## Strengths

- Apache 2.0 licensed and historically well-adopted (39,400+ GitHub stars, 3,700+ forks)
- Lightweight Python library approach (`quivr-core`) is straightforward to embed into a custom-built internal tool
- Broad LLM support (OpenAI, Anthropic, Mistral, Gemma, local via Ollama) plus reranking via Cohere
- Simple, low-friction quickstart for developers who just need a RAG building block

## Limitations

- Significant maintenance-risk signal: last commit roughly 14 months before this review (2025-06-19), last release February 2025, no confirmed recent release cadence
- The maintaining company's commercial focus has visibly shifted to an unrelated paid customer-support-agent SaaS product (quivr.com), raising real doubts about continued investment in the open-source project
- The original quivr.app marketing/product domain is unreachable
- The project has architecturally shifted from a full-stack self-hosted app (Docker Compose + UI) to a bare Python library — it is no longer a turnkey "company brain" product and needs custom development to become one
- No documented multi-user/team workspace, RBAC, SSO, or admin console in the current open-source core

## Best For

- Developers who want a lightweight, permissively licensed RAG library to embed inside a custom-built internal tool, and who are comfortable with an apparently stalled upstream
- Teams already committed to building their own UI and multi-user layer who just need a RAG component underneath

## Not Ideal For

- Teams wanting a turnkey, ready-to-run self-hosted "second brain" app with a UI, multi-user support, and admin controls out of the box
- Organizations that need active vendor support or roadmap confidence — commit and release activity suggest this project has been deprioritized relative to the company's SaaS pivot
- Anyone expecting the self-hosted "second brain" experience described in Quivr's older marketing material — that product direction does not reflect the current state of the open-source repository

## Tradeoffs

Quivr's Apache 2.0 license and lightweight library design make it easy to adopt as a RAG building block, but the project has clearly changed shape and priority since its earlier "self-hosted second brain" positioning: it now ships as a bare Python library rather than a full application, its release cadence has stalled for over a year, and the company behind it has publicly moved its commercial focus to an unrelated customer-support-agent product. Teams should not evaluate Quivr against the "full self-hosted second-brain app" premise implied by older marketing — that premise no longer matches the current repository — and should instead treat it as an unmaintained-feeling library requiring significant additional engineering to become a company-brain product, if adopted at all.

## Official Setup / Evaluation Links

- https://github.com/QuivrHQ/quivr
- https://core.quivr.com
- https://github.com/QuivrHQ/quivr/blob/main/LICENSE
- https://github.com/QuivrHQ/quivr/releases

## Sources

- https://github.com/QuivrHQ/quivr (repo metadata: stars, forks, commits, contributors, releases)
- https://raw.githubusercontent.com/QuivrHQ/quivr/main/LICENSE
- https://core.quivr.com
- https://www.quivr.com
- `www.quivr.app` (attempted — unreachable, SSL/connection failure; not linked)
