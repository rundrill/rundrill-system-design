# RunDrill System Design

Your personal **system-design coach** inside your AI agent — learn to design distributed systems and
prep for the **FAANG system design interview** the way the job actually demands it: by **reviewing
flawed designs**, **defending tradeoffs under pushback**, **estimating capacity**, and **running mock
interviews** — not by memorising reference architectures or watching the AI design the system for you.
Short targeted drills, an honest picture of your level, and mistake memory that resurfaces what you
got wrong. Your level and progress live on the RunDrill MCP server (`mcp.rundrill.com`), synced across
machines — not in a local file.

**Why this course is different.** System design has no compiler and **no single right answer** — a
design doesn't "run", so the skill that matters is *reasoning*: spotting the bottleneck, naming the
tradeoff, defending a choice or adapting when challenged. When an AI can draw any architecture on
demand, the real risk is the *illusion of competence* — accepting a design that reads fine and is
quietly wrong: a hidden single point of failure, a hot shard, a wrong consistency choice, a cache that
lies, an unbounded queue. The **signature drill hands you a plausible design with a planted defect and
asks you to find it, like a senior-engineer review.** Plus commit-then-defend tradeoff drills,
back-of-envelope estimation, predict-the-failure-mode, and full mock interviews graded on the four
interviewer dimensions with a level read (E4 / E5 / E6+).

The course climbs five levels — **Foundations** (scaling, latency, CAP, networking, load balancing,
stateless web tiers) →
**Components** (SQL/NoSQL, indexing, replication, sharding, caching, queues, Kafka, CDNs, APIs,
WebSockets, object storage, search) → **Patterns** (consistent hashing, consistency models,
idempotency, rate limiting, fan-out, distributed transactions, observability, release safety,
security) → **Systems**
(design TinyURL, Twitter, WhatsApp, YouTube, Uber, Ticketmaster, cloud storage, collaborative editing,
checkout, a payment system, and more,
end-to-end) → **Interview** (the framework, capacity estimation, deep dives, tradeoff discussion,
common mistakes, leveling). It is grounded in canonical sources (the system-design primer, DDIA-level
concepts, the Hello Interview / ByteByteGo interview frameworks).

**Pick your goal.** Three paths, your choice: **Learn system design** (understand + design real systems
— Foundations through full system designs), or **Prep for the interview** (everything plus the
interview-performance layer: the 5-step framework, estimation technique, tradeoff discussion, and
what E4/E5/E6+ answers look like), or **Systems engineering depth** (extra mechanisms and system
families beyond the interview minimum).

**Learn in your language.** Interviews are usually in English, but you don't have to study only in
English: set your native language and the coach explains in it while giving every term as *native
(English original)* — so you reason naturally and still recognise the terms in the interview.

## One plugin, three hosts

The coaching skill (`skills/system-design-coach/SKILL.md`) and `.mcp.json` are shared; each host reads
its own manifest and ignores the rest.

| Host | Reads |
|---|---|
| Claude Code / Claude Desktop | `.claude-plugin/plugin.json` + `.mcp.json` |
| OpenAI Codex | `.codex-plugin/plugin.json` + `.mcp.json` |
| Google Antigravity | `plugin.json` + `mcp_config.json` (+ `rules/`) |

The MCP endpoint is `https://mcp.rundrill.com/coach/system-design` — the coach-course host, passing
`course: "system-design"`. The server routes on the `/coach` segment and ignores the course name;
the name makes this register as its own MCP server in your agent. On first use the host opens a browser
tab for the OAuth handshake, then closes it — no API key to paste.

## Install

- **Claude Code / Desktop** — via the RunDrill marketplace:
  ```
  /plugin marketplace add rundrill/rundrill
  /plugin install rundrill-system-design@rundrill
  ```
  Then run `/system-design-coach`.
- **OpenAI Codex** — `codex plugin marketplace add rundrill/rundrill`, then install `rundrill-system-design`.
- **Google Antigravity** — drop this folder into `~/.gemini/config/plugins/rundrill-system-design/`
  (global) or `<workspace>/.agents/plugins/rundrill-system-design/` (workspace-scoped).

## License & attribution

© RunDrill. Licensed under **Creative Commons Attribution-NonCommercial-NoDerivatives 4.0
International (CC BY-NC-ND 4.0)** — full text in [LICENSE](LICENSE). You may view, run, and share this
plugin unchanged, non-commercially, with attribution; you may not use it commercially or publish
modified/derivative versions. For other licensing, contact **hello@rundrill.com**.
