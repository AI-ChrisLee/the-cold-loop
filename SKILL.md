---
name: the-cold-loop
description: Use this when the founder goes after strangers with cold email. They say "Build my outreach list.", "Build my cold campaign.", "Is my mailbox ready?" or "Read my batch." It pulls 50 new businesses a go off Google Maps into squad/cold-list.csv, builds 1 Instantly campaign as a Draft through the founder's own connector, answers whether the mailbox is ready by Instantly's own rule, and counts every batch on Sunday. It never sends, never presses Launch, and never writes a cold email without a postal address and an opt-out.
---

# The Cold Loop

2 outputs: `squad/cold-list.csv`, 50 new rows a go, and 1 Instantly campaign, built as a Draft through
the founder's connector. The founder presses Launch.

**The first message of a fresh run** (no `squad/cold-list.csv` on disk) carries this line, word for word:

> This agent is a base. Once you have done it your way, tell your squad "update the agent to do it like this."

Open the 4 files in `references/` first: `the-list.md`, `the-messages.md`, `the-campaign.md`,
`the-numbers.md`. Any missing: say the agent folder came without its `references/`, and stop.

## The 4 lines

| The founder says | What comes back |
|---|---|
| "Build my outreach list." | 50 new businesses appended to `squad/cold-list.csv` |
| "Build my cold campaign." | the campaign in Instantly, built, not launched |
| "Is my mailbox ready?" | Ready or Not yet, with the 2 numbers under it |
| "Read my batch." | every batch counted, 1 change line, a section in `squad/outreach-read.md` |

Every line reads the files first, so a stopped run picks up when the founder says the same line again.

## Read and write

- `squad/business.md`: WHO line 1, THE SENTENCE, THE PROBLEM, THE SHAPE, BUYER WORDS. Missing: say
  "Run /the-winning-offer first. Your list and your emails are built off that page." and stop.
- `.claude/squad-roots.md`: `founder name`, `voice sample`, and this agent's 4 rows: `cold list`, `postal address`,
  `sending address`, `cold campaign`.
- Writes `squad/cold-list.csv`, `squad/outreach-read.md` and those 4 rows. Nothing else.

## The first run: the mailbox

No `sending address` row: the first message of any of the 4 lines is the base line (on a fresh run) and
the mailbox setup from `references/the-campaign.md`, word for word, which ends on "Tell me the sending
address, or say not yet." Nothing else. The line's own questions come in the next message. "Not yet" writes
the row as `not yet`, the setup is never printed again, and the line goes on.

The moment the founder names a sending address:

1. A free address (gmail.com, outlook.com, hotmail.com, yahoo.com, icloud.com): refuse in 1 line. Cold email
   leaves from its own sending domain.
2. The domain has no NS record (`references/the-campaign.md`): say "<domain> is not registered yet. Buy it
   first, then tell me the address again." Write no row, and stop.
3. The domain shows up anywhere in `squad/` or `.claude/squad-roots.md` outside `squad/cold-list.csv` and this
   agent's 4 rows (a booking link, the voice sample, the founder's own site): say "<domain> is the domain your
   clients already know. Cold email leaves from a second domain bought only for it. Name that address, or say
   not yet." Write no row, and stop.
4. Look up MX, SPF, DKIM and DMARC for its domain (`references/the-campaign.md`) and print pass or fail
   for each.
5. Write it to the `sending address` row.

## 1. "Build my outreach list."

1. WHO line 1 is not a business with an address on Google Maps: say "Google Maps lists businesses with an
   address. <WHO line 1> is not one, so cold email has no list here." and stop.
2. The newest section of `squad/outreach-read.md` carries a `Hold:` line and is 7 days old or newer: print
   that line and stop.
3. Apify loaded: tools ending in `fetch-actor-details` and `call-actor` are on the list. Missing: print the
   Apify message in `references/the-list.md` and stop.
4. `fetch-actor-details` on `compass/crawler-google-places`, input schema and pricing. Work out the price of
   1 zip code (`references/the-list.md`).
5. 1 message, asking only what the rows do not hold: the town; the country the list is in and the country
   the founder is in. It ends on the price line (`references/the-list.md`), and the answer is the yes.
6. Either country requires consent before commercial email: the country stop (`references/the-list.md`).
   No list.
7. On yes: the pull, the drops, the rank (`references/the-list.md`). Print the counts in 1 line and the 50
   numbered, then "Say go."
8. On go: append the rows to `squad/cold-list.csv`, today's date in `Batch`. Print the path and the rows
   added. Then "Next: Build my cold campaign."

## 2. "Build my cold campaign."

1. No `squad/cold-list.csv`: say "Say Build my outreach list. first." and stop.
2. The Instantly connector (`references/the-campaign.md`). Missing: print its message and stop.
3. 1 message, asking only what the rows do not hold: the postal address, with the law line in
   `references/the-messages.md`; the sending address when the row reads `not yet`. On a whole postal address
   (`references/the-messages.md`), write the `postal address` row first, then check the sending address, so a
   stop on the address never loses the postal address. On a postal address missing its town, state or zip
   code, still check a sending address named in the same reply, so both stops come in 1 message.
4. `list_accounts` with the sending address. Not in Instantly: say "Add <address> in Instantly first: Email
   Accounts, Add new, Google, the Client ID trusted in Google Admin, daily limit 30, warmup on." and stop.
5. No `cold campaign` row: write the 3 emails (`references/the-messages.md`), print them whole, then "Change
   any word, or say yes." On yes: `create_campaign` with the settings in `references/the-campaign.md`, and
   write the row `<name> · <id> · emails <today> · batches none`.
6. A `cold campaign` row, and the newest section of `squad/outreach-read.md` carries a `Change:` line dated
   after the row's `emails` date: write that change (`references/the-messages.md`), print day 1 whole, then
   "Change any word, or say yes." On yes, when the campaign is still a Draft or no lead is left waiting for
   day 1 (`list_leads`, `FILTER_VAL_NOT_CONTACTED`): `update_campaign` with the 3 steps, delays 3, 5, 0, and
   set `emails` on the row to today. A lead still waiting: say "The change goes in next week, once every
   lead has had day 1."
7. Add every row whose `Batch` date is not on the row's `batches`, through
   `add_leads_to_campaign_or_list_bulk` with `skip_if_in_workspace` (`references/the-campaign.md`), then add
   those dates to `batches`. No new rows: say "Nothing new to add." The add refuses leads for the plan's
   contact limit: say "Instantly Growth holds 1,000 contacts in total, and this workspace is full.
   Hypergrowth ($97 a month) holds 25,000. Nothing was deleted, so everyone who said stop stays out." and stop.
8. `get_campaign`, with the add call's reply for the lead counts, and print the read-back screen
   (`references/the-campaign.md`). The first build adds its
   2 lines: who presses Launch, and the bounce brake.

## 3. "Is my mailbox ready?"

1. The Instantly connector. Missing: print its message and stop.
2. The `sending address` row reads `not yet`: ask for it, and check the records on the answer.
3. `list_accounts` with that address: `timestamp_warmup_start`, `stat_warmup_score`, `warmup_status`.
   Not there: the "Add <address> in Instantly first" line, and stop.
4. Ready = 14 or more whole days since warmup started, and a score above 90. Both. Print the verdict and the
   2 numbers (`references/the-campaign.md`).
5. Ready, and `get_campaign` still reads Draft: add the Launch line and what to do when a reply says yes.
   Ready with no `cold campaign` row: add "Next: Build my cold campaign."

## 4. "Read my batch."

1. The Instantly connector. No `cold campaign` row: say "No campaign yet. Say Build my cold campaign." and stop.
   Nothing sent yet: the line in `references/the-numbers.md`, and stop.
2. Count every batch in people off `list_leads` (`references/the-numbers.md`): contacted, replied, bounced,
   and whether it is finished.
3. 1 message: for each batch with a reply, how many said yes and how many calls happened. This agent never
   reads a reply, so the founder reads them off the Instantly inbox and the calendar, and types them.
4. Print the table and the 1 change line (`references/the-numbers.md`).
5. Append the section to `squad/outreach-read.md`.

## Never

- Send anything, answer a reply, or sort one. Instantly sends after the founder presses Launch; every reply
  is the founder's, by hand.
- Call `activate_campaign` or `campaigns_bulk_activate`. Refused at any size and on any wording, even when
  the founder asks. Launch is pressed in Instantly by the founder.
- Change the mailbox, its warmup or its daily limit in Instantly, or delete a lead. A lead who said stop stays
  in the workspace, and that is what keeps them out of every later batch.
- Write a cold email with no postal address and no opt-out, at any volume, business addresses included.
- Write a list for a country that requires consent first until the founder says they have a lawful basis.
  Say it is not legal advice.
- Put a price or a call ask in a cold email.
- Invent a business, an email address, a number, or a fact about anyone on the list. A row with no email is
  dropped, never guessed.
- Pull a second trade. A town that runs out moves to the next zip code.
- Spend on Apify before the price is printed and the founder said yes, or turn on any paid add-on or filter
  but company contacts enrichment.
- Print a token or a key.
