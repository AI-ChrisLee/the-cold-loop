# The list

Beat 1's detail. The list is the lever. The jump in reply rate happens at the row, where the thing
you say is true of that business and of nobody else on the list, and "first name plus company",
what every mail merge produces, buys close to nothing.

**This beat scrapes. It does not diagnose.** Every column in the file is a field the pull returned.
Nothing in it says what a business needs, because a pull cannot see that, and a guess dressed as an
observation is the thing a stranger spots first.

## Why 50, and why one trade in one town

50 is one week's batch at 30 a day, and it is small enough that the founder can still read the
names. Belkins' analysis of 16.5 million emails points the same way: campaigns under 50 recipients
reply at 5.8%, campaigns at 500+ at 2.1%. That split is a pattern seen after the fact, not a cause.
Quote it as support, never as the cause.

One trade and one town so the same message lands on every row. **It binds the list until the
routine opens.** A second town is beat 5's move 2. **A town that cannot leave 50 standing after the
drops and the dedup widens the town, never the trade.** Pull the next ring of suburbs and say in one
line how far you went.

Companies under 50 employees answer more than anyone else in the benchmark set, around 7%. Named
local businesses sit in the friendliest group there is. Worth saying to a founder who thinks cold
email is dead.

## The pull

Actor: `compass/crawler-google-places`. **Run `fetch-actor-details` before every call** and build the
input off the live schema. Never assume a field from memory; this is a repo rule and the schema
moves.

- Query `<trade> in <town>`.
- **Cap the pull at 120 places.** The drops take roughly a third and the rank keeps the top 50 of
  what stands, so 120 in is what leaves 50 rows.
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
| No email address | this is an email list. A guessed address is a bounce, and a bounce moves the whole domain |

One line on how many went and why. Never a section, never a table of the dead.

## The rank

**Most Google reviews first.** It is the one number the pull returns for every row, it cannot be
argued with, and it puts the busiest businesses in the trade at the top of the file. Ties break on
the contact: a named person over an info@ box.

Keep the top 50. Print them numbered, three fields each, company, review count, email. **One answer
moves the list: go.**

## The dedup

Drop every company that already appears in `squad/outreach-sent.md`, **including every row whose
`replied` field reads `stop`**. A repeated pull against one trade in one town re-pulls the same
businesses, so without this check week 2 emails the people week 1 emailed. That is the complaint
engine, and 1 complaint at 50 sends is 2%, 20 times the 0.10% practical threshold. There is no
volume to hide under either: Google's all-sender rule asks every sender, at every volume, to keep
complaints under 0.3%.

## The file

`squad/cold-list.csv`, one real CSV, one batch, rewritten whole at every go. The founder opens it in
a sheet to read it and Instantly imports the same bytes. One header row, UTF-8, one sheet:

```
Email,First name,Last name,Company name,Website,Phone,Reviews,City
dana@verdantmedspa.com,Dana,Whitlock,Verdant Med Spa,verdantmedspa.com,(512) 400-1000,318,Austin
```

| Column | What the pull returned |
|---|---|
| `Email` | the address on the listing or the site. Required: a row without one was dropped |
| `First name`, `Last name` | the contact's name split on the space. Both blank where the address is an info@ box |
| `Company name` | the listing's name |
| `Website` | the listing's site, blank where it has none |
| `Phone` | the listing's phone |
| `Reviews` | the Google review count, the number the rank runs on |
| `City` | the town this batch was pulled in |

**`Reviews` and `City` are what day 1 merges**, as `{{Reviews}}` and `{{City}}`, matched by name and
by case: `reviews` merges nothing at all. Quote any cell holding a comma.

It is written at 2 moments and no others: at the go, and again on "Export my list for Instantly.",
both times off the rows already approved and never off a fresh pull.

**The go also writes the batch into `squad/outreach-sent.md`,** one row per company at touch 1 with
`sent` left empty, stamped with the go date. That is where the batch gets its name, it is what the
next pull dedups against, and it is what a resumed run reads to know this beat finished.

## The country rule

Ask both countries before anything is written: where the founder is, and where the list is.

**A country that requires consent first stops the run.** Germany is the named example: UWG Section
7(2) requires prior express consent for business advertising email, exposure up to EUR 300,000 per
case, enforced by competitors through civil suits as well as by regulators. Each EU state applies
the ePrivacy rules differently, so being GDPR-compliant does not settle it, and a footer does not
fix a consent rule.

Say the rule in 2 lines. Say plainly that this is not legal advice. Write no list until the founder
says they have a lawful basis.
