---
name: the-cold-loop
description: Use this when the founder is going after strangers. They say "build my outreach list", "pull my list", "/the-cold-loop list", "write my cold email", "send this week's batch", "this week's batch went out", "put the send on Instantly", "turn it on", "start the campaign", "/the-cold-loop send", "read my batch", "how did the batch do", "/the-cold-loop read", "raise the daily number", "add a second town", "put the read on a routine", "/the-cold-loop routine", or "continue the cold loop" (picking a stopped run back up). It builds squad/cold-list.md, 50 named companies in one trade in one town, each row carrying the one thing broken there, ranked by the squad and approved with one word; writes the 3 touches with the legal footer on every one; stages 10 new names a day for the founder's own hand; once one batch has gone out by hand, puts the same send on Instantly at the same daily number, starting on the founder's word; reads 3 numbers off finished batches, people contacted, replies, calls booked; and once a batch books 2 calls or brings a paying client, runs the routine one move at a time. It never sends anything itself, and it refuses to write a cold message carrying no postal address and no opt-out.
---

# The Cold Loop

The Winning Offer, warm, talked to people the founder already knew. This one goes at strangers.
**Your work, in one line: build and rank the 50, write the 3 touches, stage the day, stamp what
went out, read what came back, and once one batch has gone out by hand, hand the next 50 to
Instantly's servers.** The founder's part: the go on the list, any word in the message that is
not theirs, their own hand on send for the first batch, and the Sunday line: one change, or a
named hold.

**You never send.** Not an email, not a draft that leaves the laptop, not a reply. You write and
you stage; the founder presses send. Once one batch has gone out by their hand, Instantly's
servers send the batches they approve, from their own mailbox, and that approval never becomes
automatic. A reply that comes back is not yours either: it sorts in `the-close` REPLY mode, and
the founder answers it by hand, always.

**Two things outrank everything else here and neither is yours to soften.** Every cold message
carries a real postal address and a working opt-out, at any volume, with no exception for
business-to-business mail. And a country that requires consent before commercial mail stops the
run. Beat 1 holds the country gate and beat 2 the footer; both are refusals, and neither has a
workaround.

This skill runs in ANY founder's repo. `.claude/squad-roots.md` is the per-repo instance file
every member-run skill reads first (founder name, voice sample, talk to me, and the `postal
address`, `cold list town` and `sending address` rows this skill fills), and its values win over
the `squad/` paths below, which are worked examples. A row reading "(none yet)" is an unanswered
field, not an override: the worked-example path stands until this run fills it. `<date>` is
`YYYY-MM-DD`. A batch is named by the date the founder said go on its list.

## The modes, and how they are called

| Mode | The founder says | Beats |
|---|---|---|
| list | "build my outreach list", "pull my list", `/the-cold-loop list` | 0, 1. Monday: the pull, the drops, the one sentence per row, the dedup, the rank, the top 50 printed. The founder says go, or swaps a row. Once a campaign is sending, that go IS the weekly approval the load waits on |
| send | "write my cold email", "send this week's batch", "this week's batch went out", "put the send on Instantly", `/the-cold-loop send` | 0, 2, 3. Beat 2 once a batch. Beat 3 by hand every sending morning: 10 new names plus the follow-ups due; "this week's batch went out" is the weekly stamp on its own. "Put the send on Instantly." is 3.3, once one batch has fully gone out by hand. With a campaign running, "send this week's batch" is 3.5: the week's 50 load instead of printing |
| turn it on | "turn it on", "start the campaign" | 3.4 only. The word that starts a campaign holding an approved batch |
| read | "read my batch", "how did the batch do", `/the-cold-loop read` | 0, 4. Measure and Improve, Sunday, before `/bip sunday`, which carries the Improve line |
| routine | "raise the daily number", "add a second town", "put the read on a routine", `/the-cold-loop routine` | 0, 5. Gated on the signal. One move at a time |

A bare `/the-cold-loop` or "continue the cold loop" reads the outputs, picks the mode off the
resume table, and says in one line which one it entered and why.

## The run map (where you run, where you STOP)

| Beat | Mode |
|---|---|
| 0 THE SOURCES | AUTO: the install check, the roots file, the offer document, the mode's own files, and the one block said once |
| 1 THE LIST | HUMAN INPUT: the town, both countries, the postal address, once. **STOP · GATE: a consent country stops the run.** Then AUTO: the pull, the drops, the one sentence per row, the dedup, the rank, the top 50 written and printed numbered. Then **STOP · GATE: the founder says go, or swap row N** |
| 2 THE MESSAGES | HUMAN INPUT, once, only where the roots file holds neither: the postal address that goes on every message, and the mailbox they go out of. Then AUTO: the master email and the day-4 and day-9 texts, the footer on all 3. Then **STOP · GATE: the founder changes any word that is not theirs.** Then AUTO: the batch's message file |
| 3 THE SEND | AUTO, every sending morning by hand: at most 10 new names, plus the day-4 and day-9 follow-ups due, as drafts or as one file, the rows written to the log as drafted. **STOP: they read the first lines and press send.** Then AUTO, once a week: the stamp. Once one batch has fully gone out by hand, on "Put the send on Instantly.": HUMAN INPUT, the connector, then AUTO: the campaign built paused. **STOP · GATE: "Turn it on."** From then on "Send this week's batch." is AUTO: the checks, the load of the week's approved 50, and the stamp off the campaign |
| 4 THE READ | AUTO: the finished check; on an unfinished batch the week's counts. On a finished one, 3 numbers, the ladder, the one honest sentence, and the winner line the day money shows. **STOP · GATE: the Improve line, one named change or a named hold, briefing the next Run** |
| 5 THE ROUTINE | AUTO: the signal read off the pipeline; not there, the count so far, and stop. Then one move at a time, each on the founder's word: HUMAN INPUT the second mailbox and AUTO the higher daily number; AUTO the second town or trade; the weekly read routine on the laptop, registered on their yes |

The beat numbers ARE the step numbers below. Never pause an automated beat to ask a small
question (batch it into the next gate); never run through a gate because the answer seems
obvious. A section carrying a `go <date>` header is approved: never re-pull that batch, never
re-rank it. The next batch is a new section on top of the file, never an overwrite of the old one.

**Resuming.** The rule keys on the OUTPUTS, never on a session's memory. Check them in this
order and continue at the first one missing or incomplete.

| Missing or incomplete | Resume at |
|---|---|
| `squad/cold-list.md` does not exist | beat 1 |
| `squad/cold-list.md` exists and `.claude/squad-roots.md` carries no `postal address` row | beat 1, the questions only |
| its newest section carries no `go <date>` | beat 1, THE GATE ONLY: print the ranked rows, never re-pull |
| the newest section is approved and `squad/cold-messages-<its go date>.md` does not exist | beat 2 |
| the messages exist and `.claude/squad-roots.md` carries no `sending address` row | beat 2, the mailbox question only |
| the messages exist, no campaign in Instantly holds this list, and today's names are not drafted or written | beat 3, the day |
| the week's rows in `squad/outreach-sent.md` are unstamped | beat 3, the stamp only. Once a campaign is doing the sending, 3.5's stamp, off the campaign's own analytics |
| a batch is past day 9 of its last name and `squad/outreach-read.md` holds no section for it | beat 4 |
| one batch has fully gone out by hand and no campaign in Instantly holds this list | say in one line that the send can go on Instantly now, then continue down this table. By hand is the same lane |
| a campaign exists, the newest section is approved, its messages exist, and the campaign does not hold them | 3.5, the load only |
| the campaign holds an approved batch and has never been started | 3.4, the word only |
| the signal is on `squad/pipeline.md` and `squad/outreach-routine.md` does not exist | beat 5 |
| every row above is done and the newest batch is finished | beat 1, a new section for the next batch |

Never re-pull a batch the file already holds, never restamp a week the log already carries, and
never regrade a batch whose section is on disk.

## The outputs (7 files, 1 campaign, 1 routine)

1. `squad/cold-list.md`: the batches, newest section on top. Each section is 50 rows, one trade,
   one town, each row carrying the one thing broken there, under a header reading `ranked by the
   squad, top 50 of <count>, <date>` and, once the founder says go, `go <date>`. A new pull adds a
   section; the sections under it are never rewritten. Beat 1, and beat 1 only.
2. `squad/cold-messages-<go date>.md`: the 3 touch templates for that batch, the footer on each,
   written for every batch whether or not a mail connector exists. It is what beat 3 fills in each
   morning and what 3.5 loads as the campaign's steps. Beat 2, and beat 2 only.
3. `squad/cold-batch-<the day it was drafted>.md`: that morning's names filled in, ready to copy,
   written only where the founder's mailbox is not reachable through their own mail connector. The
   date here is the drafting day, not the batch's go date. Beat 3, by hand only.
4. `squad/outreach-sent.md`: this skill's own memory, one row per company per touch, written the
   morning a touch is drafted and stamped once a week, and the file every future pull dedups
   against. Beat 3 by hand, and 3.5 off the campaign's own analytics once the campaign is doing
   the sending.
5. `squad/outreach-read.md`: one section per finished batch, appended and never rewritten, and
   the winner line the day money shows. Beat 4.
6. `squad/outreach-routine.md`: the signal that opened the routine, each move made and its date,
   the mailboxes and their daily numbers, and what it costs a month. Beat 5.
7. `.claude/squad-roots.md`: given the `postal address`, `cold list town` and `sending address`
   rows. Nothing else in it touched.

Off disk, exactly 2 things get created, and both need the founder's word in that turn: **one
Instantly campaign** at 3.3, in the founder's own workspace, built paused and started only on
"Turn it on."; and **one weekly read routine** named `outreach-read` at beat 5, built only on
their yes.

Nothing else gets written. Never `squad/90-day-plan.md` (the 4-week plan's outputs are closed),
never `squad/business.md`, never `squad/clients/`, never `squad/demos/`, never `squad/pipeline.md`,
and never an email that leaves the laptop.

## Beat 0 · The sources

**The install check, before you spend any of the founder's input.** Four files inside THIS
skill's folder, next to `SKILL.md`, must open: `references/the-list.md`,
`references/the-messages.md`, `references/the-numbers.md`, `references/the-campaign.md`. Any
missing: stop and say the folder was downloaded without its `references/`, and to copy the whole
skill folder in again.

**Then Apify, in `list` mode only, and here rather than mid-pull.** Probe it with one free call,
`search-actors`. Never probe with `call-actor`: that starts a billed run, and a founder on the
free tier should not pay for a handshake. A tool that errors on auth is not wired. Not wired: stop
and send them to G5's Step 1, the token and the one paste that wires Apify into this workspace,
because that is the wiring the classroom taught and a second one on top of it is 2 Apify servers.
There is no thin mode here. The pull is the list.

**Then read, and say in one line what opened:** `.claude/squad-roots.md`, `squad/business.md`,
and the mode's own files (list: `squad/outreach-sent.md`, and `squad/cold-list.md` where it
exists. send: `squad/cold-list.md`, `squad/cold-messages-<go date>.md` where beat 2 has run,
`squad/outreach-sent.md`, which is where the day each name entered is read from, and, once
Instantly is connected, `list_campaigns` for a campaign named for this list. read:
`squad/outreach-sent.md`, `squad/cold-list.md`, `squad/pipeline.md`, and, once a campaign is
sending, `analytics_campaign_overview` and `analytics_campaign_steps` for it. routine:
`squad/outreach-read.md`, `squad/pipeline.md`, `squad/outreach-routine.md` where it exists).

**`squad/business.md` in one of 3 states:**

| The file | What it means here |
|---|---|
| last line carries `confirmed <date>` | WHO gives the trade, the deliverable gives the ask |
| exists, no `confirmed <date>` stamp | enough. Its WHO and deliverable lines do the same job |
| does not exist | stop in `list` and `send`: there is no ask to make of a stranger yet. Point at G4 (a warm call drafts one) or G5 (the market path). `read` and `routine` run without it, since they only count what already went out |

A cold message never carries a price, in any of the 3 states. The price is the call's, and the
call is `the-close`'s.

**The one block, printed once, the first time any mode runs in this repo.** Nothing in it is a
question. What runs while the laptop is shut, honestly: one clock, and it is not ours. Instantly's
servers send the batch the founder approved, inside the window they set, from their own mailbox.
The list does not scrape itself, the read does not run overnight, and no split test resolves at
this volume. The first 50 go out by your hand, at 10 new names a day, and volume comes after
something is proven.

## Beat 1 · THE LIST

Mode `list`. `references/the-list.md` runs this beat: the actor and its add-on prices, the drop
rules, the shapes a broken-thing sentence takes, what makes one sharp, and the file's own layout.
Read it first.

**Ask, in one message, only what the roots file and the offer document do not already hold:**

1. The town. Written to the roots file as `cold list town`.
2. Where the founder is, and where this list is. Both. This is the country question.
3. The founder's postal address, the one that goes on every message. Written to the roots file
   as `postal address`.

**On any list after the first, print the `cold list town` and the trade the offer document gives,
and pull on them.** A second town or trade is beat 5's move. The one exception: a town that cannot
leave 50 standing after the drops and the dedup. Say so, ask which one widens, and pull on the
answer; where the town changed, update the `cold list town` row.

**STOP · GATE, the country.** If either country requires consent before commercial email to a
business, stop. Germany is the named example: UWG Section 7(2) requires prior express consent for
business advertising mail, exposure runs up to EUR 300,000 per case, and competitors enforce it
through civil suits as well as regulators, so following the GDPR does not settle it. Say the rule
in 2 lines, say plainly that this is not legal advice, and **write no list** until the founder
says they have a lawful basis. A footer does not fix a consent rule.

**Then the pull, AUTO.** Run `fetch-actor-details` on `compass/crawler-google-places` before
calling it, every time, and build the input off the live schema rather than memory. Query
`<trade> in <town>`, **capped at 120 places**. The drops take roughly a third, and the rank keeps
the top 50 of what stands. The base pull runs about $0.004 a place, so 120 is about $0.48, inside
Apify's free monthly credit. **Never enable the business leads or email verification add-ons
without printing the price first:** they cost $0.10 each on the free tier against a $5 monthly
credit, against $0.004 to $0.005 on any paid tier, so 200 verifications on the free plan is $20,
4 times the whole credit.

**Then the drops, AUTO.** Out: chains, businesses whose site was rebuilt inside a year, and rows
with no reachable contact. One line on how many went and why, never a section. Never pad the list
to reach the number.

**Then the one sentence per row, AUTO.** What is broken there, visible from outside, in one
sentence a stranger would recognise as being about them: the site on a phone, the Maps listing,
whether the booking button goes anywhere, the review count against the site. This column is the
whole list. A row whose sentence would fit any business in the trade is not a row yet.

**Then the dedup, AUTO, and it is load-bearing.** Drop every address that already appears in
`squad/outreach-sent.md`, including every row marked `stop`. A town has a fixed number of
businesses in one trade, so a second pull re-pulls the first pull's people. This check is what
stops the loop emailing a town twice, and it is the difference between a list and a complaint.

**Then the rank, AUTO.** Order the rows by how sharp the broken-thing sentence is: a thing seen
today, in their own noun, that the offer fixes, ranks first; a sentence that could be said of any
shop in the trade ranks last. Keep the top 50. Write them as a NEW section at the top of
`squad/cold-list.md` under the header `ranked by the squad, top 50 of <count>, <today's date>`,
leave every section under it exactly as it stands, and keep the ranked rows below 50 in hand for a
swap. Print the 50 numbered, each with its sentence.

**STOP · GATE, the go.** Two answers, and nothing else moves the list: **go**, which stamps the
section `go <today's date>` and names the batch; or **swap row N**, which puts the next ranked row
in N's place, prints the list again, and waits for the go. The header never carries a member rule.

**Refuses.** To invent an email address: the cell stays blank with a note that the row is worth a
phone call. To write a list for a consent country before the gate is answered.

## Beat 2 · THE MESSAGES

Mode `send`, once a batch. `references/the-messages.md` carries the cage: the word cap, what each
touch may say, the 2 lines on openers, and the footer's exact shape. Read it before you write.

**One master email**, under 125 words. **Its first line is that row's broken thing**, in the row's
own noun and town, not a compliment and not an introduction. One ask, answerable yes or no, and
the ask is a call, never a sale. Then the day-4 and the day-9, each carrying something the last
one did not say. Never a bump: "just following up" is a message about the founder.

**The footer goes on all 3, and this is a refusal.** Every message carries the founder's valid
physical postal address and a clear opt-out, honoured within 10 business days. CAN-SPAM has no
volume threshold and, in the FTC's own words, makes no exception for business-to-business email;
each message in violation runs up to $53,088. Say that once, in one line, the first time. **No
`postal address` row in the roots file:** ask for it here, once. If the founder will not give one,
write no message and say why in one line. The opt-out is real: an address that replies "stop" gets
marked in `squad/outreach-sent.md`, and beat 1's dedup drops it from every future list.

**The mailbox these leave from, asked here.** Beat 3 refuses to draft from an address the founder
has not named as theirs, so ask for it in this beat, in the same message as the postal address, and
never mid-morning at beat 3. The rule the answer has to pass: it is **never** the address paying
clients reply to. No clients yet, and the mailbox they already use is the answer, and say plainly
that their future clients will email that same address. Clients already, and it is a second free
alias or mailbox on the workspace they own. Write it to the roots file as `sending address`; 3.3
reads that row back instead of asking twice.

**STOP · GATE.** Print the 3 messages whole and stop on one line: change any word that is not
theirs. One sentence back is enough. A cold email in a voice the founder cannot hold on a call is
worse than no email.

**On their word, write the 3 touches to `squad/cold-messages-<this batch's go date>.md`**, the
footer on each, whether or not the founder has a mail connector. This file is the batch's message
set: beat 3 fills the names into it every morning, 3.5 loads it as the campaign's day 1, day 4 and
day 9 steps, and the resume rule reads it to know beat 2 is done. A message set that lives only in
a session's memory is a message set the next session rewrites.

## Beat 3 · THE SEND

Mode `send`. By hand until one batch has fully gone out that way; on Instantly after, at the same
daily number. `references/the-messages.md` carries the daily file and the log;
`references/the-campaign.md` carries the connector, the settings and the load.

**3.1, the day by hand.** Every sending morning, Monday to Saturday. Sunday carries no send: a
touch whose day falls on a Sunday goes out Monday morning with that day's names. Stage **at most
10 new names** with touch 1, plus the names from 4 days ago with touch 2 and the names from 9 days
ago with touch 3, so the 50 enter over 5 sending days and from day 9 the groups stack. Say the
total out loud. Which names are due comes off `squad/outreach-sent.md`, never off memory and never
off the founder: the rows say who got touch 1 on which morning, and day 4 and day 9 are counted off
those dates. The messages themselves come from `squad/cold-messages-<go date>.md`.

**You refuse to stage more than 10 new names a day by hand, and the one line why:** 10 a day from
one mailbox reads as a person writing, more reads as a machine and gets the mailbox flagged, and an
unproven message at volume proves nothing.

**What to watch.** Gmail flags the mailbox (sends blocked, or mail landing in spam): make a second
free Gmail, write it to the roots file as the new `sending address`, and carry on at 10 a day.
Warmups, a separate domain and a rack of mailboxes are for someone sending 100 a day; at 10 a day
none of it comes up.

**The delivery.** Where the founder's mailbox is reachable through their own mail connector, place
the day's messages as **drafts** in their own mailbox, each follow-up threaded onto the original.
Where it is not, write them to `squad/cold-batch-<today>.md` to copy, today being the drafting day
rather than the batch's go date, since one batch writes one of these every sending morning. Either
way **you never send.** A draft is not a send. And never draft from an address the founder has not
named as theirs.

**STOP.** The founder reads the first lines before they press send. At 10 names a morning, reading
them is where the pattern is learned, and there is no version of this where you read them instead.

**The log is written by you every morning and confirmed by the founder once a week.** The moment a
morning's names are drafted, write those rows into `squad/outreach-sent.md` with today's date and
the touch number, marked `drafted`. That write is yours, and it is the only record of which names
entered on which day, which is what tomorrow's day-4 and day-9 count runs on. **Never ask for a
confirmation in chat 5 mornings a week**: the founder is asked once, at the stamp.

**3.2, the stamp, once a week.** At the end of the sending week the founder says "this week's
batch went out", in those words, and that sentence runs the stamp on its own: the week's `drafted`
rows become stamped ones, and every address that replied "stop" is marked `stop`.
`squad/outreach-sent.md` is this skill's own memory, and the stamp is the whole job here: the dedup
and the read both run off it. A reply that lands is not this skill's to file. The founder hands it
to `the-close` the day it arrives, and that skill writes the person's row in `squad/pipeline.md`,
name, source, bucket, date, next touch, what went out last, money. You never write that file.

**3.3, on "Put the send on Instantly.", once one batch has fully gone out by hand.** The gate is
one finished batch, read off `squad/outreach-sent.md`: every row of one batch carries all 3
touches stamped, and the last name is past day 9. Not there yet: print how many of the 50 have all
3 touches out, and stop. No Instantly is fine: 10 a day by hand is the same lane, and 3.1 keeps
running for as long as the founder wants it to.

Read the `sending address` back off the roots file and confirm it in one line; HUMAN INPUT only
where that row is missing. Then HUMAN INPUT: Instantly's MCP is a remote hosted server, added as a
custom connector at `https://mcp.instantly.ai/mcp`; signing in is the current way, and pasting the
API key into the URL (`https://mcp.instantly.ai/mcp/YOUR_API_KEY`) still works but Instantly's own
notes call it the old form. Take whichever one their connector screen offers, and never guess a
path you have not seen answer. Then call `workspace_billing_plan_details` and **report the tier the
workspace actually has**; never assert one, since Instantly's help page and its pricing page
disagree on which tier carries the API. Print the monthly cost off `references/the-campaign.md`
before the founder subscribes to anything.

Then AUTO: **the campaign, built paused**, named for this list, holding the 3 messages of the batch
about to load (its `squad/cold-messages-<go date>.md`; no file means beat 2 runs first) as the day
1, day 4 and day 9 steps with the footer on every one. `stop_on_reply` true, `text_only` true,
`open_tracking` false, `daily_limit` in messages, the unit Instantly counts, set to the by-hand
day's total once all 3 groups were running and never above it, `email_gap` spread across the
window. Say out loud that Instantly's own High Bounce Auto-Pause does not arm until a campaign has
sent 200 emails, so for the first weeks **the founder is the brake**. Do not turn on A/Z
auto-optimize, and say why in one line: it states no minimum sample, so at 25 people an arm it can
switch off the better message. Then the load, by 3.5's checks, and then 3.4.

**3.4, STOP · GATE: the word that starts it.** The campaign is paused and it stays paused until
the founder says so. Print what is about to go out, the daily limit, the sending window and the
address it goes from, then stop and wait. On **"Turn it on."** call `activate_campaign` and say it
is live, with the date and the campaign name. On anything else, leave it paused and say it is still
paused. Nothing else in this skill activates a campaign.

**3.5, the weekly load, on "Send this week's batch." with a campaign running.** The newest section
of `squad/cold-list.md` carries `go <date>` and its message file exists; either missing sends you
to beat 1 or beat 2 rather than loading. Call `accounts_test_vitals` on the sending address first
and refuse to load when its domain comes back in the failing list; say which record failed (MX,
SPF, DKIM or DMARC). Once the campaign has sent, read its bounces with
`analytics_campaign_overview` and refuse to load when bounce is over 2%, saying the number you read;
on the first load say there is no bounce number yet and let the DNS check stand as the gate. When
the campaign's 3 steps are not that batch's message file, set them from it first (`update_campaign`),
the footer on every one. Then load that batch and nothing else: the approved rows as leads
(`add_leads_to_campaign_or_list_bulk`), each carrying its own broken-thing first line. Never load a
row with no `go <date>` above it, never load a row already in `squad/outreach-sent.md`, never load
more than 50, and never raise `daily_limit` here, since that is beat 5's move. Report 3 counts:
loaded, dropped as duplicates, dropped for a missing address. From the second week on the campaign
is already running, the batch loads into it, and there is nothing to press.

**The stamp, once the campaign does the sending.** Nobody typed the week out by hand, so nothing
fills the log unless you do it. At the end of each sending week read `analytics_campaign_steps`
for the campaign, stamp that batch's rows in `squad/outreach-sent.md` with the dates and touch
numbers it reports, and mark `stop` on every address that opted out. Skip this and beat 1's dedup
goes blind, beat 4 reads its numbers off a file nobody writes, and the next pull emails the town a
second time.

**3.6, the deck for the best name.** When a company on the list is worth it, hand it to `/mep` on
its cold path, which is the founder saying "build the deck for <company> off my cold list": the
buyer's own words do not exist yet, so that skill builds off the row's broken-thing sentence plus
what can be seen from outside, each line labeled an observation and never a quote. `/mep` writes
the deck; this skill writes nothing there. When the deck exists, the case-study message to that
company's competitors goes **on the same list, as the next batch's first line**, never as a second
campaign beside this one.

**Refuses.** To stage more than 10 new names a day by hand. To write to a 51st company. To send
anything. To draft from an address the founder has not named. To write any message with no footer.
To start a campaign on any word but "Turn it on."

## Beat 4 · THE READ

Mode `read`, Sunday: Measure, then Improve. `references/the-numbers.md` runs this beat: the 3
numbers and where each comes from, the ladder, the one honest sentence, and the file's layout.
Read it before you print a number.

**Run this read BEFORE `/bip sunday`**, so the Improve line is decided before the founder writes
the week, and the Sunday post carries it.

**The completeness check, first.** Measure reads what has finished, which is usually last week's
Run. A batch whose last name went out fewer than 9 days ago is **unfinished**. Say so, then print
the week's raw counts off `squad/outreach-sent.md`, labeled as counts and not as a rate: people
contacted so far, replies so far. Then stop: the ladder and any comparison wait for the batch to
finish. Hand the founder the hold for the plan's Improve cell, `holding until 50 people are past
day 9, week N`. Week 1's Sunday reads the counts and little else, and that is a complete read for
week 1.

**One thing runs on any batch, finished or not: the winner line.** The day `squad/pipeline.md`
shows money from a row whose source names this list, write that batch's **first line, word for
word**, under `THE WINNER` in `squad/outreach-read.md`, say you wrote it, and carry on. Written
when it happens, never recalled later. Nothing for the founder to do.

**Three numbers per finished batch: people contacted, replies, calls booked**, every batch side by
side in one table so the change between them is visible. All 3 are counted in **people**, never in
messages: 50 people at 3 touches is up to 150 messages, and a rate on messages is a third of the
truth. People contacted is the batch's rows in `squad/outreach-sent.md` by hand, or step 1's sent
count in `analytics_campaign_steps` once the campaign sends; never a campaign total divided by 3,
since `stop_on_reply` means a person who answered got 1 or 2 touches. Replies is the log's Replied
column, or the campaign's reply count. Calls booked is the rows in `squad/pipeline.md` whose source
names this list and whose next touch or outcome is a call; where the pipeline holds none and the
founder says one booked, count it and print it as their word. When the campaign and the log
disagree, print both, name which is which, and use the campaign's number. No opens: an open needs a
pixel, `text_only` exists to avoid one, and Apple and Gmail inflate the number anyway.

**The ladder, stopping at the first failure.** Sent under the plan, and the block did not happen:
fix the block, nothing else. Sent fine and replies near zero: the people first, then the first
line, in that order. Replies land, no calls: the ask is too big; ask for 20 minutes and nothing
else. Calls but no money: that is G6, not this lane.

**The one honest sentence, under any batch or comparison below 300 people contacted:** under 300
people, 3 against 5 is a coin; do not rewrite the email on it. Two batches under 300 a side get
both rows printed and no winner named. What moves a number far enough to see at this volume is who
is on the list, what the first line says about them, and whether the ask is a call.

**STOP · GATE, Improve.** One line, and it takes exactly 2 forms: one named change, proposed with
its reason, or `holding until <number>, week N`. Most weeks read holding, and that is the plan
working. The change is the brief for Monday's Run, never an edit to a batch already sending;
marking a `stop` and answering people are housekeeping, not the change. The founder's yes or their
own line instead. Then write the batch's section into `squad/outreach-read.md`.

**Last, hand the founder the line to paste**, in the 4-week plan's own words, so they carry a
finished sentence rather than compose one:

> Put this in week N's Measure: `<n> people contacted, <n> replies, <n> calls booked` / Improve: `<the line>`

On an unfinished batch the Measure half reads `held until batch <date> is past day 9`, which is
the form that plan accepts, and the Improve half is the hold. It goes in 2 places by their hand:
the Improve cell of that week's row in the 4-week plan, and the Sunday post, since `/bip sunday`
adds nothing up and takes the line, not a total. Then stop. You never write `squad/90-day-plan.md`.

## Beat 5 · THE ROUTINE

Mode `routine`. `references/the-campaign.md` carries the second mailbox, the ramp table, the
cost table and the routine file's layout. Read it before you touch anything.

**5.0, the signal, and it is the point of this mode.** Read `squad/pipeline.md`. The routine opens
on one of 2 things: **one batch whose first line booked 2 or more calls** (rows whose source names
that batch and whose next touch or outcome is a call), or **one paying client from this list** (a
row from a cold list with money in its last field). Print which one opened it, with the batch and
the date. Neither there: print the count so far, calls per batch and money, and stop at this beat.
No workaround, no override, no "if you want to anyway." A call the founder names that the pipeline
does not hold is `the-close`'s row to write first.

**5.1, three moves, one at a time, each on the founder's word, never 2 in a week.** They name the
move; you make it and write it to the routine file.

**Move 1: the daily number rises on a second mailbox.** HUMAN INPUT: the second mailbox. An alias
on the workspace they already own comes first, since it is free and needs no wait. A second domain
only when the first mailbox is full, and then the 14-day wait before it sends and the ramp in
`references/the-campaign.md`'s one table. Add the mailbox to the campaign, run `accounts_test_vitals`
on it, and raise `daily_limit` by that mailbox's own number, never the first mailbox's. Both stay
addresses paying clients do not reply to.

**Move 2: a second town or trade, on the same first line.** Update the `cold list town` row, or
the trade, and say that Monday's pull runs on it. The first line that booked the calls does not
change: the new batch's messages are the winning batch's 3 touches, copied. Beat 1 ranks the new
town the same way.

**Move 3: the weekly read on a routine, on the laptop.** Name it `outreach-read`, weekly, Sunday
morning, in the founder's own company folder, and its whole instruction is the sentence they have
been typing: "Read my batch." Where the app they are in can create a local routine, create it and
say what you made. Where it cannot, print the path and stop there: Claude Desktop, Code tab,
Routines, New routine, **Local**, weekly. Local, never Cloud, since a cloud routine runs on a copy
of a repository and cannot see `squad/` at all. Either way, tell them to press **Run now** once and
choose always-allow on every read it asks about, because a routine that hits a permission it does
not have stalls until somebody approves it, and nobody is watching at 9am on a Sunday. It only
reads. On a no, register nothing, and never offer again.

**The week, once the routine is on.** Monday the squad pulls and ranks, the founder says go, the
campaign keeps sending, Sunday the read.

**Never built, and say why in one line each when asked.** An Apify schedule: the Apify MCP
publishes no schedule tool, so this skill cannot make one, and a weekly pull takes minutes by hand
in the same session where the list is approved. A scheduled task for the send: it fires when the
lid opens, which is the moment the founder could type the command, and the standing rule forbids
scheduling anything that sends. A cloud routine over `squad/`: `squad/clients/*/transcript.md`
holds real people's recorded words, and pushing that to a hosted repository to save one typed
command is a trade nobody makes once it is stated that way.

**Never automated, and it belongs in this mode's last line.** The reply. No auto-reply agent,
ever. Taste is the first reason; since 2026-08-02 the EU's AI Act also asks that a person be told
when a machine wrote to them, and a draft the founder sends by hand keeps this lane clear of the
question.

Write `squad/outreach-routine.md`: the signal and its date, each move made with its date, the
mailboxes and their daily numbers, the routine's name, and the monthly cost. Then stop.

## Rules

- Every message to the founder is scannable: a short header, then a table or short bullets. They
  are deciding, not studying.
- Never send. Not an email, not a reply, not a booking. Instantly's servers send only what the
  founder approved; every other message leaves by their hand.
- Never stage more than 10 new names a day by hand.
- Never write a cold message with no postal address and no opt-out, at any volume, business
  recipients included.
- Never write a list for a country that requires consent first, until the founder says they have a
  lawful basis. Say it is not legal advice.
- Never price past `squad/business.md`, and never put a price in a cold message at all. The ask
  is a call.
- Never invent a company, a contact, an email address, a number or a need. A blank cell is an
  answer; a guessed address is a bounce.
- Never save an observation as a quote. A stranger has said nothing yet, so what can be seen from
  outside is labeled an observation, and only the words a person actually wrote are quoted.
- Never name a winner between 2 batches under 300 people a side. Print both and the one sentence.
- Never make a gate a rate. One finished batch by hand opens Instantly; 2 calls off one first line,
  or one paying client, opens the routine. All counts.
- Never claim the list scrapes itself, that the numbers get read overnight, or that a split test
  runs on its own. At this volume none of the 3 is true.
- Never remove the weekly go, never load a list the founder has not approved, and never raise
  `daily_limit` outside beat 5's move 1.
- Never turn on Instantly's A/Z auto-optimize at this volume.
- Never write `squad/90-day-plan.md`, `squad/business.md` or `squad/pipeline.md`. A person's row
  is `the-close`'s to write.
