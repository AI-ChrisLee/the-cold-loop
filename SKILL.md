---
name: the-cold-loop
description: Use this when the founder is going after strangers. They say "build my outreach list", "pull my list", "/the-cold-loop list", "write my cold email", "send this week's batch", "this week's batch went out", "put the send on Instantly", "turn it on", "start the campaign", "/the-cold-loop send", "read my batch", "how did the batch do", "/the-cold-loop read", "raise the daily number", "add a second town", "put the read on a routine", "/the-cold-loop routine", or "continue the cold loop" (picking a stopped run back up). It builds the list of 50, writes the 3 touches with the legal footer, stages 10 names a morning for the founder's own hand, moves the send to Instantly after one batch, reads 3 numbers off finished batches, and runs the routine one move at a time. It never sends, and it refuses to write a cold message carrying no postal address and no opt-out.
---

# The Cold Loop

**Your first message on a fresh run carries this line, once:**

> This skill is a base. Once you have done it your way, tell your squad "update the skill to do it like this."

Strangers, one town and one trade at a time: get the list, send, read, make it a routine.

**You never send.** You write and you stage; the founder presses send, and answers every reply by
hand after `the-close` sorts it. Instantly's servers send only the batch they approved, from their
own mailbox.

Two refusals. Every cold message carries a real postal address and a working opt-out, at any
volume, with no exception for business-to-business mail. And a country that requires consent before
commercial mail stops the run.

`.claude/squad-roots.md` is the per-repo instance file every member-run skill reads first, and its
values win over the `squad/` paths below, which are worked examples. `<date>` is `YYYY-MM-DD`, and
a batch is named by the date the founder said go.

## The modes

| Mode | The founder says |
|---|---|
| list | "build my outreach list", "pull my list", `/the-cold-loop list` |
| send | "write my cold email", "send this week's batch", "this week's batch went out", "put the send on Instantly", `/the-cold-loop send` |
| turn it on | "turn it on", "start the campaign" |
| read | "read my batch", "how did the batch do", `/the-cold-loop read` |
| routine | "raise the daily number", "add a second town", "put the read on a routine", `/the-cold-loop routine` |

**Resuming.** A bare `/the-cold-loop` or "continue the cold loop" reads the outputs, never a
session's memory, and continues at the first thing missing: no list, or no `go <date>` on its
newest section, section 1; no messages for that go date, 2; today's names not drafted, 3; a batch
past day 9 of its last name with no read section, 4. A section carrying a `go <date>` is approved:
never re-pull it, never re-rank it. Say in one line where you picked up.

## The files

| Path | What it holds |
|---|---|
| `squad/cold-list.md` | the batches, newest section on top, 50 ranked rows each |
| `squad/cold-messages-<go date>.md` | that batch's 3 touches, the footer on each |
| `squad/cold-batch-<the day it was drafted>.md` | that morning's names, where no mail connector reaches the mailbox |
| `squad/outreach-sent.md` | a row per company per touch. This skill's memory, and what every pull dedups against |
| `squad/outreach-read.md` | a section per finished batch, appended, plus the winner line |
| `squad/outreach-routine.md` | the signal, each move and its date, the mailboxes, the monthly cost |
| `.claude/squad-roots.md` | the `postal address`, `cold list town` and `sending address` rows, nothing else |

Off disk, 2 things, each on the founder's word in that turn: one Instantly campaign, built paused,
and one weekly read routine. Nothing else gets written.

## Before any mode

- Four files next to `SKILL.md` must open: `references/the-list.md`, `references/the-messages.md`,
  `references/the-numbers.md`, `references/the-campaign.md`. Any missing: stop, and say the folder
  was downloaded without its `references/`.
- In `list` mode, probe Apify with one free `search-actors` call. Never probe with `call-actor`:
  that starts a billed run. Not wired: stop and send them to the token paste in g5.
- Read `.claude/squad-roots.md`, `squad/business.md` and the mode's own files, and say in one line
  what opened. No `squad/business.md`: stop in `list` and `send`, since there is no ask to make of
  a stranger yet, and point at g4 or g5. `read` and `routine` run without it.

## 1 The list

Mode `list`. `references/the-list.md` runs this section: the drops, the sentence, the rank, the
file. Read it first.

**Ask 3 things in one message,** and only what the roots file and the offer document do not hold:
the town, written to the roots file as `cold list town`; where the founder is and where this list
is; the postal address that goes on every message, written as `postal address`.

**If either country requires consent before commercial email to a business, stop.** Germany is the
named example: UWG Section 7(2) requires prior express consent for business advertising mail, and
exposure runs up to EUR 300,000 per case. Say the rule in 2 lines, say plainly that this is not
legal advice, and write no list until the founder says they have a lawful basis. A footer does not
fix a consent rule.

Then the work, alone. Run `fetch-actor-details` on `compass/crawler-google-places` every time
before calling it and build the input off the live schema: `<trade> in <town>`, **capped at 120
places**, about $0.48. **Never enable the business leads or email verification add-ons without
printing the price first:** $0.10 each on the free tier against a $5 monthly credit, so 200
verifications is $20, 4 times the whole credit. Then the drops, the one sentence per row, the rank,
the top 50.

**Then the dedup, and it is load-bearing.** Drop every address already in `squad/outreach-sent.md`,
including every row marked `stop`, or the second pull re-pulls the first pull's people.

Print the 50 numbered, each with its sentence. **Two answers move the list:** **go**, which stamps
the section `go <today's date>` and names the batch, or **swap row N**, which puts the next ranked
row in N's place, prints the list again and waits.

Later lists pull on the `cold list town` and the trade the offer document gives; a second town or
trade is the routine's move. The one exception is a town that cannot leave 50 standing: say so, ask
which widens, and pull on the answer.

## 2 The messages

Mode `send`, once a batch. `references/the-messages.md` carries the cage. Read it before you write.

**It asks one thing: which mailbox these leave from.** Never the address paying clients reply to;
no clients yet, and the mailbox they already use is the answer. Write it to the roots file as
`sending address`. Ask for the postal address only where the `postal address` row is missing,
since section 1 asked for it.

Day 1 runs under 125 words, its first line that row's broken thing in their own noun and town, one
ask answerable yes or no, and the ask is a call. Then day 4 and day 9, each carrying something the
last did not say. Never a bump. No price in any of the 3: the price is the call's, and the call is
`the-close`'s.

**The footer goes on all 3, and this is a refusal.** The founder's valid physical postal address
and a clear opt-out, honoured within 10 business days. CAN-SPAM has no volume threshold and, in the
FTC's own words, makes no exception for business-to-business email; each message in violation runs
up to $53,088. Say that once, in one line, the first time. No address, no message, and say why in
one line. The opt-out is real: an address replying "stop" is marked in `squad/outreach-sent.md`,
and the dedup drops it from every future list.

Print the 3 whole and stop on one line: change any word that is not yours. On their word, write
them to `squad/cold-messages-<this batch's go date>.md`, the footer on each, connector or no
connector.

## 3 The send

Mode `send`. By hand until one batch has fully gone out that way, on Instantly after, at the same
daily number. `references/the-messages.md` carries the daily file and the log;
`references/the-campaign.md` carries the connector, the settings, the load, the costs.

**The day**, Monday to Saturday, a Sunday touch going out Monday. At most 10 new names with touch
1, the names from 4 days ago with touch 2, the names from 9 days ago with touch 3, so the 50 enter
over 5 sending days. Which names are due comes off `squad/outreach-sent.md`, never off memory and
never off the founder. **You refuse to stage more than 10 new names a day by hand**, and say why in
one line: 10 a day from one mailbox reads as a person writing, more gets the mailbox flagged, and
an unproven message at volume proves nothing.

Place them as **drafts** through the founder's own mail connector, each follow-up threaded onto the
original, or write them to `squad/cold-batch-<today>.md` to copy. Either way **you never send**,
and never draft from an address the founder has not named as theirs. They read the first lines and
press send. Write each drafted row into `squad/outreach-sent.md` that morning, with the date, the
touch and `drafted`.

**The stamp, once a week.** "This week's batch went out." stamps that week's `drafted` rows and
marks `stop` on every address that replied stop. A reply is the founder's to hand to `the-close`,
which writes the person's row in `squad/pipeline.md`. You never write that file. A new address they
name, postal or sending, replaces its roots row and the messages are rewritten from it.

**Instantly, on "Put the send on Instantly."** The gate is one finished batch in
`squad/outreach-sent.md`: all 3 touches stamped on every row, the last name past day 9. Not there:
print how many of the 50 have all 3 touches out, and stop. No Instantly is fine, and 10 a day by
hand is the same lane. Then:

- The connector is a remote hosted server at `https://mcp.instantly.ai/mcp`, signed into on their
  own connector screen; never guess a path you have not seen answer. Call
  `workspace_billing_plan_details` and **report the tier the workspace actually has**, never assert
  one. Print the monthly cost off `references/the-campaign.md` before they subscribe to anything.
- Build **the campaign, paused**, named for this list, that batch's 3 messages as the day 1, day 4
  and day 9 steps with the footer on every one, `daily_limit` never above the by-hand day's total.
  Instantly's own High Bounce Auto-Pause does not arm until a campaign has sent 200 emails, so say
  out loud that for the first weeks **the founder is the brake**. Never turn on A/Z auto-optimize.
- Print what goes out, the daily limit, the window and the sending address, then stop. On **"Turn
  it on."** call `activate_campaign` and say it is live, with the date and the campaign name.
  Anything else leaves it paused, and you say so. Nothing else in this skill starts a campaign.

**The weekly load, on "Send this week's batch." with a campaign running.** `accounts_test_vitals`
on the sending address first, and refuse to load when its domain comes back failing, naming the
record (MX, SPF, DKIM or DMARC). Once it has sent, refuse to load over 2% bounce off
`analytics_campaign_overview`, saying the number you read. Where the campaign's 3 steps are not
that batch's message file, set them from it first (`update_campaign`), the footer on every one.
Load that batch and nothing else, each row carrying its own first line. Never load a row with no
`go <date>` above it, never one already in `squad/outreach-sent.md`, never more than 50, and never
raise `daily_limit` here. Report loaded, dropped as duplicates, dropped for a missing address. Then
stamp that week off `analytics_campaign_steps` into the log, `stop` on every opt-out, or the dedup
goes blind and the next pull emails the town twice.

## 4 The read

Mode `read`, Sunday, before `/bip sunday`. `references/the-numbers.md` runs this section.

A batch whose last name went out fewer than 9 days ago is **unfinished**. Say the batch is not
finished, print the week's raw counts labeled as counts and not as a rate, and stop there.

Finished: **3 numbers, people contacted, replies, calls booked**, every batch side by side in one
table. All 3 counted in **people**, never in messages: 50 people at 3 touches is up to 150
messages, and a rate on messages is a third of the truth. No opens. Campaign and log disagreeing:
print both, name which is which, use the campaign's.

Then the ladder, stopping at the first failure, and name the rung it stopped at; its last rung,
calls but no money, is g6's, not this lane's. **Under 300 people, print this word for word: under
300 people, 3 against 5 is a coin; do not rewrite the email on it.** Two batches under 300 a side
get both rows printed and no winner named.

One line for next week: one named change with its reason, or a hold. Most Sundays it is hold, and
that is the plan working. The change briefs Monday's run, never an edit to a batch already sending.
Wrong line, and the founder says what they would change instead; right, and they say yes. Then
write the batch's section into `squad/outreach-read.md` and stop. The founder tells their squad the
week, the numbers and the line, and the 4-week plan takes them.

The winner line runs on any batch, finished or not. The day `squad/pipeline.md` shows money from a
row whose source names this list, write that batch's first line word for word under `THE WINNER` in
`squad/outreach-read.md`, say you wrote it, and carry on.

## 5 The routine

Mode `routine`. `references/the-campaign.md` carries the second mailbox, the ramp, the costs, the
file's layout.

**The signal, read off `squad/pipeline.md`,** is one of 2 counts: one batch whose first line booked
2 or more calls, or one paying client from this list. Print which one opened it, with the batch and
the date. Neither there: print the count so far, calls per batch and money, and stop here. No
workaround, no override.

**Then 3 moves, one at a time, each on the founder's word, never 2 in a week.**

- **Raise the daily number.** The founder makes the second mailbox and names it: an alias on the
  workspace they own first, free and sending today; a second domain only when the first mailbox is
  full, then the 14-day wait and the ramp in `references/the-campaign.md`. Add it to the campaign,
  run `accounts_test_vitals` on it, and raise `daily_limit` by that mailbox's own number, never the
  first mailbox's. Both stay addresses paying clients do not write to.
- **Add a second town.** Update the `cold list town` row, or the trade, and say Monday's pull runs
  on it. The messages are the winning batch's 3 touches, copied: the first line that booked the
  calls does not change.
- **Put the read on a routine.** Name it `outreach-read`, weekly, Sunday morning, in the founder's
  own company folder, its whole instruction one sentence: "Read my batch." Where the app can create
  a local routine, create it and say what you made; where it cannot, print the path: Claude app,
  Code tab, Routines, New routine, **Local**, weekly. Local, never Cloud, since a cloud routine
  cannot see `squad/` at all. Tell them to press **Run now** once and choose always allow on every
  read it asks about. It only reads, so it sends nothing and spends nothing. On a no, register
  nothing and never offer again.

**The reply is never automated. No auto-reply agent, at any size.** Taste is the first reason;
since 2026-08-02 the EU's AI Act also asks that a person be told when an AI wrote to them, and a
draft the founder sends by hand keeps this lane clear of the question.

Write `squad/outreach-routine.md`: the signal and its date, each move with its date, the mailboxes
and their daily numbers, the routine's name, the monthly cost. Then stop.

## Never

- Never send. Not an email, not a reply, not a booking. Instantly's servers send only what the
  founder approved; every other message leaves by their hand.
- Never write a cold message with no postal address and no opt-out, at any volume, business
  recipients included.
- Never write a list for a country that requires consent first, until the founder says they have a
  lawful basis. Say it is not legal advice.
- Never stage more than 10 new names a day by hand, and never write to a 51st company.
- Never put a price in a cold message, and never price past `squad/business.md`. The ask is a call.
- Never start a campaign on any word but "Turn it on.", and never raise `daily_limit` outside the
  routine's first move.
- Never invent a company, a contact, an email address, a number or a need. A blank cell with a note
  that the row is worth a phone call is an answer; a guessed address is a bounce. What is seen from
  outside is an observation, never a quote.
- Never make a gate a rate. One finished batch by hand opens Instantly; 2 calls off one first line,
  or one paying client, opens the routine. All counts.
- Never claim the list scrapes itself, that the numbers get read overnight, or that a split test
  runs on its own. At this volume none of the 3 is true.
- Never write `squad/90-day-plan.md`, `squad/business.md` or `squad/pipeline.md`. A person's row is
  `the-close`'s to write.
