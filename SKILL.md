---
name: the-cold-loop
description: Use this when the founder is going after strangers. They say "build my outreach list", "pull my list", "/the-cold-loop list", "write my cold email", "send this week's batch", "this week's batch went out", "/the-cold-loop send", "read my batch", "how did the batch do", "/the-cold-loop read", "put the send on Instantly", "/the-cold-loop routine", "turn it on", or "continue the cold loop" (picking a stopped run back up). It builds squad/cold-list.md, 50 named companies in one trade in one town, each row carrying the one thing broken there; writes the 3 touches with the legal footer on every one; stamps what went out; reads 2 numbers off finished batches with the honest interval in words; and once the gate opens loads the approved 50 into one Instantly campaign that starts, on the founder's word, sending on Instantly's servers. It never sends anything itself, and it refuses to write a cold message carrying no postal address and no opt-out.
---

# The Cold Loop

The Winning Offer, warm, talked to people the founder already knew. This one goes at strangers.
**Your work, in one line: build the 50, write the 3 touches, stamp what went out, read what came
back, and once the gate opens hand the approved 50 to Instantly's servers.** The founder's part: the cut,
any word in the message that is not theirs, their own hand on send, and one change a week.

**You never send.** Not an email, not a draft that leaves the laptop, not a reply. You write and
you stage; the founder presses send. After Gate A opens, Instantly's servers send the batch the
founder personally approved, from the founder's own mailbox, and that approval never becomes
automatic. A reply that comes back is not yours either: it sorts in `the-close` REPLY mode, and
the founder answers it by hand, always.

**Two things outrank everything else here and neither is yours to soften.** Every cold message
carries a real postal address and a working opt-out, at any volume, with no exception for
business-to-business mail. And a country that requires consent before commercial mail stops the
run. Both are in beat 0's block, both are refusals, and neither has a workaround.

This skill runs in ANY founder's repo. `.claude/squad-roots.md` is the per-repo instance file
every member-run skill reads first (founder name, voice sample, talk to me, and the `postal
address`, `cold list town` and `sending address` rows this skill fills), and its values win over
the `squad/` paths below, which are worked examples. A row reading "(none yet)" is an unanswered
field, not an override: the worked-example path stands until this run fills it. `<date>` is
`YYYY-MM-DD`. A batch is named by the date its list was cut.

## The modes, and how they are called

| Mode | The founder says | Beats |
|---|---|---|
| list | "build my outreach list", "pull my list", `/the-cold-loop list` | 0, 1. Weekly, before anything goes out. Once `squad/outreach-routine.md` exists, beat 1's cut IS the weekly approval the load waits on, and you say the load is next |
| send | "write my cold email", "send this week's batch", "this week's batch went out", `/the-cold-loop send` | 0, 2, 3. Beat 2 once a batch, beat 3 every morning of the week, and "this week's batch went out" is beat 3's weekly stamp on its own. Once `squad/outreach-routine.md` exists, 5.4 to 5.6 replace beat 3: the batch loads instead of printing cohorts to copy |
| read | "read my batch", "how did the batch do", `/the-cold-loop read` | 0, 4. Sunday, before `/bip sunday` |
| routine | "put the send on Instantly", `/the-cold-loop routine` | 0, 5. Once Gate A is open, the setup and the first load |
| turn it on | "turn it on", "start the campaign" | 5.6 only. The word that starts a campaign holding an approved batch |

A bare `/the-cold-loop` or "continue the cold loop" reads the outputs, picks the mode off the
resume table, and says in one line which one it entered and why.

## The run map (where you run, where you STOP)

| Beat | Mode |
|---|---|
| 0 THE SOURCES | AUTO: the install check, the roots file, the offer document, the mode's own files, and the 2 blocks said once |
| 1 THE LIST | HUMAN INPUT: the town, both countries, the postal address, once. **STOP · GATE: a consent country stops the run.** Then AUTO: the pull, the drops, the broken-thing sentence, the dedup. Then **STOP · GATE: the founder cuts to 50 and says why in their own words** |
| 2 THE MESSAGES | HUMAN INPUT, once, only where the roots file holds neither: the postal address that goes on every message, and the mailbox they go out of. Then AUTO: the master email and the day-4 and day-9 texts, the footer on all 3. Then **STOP · GATE: the founder changes any word that is not theirs** |
| 3 THE DAY | AUTO: all 3 cohorts, as drafts in the founder's mailbox or as one file. **STOP: they read the first lines and press send.** Then AUTO, once a week: the stamp |
| 4 THE READ | AUTO: the finished check, 2 numbers off the log and off the campaign's own analytics once one exists, the ladder, the interval in words, both scoreboards. **STOP · GATE: exactly one change for next week.** Then the weekly task, offered once behind the risk gate, and registered in that turn on a yes |
| 5 THE ROUTINE | AUTO: the gates read out of the files. Then the sending address read back off the roots file, HUMAN INPUT only where beat 2 never asked, then Instantly connected. AUTO: the campaign built paused, and from the load on, the week's stamp read off the campaign. **STOP · GATE, every week, forever: the founder approves the list before it loads.** Then AUTO: the load. Then, the first time only, **STOP · GATE: the founder says the word and the campaign starts.** Beat 5.7 runs behind Gate B only |

The beat numbers ARE the step numbers below. Never pause an automated beat to ask a small
question (batch it into the next gate); never run through a gate because the answer seems
obvious. A section carrying a `cut <date>` header is cut: never re-pull that batch, never re-ask
its rule. The next batch is a new section on top of the file, never an overwrite of the old one.

**Resuming.** The rule keys on the OUTPUTS, never on a session's memory. Check them in this
order and continue at the first one missing or incomplete.

| Missing or incomplete | Resume at |
|---|---|
| `.claude/squad-roots.md` carries no `postal address` row | beat 1, the questions only |
| `squad/cold-list.md` does not exist | beat 1 |
| its newest section carries no `cut <date>` | beat 1, THE GATE ONLY: print the rows, never re-pull |
| the newest section is cut and no message set exists for it | beat 2 |
| the messages exist and `.claude/squad-roots.md` carries no `sending address` row | beat 2, the mailbox question only |
| the messages exist and today's cohorts are not drafted or written | beat 3 |
| the week's rows in `squad/outreach-sent.md` are unstamped | beat 3, the stamp only. Once a campaign is doing the sending, beat 5's stamp, off the campaign's own analytics |
| a batch is past day 9 of its last name and `squad/outreach-read.md` holds no section for it | beat 4 |
| Gate A is open and `squad/outreach-routine.md` does not exist | beat 5 |
| the routine exists and this week's list is not approved | beat 1, the cut, which IS 5.4's approval |
| this week's list is approved, its messages are written, and the campaign does not hold them | beat 5.5, the load only |
| the campaign holds an approved batch and has never been started | beat 5.6, the word only |
| every row above is done and the newest batch is finished | beat 1, a new section for the next batch |

Never re-pull a batch the file already holds, never restamp a week the log already carries, and
never regrade a batch whose section is on disk.

## The outputs (5 files, 1 campaign, 1 task)

1. `squad/cold-list.md`: the batches, newest section on top. Each section is 50 rows, one trade,
   one town, each row carrying the one thing broken there, under a header holding the founder's own
   cut rule and `cut <date>`. A new pull adds a section; the sections under it are never rewritten.
   Beat 1, and beat 1 only.
2. `squad/cold-batch-<date>.md`: the day's 3 cohorts, ready to copy, written only where the
   founder's mailbox is not reachable through their own mail connector. Beat 3.
3. `squad/outreach-sent.md`: the founder's own log, one row per company per touch, stamped once
   a week, and the file every future pull dedups against. Beat 3 by hand, and beat 5 off the
   campaign's own analytics once the campaign is doing the sending.
4. `squad/outreach-read.md`: the scoreboards at the top, rewritten each run, and one section per
   finished batch below them, appended and never rewritten. Beat 4.
5. `squad/outreach-routine.md`: what was built in Instantly, the sending address, the daily
   limit, the gate state on the day it was built, and what it costs a month. Beat 5.
6. `.claude/squad-roots.md`: given the `postal address`, `cold list town` and `sending address`
   rows. Nothing else in it touched.

Off disk, exactly 2 things get created, and both need the founder's word in that turn: **one
Instantly campaign** at beat 5, in the founder's own workspace, holding the batch they approved and
paused until they say the word that starts it, and **one weekly read task** named `outreach-read` at
beat 4, offered once behind the risk gate and built only on their yes.

Nothing else gets written. Never `squad/90-day-plan.md` (the 90-Day Plan's outputs are closed),
never `squad/business.md`, never `squad/clients/`, never `squad/demos/`, never the Outreach
Sheet, and never an email that leaves the laptop.

## Beat 0 · The sources

**The install check, before you spend any of the founder's input.** Four files inside THIS
skill's folder, next to `SKILL.md`, must open: `references/the-list.md`,
`references/the-messages.md`, `references/the-numbers.md`, `references/the-campaign.md`. Any
missing: stop and say the folder was downloaded without its `references/`, and to copy the whole
skill folder in again. An interval computed from memory is wrong quietly, which is the expensive
way to be wrong.

**Then Apify, in `list` mode only, and here rather than mid-pull.** Probe it with one
free call, `search-actors`. Never probe with `call-actor`: that starts a billed run, and a founder
on the free tier should not pay for a handshake. A tool that errors on auth is not wired. Not
wired: stop and send them to G5's Step 1, the token and the one paste that wires Apify into this
workspace, because that is the wiring the classroom taught and a second one on top of it is 2 Apify
servers. There is no thin mode here. The pull is the list.

**Then read, and say in one line what opened:** `.claude/squad-roots.md`, `squad/business.md`,
and the mode's own files (list: `squad/outreach-sent.md`, and `squad/cold-list.md` where it exists,
for the newest section's cut rule. send: `squad/cold-list.md`,
`squad/sales.md` if it exists. read: `squad/outreach-sent.md`, `squad/cold-list.md`,
`squad/pipeline.md`, and, once `squad/outreach-routine.md` names a campaign,
`analytics_campaign_overview` and `analytics_campaign_steps` for it. routine:
`squad/outreach-read.md`, `squad/pipeline.md`).

**`squad/business.md` in one of 3 states:**

| The file | What it means here |
|---|---|
| last line carries `confirmed <date>` | WHO gives the trade, the deliverable gives the ask |
| exists, no `confirmed <date>` stamp | enough. Its WHO and deliverable lines do the same job |
| does not exist | stop in `list` and `send`: there is no ask to make of a stranger yet. Point at G4 (a warm call drafts one) or G5 (the market path). `read` and `routine` run without it, since they only count what already went out |

A cold message never carries a price, in any of the 3 states. The price is the call's, and the
call is `the-close`'s.

**The 2 blocks, printed once, the first time any mode runs in this repo.** Nothing in either is
a question.

**What runs while the laptop is shut, honestly.** One clock, and it is not ours. Instantly's
servers send the batch the founder approved, inside the window they set, from their own mailbox.
That is the whole of it. The list does not scrape itself, the read does not run overnight, and
no split test resolves at this volume. Everything else in this lane happens while the founder is
sitting at their laptop, and the first 3 weeks are entirely by hand.

**The real load, said before week 2 says it for you.** 50 people a week, 10 new names a day. Each
name gets 3 touches, on day 1, day 4 and day 9, so from day 9 onward a weekday carries about **30
messages** to 3 different cohorts. The block is about 30 minutes. And the unit never moves: a
reply rate's denominator is **people contacted**, never messages sent, and the two are off by 3x.

## Beat 1 · THE LIST

Mode `list`. `references/the-list.md` runs this beat: the actor and its add-on prices, the drop
rules, the shapes a broken-thing sentence takes, and the file's own layout. Read it first.

**Ask, in one message, only what the roots file and the offer document do not already hold:**

1. The town. Written to the roots file as `cold list town`.
2. Where the founder is, and where this list is. Both. This is the jurisdiction question.
3. The founder's postal address, the one that goes on every message. Written to the roots file
   as `postal address`.

**STOP · GATE, jurisdiction.** If either country runs a prior-consent regime for commercial
email to a business, stop. Germany is the named example: UWG Section 7(2) requires prior express
consent for business advertising mail, exposure runs up to EUR 300,000 per case, and competitors
enforce it through civil litigation as well as regulators, so following the GDPR does not settle
it. Say the rule in 2 lines, say plainly that this is not legal advice, and **write no list**
until the founder says they have a lawful basis. A footer does not fix a consent regime.

**Then the pull, AUTO.** Run `fetch-actor-details` on `compass/crawler-google-places` before
calling it, every time, and build the input off the live schema rather than memory. Query
`<trade> in <town>`, **capped at 120 places**. The drops take roughly a third and the founder still
has to cut, so 120 in is what leaves 50 standing on the other side of a real cut. The base pull
runs about $0.004 a place, so 120 is about $0.48, inside Apify's free monthly credit. **Never
enable the business leads or email verification add-ons without printing the price first:** they
cost $0.10 each on the free tier against a $5 monthly credit, against $0.004 to $0.005 on any paid
tier, so 200 verifications on the free plan is $20, 4 times the whole credit.

**When `squad/cold-list.md` already holds a section, inherit the rule.** Read the newest section's
cut rule, apply it here to the drops and to the broken-thing pass, and say in one line which rule
you inherited. The founder wrote it once. Making them write it again is asking for the same work
twice.

**Then the drops, AUTO.** Out: chains, businesses whose site was rebuilt inside a year, and rows
with no reachable contact. One line on how many went and why, never a section. A town that cannot
leave 50 standing after the drops is a town that needs the trade widened: say that, and never pad
the list to reach the number.

**Then the one sentence per row, AUTO.** What is broken there, visible from outside, in one
sentence a stranger would recognise as being about them: the site on a phone, the Maps listing,
whether the booking button goes anywhere, the review count against the site. This column is the
whole list. A row whose sentence would fit any business in the trade is not a row yet.

**Then the dedup, AUTO, and it is load-bearing.** Drop every address that already appears in
`squad/outreach-sent.md`, including every row marked `stop`. A town has a fixed number of
businesses in one trade, so a second pull re-pulls the first pull's people. This check is what
stops the loop emailing a town twice, and it is the difference between a list and a complaint.

**STOP · GATE, the cut.** Print the broken-thing column, numbered, top to bottom, and stop. The
founder cuts to 50. **Their reason, in their own words, goes into this batch's header**, and the
next pull reads it back at the line above. On their cut, write this batch as a NEW section at the
top of `squad/cold-list.md`, headed `cut <today's date>`, and leave every section under it exactly
as it stands.

**On any list after the first, one line:** the trade or the town may widen now. One trade and one
town binds the first list only, a town holds a fixed number of businesses, and Gate B needs 2
finished batches.

**Refuses.** To invent an email address: the cell stays blank with a note that the row is worth a
phone call. To write a list for a consent country before the gate is answered.

## Beat 2 · THE MESSAGES

Mode `send`, once a batch. `references/the-messages.md` carries the cage: the word cap, what each
touch may say, the 2 lines on openers, and the footer's exact shape. Read it before you write.

**One master email**, under 125 words. **Its first line is that row's broken thing**, in the row's
own noun and town, not a compliment and not an introduction. One ask, answerable yes or no. Then
the day-4 and the day-9, each carrying something the last one did not say. Never a bump: "just
following up" is a message about the founder.

**The footer goes on all 3, and this is a refusal, not a preference.** Every message carries the
founder's valid physical postal address and a clear opt-out, honoured within 10 business days.
CAN-SPAM has no volume threshold and, in the FTC's own words, makes no exception for
business-to-business email; each message in violation runs up to $53,088. Say that once, in one
line, the first time. **No `postal address` row in the roots file:** ask for it here, once. If the
founder will not give one, write no message and say why in one line. The opt-out is real, not
decorative: an address that replies "stop" gets marked in `squad/outreach-sent.md`, and beat 1's
dedup drops it from every future list.

**The mailbox these leave from, asked here rather than in week 4.** Beat 3 refuses to draft from an
address the founder has not named as theirs, so ask for it in this beat, in the same message as the
postal address, and never mid-morning at beat 3. The rule the answer has to pass: it is **not** the
address paying clients reply to. No clients yet, and the mailbox they already use is the answer, and
say plainly that their future clients will email that same address. Clients already, and it is a
second free alias or mailbox on the workspace they own. Write it to the roots file as `sending
address`; beat 5.1 reads that row back instead of asking twice.

**STOP · GATE.** Print the 3 messages whole and stop on one line: change any word that is not
theirs. One sentence back is enough. A cold email in a voice the founder cannot hold on a call is
worse than no email.

## Beat 3 · THE DAY

Mode `send`, every morning of the sending week.

**Print all 3 cohorts, not just the new 10:** today's 10 new names with touch 1, the cohort from 4
days ago with touch 2, the cohort from 9 days ago with touch 3. **Say the total out loud**, because
from day 9 it is about 30.

**The delivery.** Where the founder's mailbox is reachable through their own mail connector, place
the day's messages as **drafts** in their own mailbox, each follow-up threaded onto the original.
Where it is not, write them to `squad/cold-batch-<date>.md` to copy. Either way **you never send.**
A draft is not a send. And never draft from an address the founder has not named as theirs.

**STOP.** The founder reads the first lines before they press send. At 50 people a week, reading
them is where the pattern is learned, and there is no version of this where you read them instead.

**The log, once a week, not once a day.** At the end of the sending week the founder says the week
went out, in those words, and you stamp that week's rows in `squad/outreach-sent.md` with their
dates and touch numbers. That sentence runs the stamp on its own, with nothing else in this beat
attached to it. A confirmation typed into chat 5 mornings a week is a ritual, not a record.

**The demo, when a company on the list is worth it.** Outreach needs proof; without proof it is not
outreach. Hand the company to `/mep` on its cold path, which is the founder saying "build the deck
for <company> off my cold list": the buyer's own words do not exist yet, so that skill builds off the
row's broken-thing sentence plus what can be seen from outside, each line labeled an observation and
never a quote. `/mep` writes the deck; this skill writes nothing there.
When the deck exists, draft the case-study message to that company's competitors **on the same
list, as the next batch's first line**, never as a second campaign running beside this one.

**Refuses.** To write a 51st email. To send anything. To draft from an address the founder has not
named. To write any message with no footer.

## Beat 4 · THE READ

Mode `read`, Sunday. `references/the-numbers.md` runs this beat: the interval, how to say it in
words, the ladder, and the file's layout. Read it before you print a number.

**Run this read BEFORE `/bip sunday`**, so the week's one change is decided before the founder
writes the week.

**The completeness check, first.** A batch whose last name went out fewer than 9 days ago is
**unfinished**. Say so and stop: "Your number does not exist yet. Keep sending." Nothing below this
line runs on an unfinished batch.

**One thing is exempt from that stop, and only one.** The winning-cut write further down keys on
`squad/pipeline.md`, never on a finished batch. Money can clear in week 2, so when a cold row shows
money, write the cut rule and the first line even on an unfinished batch, say you wrote it, and
then stop where the check said to stop. Gate B's condition 4 is only true if it is written on the
day it happens.

**Two numbers per finished batch: `sent` and `replied`**, every batch side by side in one table so
replacement is visible. `sent` counts **people contacted**, and the table says so in its header. No
opens (an open needs a pixel, `text_only` exists to avoid one, and Apple and Gmail inflate the
number anyway), no bounce row, no batch age.

**Where those 2 numbers come from, in both worlds.** `squad/outreach-sent.md` is the source of
truth either way. Before Gate A the founder's own hand sent the batch and beat 3's stamp fills the
log. After the campaign is live the sending happened on Instantly's servers, so read that batch's
window with `analytics_campaign_overview` and its per-touch counts with `analytics_campaign_steps`,
and take `sent` and `replied` from there. **Convert to people before you print anything**: Instantly
counts messages, this read counts people contacted, and the 2 are off by 3x. When the campaign and
the log disagree, print both, name which is which, and use the campaign's number.

**The ladder, stopping at the first failure.** Sent under the plan, and the block did not happen:
fix the block, nothing else. Sent fine and replies near zero: the people first, then the first
line, in that order. Replies but nothing books: the ask is too big. Calls but no money: that is
G6, not this lane.

**The honesty line, whenever a batch is under 300 people contacted.** Print the Wilson 95%
interval **in words**: "3 replies out of 50 is anywhere from 1 in 50 to 1 in 6. Do not rewrite the
email on this." Compute it with the formula in `references/the-numbers.md`. Never the normal
approximation, which returns impossible negative rates at small counts and has already been
shipped once.

**Comparing 2 batches.** Name a difference only when the 2 Wilson intervals do not overlap. When
they overlap, print both in words, say the 2 are not distinguishable yet, and say how many people
each side would need. **Every printed comparison carries the same sentence: this is a
before-and-after, not an experiment.** Different week, different list, no control.

**The record that makes Gate B condition 4 real.** The moment `squad/pipeline.md` shows money from
a row that came off a cold list, write that batch's **cut rule and first line, verbatim**, into
`squad/outreach-read.md`. Written when it happens, never recalled later.

**Both scoreboards, every run.** Print Gate A and Gate B as they stand, each condition with a tick
or a cross, the count so far, and the file it was read from. Then one line naming which conditions
the founder self-reports. A gate that pretends to be tamper-proof and is not is worse than one that
says where it trusts you.

**Gate A · the send gate.** Both true, and it typically clears in about 3 weeks.

| # | The condition | Read from |
|---|---|---|
| 1 | One finished batch: 50 names, all 3 touches out, past day 9 of the last name | `squad/outreach-sent.md` |
| 2 | The founder approved that list by hand, and keeps approving every week | the `cut <date>` header in `squad/cold-list.md`, one per batch |

What Gate A opens: beat 5, which is the same 50 a week from the same mailbox at the same daily
number, sending on Instantly's servers instead of by copy and paste. It multiplies nothing.

**Gate B · the scale gate.** All 4 true at once, and the founder can say each one out loud.

| # | The condition | Read from |
|---|---|---|
| 1 | One client has paid, from this cold list. Money received, not a reply and not a proposal | `squad/pipeline.md` · self-reported |
| 2 | Two calls booked from cold, in 2 different batches | `squad/pipeline.md` · self-reported |
| 3 | 100 people contacted across at least 2 finished batches. The unit is people: 100 people is about 300 messages | `squad/outreach-sent.md` · self-reported |
| 4 | The winning batch's cut rule and first line, written verbatim when the money landed | `squad/outreach-read.md` · written by beat 4 |

What Gate B opens: beat 5.7, and nothing before it. A founder at day 120 with Gate B unmet still
has Gate A, which they have had since week 4, and a read that names which condition is missing and
which lever moves it. Say that plainly rather than inventing a clock.

**STOP · GATE.** One change for next week, proposed with its reason. Exactly one, the founder's yes
or their own instead.

**Then the weekly task, offered once, and only behind the risk gate.** The gate is 3 by-hand runs
of this exact read, and the founder can say in one line what they changed last time. Offer it as
what it is: **it makes sure the read happens on the days you would have skipped it.** Never as
running while you sleep. A scheduled task is skipped whenever the laptop sleeps and fires when the
lid opens. **One task per founder, and this lane's is the read.** The standing rule, quoted: a
routine that only reads, only drafts or only reduces spend may be scheduled; a routine that sends,
spends more or publishes never runs unattended.

**On a yes, register it in that same turn.** Name it `outreach-read`, weekly, Sunday morning, in
the founder's own company folder, and its whole instruction is the sentence they have typed 3
times: "Read my batch." Where the app they are in can create a local task, create it and say what
you made. Where it cannot, print the path and stop there: Claude Desktop, Code tab, Routines, New
routine, **Local**, weekly. **Local, never Cloud**, since a cloud routine runs on a copy of a
repository and cannot see `squad/` at all. Either way, tell them to press **Run now** once and
choose always-allow on every read it asks about, because a task that hits a permission it does not
have stalls until somebody approves it, and nobody is watching at 9am on a Sunday. On a no, write
nothing, register nothing, and never offer again.

**Last, hand the founder one line for Sunday**: the one change they just agreed to, in their own
words. `/bip sunday` adds nothing up, so it takes the change, not a total. Then stop. You never write
`squad/90-day-plan.md`.

## Beat 5 · THE ROUTINE

Mode `routine`. `references/the-campaign.md` carries the connector path, every campaign setting,
the cost table and the ramp. Read it before you touch Instantly.

**5.0, the gate, and it is the point of this mode.** Read `squad/outreach-read.md` and
`squad/pipeline.md` and score both gates by the tables in beat 4. Gate A open runs 5.1 to 5.6.
Gate B open also runs 5.7. Any condition false: print which one, print the count so far,
and stop at that beat. No workaround, no override, no "if you want to anyway." Say which conditions
you took the founder's word for.

**5.1, the sending address, usually already answered.** The roots file carries a `sending address`
row whenever beat 2 asked for it: read it back, confirm it in one line, and do not ask again. HUMAN
INPUT only where that row is missing, and then write it to the roots file. The rule the answer has
to pass either way: it is **not** the address paying clients reply to, and before Gate B it lives on
the workspace they already own rather than on a new domain. Say plainly which one they are being
sent to make: **an alias on their existing mailbox is free and it is all this lane asks for**, while
a second seat, with its own inbox, runs about $7 to $8 a month and is not needed yet. A founder with
no clients is sending cold from the mailbox their future clients will also email: say that out loud
rather than pretending the risk is elsewhere.

**5.2, HUMAN INPUT then AUTO: Instantly.** Instantly's MCP is a remote hosted server, added as a
custom connector at `https://mcp.instantly.ai/mcp`. Instantly publishes several ways to
authenticate: signing in through OAuth is the current one, and pasting the API key into the URL
(`https://mcp.instantly.ai/mcp/YOUR_API_KEY`) still works but Instantly's own notes call it the
legacy form. Take whichever one their connector screen offers, and never guess a path you have not
seen answer. Then call `workspace_billing_plan_details` and **report the tier the workspace
actually has**. Never assert a tier: the help page says the server is free with the subscription
plus an account with API access, and the pricing page puts API at a paid tier, and those 2 pages
disagree. Print the monthly total off `references/the-campaign.md` before the founder subscribes to
anything.

**5.3, AUTO: the campaign, built paused.** `stop_on_reply` true, `text_only` true, `open_tracking`
false, `daily_limit` set in messages, which is the unit Instantly counts (the by-hand day's total,
about 30 once all 3 cohorts are running, and never above the number they were already sending by
hand), `email_gap` spread across the window, the footer preserved on every step. Say out loud that
Instantly's own High Bounce Auto-Pause does not arm until a campaign has sent 200 emails, so for the
first weeks **the founder is the brake**. Do not turn on A/Z auto-optimize, and say why: its own documentation states
no threshold and no minimum sample, so at 25 people an arm it can switch off the better message.

**5.4, STOP · GATE, every week, forever.** The founder pulls the week's list at beat 1, cuts it, and
approves it before it loads. You cannot remove this beat and you refuse a request to. It is the
dedup checkpoint and the complaint brake, and it is the reason the send is honest.

**5.5, AUTO: the load.** Call `accounts_test_vitals` on the sending address first and refuse to load
when its domain comes back in the failing list; say which record failed (MX, SPF, DKIM or DMARC).
Once a campaign has sent, read that campaign's bounces with `analytics_campaign_overview` and refuse
to load when bounce is over 2%, saying the number you read. On the first load nothing has sent
through Instantly yet, so say there is no bounce number yet and let the DNS check stand as the gate.
Then load that batch and nothing else: the approved rows as leads
(`add_leads_to_campaign_or_list_bulk`), each carrying its own broken-thing first line, and beat 2's
3 touches as the campaign's day 1, day 4 and day 9 steps with the footer preserved on every one.
Never load a row with no `cut <date>` above it, never load a row already in `squad/outreach-sent.md`,
and never load more than 50. Report 3 counts: loaded, dropped as duplicates, dropped for a missing
address.

**5.6, STOP · GATE: the word that starts it.** The campaign is paused and it stays paused until the
founder says so. Print what is about to go out, the daily limit, the sending window and the address
it goes from, then stop and wait. On **"Turn it on."** call `activate_campaign` and say it is live,
with the date and the campaign name. On anything else, leave it paused and say it is still paused.
Nothing else in this skill activates a campaign. From the second week on this beat is one line: the
campaign is already running, the batch just loaded into it, and there is nothing to press.

**The stamp, at the end of each sending week, because beat 3 no longer runs.** The campaign did the
sending, so nobody typed the week out by hand and nothing fills the log unless you do it. Read
`analytics_campaign_steps` for that campaign, stamp that batch's rows in `squad/outreach-sent.md`
with the dates and touch numbers it reports, and mark `stop` on every address that opted out. Skip
this and beat 1's dedup goes blind, beat 4 reads its 2 numbers off a file nobody writes, and the
next pull emails the town a second time.

**5.7, Gate B only.** The second domain and its ramp, dates named: 14 days minimum domain age, then
a 30-day ramp starting at 5 to 10 a day and capped at 200, about 4 weeks. A daily limit above the
by-hand number. A second town or a second trade. Any split test. Every one of them is earned by
money rather than granted by a date, and one at a time, never 4 in a week.

**Never built, and say why in one line each when asked.** An Apify schedule: the Apify MCP publishes
no schedule tool at all, so this skill cannot make one, and a weekly pull takes minutes by hand in
the same session where the list is approved. Apify's own console can run one, at about $1.20 a month
for a weekly 200-place pull, for the founder who asks. A scheduled task for the send: it fires when
the lid opens, which is the moment the founder could type the command, and the direction rule
forbids scheduling anything that sends. A cloud routine over `squad/`: `squad/clients/*/transcript.md`
holds real people's recorded words, and pushing that to a hosted repository to save one typed
command is a trade nobody makes once it is stated that way.

**Never automated, and it belongs in this mode's last line.** The reply. No auto-reply agent, ever.
Taste is the first reason; since 2026-08-02 the EU AI Act's Article 50 transparency duties are the
second, and a human-approved draft the founder sends keeps this lane clear of the question entirely.

Write `squad/outreach-routine.md`: what was created, in which workspace, the sending address, the
daily limit, the gate state on the day it was built, and the monthly cost. Then stop.

## Rules

- Every message to the founder is scannable: a short header, then a table or short bullets. They
  are deciding, not studying.
- Never send. Not an email, not a reply, not a booking. Instantly's servers send only what the
  founder approved; every other message leaves by their hand.
- Never write a cold message with no postal address and no opt-out, at any volume, business
  recipients included.
- Never write a list for a country that requires consent first, until the founder says they have a
  lawful basis. Say it is not legal advice.
- Never price past `squad/business.md`, and never put a price in a cold message at all.
- Never invent a company, a contact, an email address, a number or a need. A blank cell is an
  answer; a guessed address is a bounce.
- Never save an observation as a quote. A stranger has said nothing yet, so what can be seen from
  outside is labeled an observation, and only the words a person actually wrote are quoted.
- Never name a winner unless the 2 Wilson 95% intervals do not overlap. When they overlap, print
  both in words and how many people each side would need.
- Never make a gate a rate. Both gates are counts, and 3 of Gate B's 4 are the founder's own word.
- Never claim the list scrapes itself, that the numbers get read overnight, or that a split test
  runs on its own. At this volume none of the 3 is true.
- Never remove the weekly approval, never load a list the founder has not cut, and never raise
  `daily_limit` above the number they sent by hand.
- Never turn on Instantly's A/Z auto-optimize at this volume.
- Never write `squad/90-day-plan.md`, `squad/business.md` or the Outreach Sheet.
