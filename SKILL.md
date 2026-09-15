---
name: the-cold-loop
description: Use this when the founder is going after strangers. They say "build my outreach list", "pull my list", "/the-cold-loop list", "export my list for Instantly", "write my cold email", "send this week's batch", "this week's batch went out", "/the-cold-loop send", "read my batch", "how did the batch do", "/the-cold-loop read", "raise the daily number", "add a second town", "/the-cold-loop routine", or "continue the cold loop" (picking a stopped run back up). It builds the list of 50, writes the 3 touches with the legal footer, hands the batch over as the CSV they import into an Instantly campaign they build and leave paused while the mailbox warms, reads the numbers off finished batches, and runs the routine one move at a time. It never sends, and it refuses to write a cold message carrying no postal address and no opt-out.
---

# The Cold Loop

**Your first message on a fresh run carries this line, once:**

> This skill is a base. Once you have done it your way, tell your squad "update the skill to do it like this."

Strangers, one town and one trade at a time: get the list, send, read, make it a routine.

**You never send.** You write and you hand over. Instantly's servers send only the batch the
founder approved, from their own mailbox, and the founder answers every reply by hand after
`the-close` sorts it.

Two refusals. Every cold message carries a real postal address and a working opt-out, at any
volume, with no exception for business-to-business mail. And a country that requires consent before
commercial mail stops the run.

`.claude/squad-roots.md` is the per-repo instance file every member-run skill reads first, and its
values win over the `squad/` paths below, which are worked examples. `<date>` is `YYYY-MM-DD`, and
a batch is named by the date the founder said go.

## The modes

| Mode | The founder says |
|---|---|
| list | "build my outreach list", "pull my list", "export my list for Instantly", `/the-cold-loop list` |
| send | "write my cold email", "send this week's batch", "this week's batch went out", `/the-cold-loop send` |
| read | "read my batch", "how did the batch do", `/the-cold-loop read` |
| routine | "raise the daily number", "add a second town", `/the-cold-loop routine` |

**Resuming.** A bare `/the-cold-loop` or "continue the cold loop" reads the outputs, never a
session's memory, and continues at the first thing missing: no `squad/cold-list.csv`, or no batch
for it in `squad/outreach-sent.md`, section 1; no `squad/cold-messages-<go date>.md` for that batch,
2; no campaign built for it, 3; a batch whose last name went out 9 or more days ago and no read
section, 4. A batch already named in `squad/outreach-sent.md` is approved: never re-pull it, never
re-rank it. Say in one line where you picked up.

## The files

| Path | What it holds |
|---|---|
| `squad/cold-list.csv` | the newest approved batch, 50 rows ranked by review count, in Instantly's import shape |
| `squad/cold-messages-<go date>.md` | that batch's 3 touches, the footer on each |
| `squad/outreach-sent.md` | one row per company per touch, `batch · company · touch · sent · replied`. This skill's memory, and what every pull dedups against |
| `squad/outreach-read.md` | a section per finished batch, appended, plus the winner line |
| `squad/outreach-routine.md` | the signal, each move and its date, the mailboxes, the monthly cost |
| `.claude/squad-roots.md` | the `postal address`, `cold list town` and `sending address` rows, nothing else |

Nothing is registered off disk. The Instantly account, the warmup, the import and the launch are
the founder's own hands on Instantly's own screens; this skill writes files and never reaches into
that workspace.

## Before any mode

- Four files next to `SKILL.md` must open: `references/the-list.md`, `references/the-messages.md`,
  `references/the-numbers.md`, `references/the-campaign.md`. Any missing: stop, and say the folder
  was downloaded without its `references/`.
- In `list` mode, **where the run will pull**, probe Apify with one free `search-actors` call.
  Never probe with `call-actor`: that starts a billed run. Not wired: stop and send them to the
  token paste in g5. "Export my list for Instantly." pulls nothing, so it probes nothing.
- Read `.claude/squad-roots.md`, `squad/business.md` and the mode's own files, and say in one line
  what opened. No `squad/business.md`: stop in `list` and `send`, since there is no ask to make of
  a stranger yet, and point at g4 or g5. `read`, `routine` and the export run without it, since the
  export rewrites a file off rows the founder already approved.

## 1 The list

Mode `list`. `references/the-list.md` runs this section: the drops, the rank, the file. Read it
first.

**Ask 2 things in one message,** and only what the roots file does not already hold: the town,
written to the roots file as `cold list town`, and where the founder is and where this list is. The
postal address belongs to section 2, asked in the sitting where the message that carries it is
written.

**If either country requires consent before commercial email to a business, stop.** Germany is the
named example: UWG Section 7(2) requires prior express consent for business advertising mail, and
exposure runs up to EUR 300,000 per case. Say the rule in 2 lines, say plainly that this is not
legal advice, and write no list until the founder says they have a lawful basis. A footer does not
fix a consent rule.

Then the work, alone. Run `fetch-actor-details` on `compass/crawler-google-places` every time
before calling it and build the input off the live schema: `<trade> in <town>`, **capped at 120
places**, about $0.48. **Never enable the business leads or email verification add-ons without
printing the price first:** $0.10 each on the free tier against a $5 monthly credit, so 200
verifications is $20, 4 times the whole credit. Then the drops, the rank, the top 50.

**Then the dedup, and it is load-bearing.** Drop every address already in `squad/outreach-sent.md`,
including every row marked `stop`, or the second pull re-pulls the first pull's people.

Print the 50 numbered: company, review count, email. **One answer moves the list: go**, which
stamps the batch with today's date and names it.

**The go also writes `squad/cold-list.csv`,** the same approved rows in the shape Instantly's
importer reads, 8 headers in this order:
`Email,First name,Last name,Company name,Website,Phone,Reviews,City`. **Every one of the 8 is a
field the pull returned.** No column carries a judgment about what a business needs, because a
scrape cannot see that. **The go also writes the batch into `squad/outreach-sent.md`,** one row per
company at touch 1 with `sent` empty, which is where the batch gets its name. "Export my list for
Instantly." rewrites the CSV off those rows and pulls nothing.

Later lists pull on the `cold list town` and the trade the offer document gives; a second town is
the routine's move. **A town that cannot leave 50 standing widens the town, never the trade.** Pull
the next ring of suburbs, say in one line how far you went, and keep the trade exactly as the offer
document gives it: one trade is what lets the same words land on every row.

## 2 The messages

Mode `send`, once a batch. `references/the-messages.md` carries the cage. Read it before you write.

**It asks 2 things in one message,** and only what the roots file does not already hold. The postal
address that goes under all 3, written as `postal address`: say in one line that a home address
leaves on every message and cannot be called back, so a mailbox service comes first. And which
mailbox these leave from, written as `sending address`, **and the answer is a second free address on
the workspace they already own**, never the address paying clients reply to, whether or not they
have clients yet: a client landed off this lane in week 3 writes back to the address they were
emailed from.

Day 1 runs under 80 words. **Its first line is that row's own review count and town, merged:
`{{Reviews}}` and `{{City}}`.** That is what the pull knows to be true of them and of nobody else on
the list, and it is the whole opening. One ask, answerable yes or no, and the ask is 20 minutes on a
call. Then day 4 and day 9, each carrying something the last did not say. Never a bump. No price in any of the 3: the price is the call's, and
the call is `the-close`'s.

**Twenty minutes needs a 20-minute door.** The cal.com link g6 made carries a 60-minute event type.
Say once, in one line, that the founder adds a 20-minute event type to that same link and sends that
one in the reply. A stranger who agreed to 20 minutes and lands on an hour books nothing.

**The footer goes on all 3, and this is a refusal.** The founder's valid physical postal address
and a clear opt-out, honoured within 10 business days. CAN-SPAM has no volume threshold and, in the
FTC's own words, makes no exception for business-to-business email; each message in violation runs
up to $53,088. Say that once, in one line, the first time. No address, no message, and say why in
one line. The opt-out is real: an address replying "stop" is marked in `squad/outreach-sent.md`,
and the dedup drops it from every future list.

Print the 3 whole and stop on one line: change any word that is not yours. On their word, write
them to `squad/cold-messages-<this batch's go date>.md`, the footer on each. That file is what the
campaign's 3 steps get built from.

## 3 The send

Mode `send`. Instantly is the spine and it starts on day one: the mailbox goes into warmup that
morning, the campaign is built the same sitting and left **paused**, and it launches the first
Monday the warmup health reads good. `references/the-campaign.md` carries the warmup, the import,
the settings, the costs; `references/the-messages.md` carries the batch's message file and the log.

**Day one, before a message goes out.** Print these 4 steps and let the founder do them on
Instantly's own screens: make the account; make a second free address on the workspace they already
own and connect that, never the address paying clients reply to, written to the roots file as
`sending address`; set that account's daily campaign limit to 30; turn warmup on. It runs about 2
weeks and nothing touches it again. The health score is read on Sundays and nowhere else.

**Nothing leaves by the founder's hand, at any point, and this is a refusal.** No drafts, no 10 a
morning, no mail connector. Say why in one line the first time: a message sent by hand is a message
that can be edited, and the postal address and the opt-out at the bottom are the 2 lines a founder
in a hurry deletes. The campaign carries them on every send. The 2 weeks of warmup belong to the
people who already know them, which is g4.

**The campaign is built by the founder, in Instantly, the same sitting.** You open nothing in that
workspace: no connector, no key, no call. Print the path once, in this order, then stop:

- **Campaigns > Add new**, named for this list. Then **Leads > Add Leads > CSV**, and the file goes
  in there. **Never a Lead List:** Lead Lists are gated to Hyper Growth and above, so a member on
  the trial or on Growth cannot open one, and leads sitting in a list are not in a campaign and
  send nothing.
- The importer reads the headers and maps them. **Two checks, and nothing else: Email** mapped to
  Email, and **check for duplicates** left on, which skips anyone already sitting in another
  campaign in that workspace. The free trial holds 250 contacts, so the fifth batch imported fills
  it; say that the first time the importer comes up.
- **Sequences.** Day 1's message is step 1, `{{Reviews}}` and `{{City}}` in its first line, merged
  off the CSV's own columns by name and by case. Then 2 more steps, about 2 days apart, the subject
  left empty on both so they thread onto the first. Run the spam checker on step 1 and take its
  swaps. The footer stays on every step.
- **Schedule.** The founder's own hours, Monday to Friday. Not weekends.
- **Options**, 4 of them: stop sending on reply **on**, open tracking **off** (the pixel costs
  deliverability, and it is why this lane has no open rate), provider matching **on**, daily limit
  **30**, the number already on the mailbox.
- **Then stop. Do not launch.** The campaign sits paused with 50 people in it and 3 messages
  written, waiting on a mailbox that is not ready.

**The gate is the warmup's own health reading, and nothing else:** not a batch count, not a number
of weeks. Every Sunday the founder reads it in Instantly and says what it says. The first Monday it
reads good, they press Launch, and the send is theirs to press once.

**Say this before the launch.** Instantly's own High Bounce Auto-Pause does not arm until a campaign
has sent 200 emails, so for the first weeks **the founder is the brake**, and the bounce number on
the campaign's own screen is what stops the next import.

**The stamp, once a week.** "This week's batch went out." fills `sent` on that week's rows in
`squad/outreach-sent.md` and adds touches 2 and 3, then asks one question: who replied this week. The founder reads that off
their own mailbox and names them; write `yes` in the `replied` field of each of those companies'
rows, and `stop` where the reply was stop. A reply is also the founder's to hand to `the-close`,
which writes the person's row in `squad/pipeline.md`. You never write that file. A new address they
name, postal or sending, replaces its roots row and the messages are rewritten from it.

**With the campaign running**, each week's approved batch goes in the same way, the same campaign,
Leads > Add Leads > CSV. Never export a row with no `go <date>` above it and never more than 50.
The weekly stamp takes the sent and reply totals the founder reads off the campaign's own analytics
screen, plus `stop` on every opt-out, or the dedup goes blind and the next pull emails the town
twice.

## 4 The read

Mode `read`, Sunday, before `/bip sunday`. `references/the-numbers.md` runs this section. You are the
coach here: 3 numbers, the rung that broke, one thing to do this week.

A batch whose last name went out fewer than 9 days ago is **unfinished**. Nine days from that first
email is the clock. Say the batch is not finished, print the week's raw counts labeled as counts and
not as a rate, and stop there.

Finished: **3 numbers, people contacted, replies, calls booked**, every batch side by side in one
table. All 3 counted in **people**, never in messages: 50 people at 3 touches is up to 150 messages,
and a rate on messages is a third of the truth. No opens.

**One source per number, and no second source.** People contacted and replies are the campaign's:
stop and ask the founder to open that campaign in Instantly, go to Analytics, and paste step 1's
sent count and the reply count **as they read**. Calls booked are `squad/pipeline.md`'s, counted
here and never asked for. Instantly does not know a call happened, and this skill reaches into no
workspace.

**The screen counts the campaign, not the batch,** since one campaign carries every batch ever
loaded into it. By the fourth batch imported, step 1's sent count reads 200 for a batch of 50. On
the campaign's **first** batch nothing else has sent, so those totals are that batch's and nothing
is subtracted. From the second batch on, subtract the 2 totals carried in the previous section of
`squad/outreach-read.md`, and the difference is this batch. **Never divide a campaign total by 3 to
get people:** stop sending on reply is on, so whoever answered got 1 touch or 2 and the divisor is
never really 3.

Then the ladder, stopping at the first failure, and name the rung it stopped at; its last rung,
calls but no money, is g6's, not this lane's. The rung names the change, and the change is printed
as one line: `Do this week: <the change>`, or a named hold. **One change a week, nothing else
moves.** Two changes and next Sunday cannot tell which one moved. The change briefs Monday's run,
never an edit to a batch already sending. Wrong line, and the founder says what they would change
instead; right, and they say yes.

Then write the batch's section into `squad/outreach-read.md`, **carrying the 2 campaign totals it
read**, so next Sunday subtracts from that section and nothing is handed through another file. Then
hand them the 4-week plan's own sentence to paste, **2 numbers, not 3**: `Put this in week N's
Measure: <n> people contacted, <n> replies / Improve: <the line>`. Calls booked is read here and
stays out of that line; the plan takes 2 numbers a lane.

The winner line runs on any batch, finished or not, and only on money that is new this Sunday. A
money row already in `squad/pipeline.md` before the last section in `squad/outreach-read.md` was
written is old news, and nothing is written for it. New money from a row whose source names this
list: write that batch's first line word for word under `THE WINNER` in `squad/outreach-read.md`,
say you wrote it, and carry on.

## 5 The routine

Mode `routine`. `references/the-campaign.md` carries the second mailbox, the costs, the file's
layout.

**The signal, read off `squad/pipeline.md`,** is one of 2 counts: one batch whose first line booked
2 or more calls, or one paying client from this list. A call is counted the way beat 4 counts it,
off the row's `next touch` and `what went out last` fields. Print which one opened it, with the
batch and the date. Neither there: print the count so far, calls per batch and money, and stop
here. No workaround, no override.

**Then 2 moves, in this order, one a week, never 2 in a week:** the daily number, then the second
town. Name the next one only. A founder handed both at once stops to choose.

- **Raise the daily number.** The founder makes a second free address on the workspace they already
  own and names it. Into warmup the day it is made, onto the campaign about 2 weeks later when its
  own health reads good, the same gate the first mailbox passed. They add it in Instantly, read its
  health there, and raise the daily limit by that mailbox's own number, never the first mailbox's.
  Both stay addresses paying clients do not write to. Two free addresses carry this lane; a second
  domain waits until the first mailbox is full, and `references/the-campaign.md` holds the one line
  on it.
- **Add a second town.** Update the `cold list town` row and say Monday's pull runs on it. The trade
  does not move. The messages are the winning batch's 3 touches, copied: the first line that booked
  the calls does not change. That batch goes in as its own campaign, the way beat 3's went in,
  never a Lead List.

**The reply is never automated. No auto-reply agent, at any size.** A stranger wrote back to a
person. The founder answers in their own words, with `the-close`'s draft in front of them.

**Nothing in this lane is put on a timer.** The campaign already sends; the pull, the go and the
read are the founder's 2 sentences a week, and a routine that sends, spends more or publishes never
runs unattended.

Write `squad/outreach-routine.md`: the signal and its date, each move with its date, the mailboxes
and their daily numbers, the monthly cost. Then stop.

## Never

- Never send. Not an email, not a reply, not a booking. Instantly's servers send only what the
  founder approved; every other message leaves by their hand.
- Never write a cold message with no postal address and no opt-out, at any volume, business
  recipients included.
- Never write a list for a country that requires consent first, until the founder says they have a
  lawful basis. Say it is not legal advice.
- Never stage a message for the founder to send by hand, and never write to a 51st company.
- Never put a price in a cold message, and never price past `squad/business.md`. The ask is a call.
- Never reach into the founder's Instantly workspace. The account, the warmup, the import, the
  launch and the daily number are theirs to press on Instantly's own screens, and the daily number
  rises only on the routine's first move.
- Never invent a company, a contact, an email address or a number. A row the pull reached no
  address for is dropped and counted, never guessed: a guessed address is a bounce.
- Never invent a gate. Instantly's own warmup health reading opens the campaign; 2 calls off one
  first line, or one paying client, opens the routine. No percentage this skill computed ever opens
  anything.
- Never claim the list scrapes itself, that the numbers get read overnight, or that a split test
  runs on its own. At this volume none of the 3 is true.
- Never write `squad/4-week-plan.md`, `squad/business.md` or `squad/pipeline.md`. A person's row is
  `the-close`'s to write.
