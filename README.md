# LadyDev Command Center

The LadyDev agent org, packaged as a Claude plugin so it installs on any machine.

**You talk to Khadijah. Nobody else.** She's chief of staff — she takes the request, decides who does the work, delegates it, and comes back with one answer.

## The org

| Agent | Role | Model |
|---|---|---|
| **Khadijah** | Chief of Staff — the only one you talk to | Opus 5 |
| **Scooter** | Memory Curator — tends the shared Brain | Sonnet |
| **Sinclair** | Product — coding, design, ship QA, feature ideation | Sonnet |
| **Maxine** | Written Content — LinkedIn, X, newsletter, recycling | Sonnet |
| **Ivan** | Video & Audio — Reels, YouTube, podcast, production briefs | Sonnet |
| **Overton** | Clients & Advising — pipeline, proposals, presentations | Sonnet |
| **Regine** | Education — curriculum, sessions, student outcomes | Sonnet |
| **Kyle** | Operations & Admin — calendar, invoices, dependencies | Sonnet |
| **Gladys** | Creative Research — signals, people, market, workforce | Sonnet |
| **Tripp** | Insight — funnel, analytics, performance, did-it-work | Sonnet |

## Playbooks

Skills Khadijah loads when the situation calls for them.

| Skill | What it does |
|---|---|
| `khadijah` | The chief of staff herself. Load at session start. |
| `hot-take` | One raw thought → drafts across every channel. Captures your exact words first, interrogates the claim, then fans out to Maxine and Ivan. |
| `daily-standup` | The org reports up. Five minutes to read, decisions first, empty sections deleted rather than padded. |
| `contract-review` | "Where am I getting screwed?" on any contract, proposal, or brand deal. Agent pass → human read → lawyer. Never agent → signature. |

## Scheduled tasks

Set these up per machine (they aren't part of the plugin — scheduled tasks are account-level).

| When | What |
|---|---|
| Daily, morning | **Daily standup** — the org reports what happened overnight |
| Daily, an hour later | **Hot take** — "any craziness to share?" Answer it and the pipeline runs. Silence is fine; it never follows up. |

## Install

Requires a **paid Claude plan** (Pro or Max) and the **Claude desktop app**.

1. Desktop app → **Customize** → **Plugins**
2. **Add marketplace** → **Add from a repository**
3. Paste this repo's URL
4. Install **ladydev-agents**

To update later: push changes to this repo, then run marketplace update on each machine.

## Use it

Start a session and invoke Khadijah:

```
/ladydev-agents:khadijah
```

Then just talk to her normally. She handles the rest.

**To make every session start as Khadijah**, paste this into your Cowork project instructions:

> You are Khadijah, chief of staff of the LadyDev agent org. Load the `khadijah` skill from the ladydev-agents plugin at the start of every session and operate as her.

## Architecture: why Khadijah is a skill, not a subagent

Subagents can't reliably spawn other subagents. If Khadijah were a subagent, she couldn't delegate — which is her entire job.

So Khadijah is a **skill** that the main session adopts. The main session *becomes* her, and she spawns the directors as subagents. That's what makes the chain of command actually work rather than just being described in a document.

## The Brain

Agent definitions sync through this repo. **Knowledge does not.** Cowork memory is local to each machine and never syncs, so without an external store, work done on one machine is invisible on the other.

That store is Notion: **⚡ Command Center V2 → 🧠 The Brain**, with four boards — Agent Roster, Directives, Research Log, and Decisions.

Both people need access to the same Notion workspace. The standing rule, built into every agent: **nothing is finished until it's written to the Brain.**

## Connectors each agent needs

Connect these on each machine. An agent missing its connector will still run, but can't do its job.

| Agent | Needs |
|---|---|
| Khadijah | Notion |
| Scooter | Notion, web search |
| Sinclair | Files, shell, Notion |
| Maxine | **Kit**, Notion, web search |
| Ivan | Notion, Google Drive, Kajabi, web search |
| Overton | **Gmail**, **Google Calendar**, Google Drive, Notion |
| Regine | **Kajabi**, Notion |
| Kyle | **Google Calendar**, Gmail, Kajabi, Notion |
| Gladys | Web search, Apify, Notion |
| Tripp | **Kit**, **Kajabi**, Notion |

Bold = the connector that agent is useless without.

Each person connects these under their **own** Claude account. Nothing is shared through this repo — no API keys, no tokens. Keep it that way.

## Standing rules, enforced in every agent

- **No AI-written copy is ever published.** Agents draft; humans write what ships.
- **Nothing sends automatically.** Emails, proposals, invoices, posts — all go to a human first.
- **Nothing is finished until it's written to the Brain.**
- **Every agent has a "Never Does" boundary.** Overlapping vague agents is the main failure mode at this size.

## Renaming an agent

Names come from the *Living Single* cast. To rename one:

1. Rename the file in `plugins/ladydev-agents/agents/`
2. Change the `name:` field in its frontmatter
3. Update the table in `skills/khadijah/SKILL.md` — Khadijah routes by name
4. Bump `version` in both `plugin.json` and `marketplace.json`
5. Push, then update the marketplace on each machine

Step 3 is the one that breaks things if you skip it.

## Adding an agent

Drop a new `.md` file in `agents/` with the same frontmatter shape, add it to Khadijah's routing table, add a row to the Notion Agent Roster, and bump the version.

Keep charters sharp. Ten well-defined agents beat twenty vague ones — vague agents overlap, duplicate each other's work, and quietly stop being used.
