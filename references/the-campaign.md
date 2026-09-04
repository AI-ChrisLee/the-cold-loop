# The campaign

Beat 5's detail. One campaign, one mailbox, the same daily number the founder already sent by hand.

## The one honest sentence

**The send runs overnight, on Instantly's servers, from the founder's own mailbox, on a list they
approved.** Not the scraper, which deposits a raw dataset that is not a list until a human cuts it.
Not the read, which takes a minute on Sunday. One true leg beats 3 claimed ones.

## Connecting Instantly

Instantly's MCP is a remote hosted server, added as a custom connector at
`https://mcp.instantly.ai/mcp`. Instantly publishes several ways to authenticate: signing in through
OAuth is the current one, and pasting the API key into the URL
(`https://mcp.instantly.ai/mcp/YOUR_API_KEY`) still works but Instantly's own notes call it the legacy
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
| `daily_limit` | in messages, the unit Instantly counts: the by-hand day's total, about 30 once all 3 cohorts are running, never above what they were already sending by hand | Gate A multiplies nothing. It removes the copy and paste |
| `email_gap` | spread across the sending window | 30 messages arriving in 4 minutes reads as what it is |
| the footer | preserved on every step | the postal address and the opt-out do not become optional here |

**Say this out loud, because it is the most useful safety fact in the lane:** Instantly's own High
Bounce Auto-Pause is on by default at 5%, but its help article says a campaign must send at least 200
emails before that check runs. A founder sending 50 a week has no automatic brake for the first
weeks. **The founder is the brake.**

**Do not turn on A/Z auto-optimize.** Its own documentation states no threshold and no minimum sample
before it deactivates a variant. At about 25 people an arm it can quietly switch off the better
message.

## What it costs a month

| Item | Cost |
|---|---|
| Instantly, the tier with API access | about $47 a month, confirmed against the workspace's own billing at run time |
| A second seat on the workspace the founder already owns, its own inbox | about $7 to $8 a month. An alias on their existing mailbox is free, and before Gate B an alias is what this lane asks for |
| A domain, Gate B only | about $12 a year |
| Apify, a weekly 200-place pull | about $1.20 a month, inside the free $5 credit |
| **After Gate A** | Instantly, and nothing else. The alias costs nothing |
| **Before Gate A** | **$0** |

Print this before the founder subscribes to anything, not after. A member on a small budget deserves
the number in front of the step.

## The load, and the word that starts it

**Before every load, call `accounts_test_vitals` on the sending address, and refuse to load when its
domain comes back in the failing list; say which record failed (MX, SPF, DKIM or DMARC).** Once a
campaign has sent, read that campaign's bounces with `analytics_campaign_overview` and refuse to load
when bounce is over 2%. Sustained bounce over 2% for a few days suppresses placement across the whole
domain. On the first load nothing has sent through Instantly yet, so there is no bounce number and the
DNS check stands as the gate.

**The load is one batch and nothing else.** The approved rows go in as leads through
`add_leads_to_campaign_or_list_bulk`, each carrying its own broken-thing first line, and the 3
touches become the campaign's day 1, day 4 and day 9 steps with the footer on every one. A row with
no `cut <date>` above it does not load. A row already in `squad/outreach-sent.md` does not load.
Report loaded, dropped as duplicates, and dropped for a missing address.

**The campaign starts on one word, and only on it.** Print what is about to go out, the daily limit,
the window and the sending address, then wait. **"Turn it on."** calls `activate_campaign`. Anything
else leaves it paused. From the second week on the campaign is already running, the batch simply
loads into it, and there is nothing to press.

## The ramp, Gate B only

Behind Gate B, and never before it:

- A domain at least 14 days old before it sends anything.
- A 30-day ramp: 5 to 10 a day in week 1, 10 to 20 in weeks 3 and 4, 30 to 50 once it is 30 days old
  and clean, capped at 200.
- Then, and only then, a daily limit above the by-hand number, a second town or trade, and any split
  test.
- **Do not send cold from the address paying clients reply to.** A founder with no clients yet has
  nothing to protect and everything to learn; a founder with clients takes a second mailbox.

## What is never built, and the one line for each

| Never | The line |
|---|---|
| An Apify schedule | the Apify MCP publishes no schedule tool, so this skill cannot make one, and a weekly pull takes minutes by hand in the same session where the list is approved. Apify's own console can run one, about $1.20 a month, for the founder who asks |
| A scheduled task for the send | it is skipped whenever the laptop sleeps and fires when the lid opens, which is the moment the founder could type the command. And the standing rule forbids scheduling anything that sends |
| A cloud routine over `squad/` | `squad/clients/*/transcript.md` holds real people's recorded words. Pushing that to a hosted repository to save one typed command is a trade nobody makes once it is stated that way |
| An auto-reply agent | every reply is answered by the founder. Taste first; since 2026-08-02 the EU AI Act's Article 50 transparency duties are the second reason, and a human-sent draft keeps this lane clear of the question |

**The standing rule, quoted wherever a schedule comes up:** a routine that only reads, only drafts or
only reduces spend may be scheduled. A routine that sends, spends more or publishes never runs
unattended.

## The file

`squad/outreach-routine.md`:

```
# Outreach routine
built <date> · Gate A open <date> · Gate B <open <date> | not yet>

Sending address: <address, not the one clients reply to>
Workspace: <Instantly workspace> · plan: <what workspace_billing_plan_details returned>
Campaign: <name> · daily limit <n> · stop_on_reply on · text_only on · open tracking off
Started: <date the founder said "Turn it on.">
Cost a month: <total, itemised>

The weekly approval: the founder cuts and approves the list before it loads. Every week. Forever.
```
