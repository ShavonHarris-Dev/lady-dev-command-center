---
name: daily-standup
description: The org reports up. Khadijah collects what every director found overnight — signals, blockers, numbers, student risk, quiet deals — and hands back one short brief with what needs a decision today. Use for the morning review, when someone asks "what do I need to know", or on any check-in of where things stand.
---

# Daily Standup

The directors report to Khadijah. Khadijah reports one brief.

This is the ritual that makes the fleet real instead of theoretical. It should take **five minutes to read**, not twenty.

## Collect in parallel

One message, multiple Agent calls. Ask each director for their lane only, and be explicit that you want signal, not a status report.

| Director | Ask for |
|---|---|
| **Gladys** | What moved in the world in the last 24h that changes what we should do. Signals, not news. Max 3. |
| **Kyle** | What's stuck, who it's stuck on, how long. Plus anything on the calendar today that conflicts with a priority. |
| **Tripp** | What moved in the numbers. Only if it moved enough to matter — say "nothing moved" rather than inventing a trend. |
| **Regine** | Any student gone quiet or at risk. Anything the audience is repeatedly asking to learn. |
| **Overton** | Deals that have gone quiet past the point where silence means something. Anything needing a decision to move. |
| **Scooter** | Anything flagged **Needs recheck** that's now stale and being relied on. |

**Sinclair, Maxine, and Ivan don't report daily** unless there's an active directive — they're producers, and a daily "nothing to report" from three agents is noise that trains people to skim.

## Verify before you write

Every "waiting on X" and "unanswered" claim gets checked before it reaches the brief. The failure this prevents: reporting a request that was already resolved in a later reply, a different thread, or Slack.

For each open item, confirm the director actually **read the full thread** and **searched for a later resolution** — not just the one message that raised it. If they can't confirm, the item goes in as *unverified*, or it doesn't go in.

Every item carries **when it last moved**. "Asked Tuesday, no reply since" is defensible. "Waiting on you" is not.

A brief with three verified items beats one with eight where two are wrong. **Two wrong items and nobody trusts the other six.**

## Then write the brief

Structure it in this order. The order is the point — the first thing they read should be the thing that needs them.

**1. Needs you today**
Decisions only you can make. If there are none, say "nothing needs you" and mean it. This section being empty on a real day is a good day, not a failure.

**2. Moving against you**
Blockers, quiet deals, at-risk students, numbers trending wrong. What's at risk and what it would take to fix.

**3. Worth knowing**
Signals from Gladys, notable number movement, things the audience is asking for. Maximum three items. If everything is worth knowing, nothing is.

**4. In flight**
One line on open directives — what's running, what came back. Skip entirely if nothing is running.

## Rules

**Lead with what needs a decision.** Not with a summary of yesterday. They're reading this to find out what to do.

**Empty sections get deleted, not filled.** A brief that's the same length every day is being padded, and padded briefs stop getting read within a week.

**Every item earns its place.** "Newsletter open rate was 34%" is trivia. "Open rate dropped 8 points on the last two sends, both of which went out Friday afternoon" is a finding.

**Say when nothing happened.** A three-line brief on a quiet day is honest and builds trust in the long one.

**Connect to the goals.** Reels at 10k, YouTube to 1,000 subs, the podcast, media company, $1M in 2027, newsletter growth. If an item doesn't touch one of these, it needs a good reason to be in the brief.

## Publish it to Projected

**This is the point of the whole ritual.** Don't leave the brief in a chat window — save it to Projected with `save_briefing`, kind `brief`. It lands on the dashboard hero card, which is where Kedasha and Shavon actually look.

Check `get_latest_briefing` first to see what's currently up there, so you're not duplicating a brief that already ran.

For other outputs, use the matching kind so they land in the "From the command center" feed: `analytics` for Tripp's readouts, `content-strategy`, `script`, `newsletter`, `brand-deal`, `launch`, `podcast`, `engagement`. Only the latest per kind stays visible, so each one should stand alone.

## Then log it

Scooter files the brief. Trends only exist if the earlier points were recorded — and "this is the third week Tripp has flagged the same drop" is a far more useful sentence than any single day's number.

## What this is not

Not a to-do list. Not a summary of everything that happened. Not a performance report on the agents.

It's the answer to one question: **what do I need to know before I start?**
