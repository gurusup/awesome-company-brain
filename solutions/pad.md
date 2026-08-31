# Pad

## Snapshot

- Website / docs: https://getpad.dev (code: https://github.com/PerpetualSoftware/pad)
- Company / maintainer: PerpetualSoftware (open-source project).
- Status: Unknown — activity/release cadence not independently verified beyond the repo existing and being documented.
- Open source: Yes — Apache License 2.0.
- Deployment: Self-hosted (Postgres + Redis for multi-instance) or managed cloud at app.getpad.dev.
- Primary users: Teams that want an agent-operated shared workspace with real role-based access, not just a single-user notes app.
- Best company-brain role: Self-hosted or managed team workspace giving agents durable, structured project context via a native skill, MCP, API, and CLI.
- Last reviewed: 2026-08-31

## One-line Summary

Pad is a self-hostable (or managed-cloud) team workspace with typed collections, RBAC, and real-time collaboration, designed for AI agents to read and write durable project context through MCP, API, and CLI.

## Company-Brain Fit

Pad's role-based access control (owner/editor/viewer), real-time collaborative editing, and email/CLI-based team invitations make it one of the few tools in the open-source "second brain" space with genuine, first-party multi-user support rather than a personal tool a team adopts informally. Its MCP/API/CLI surface is built for agents to read conventions, playbooks, and project context directly, which fits the Use and Organize stages of the company-brain lifecycle well; Evolve and Govern maturity (review cycles, audit trails) is less documented.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Self-hosted (Postgres + Redis) or managed cloud (app.getpad.dev). |
| Context capture (docs, wikis, chats, tickets, CRM, meetings) | Primarily manual/agent-written collections rather than broad third-party connectors; connector breadth beyond that is Unknown. |
| Knowledge organization | Typed collections, conventions, and playbooks as the core organizing structure. |
| Knowledge evolution (freshness, dedup, review cycles) | Unknown — no dedicated staleness/dedup mechanism documented. |
| Retrieval / use (search, grounding, citations) | Structured/keyword retrieval (per the reference-repo profile this project is cross-listed in); no semantic/vector recall or automatic consolidation documented. |
| Agent activation / write-back (MCP, API, Slack/Teams, support bots) | Native skill, MCP, API, and CLI access — a first-class integration surface for agents to both read and write. |
| Team / org / role scope | RBAC with owner/editor/viewer roles; email/CLI invitations for onboarding teammates. |
| Feedback / correction | Unknown. |
| Privacy / access control | Role-based permissions are the documented control; no compliance certification claims found. |
| Setup / operations | Low if using the managed cloud; higher for self-hosting (Postgres + Redis for multi-instance deployments). |

## Strengths

- Real RBAC and real-time collaboration, not just single-user local storage.
- Agent-first design: native skill, MCP, API, and CLI as first-class access paths.
- Choice of self-hosted or managed cloud deployment.
- Apache 2.0 license — fully open source with no enterprise carve-out found.

## Limitations

- Structured/keyword retrieval only — no semantic recall or automatic consolidation, per its own positioning.
- Connector breadth for pulling in third-party company sources (Slack, tickets, CRM) is not clearly documented.
- Governance/audit maturity (review cycles, compliance) is unproven relative to established enterprise platforms.

## Best For

- Teams wanting an agent-operated, self-hostable project workspace with real multi-user permissions.
- Teams already comfortable running Postgres/Redis who want full ownership of the data.

## Not Ideal For

- Teams that need semantic/vector search over company knowledge rather than structured/keyword lookup.
- Teams wanting broad out-of-the-box connectors to existing company tools (Slack, CRM, ticketing).

## Tradeoffs

Pad trades semantic search sophistication for a simpler, structured, agent-writable workspace with genuine team permissions — a good fit for teams that want agents to operate a shared, typed knowledge base rather than search unstructured documents.

## Official Setup / Evaluation Links

- https://getpad.dev
- https://github.com/PerpetualSoftware/pad

## Sources

- https://github.com/PerpetualSoftware/pad
- https://getpad.dev
- Cross-referenced against its profile in the related list aristoapp/awesome-second-brain (solutions/pad.md) for the "structured/keyword retrieval only" characterization
