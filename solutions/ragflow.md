# RAGFlow

## Snapshot

- Website / docs: https://ragflow.io (docs: https://ragflow.io/docs) — code: https://github.com/infiniflow/ragflow
- Company / maintainer: InfiniFlow Inc.
- Status: Actively maintained — 89,700+ GitHub stars, 10,500+ forks, 1,738 open issues; latest release v0.27.1 (2026-08-28), releases roughly every 2-3 weeks, last commit pushed 2026-08-31.
- Open source: Yes — Apache License 2.0 (verified in the repo's LICENSE file).
- Deployment: Self-hosted via Docker Compose (recommended minimums: 4+ CPU cores, 16GB+ RAM, 50GB+ disk, Docker 24.0.0+, Python 3.13+; optional GPU acceleration for document processing). InfiniFlow also runs an official managed cloud at cloud.ragflow.io with Free (1 member), Starter (5 members), Pro (20 members, $129/mo), and Enterprise (BYOC/on-prem, dedicated support, custom SLA) tiers.
- Primary users: Technical teams and enterprises handling document-heavy, structurally complex content — publicized use cases span finance, legal/compliance, manufacturing, and education.
- Best company-brain role: Self-hosted RAG engine with deep document understanding
- Last reviewed: 2026-08-31

## One-line Summary

RAGFlow is an Apache-2.0-licensed, self-hostable RAG engine from InfiniFlow that specializes in layout-aware "deep document understanding" (tables, scans, mixed layouts) with grounded citations and agentic/MCP workflows, at the cost of noticeably heavier self-hosting resource requirements than lighter alternatives.

## Company-Brain Fit

RAGFlow's strongest lifecycle fit is **Collect** and **Use**: its document pipeline (template-based chunking, MinerU/Docling integration, multimodal image extraction from PDFs and DOCX) is built specifically to handle messy, structurally complex source documents — tables, scanned files, mixed layouts — better than naive chunkers, and its chat/retrieval layer returns grounded, traceable citations. **Organize** is handled via per-document-type chunking templates rather than a broader taxonomy or knowledge-graph layer. **Evolve** (freshness, dedup, review cycles) is not documented from primary sources. **Govern** is where self-hosting and licensing tiers intersect: the free, Apache-2.0 self-hosted build's exact multi-tenant RBAC/SSO depth could not be verified from official docs, while InfiniFlow's paid Enterprise/BYOC tier explicitly offers on-prem deployment, dedicated support, and custom SLAs — implying the deepest governance controls sit behind the commercial tier. Self-hosting RAGFlow is a heavier commitment than many alternatives (16GB+ RAM, 50GB+ disk, Python 3.13+, optional GPU), so teams should weigh that operational cost against its document-parsing advantages.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Self-hosted via Docker Compose with comparatively high resource requirements (4+ CPU cores, 16GB+ RAM, 50GB+ disk, Docker 24.0.0+, Python 3.13+; GPU acceleration optional for document processing). Also available as InfiniFlow's managed cloud (cloud.ragflow.io) across Free, Starter, Pro ($129/mo), and Enterprise/BYOC tiers. |
| Context capture (docs, wikis, chats, tickets, CRM, meetings) | "Deep document understanding" via template-based chunking with MinerU and Docling support, plus multimodal image processing inside PDFs/DOCX. Ingests Word, Slides, Excel, TXT, images, scanned documents, structured data, and web content; connectors reported for Confluence, S3, Notion, Discord, and Google Drive. |
| Knowledge organization | Chunking strategies are templated to document type/layout rather than freeform; retrieval uses fused re-ranking across chunks. |
| Knowledge evolution (freshness, dedup, review cycles) | Unknown — no documented freshness, deduplication, or scheduled review-cycle tooling verified from primary sources. |
| Retrieval / use (search, grounding, citations) | "Grounded citations" with traceable reference visualization in answers; configurable LLM backends (recent release notes reference OpenAI GPT-5, DeepSeek, and Gemini support). |
| Agent activation / write-back (MCP, API, Slack/Teams, support bots) | Agentic workflows, native MCP integration, a built-in Python/JS code executor, agent memory, and chat-channel integrations for Feishu, Discord, Telegram, and Line. No native Slack/Teams write-back integration was confirmed. |
| Team / org / role scope | Multi-tenant RBAC and SSO appear to be primarily features of the paid Enterprise tier; the exact role-based access control scope available in the free, self-hosted open-source build could not be verified from official primary sources — Unknown. (A third-party, unofficial fork called "ragflow-plus" advertises more elaborate RBAC — this is not part of official RAGFlow and should not be attributed to it.) |
| Feedback / correction | Unknown — not verified from primary sources. |
| Privacy / access control | Self-hosted deployment keeps data on your own infrastructure. Fine-grained RBAC and SSO appear to be gated behind the paid Enterprise/BYOC tier rather than confirmed as fully available in the free OSS build. |
| Setup / operations | Docker Compose quickstart; notably heavier infrastructure requirements than many lighter RAG tools (16GB+ RAM, 50GB+ disk, Python 3.13+); GPU acceleration optional but recommended for heavier document processing. The managed cloud tier removes this operational burden at a cost. |

## Strengths

- Apache 2.0 licensed, with extremely active development (89k+ stars, releases roughly every 2-3 weeks, commits as recent as the day of this review)
- Strong, differentiated document-understanding pipeline — layout-aware chunking, OCR/multimodal image extraction, MinerU/Docling support — well suited to tables, scans, and complex layouts
- Grounded, traceable citations in retrieval output
- Agentic workflows with native MCP integration and a built-in code executor
- Clear path from a free self-hosted deployment to a managed cloud or Enterprise/BYOC on-prem tier as needs grow

## Limitations

- Meaningfully higher self-hosting resource requirements than many alternatives (16GB+ RAM, 50GB+ disk, Python 3.13+, GPU recommended)
- Fine-grained multi-tenant RBAC and SSO appear to be primarily Enterprise-tier features; the access-control depth of the free OSS build is unverified from primary sources
- No documented native Slack/Teams write-back integration (supported chat channels are Feishu, Discord, Telegram, and Line instead)
- 1,738 open GitHub issues suggests a sizeable backlog relative to throughput despite active development
- No documented knowledge-freshness, deduplication, or review-cycle tooling

## Best For

- Teams with document-heavy, structurally complex content (tables, scanned files, mixed layouts) that need high-fidelity parsing
- Organizations with the infrastructure budget (RAM, disk, optional GPU) to self-host a resource-intensive RAG engine
- Teams wanting a clear upgrade path from a free self-hosted trial to a paid managed or BYOC enterprise deployment

## Not Ideal For

- Small teams or projects with limited server resources — the 16GB+ RAM / 50GB+ disk baseline is steep for lightweight use
- Organizations that need verified, out-of-the-box fine-grained RBAC/SSO without purchasing the Enterprise tier
- Teams specifically wanting native Slack/Teams bot integration, which isn't among the supported chat channels

## Tradeoffs

RAGFlow trades operational simplicity for document-parsing depth: its layout-aware chunking and multimodal extraction genuinely differentiate it on messy, complex source documents, and its Apache 2.0 license plus rapid release cadence make it a credible open-source foundation. But that capability comes with real infrastructure cost (16GB+ RAM, 50GB+ disk, GPU recommended), and the governance layer a company-brain deployment needs — fine-grained RBAC, SSO — appears to live mostly behind InfiniFlow's paid Enterprise/BYOC tier rather than being clearly guaranteed in the free self-hosted build. Teams evaluating it should self-host a proof-of-concept against their own document mix before committing, and budget for either the resource footprint or the Enterprise tier if strict access control is a requirement.

## Official Setup / Evaluation Links

- https://github.com/infiniflow/ragflow
- https://ragflow.io
- https://ragflow.io/docs
- https://cloud.ragflow.io (official managed cloud)
- https://github.com/infiniflow/ragflow/blob/main/LICENSE

## Sources

- https://github.com/infiniflow/ragflow (repo metadata: stars, forks, issues, releases)
- https://github.com/infiniflow/ragflow/blob/main/LICENSE
- https://raw.githubusercontent.com/infiniflow/ragflow/main/README.md
- https://ragflow.io/
