# Google Workspace / NotebookLM Enterprise

## Snapshot

- Website / docs: https://workspace.google.com
- Company / maintainer: Google
- Status: Generally available. Google now refers to the enterprise product as "Gemini Notebook Enterprise" in current docs (URL path still `notebooklm-enterprise`), sold standalone or bundled inside Gemini Enterprise subscriptions; separately, Gemini AI features (including Gemini app access and "Gemini Notebook") are now included in Google Workspace Business and Enterprise plans with no separate add-on required.
- Open source: No — proprietary Google Cloud / Workspace SaaS.
- Deployment: Two separate products/consoles. Gemini Notebook Enterprise runs inside the customer's own Google Cloud project (admin config in Cloud Console, separate end-user web UI). Gemini for Workspace is delivered as a feature layer inside the customer's existing Workspace tenant, managed from the Google Admin console — no separate Cloud project needed.
- Primary users: Gemini Notebook Enterprise — enterprise teams needing compliance/security controls doing document-grounded research over a known set of sources. Gemini for Workspace — broad Workspace end users doing everyday productivity tasks across Gmail, Docs, Sheets, Meet, etc.
- Best company-brain role: Platform baseline: AI grounded in Google Workspace org content
- Last reviewed: 2026-08-31

## One-line Summary

Google's offering is split across two products: Gemini for Workspace embeds AI assistance across Gmail/Docs/Sheets/Slides/Meet/Chat/Drive using live Workspace content, while Gemini Notebook Enterprise (the Google Cloud-hosted enterprise version of NotebookLM) lets users build "notebooks" of explicitly uploaded or linked sources for grounded, cited Q&A and generated outputs.

## Company-Brain Fit

Context here is scoped either to what's explicitly uploaded into a notebook (Gemini Notebook Enterprise) or to the Google Workspace ecosystem itself (Gemini for Workspace) — not a universal, continuously self-updating company brain. Collect: Notebook Enterprise requires manual/explicit source upload — PDFs, Google Docs/Slides/Sheets, DOCX/PPTX/XLSX, audio files, website URLs, and documents pushed in from Gemini Enterprise search results (as copies, not live references); Gemini for Workspace instead draws on live content within Gmail, Docs, Drive, and Meet transcripts as users work, with no separate capture step. Organize: Notebook Enterprise uses a notebooks-containing-sources model (500 notebooks/user, 300 sources/notebook per docs); Gemini for Workspace has no independent organization layer and simply inherits existing Drive/Docs structure. Evolve: as of a May 2026 update, notebook sources that are native Drive-linked Google Docs/Sheets/Slides now auto-refresh when the underlying file changes (on by default, no toggle); PDFs, web links, pasted text, and audio sources still require manual re-upload. Use: grounded chat with inline citations, audio overviews, study guides/FAQs/briefing docs, and mind maps in Notebook Enterprise; "Help me write," Smart Fill, meeting notes, and a side-panel assistant across Workspace apps for Gemini for Workspace. Govern: Notebook Enterprise uses Cloud IAM roles, VPC Service Controls, and CMEK, scoped per Cloud project; Gemini for Workspace uses Admin-console per-OU/group toggles plus DLP/IRM/client-side encryption. Because these are two separately licensed, separately administered products, teams evaluating this as a "company brain" candidate should treat it as two complementary tools rather than one system.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Gemini Notebook Enterprise is hosted per-customer inside their own Google Cloud project with separate admin/user interfaces. Gemini for Workspace is a feature layer inside the existing Workspace tenant, no separate Cloud project required. |
| Context capture (docs, wikis, chats, tickets, CRM, meetings) | Notebook Enterprise: manual/explicit upload — PDFs, Google Docs/Slides/Sheets (now with automatic sync for native Drive files), DOCX/PPTX/XLSX, audio files, website URLs, plus copies of documents surfaced via Gemini Enterprise search. Gemini for Workspace: reads in-flow content inside Gmail/Docs/Sheets/Slides/Drive/Meet/Chat with no separate capture step. |
| Knowledge organization | Notebook Enterprise uses a notebooks → sources model (documented limits: 500 notebooks/user, 300 sources/notebook). Gemini for Workspace has no independent organization layer; it inherits Drive/Docs folder structure. |
| Knowledge evolution (freshness, dedup, review cycles) | Since May 2026, notebooks with native Drive-linked Docs/Sheets/Slides sources auto-update when the source file changes, and respect file deletion/permission revocation automatically — on by default with no config toggle. PDFs, web links, pasted text, and audio sources still require manual re-sync/re-upload. |
| Retrieval / use (search, grounding, citations) | Notebook Enterprise: grounded chat with inline citations to source passages, Audio Overview formats (Deep Dive, The Brief, The Critique, The Debate), video/slide-deck generation, mind maps, and generated reports (FAQ, study guide, briefing document), with documented per-user daily generation caps on some outputs. Gemini for Workspace: "Help me write" (Gmail/Docs), Smart Fill/table creation (Sheets), "Help me design" (Slides), automatic meeting notes and speech translation (Meet), side-panel summarization (Chat/Drive). |
| Agent activation / write-back (MCP, API, Slack/Teams, support bots) | Gemini Notebook Enterprise exposes a REST API (create/get/list/delete/share notebooks, source management) that is lifecycle/CRUD-oriented rather than a general agent-orchestration interface; it also surfaces as an agent inside the Gemini Enterprise app. No MCP support and no native Slack or Microsoft Teams write-back integration is documented for either product. |
| Activation evidence (proof retrieved context is actually used, not just retrievable) | Strong for Notebook Enterprise — grounded chat includes inline citations to specific source passages, a documented, user-visible citation mechanism. No equivalent citation mechanism is documented on the Gemini for Workspace side. |
| Team / org / role scope | Notebook Enterprise: notebooks can be shared within the same Google Cloud project/multi-region only — not across Cloud organizations (manual export/import only); sources can't be added to an already-shared notebook. Gemini for Workspace: admin scoping by organizational unit or configuration group, per Workspace service, default on; a documented gap means disabling Gemini for one app (e.g., Drive) doesn't stop another app's Gemini (e.g., Gmail) from surfacing that app's data. |
| Feedback / correction | Thumbs up/down feedback in both products. Per Google's privacy documentation, uploads/queries/responses are not used for model training or routinely human-reviewed, but submitted feedback itself is reviewed by trained human teams for safety/quality (disconnected from the user's account first, retained up to 3 years). Source-level add/remove is the main "correction" mechanism in notebooks, not a distinct correction workflow. |
| Privacy / access control | Notebook Enterprise: VPC Service Controls (GA, cannot be retrofitted onto a project with existing data stores), Customer-Managed Encryption Keys, data residency to US/EU multi-regions (additional in-country regions available via allowlist). Gemini for Workspace: Google states customer content is not human-reviewed or used to train generative models outside the domain without permission, plus admin-configurable DLP, Information Rights Management, and client-side encryption that can block Gemini from retrieving content a user lacks permission to access; cited certifications include ISO 42001, BSI C5, FedRAMP High, and HIPAA support. |
| Setup / operations | Notebook Enterprise requires an existing Google Cloud project and billing account; subscriptions run 15–5,000 licenses (contact sales above that), with a 14-day free trial covering 5,000 licenses; no official Google Cloud page with exact per-seat dollar pricing was found as of 2026-08-31. Gemini for Workspace needs no separate Cloud project — Gemini AI features are now included in Workspace Business/Enterprise plan subscriptions, with an optional "AI Expanded Access" add-on for higher usage limits. |

## Strengths

- The enterprise product adds VPC Service Controls (GA), CMEK, and configurable data residency not available in the consumer NotebookLM product.
- Grounded chat answers cite back to specific passages in uploaded sources, reducing hallucination risk relative to open-ended chat.
- As of May 2026, notebooks built from native Drive files (Docs/Sheets/Slides) auto-update when the source changes, removing a prior manual-resync pain point for that source type.
- Gemini for Workspace is deeply embedded across the daily-use productivity suite (Gmail, Docs, Sheets, Slides, Meet, Chat, Drive) rather than being a separate destination app.
- Both products carry Google's stated commitment that customer content/queries are not used to train foundational models and are not routinely human-reviewed.
- Admins get granular, per-service, per-OU/group control over where Gemini is enabled in Workspace, plus DLP/IRM/CSE enforcement on what it can retrieve.

## Limitations

- Gemini Notebook Enterprise's core model is manual curation into notebooks/sources — it does not continuously auto-ingest arbitrary company knowledge the way a universal company brain would; auto-refresh covers only native Drive-linked Docs/Sheets/Slides.
- The offering is split across two separate consoles/products (Google Cloud project vs. Workspace Admin console) with separate licensing, IAM models, and Terms of Service — not one unified system.
- No documented native Slack or Microsoft Teams write-back/agent integration for either product; the Notebook Enterprise API is lifecycle/CRUD-oriented, not a general agent-orchestration or MCP interface.
- Notebooks can't be shared or transferred across Google Cloud organizations, and sources can't be added to an already-shared notebook — limiting cross-org or cross-team knowledge reuse.
- Disabling Gemini in one Workspace app doesn't fully wall off that app's data from another app's Gemini experience — a documented governance gap.

## Best For

- Organizations already standardized on Google Workspace wanting AI assistance embedded directly into Gmail/Docs/Sheets/Meet without adopting a separate tool.
- Teams needing a compliance-friendly (VPC-SC, CMEK, data-residency-controlled), citation-grounded Q&A tool over a known, bounded set of documents.
- Teams that want auto-generated study guides, briefing docs, or audio-overview summaries of a specific document set.

## Not Ideal For

- Building a single, continuously self-updating company-wide knowledge base that auto-ingests arbitrary third-party or non-Drive sources.
- Organizations wanting one unified admin console/licensing model instead of managing two separate products.
- Teams that need native Slack/Teams-based agent interactions or an open orchestration/MCP layer on top of the knowledge base.

## Tradeoffs

Google's answer to "company brain" is deliberately bifurcated rather than unified: Gemini for Workspace gives broad, low-friction AI assistance wherever work already happens, trading a bounded, curated knowledge model for ambient convenience across live, ever-changing Workspace content — it functions more as an AI layer over existing data than as a distinct knowledge base. Gemini Notebook Enterprise instead trades that ambient breadth for precision: it requires users to manually curate a bounded set of sources into notebooks, in exchange for grounded, citation-backed answers plus Google Cloud-grade governance (VPC-SC, CMEK, data residency) the Workspace product doesn't independently expose. The two are complementary and increasingly bridged (Gemini Enterprise search results can be pushed into a notebook, and Drive-native sources now sync automatically), but a team evaluating this as a company-brain candidate should recognize it's two separately licensed, separately administered products with different data-freshness models, different sharing/governance boundaries, and no native third-party (Slack/Teams) agent surface.

## Official Setup / Evaluation Links

- [Gemini Notebook Enterprise overview](https://docs.cloud.google.com/gemini/enterprise/notebooklm-enterprise/docs/overview)
- [Get licenses for Gemini Notebook Enterprise](https://docs.cloud.google.com/gemini/enterprise/notebooklm-enterprise/docs/set-up-licensing)
- [Gemini Notebook Enterprise vs. Gemini Enterprise (choose product)](https://docs.cloud.google.com/gemini/enterprise/docs/choose-product)
- [Google Workspace with Gemini (admin overview)](https://knowledge.workspace.google.com/admin/gemini/google-workspace-with-gemini)
- [Manage access to Gemini features in Workspace services](https://knowledge.workspace.google.com/admin/gemini/manage-access-to-gemini-features-in-workspace-services)

## Sources

- [Gemini Notebook Enterprise overview](https://docs.cloud.google.com/gemini/enterprise/notebooklm-enterprise/docs/overview)
- [Data residency / locations](https://docs.cloud.google.com/gemini/enterprise/docs/locations)
- [Use VPC Service Controls](https://docs.cloud.google.com/gemini/enterprise/docs/use-vpc-service-controls)
- [Notebook Enterprise API reference](https://docs.cloud.google.com/gemini/enterprise/notebooklm-enterprise/docs/api-notebooks)
- [Set up licensing](https://docs.cloud.google.com/gemini/enterprise/notebooklm-enterprise/docs/set-up-licensing)
- [Gemini Notebook Enterprise FAQ](https://docs.cloud.google.com/gemini/enterprise/notebooklm-enterprise/docs/faq)
- [Choose product (Notebook Enterprise vs. Gemini Enterprise)](https://docs.cloud.google.com/gemini/enterprise/docs/choose-product)
- [Access NotebookLM via Gemini Enterprise](https://docs.cloud.google.com/gemini/enterprise/docs/access-notebooklm)
- [Google Workspace with Gemini](https://knowledge.workspace.google.com/admin/gemini/google-workspace-with-gemini)
- [Manage access to Gemini features in Workspace services](https://knowledge.workspace.google.com/admin/gemini/manage-access-to-gemini-features-in-workspace-services)
- [Workspace AI privacy commitments](https://workspace.google.com/intl/en_ph/security/ai-privacy)
- [Empowering businesses with AI — Workspace blog](https://workspace.google.com/blog/product-announcements/empowering-businesses-with-AI)
- [Keep your sources up to date with automatic Drive syncing in NotebookLM — Workspace Updates blog](https://workspaceupdates.googleblog.com/2026/05/keep-your-sources-up-to-date-with-automatic-Drive-syncing-in-NotebookLM.html)
- [NotebookLM Privacy and Terms of Use](https://support.google.com/notebooklm/answer/17004255?hl=en)
