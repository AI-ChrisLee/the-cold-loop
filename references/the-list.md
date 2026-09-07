# The list

Beat 1's detail. The list is the lever, not the sentence craft: the jump in reply rate happens at
the row, where something specific about this business is true, and "first name plus company" (what
every mail merge produces) buys close to nothing.

## Why 50, and why one trade in one town

**50 is how many real first lines one founder can read and send in a week at 10 a day.** Belkins'
analysis of 16.5 million emails points the same way (campaigns under 50 recipients reply at 5.8%,
campaigns at 500+ at 2.1%), and that split is a pattern seen after the fact, not a cause: small
campaigns are small because a human picked them, and the same hand wrote the better email. Quote it
as support, never as the cause.

One trade and one town so the broken-thing sentence can repeat its shape across the batch and the
founder learns which shape lands. **It binds the list until the routine opens.** A second town or
trade is beat 5's move 2, made on the same first line once that line has booked calls. The one
exception is a town that cannot leave 50 standing after the drops and the dedup: say so, ask which
one widens, and pull on the answer.

Companies under 50 employees answer more than anyone else in the benchmark set, around 7%. Named
local businesses sit in the friendliest group there is. Worth saying to a founder who thinks cold
email is dead.

## The pull

Actor: `compass/crawler-google-places`. **Run `fetch-actor-details` before every call** and build the
input off the live schema. Never assume a field from memory; this is a repo rule and the schema
moves.

- Query `<trade> in <town>`.
- **Cap the pull at 120 places.** The drops take roughly a third, and the rank keeps the top 50 of
  what stands, so 120 in is what leaves 50 sharp rows.
- Never pad the list to reach the number.
- **The add-ons cost real money on the free tier.** Business leads and email verification are $0.10
  each on free, against a $5 monthly credit, and $0.004 to $0.005 on any paid tier. 200
  verifications on free is $20, 4 times the whole credit. Print the price before enabling either,
  every time.
- The base pull is about $0.004 a place, so 120 places is about $0.48, well inside the free credit.

## The drops

| Out | Why |
|---|---|
| Chains and franchises | the person who could say yes is not at that address |
| A site rebuilt inside the last year | somebody already sold them the thing that is broken |
| No reachable contact | a row you cannot write to is not a row |

One line on how many went and why. Never a section, never a table of the dead.

## The one sentence

What is broken there, visible from outside, in one sentence a stranger would recognise as being
about them. Where to look, in the order that pays:

1. **The site on a phone.** Text under the fold, a menu that does not open, a form that overflows.
2. **The Maps listing.** No hours, no photos since 2019, a phone number that is not the site's.
3. **The booking button.** Whether it goes anywhere, and what happens after the second tap.
4. **The reviews against the site.** 200 reviews at 4.8 and a site that never mentions one.

**The test.** A sentence that would fit any business in the trade is not a row yet. Rewrite it with
their noun in it, or drop the row.

## The rank

The squad orders the rows and keeps the top 50. Sharp, from the top down:

| Rank | The sentence |
|---|---|
| first | names one thing seen today, in their own noun, that the offer fixes: "your booking button on a phone opens a blank page" |
| middle | true and specific, but the offer fixes it only sideways: "no photos on Maps since 2019" for someone selling booking pages |
| last | true of any shop in the trade: "your site could look more modern" |

Ties break on the contact: a named person over an info@ box, a reachable email over a phone-only
row. Print the 50 numbered with their sentences. The rows below 50 stay in hand, in rank order,
so "swap row N" puts the next one in N's place without a second pull.

## The dedup

Drop every address that already appears in `squad/outreach-sent.md`, **including every row marked
`stop`**. A repeated pull against one trade in one town re-pulls the same businesses, so without
this check week 2 emails the people week 1 emailed. That is the complaint engine, and 1 complaint at
50 sends is 2%, 20 times the 0.10% practical threshold. There is no volume to hide under either:
Google's all-sender rule asks every sender, at every volume, to keep complaints under 0.3%.

## The file

`squad/cold-list.md`, one section per batch, newest on top:

```
# Cold list

## <trade> in <town>
ranked by the squad, top 50 of <count>, <date> · go <date> · dropped <n> (chains, rebuilt inside a year, no contact)

| # | Company | Contact | Email | Link | What is broken there |
|---|---|---|---|---|---|
| 1 | ... | ... | ... | site or Maps listing | one sentence |
```

The header is written at the rank, without `go`; the founder's go stamps `go <date>` onto it, and
that date names the batch. The header never carries a member rule. A new pull writes a new section
above the last one and rewrites nothing underneath.

Who got which touch on which day lives in `squad/outreach-sent.md`, and only there. This file
carries no touch column: one fact, one home. `Link` is the company's site, or its Maps listing
where it has no site.

The `Email` cell stays blank where no address is reachable, with a note that the row is worth a
phone call. Never invent one: a guessed address is a bounce, and bounces move the whole domain.

## The country rule

Ask both countries before anything is written: where the founder is, and where the list is.

**A country that requires consent first stops the run.** Germany is the named example: UWG Section
7(2) requires prior express consent for business advertising email, exposure up to EUR 300,000 per
case, enforced by competitors through civil suits as well as by regulators. Each EU state applies
the ePrivacy rules differently, so being GDPR-compliant does not settle it, and a footer does not
fix a consent rule.

Say the rule in 2 lines. Say plainly that this is not legal advice. Write no list until the founder
says they have a lawful basis.
