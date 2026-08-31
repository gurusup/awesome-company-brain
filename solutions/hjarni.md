# Hjarni

## Snapshot

- Website / docs: https://hjarni.com (MCP client: https://github.com/hjarni/hjarni-mcp)
- Company / maintainer: Hjarni.
- Status: Unknown — release cadence and company stage not independently verified beyond the product and MCP client existing.
- Open source: Partial — the app itself is a proprietary hosted SaaS; the MCP client is MIT licensed.
- Deployment: Hosted SaaS.
- Primary users: Teams wanting a simple hosted Markdown notes app with shared team spaces that Claude/ChatGPT can read, search, and write to via MCP.
- Best company-brain role: Hosted team workspace with native per-team AI instructions and OAuth2 remote MCP access.
- Last reviewed: 2026-08-31

## One-line Summary

Hjarni is a hosted Markdown notes app with shared team spaces, member management, and per-team custom AI instructions, exposed to AI agents through 24+ MCP tools over OAuth2 remote MCP.

## Company-Brain Fit

Hjarni's shared team spaces with member management give it real multi-user support (unlike many personal note-taking tools that get repurposed for teams informally). Its MCP surface lets agents read, search, and write notes directly, which fits the Use stage well. Capture is manual note-writing rather than automatic connectors from company tools, and Evolve/Govern maturity (staleness handling, formal audit) is not documented, so it fits best as a lightweight, agent-writable team notebook rather than a full enterprise knowledge platform.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Hosted SaaS only — no self-hosting option found. |
| Context capture (docs, wikis, chats, tickets, CRM, meetings) | Manual note-writing by people or agents; no automatic connectors to Slack, tickets, CRM, or meetings documented. |
| Knowledge organization | Markdown notes organized into shared team spaces. |
| Knowledge evolution (freshness, dedup, review cycles) | Unknown. |
| Retrieval / use (search, grounding, citations) | Search over notes exposed via MCP tools; citation/grounding format not detailed. |
| Agent activation / write-back (MCP, API, Slack/Teams, support bots) | 24+ MCP tools over OAuth2 remote MCP — agents can read, search, and write notes directly. |
| Team / org / role scope | Shared team spaces with member management and per-team custom AI instructions. |
| Feedback / correction | Unknown. |
| Privacy / access control | OAuth2-based access to the MCP surface; no compliance certification claims found. |
| Setup / operations | Low — hosted product, no infrastructure to operate. |

## Strengths

- Real team spaces with member management, not just a personal notes app.
- Per-team custom AI instructions — lets a team tune how agents behave against its own notes.
- Broad MCP tool surface (24+ tools) for both reading and writing.
- Low setup burden as a hosted product.

## Limitations

- No automatic capture from company tools (Slack, tickets, CRM, meetings) — content only enters via manual notes.
- No self-hosting option for teams that require data residency control.
- Knowledge-evolution and governance features (staleness detection, audit trails) are not documented.

## Best For

- Small teams that want a lightweight, agent-writable shared notebook rather than a full enterprise knowledge platform.
- Teams already standardized on MCP-based agent workflows (Claude, other MCP clients) who want quick team-level context.

## Not Ideal For

- Organizations needing automatic ingestion from many existing company tools.
- Organizations requiring self-hosting or formal compliance certifications.

## Tradeoffs

Hjarni trades broad connector coverage for simplicity: it is a fast, low-setup way to give a team's AI agents a shared, writable notebook, but it does not replace a full enterprise-knowledge platform that ingests from many existing systems automatically.

## Official Setup / Evaluation Links

- https://hjarni.com
- https://github.com/hjarni/hjarni-mcp

## Sources

- https://hjarni.com
- https://github.com/hjarni/hjarni-mcp
- Cross-referenced against its profile in the related list aristoapp/awesome-second-brain for the "shared team spaces" and MCP tool count characterization
