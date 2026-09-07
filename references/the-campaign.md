# The campaign

3.3 to 3.5's detail, and beat 5's moves. One campaign, one mailbox, the same daily number the
founder already sent by hand.

## The one honest sentence

**The send runs overnight, on Instantly's servers, from the founder's own mailbox, on a list they
approved.** Not the scraper, which deposits a raw dataset that is not a list until the squad ranks
it and the founder says go. Not the read, which takes a minute on Sunday. One true leg beats 3
claimed ones.

## The gate, in one line

One finished batch by hand: every row of one batch carries all 3 touches stamped in
`squad/outreach-sent.md`, and the last name is past day 9. That is the whole gate. No Instantly is
fine; 10 a day by hand is the same lane.

## Connecting Instantly

Instantly's MCP is a remote hosted server, added as a custom connector at
`https://mcp.instantly.ai/mcp`. Instantly publishes several ways to sign in: signing in through
OAuth is the current one, and pasting the API key into the URL
(`https://mcp.instantly.ai/mcp/YOUR_API_KEY`) still works but Instantly's own notes call it the old
form. Take whichever one their connector screen offers, and never guess a path you have not seen
answer. (Apify is in the connector directory, which is why the list beat's connector line is
different.)

**Never assert a plan tier.** Instantly's help page says the server is free with the subscription
plus "an account with API access"; the pricing page puts API at a paid tier. The 2 pages disagree, so
call `workspace_billing_plan_details` and report what the workspace actually has.

## The settings

| Setting | Value | Why |
|---|---|---|
| `stop_on_reply` | true | a reply ends the sequence for that person. Nobody gets touch 3 after answering |
| `text_only` | true | no tracking pixel, no HTML. It is also why there is no open rate |
| `open_tracking` | false | same reason. Apple and Gmail inflate opens anyway |
| `daily_limit` | in messages, the unit Instantly counts: the by-hand day's total once all 3 groups were running (10 new names plus that day's follow-ups), never above what they were already sending by hand | Instantly multiplies nothing. It removes the copy and paste |
| `email_gap` | spread across the sending window | 30 messages arriving in 4 minutes reads as what it is |
| the footer | preserved on every step | the postal address and the opt-out do not become optional here |

**Say this out loud, because it is the most useful safety fact in the lane:** Instantly's own High
Bounce Auto-Pause is on by default at 5%, but its help article says a campaign must send at least 200
emails before that check runs. A founder sending 50 a week has no automatic brake for the first
weeks. **The founder is the brake.**

**Do not turn on A/Z auto-optimize.** Its own documentation states no threshold and no minimum sample
before it deactivates a version. At about 25 people an arm it can quietly switch off the better
message.

## What it costs a month

| Item | Cost |
|---|---|
| Instantly, the tier with API access | about $47 a month, confirmed against the workspace's own billing at run time |
| A second mailbox, beat 5's move 1 | an alias on the workspace the founder already owns is free; a second seat with its own inbox is about $7 to $8 a month |
| A second domain, move 1 only when the first mailbox is full | about $12 a year |
| Apify, a weekly 120-place pull | about $2 a month, inside the free $5 credit |
| **By hand** | **$0** |

Print this before the founder subscribes to anything, not after. A member on a small budget deserves
the number in front of the step.

## The load, and the word that starts it

**Before every load, call `accounts_test_vitals` on the sending address, and refuse to load when its
domain comes back in the failing list; say which record failed (MX, SPF, DKIM or DMARC).** Once a
campaign has sent, read that campaign's bounces with `analytics_campaign_overview` and refuse to load
when bounce is over 2%. Sustained bounce over 2% for a few days pushes every message from that
domain toward spam. On the first load nothing has sent through Instantly yet, so there is no bounce
number and the DNS check stands as the gate.

**The load is one batch and nothing else.** The approved rows go in as leads through
`add_leads_to_campaign_or_list_bulk`, each carrying its own broken-thing first line, against the 3
steps built from `squad/cold-messages-<that batch's go date>.md` with the footer on every one. No
message file for that batch means beat 2 never finished, and the touches are written there rather
than recalled here. A row with no `go <date>` above it does not load. A row already in
`squad/outreach-sent.md` does not load. Report loaded, dropped as duplicates, and dropped for a
missing address.

**The campaign starts on one word, and only on it.** Print what is about to go out, the daily limit,
the window and the sending address, then wait. **"Turn it on."** calls `activate_campaign`. Anything
else leaves it paused. From the second week on the campaign is already running, the batch simply
loads into it, and there is nothing to press.

## The second mailbox and the ramp, beat 5's move 1 only

The signal opens it: one batch whose first line booked 2 or more calls, or one paying client from
this list, read off `squad/pipeline.md`. Never before.

- **An alias first.** Free, on the workspace the founder already owns, sending the day it is made.
- **A second domain only when the first mailbox is full.** Then the wait and the ramp:

| Day | The new domain sends |
|---|---|
| 0 to 14 | nothing. SPF, DKIM and DMARC set, and the domain ages |
| 15 to 21 | 5 to 10 a day |
| 22 to 44 | 10 to 20 a day |
| 45 on, and clean | 30 to 50 a day, capped at 200 |

- `daily_limit` rises by the new mailbox's own number, never the first mailbox's.
- **Do not send cold from the address paying clients reply to.** Both mailboxes stay addresses
  clients do not write to.

## What is never built, and the one line for each

| Never | The line |
|---|---|
| An Apify schedule | the Apify MCP publishes no schedule tool, so this skill cannot make one, and a weekly pull takes minutes by hand in the same session where the list is approved. Apify's own console can run one, for the founder who asks |
| A scheduled task for the send | it is skipped whenever the laptop sleeps and fires when the lid opens, which is the moment the founder could type the command. And the standing rule forbids scheduling anything that sends |
| A cloud routine over `squad/` | `squad/clients/*/transcript.md` holds real people's recorded words. Pushing that to a hosted repository to save one typed command is a trade nobody makes once it is stated that way |
| An auto-reply agent | every reply is answered by the founder. Taste first; since 2026-08-02 the EU's AI Act also asks that a person be told when a machine wrote to them, and a draft the founder sends by hand keeps this lane clear of the question |

**The standing rule, quoted wherever a schedule comes up:** a routine that only reads, only drafts or
only reduces spend may be scheduled. A routine that sends, spends more or publishes never runs
unattended.

## The file

`squad/outreach-routine.md`, written by beat 5:

```
# Outreach routine
opened <date> on <the signal: 2 calls off batch <go date>'s first line | a paying client from batch <go date>>

Campaign: <name> · started <date the founder said "Turn it on.">
Mailboxes: <address> at <n> a day · <second address, or none yet> at <n> a day
Move 1, the daily number: <date, or not yet> · <what was added>
Move 2, the second town or trade: <date, or not yet> · <town or trade>
Move 3, the read routine: <date, or not yet> · outreach-read, local, Sunday
Cost a month: <total, itemised>

The week: Monday the pull and the rank, the founder says go, the campaign keeps sending, Sunday the read.
Replies: by the founder's hand, always.
```
