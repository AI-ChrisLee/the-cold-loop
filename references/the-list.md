# The list

Beat 1's detail. The list is the lever, not the sentence craft: the jump in reply rate happens at
the row, where something specific about this business is true, and "first name plus company" (what
every mail merge produces) buys close to nothing.

## Why 50, and why one trade in one town

**50 is how many real first lines one founder can write in a week.** The cap is the founder's own
hand, not a study. Belkins' analysis of 16.5 million emails points the same way (campaigns under 50
recipients reply at 5.8%, campaigns at 500+ at 2.1%), and that split is observational: small
campaigns are small because a human picked them, and the same hand wrote the better email. Quote it
as support, never as the cause.

One trade and one town so the broken-thing sentence can repeat its shape across the batch and the
founder learns which shape lands. **It binds the FIRST list only.** From batch 2, ask in one line,
in beat 1's own question and before the pull, whether the trade or the town widens this week,
because a town holds a fixed number of businesses in one trade, the dedup takes out everyone the
first pull already got, and Gate B needs 2 finished batches.

Companies under 50 employees answer more than anyone else in the benchmark set, around 7%. Named
local businesses sit in the friendliest segment there is. Worth saying to a founder who thinks cold
email is dead.

## The pull

Actor: `compass/crawler-google-places`. **Run `fetch-actor-details` before every call** and build the
input off the live schema. Never assume a field from memory; this is a repo rule and the schema
moves.

- Query `<trade> in <town>`.
- **Cap the pull at 120 places.** The drops take roughly a third and the founder still has to cut,
  so 120 in is what leaves 50 standing after a real cut. A cut that starts at 50 ends under 50.
- A town that cannot leave 50 standing after the drops needs the trade widened. Say so. Never pad.
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

## The dedup

Drop every address that already appears in `squad/outreach-sent.md`, **including every row marked
`stop`**. A repeated pull against one trade in one town re-pulls the same businesses, so without
this check week 2 emails the people week 1 emailed. That is the complaint engine, and 1 complaint at
50 sends is 2%, 20 times the 0.10% practical threshold. There is no volume to hide under either:
Google's all-sender rule asks every sender, at every volume, to keep complaints under 0.3%. The only
real protection at this stage is 50 businesses a human chose.

## The file

`squad/cold-list.md`, one section per batch, newest on top:

```
# Cold list

## <trade> in <town>
cut <date> · pulled <date> · 50 rows · dropped <n> (chains, rebuilt inside a year, no contact)

The cut rule, in the founder's words: "<verbatim>"

| # | Company | Contact | Email | What is broken there |
|---|---|---|---|---|
| 1 | ... | ... | ... | one sentence |
```

A new pull writes a new section above the last one and rewrites nothing underneath. **Read the
newest section's cut rule at the start of the next pull** and apply it to the drops and to the
broken-thing pass, so the founder writes their rule once.

Who got which touch on which day lives in `squad/outreach-sent.md`, and only there. This file
carries no touch column: one fact, one home.

The `Email` cell stays blank where no address is reachable, with a note that the row is worth a
phone call. Never invent one: a guessed address is a bounce, and bounces move the whole domain.

## The jurisdiction rule

Ask both countries before anything is written: where the founder is, and where the list is.

**A prior-consent regime stops the run.** Germany is the named example: UWG Section 7(2) requires
prior express consent for business advertising email, exposure up to EUR 300,000 per case, enforced
by competitors through civil litigation as well as by regulators. Each EU state implements the
ePrivacy rules differently, so being GDPR-compliant does not settle it, and a footer does not fix a
consent regime.

Say the rule in 2 lines. Say plainly that this is not legal advice. Write no list until the founder
says they have a lawful basis. Naming the rule is not advice; staying silent is worse.
