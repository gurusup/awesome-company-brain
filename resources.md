# External Resources

Essays, talks, and public discussion that shaped or popularized the "company brain" category — useful context beyond the solution comparisons above. As with the rest of this repo, every claim below is either linked to a primary source or explicitly flagged as unverified.

## Essays & Talks

- **["From Hierarchy to Intelligence"](https://www.sequoiacap.com/article/from-hierarchy-to-intelligence/)** — Roelof Botha (Sequoia Capital) and Jack Dorsey (Block), March 2026. Argues that management hierarchies exist largely to route information manually, and that AI can now maintain a continuously updated "world model" of a company's operations — letting intelligence live in the system rather than being routed through people. One of the more prominent VC essays articulating the organizational-world-model thesis behind "company brain."
- **[Karpathy's "LLM Wiki" gist](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)** — Andrej Karpathy, April 2026 (reportedly ~17M views on X). Describes a pattern where an LLM actively maintains a structured, cross-referenced wiki distilled from raw sources — "Obsidian is the IDE, the LLM is the programmer, the wiki is the codebase" — rather than just searching flat notes. This is the personal/individual-scale concept behind many "second brain" implementations (see [Awesome AI Second Brain](https://github.com/aristoapp/awesome-second-brain)); it's included here as the conceptual ancestor of company-scale tools like [GBrain](solutions/gbrain.md) and [OpenViking](solutions/openviking.md), which apply the same "durable, structured, LLM-maintained knowledge base" idea at team/org scale.

## YC and the "Company Brain" Label

Y Combinator's Spring/Summer 2026 batches produced a cluster of startups independently converging on "company brain" as their positioning — this is the more defensible "YC popularized this term" story, evidenced directly via Hacker News and YC's own company pages, rather than a single official YC document:

- **[Launch HN: Hyper (YC P26) – Company brain to power agentic development](https://news.ycombinator.com/item?id=48387095)** — real Hacker News thread, 79 points / 78 comments.
- **[Memory Store's YC company page](https://www.ycombinator.com/companies/memory-store)** — tagline: "Company Brain. One memory for your team's agents."
- **[Hyperspell's YC company page](https://www.ycombinator.com/companies/hyperspell)** — marketed as "Your Company Brain," an infra/API memory layer for other builders' agents.
- **[Wato's Launch YC post](https://www.ycombinator.com/companies/wato)** — "a shared AI workspace for teams."
- **[GBrain](solutions/gbrain.md)** ([github.com/garrytan/gbrain](https://github.com/garrytan/gbrain)) — an open-source agent-memory project whose README attributes it to Garry Tan, President and CEO of Y Combinator, with a documented "company brain" team mode. The authorship claim is self-reported in the README and corroborated by several third-party write-ups, but is not independently certified — see the [solution profile](solutions/gbrain.md) for the full caveat. If accurate, it's a notable case of a senior YC figure personally building and open-sourcing a "company brain" reference implementation.

### A claim we could not verify — read before repeating it

Numerous blogs (colrows.com, modelence.com, and others) claim that a Y Combinator "Requests for Startups" page named "Company Brain" as a wishlist idea, attributed to partner Tom Blomfield, quoting: *"If we want every company to run on AI automation, we need a new primitive: a company brain..."* We directly fetched `ycombinator.com/rfs` and found the current (Fall 2026) RFS list does **not** include this entry or any Tom Blomfield attribution. It's possible this appeared in an earlier RFS season and was later rotated off the live page — YC's RFS page only shows the current batch's wishlist — but we could not confirm this against an archived snapshot or an independent reputable source. **Treat this specific claim as unverified/"reportedly," not fact**, until someone finds a dated archive or a citation from a reputable outlet.

## Further Reading (secondary sources, framing the category)

These are secondary/commentary sources — useful for how others frame the category, not primary evidence for any factual claim in this repo:

- [Vectorize — "How to Build a Company Brain"](https://vectorize.io/articles/how-to-build-company-brain)
- [Falconer — "Company Brain: Competitive Moat"](https://falconer.com/guides/company-brain-competitive-moat/)
- [Sentra — "What Is a Company Brain?"](https://www.sentra.app/articles/what-is-a-company-brain)
- [Forbes — "Enterprise Brain Replaces AI Agents And Loops As Microsoft And Glean Race"](https://www.forbes.com/sites/sandycarter/2026/08/11/enterprise-brain-replaces-ai-agents-and-loops-as-microsoft-and-glean-race/) (August 2026)

## Related tools we deliberately did not add

Several tools that use "company brain"-adjacent framing were evaluated and left out — see [watchlist.md](watchlist.md) for tools needing more verification, and each affected [solution profile](solutions/README.md) (e.g. [Quivr](solutions/quivr.md), [Amazon Q Business](solutions/amazon-q-business.md)) for tools whose positioning has materially changed since launch.
