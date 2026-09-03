# Capability Definitions

These are the eleven evaluation dimensions used across every [solution profile](../solutions/README.md). They exist so that "GuruSup vs. Glean vs. Confluence" comparisons are judged on the same axes instead of on marketing language.

| Area | What it evaluates |
|---|---|
| Deployment / ownership | Hosted, self-hosted, or hybrid; who operates the infrastructure. |
| Context capture | How docs, wikis, chats (Slack/Teams), tickets, CRM, meetings, email, and code enter the brain — connectors, imports, APIs, or manual entry. |
| Knowledge organization | Whether raw content becomes structured knowledge (entities, FAQs, playbooks, decisions) instead of a pile of unlinked documents. |
| Knowledge evolution | Whether the brain stays current as policies, products, and teams change — deduplication, review cycles, deprecation, staleness detection. |
| Retrieval / use | Whether the right context surfaces when someone (or an agent) is doing real work — search quality, grounding, filters, citations. |
| Agent activation / write-back | Whether AI agents (support bots, copilots, internal assistants) can read and, where relevant, write back through MCP, API, SDK, or plugin surfaces. |
| Activation evidence | Whether there is documented or observed proof that retrieved context is actually loaded into an agent's response — with a citation, a lineage trail, or a logged tool call — rather than merely being retrievable in principle. |
| Team / org / role scope | Whether knowledge can be scoped by team, department, role, or customer, and how permissions are enforced. |
| Feedback / correction | How subject-matter experts flag, verify, or correct what the brain knows. |
| Privacy / access control | Authentication, PII handling, audit trails, and data residency/retention controls. |
| Setup / operations | How much integration and maintenance work is required to get value, and to keep it running. |

## How to use this

When filling in a [solution profile](../templates/system-profile.md), evaluate each row against primary sources (official docs, official repos, or verified hands-on use). If a dimension cannot be verified yet, write `Unknown` rather than inferring — see [CONTRIBUTING.md](../CONTRIBUTING.md).
