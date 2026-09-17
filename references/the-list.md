# The list · Google Maps through Apify

1 output: 50 new rows appended to `squad/cold-list.csv` at every go.

## Apify not loaded

Print this, word for word, and stop:

```
Your list needs Apify, and it isn't connected yet. 3 steps:
1. Make a free account at apify.com and copy your API token (Settings, then API & Integrations).
2. Type: Here is my Apify token: ____. Use it for the winning offer.
3. Quit and reopen Claude Code.
Then say "Build my outreach list." again.
```

The token line writes `.mcp.json`, the same file /the-winning-offer uses. Never print the token back.

## The search and the zip codes

- **The search** is WHO line 1, said the way someone types it into Google Maps: 1 or 2 words ("dentists", not
  "independent dental offices with 2 to 10 staff"). It never changes. A second trade is never pulled. If WHO
  line 1 on `squad/business.md` changed since the row was written, say so in 1 line and use the new one.
- **The zip codes.** The founder names 1 town. Right after the town comes back, before any pull, list its
  zip codes (postal codes outside the US) once, each with the latitude and longitude of its center (in the
  US, the Census Gazetteer ZCTA table carries both), the zip code the founder named first, else the center of
  town first, then the rest sorted by straight-line distance from it. Never order them by eye off a map or a
  numbered list. The town's zip codes are the ones whose place name is the town (in the US, the GeoNames US
  postal file). Leave out any with no row in the Gazetteer ZCTA table (PO-box-only and single-company codes,
  like Austin's 73301 and 73344) and any whose `ALAND_SQMI` is under 0.02 (a single building, like Denver's
  80293). Each pull takes the first zip code not yet in the file's `Zip code` column. All used: ask for the
  next town in 1 line. The search stays.
- **The row.** `cold list` = `<search> · <town>, <country of the list> · founder in <country> · zip codes
  <code>, <code>, <code>`.

## The price, before any spend

Off `fetch-actor-details` pricing, at the account's own tier (`userTier`):

1 zip code = 120 × (Scraped place + Add-on: Company contacts enrichment).

On Apify's free plan that is 120 × ($0.004 + $0.002) = $0.72. The free plan carries $5 of credit a month.

The price line ends the question message, and the answer is the yes:

```
Next: <search>, 1 zip code at a time. Up to 120 places with their contacts, $<price> of your Apify credit a zip code. If 1 zip code leaves fewer than 50, I pull the next, 3 at most: $<price × 3> at most. Your answer is your yes.
```

The rows already hold the town and both countries: nothing to ask, so the message is the price line alone,
`<search>, 1 zip code at a time` becomes `<search> in <next zip code>`, and it ends on "Say yes."

## The pull

- `call-actor` on `compass/crawler-google-places`, input built off the live schema:
  `searchStringsArray` [the search], `postalCode` the zip code, `countryCode` the list's country,
  `maxCrawledPlacesPerSearch` 120, `scrapeContacts` true. A postal code goes with the country only, never
  with a city.
- `callOptions.maxTotalChargeUsd` = the price of 1 zip code, or $0.50 when the price is lower, because Apify
  refuses any cap under $0.50. `maxCrawledPlacesPerSearch` 120 still holds the spend to the printed price.
- `waitSecs` 45, then `get-actor-run` with `waitSecs` 45 until it reads SUCCEEDED, then `get-dataset-items`.
- Nothing else is turned on. Business leads, email verification, skip closed places, minimum stars, the
  website filter, reviews and images each cost extra per place.

## The drops, in this order, counted

1. **Another trade.** The listing's `categoryName` is not the search's trade or a specialty of it (dentists:
   Dentist, Dental clinic, Cosmetic dentist, Pediatric dentist, Orthodontist and Dental implants provider
   stay; Podiatrist and Medical clinic go). A listing whose own name names a kind WHO line 1 rules out goes
   too, counted here ("Commercial" in the name when WHO line 1 says residential or homeowners). Day 1 would
   tell him about a problem his business does not have.
2. **Chains.** A company name that shows up more than once in the pull, a national brand, a phone number
   another row in the pull also carries, a toll-free phone number (US 800, 833, 844, 855, 866, 877, 888), or
   a website that is a location page inside a bigger site (a path like `/south-lamar-dentist/`, not the home
   page). The person who could say yes does not work at that address.
3. **No email.** No business email came back from the contacts enrichment. Never guessed: a guessed address
   is a bounce.
4. **Already on the list.** The email, or the company name in the same city, is already in
   `squad/cold-list.csv`, or the same email is on another row of this pull, dropped or not, with more reviews
   (on a tie, the first one pulled stays). 1 inbox gets 1 set of emails.
5. **Under 10 Google reviews**, or no review count. "You have 6 Google reviews" reads like a dig, and
   "1 Google reviews" breaks.

## The rank

Most Google reviews first. Keep the top 50.

Fewer than 50 standing: pull the next zip code (inside the same yes, 3 zip codes at most), drop again,
rank again. Still fewer than 50 after 3: show what stands and say the count. Never pad the list.

Print:

```
Pulled <n> places in <zip codes>. Dropped <n> other trades, <n> chains, <n> with no email, <n> already on your list or twice in this pull, <n> under 10 reviews.
1. <Company name> · <reviews> reviews · <email>
2. ...
Say go.
```

A count of 1 is singular: 1 other trade, 1 chain.

## The file

`squad/cold-list.csv`. Appended at every go, never rewritten. The header is written once, UTF-8:

```
Email,Company name,Website,Phone,Reviews,City,Zip code,Batch
```

| Column | Holds |
|---|---|
| `Email` | the business email the contacts enrichment returned. More than 1: the first on the business's own website domain, else the first. A free-mail address (gmail.com, hotmail.com) counts when it is the only one |
| `Company name` | the Google Maps listing's name |
| `Website` | the listing's website, cut at any `?`, blank when it has none |
| `Phone` | the listing's phone |
| `Reviews` | the Google review count, the number the rank runs on |
| `City` | the listing's city |
| `Zip code` | the zip code this row was pulled on |
| `Batch` | the go date, `YYYY-MM-DD` |

Every cell is a field the pull returned, or the go date. Quote any cell holding a comma.

## The country stop

Where the list is and where the founder is, both. Either one requires consent before commercial email:
print these 2 lines and write no list.

```
<country> requires consent before commercial email, business addresses included (Germany: UWG section 7. Canada: CASL). A footer does not fix a consent rule.
This is not legal advice. I write no list until you tell me you have a lawful basis.
```

Germany and Canada are 2 of these countries, not the whole list. When unsure about a country, stop the same
way.
