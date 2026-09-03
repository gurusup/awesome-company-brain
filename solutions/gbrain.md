# GBrain

## Snapshot

- Website / docs: https://gbrain.homes (code: https://github.com/garrytan/gbrain)
- Company / maintainer: Community project. The repo's own README states in first person "I'm Garry Tan, President and CEO of Y Combinator. I built GBrain to run my own AI agents." This identity claim is corroborated by several independent third-party write-ups (e.g. MarkTechPost, colrows.com), but is not independently verifiable via GitHub's own identity signals — treat the authorship as widely reported, not certified.
- Status: Very actively maintained — created 2026-04-05, commits as recent as the day this profile was reviewed. Not archived, not a fork.
- Open source: Yes — MIT license (confirmed in repo metadata).
- Deployment: Local-first by default (embedded PGLite / Postgres+pgvector); Postgres or Supabase for multi-user/team deployments.
- Primary users: Individuals running personal AI agents by default; documented path to 10-50 person teams wanting a shared, permission-scoped company brain.
- Best company-brain role: Open-source agent memory system with a documented, named "company brain" team mode, not just a personal tool used informally by a team.
- Last reviewed: 2026-08-31

## One-line Summary

GBrain is an open-source, MIT-licensed memory system for AI agents (pages, graph, timeline, hybrid search, MCP server) that ships an explicit multi-user "company brain" mode with OAuth-scoped, per-person access.

## Company-Brain Fit

GBrain started as a personal agent-memory tool but documents a specific team deployment (`docs/tutorials/company-brain.md`) describing "federated, multi-user, OAuth-scoped institutional memory for a 10-50 person team," where each team member gets their own slice of the brain scoped by login. That makes it a genuine candidate for Collect/Organize/Use in a company context, via its MCP server (reported ~74 tools) and hybrid vector+BM25+reranker search — but Govern-level maturity (formal roles, audit, compliance) is unproven for an open-source project this young (~5 months old at time of review).

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Self-hosted. Local PGLite for individual use; Postgres/Supabase required for the team/company mode — not zero-config like the personal mode. |
| Context capture (docs, wikis, chats, tickets, CRM, meetings) | Personal-agent-session capture is the core design; connector breadth for company sources (CRM, tickets, meetings) beyond what an agent session touches is Unknown. |
| Knowledge organization | "Pages, graph, timeline" data model with an append-only evidence trail; self-wiring knowledge graph per the repo's own description. |
| Knowledge evolution (freshness, dedup, review cycles) | Ships maintenance jobs (a "dream"/autopilot process) for consolidation. Independent verification of dedup/staleness quality is Unknown. |
| Retrieval / use (search, grounding, citations) | Hybrid search: vector + BM25 + RRF + reranker, per repo docs. |
| Agent activation / write-back (MCP, API, Slack/Teams, support bots) | Native MCP server (reported ~74 tools) — this is the primary integration surface, not a separate REST API. |
| Activation evidence (proof retrieved context is actually used, not just retrievable) | Partial: the append-only evidence trail in its page/graph/timeline model preserves provenance of stored memories, but no documented example shows a retrieved memory being cited or loaded into an agent's final response — Unknown beyond that trail. |
| Team / org / role scope | Documented: OAuth-scoped, per-login access ("you only see what you're allowed to see") for the team/company deployment mode. Granularity beyond per-person scoping (e.g. per-team, per-role) is Unknown. |
| Feedback / correction | Unknown — no dedicated correction/verification workflow found in the docs reviewed. |
| Privacy / access control | Per-person OAuth scoping is documented for team mode; no compliance certification (SOC 2, ISO) claims found, as expected for an open-source project of this kind. |
| Setup / operations | Low for personal/local mode; meaningfully higher for team mode (requires standing up Postgres/Supabase and OAuth). |

## Strengths

- Real, working open-source project (MIT, ~29k GitHub stars, very active commit history) rather than a marketing page.
- Explicit, documented team/company deployment path with per-person access scoping — not just "you could self-host this for a team if you build the permissions yourself."
- Native MCP server as the integration surface, fitting naturally into agent-first workflows (Claude, other MCP clients).
- High-profile origin (if the authorship claim holds) has driven fast community attention and contribution activity.

## Limitations

- Project is very young (~5 months old as of this review); no long track record for reliability, governance, or security at company scale.
- Team/company mode requires real infrastructure setup (Postgres/Supabase, OAuth) — not the "5-minute quickstart" some hosted competitors offer.
- No compliance certifications or formal access-control audit found — appropriate caution before trusting it with sensitive company data.
- Authorship/backing is self-reported in the README, not independently certified.

## Best For

- Technical teams comfortable self-hosting who want an open-source, MIT-licensed alternative to hosted "company brain" SaaS products.
- Teams already using MCP-based agent workflows who want a shared memory layer they fully own and can inspect.

## Not Ideal For

- Non-technical teams wanting a zero-setup hosted product.
- Organizations that need compliance certifications (SOC 2, ISO 27001) or mature, audited access controls today.

## Tradeoffs

GBrain trades hosted-product polish for full ownership and inspectability: it's free, open, and has a real team mode, but you operate the infrastructure yourself and take on more setup than a hosted SaaS competitor, with less governance maturity than an established enterprise platform.

## Official Setup / Evaluation Links

- https://github.com/garrytan/gbrain
- https://gbrain.homes
- Team/company mode tutorial: `docs/tutorials/company-brain.md` in the repo

## Sources

- https://github.com/garrytan/gbrain (README, repo metadata, GitHub API for stars/license/activity)
- https://gbrain.homes
- Third-party coverage corroborating the authorship claim: MarkTechPost, colrows.com (cited by the researching agent; not independently re-verified line by line)
