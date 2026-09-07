# The numbers

Beat 4's detail. Measure, then Improve: 3 numbers, one ladder, one honest sentence, one line that
is a change or a hold.

## The 3 numbers, and the unit

**People contacted, replies, calls booked.** All 3 in **people**, never in messages sent. 50 people
at 3 touches is up to 150 messages, so the 2 units are off by 3x, and a reply rate computed on
messages is a third of the truth. Every table header says which unit it is in.

| Number | By hand | Once the campaign sends |
|---|---|---|
| people contacted | the batch's rows in `squad/outreach-sent.md` with touch 1 stamped | step 1's sent count in `analytics_campaign_steps` |
| replies | the log's Replied column | the campaign's reply count in `analytics_campaign_overview` |
| calls booked | rows in `squad/pipeline.md` whose source names this list and whose next touch or outcome is a call; where the pipeline holds none and the founder says one booked, count it and print it as their word | the same |

**Do not get people by dividing a campaign total by 3.** `stop_on_reply` is true, so a person who
replied got 1 or 2 touches, and the divisor is never actually 3. When the campaign and the log
disagree, print both, name which is which, and use the campaign's number.

The benchmark to sit next to, said without a year on it: **about 3%** of people reply across the
whole market, top campaigns over 10%, and 58% of replies arrive off touch 1. A ranked list of named
local businesses lives in the friendlier half of that.

## The one honest sentence

Under any batch or comparison below 300 people contacted, print it word for word: **under 300
people, 3 against 5 is a coin; do not rewrite the email on it.**

Two batches under 300 a side get both rows printed side by side and no winner named. The 3 things
that move a number far enough to see at this volume are **who is on the list**, **what the first
line says about them**, and **whether the ask is a call**. Nothing about a subject line resolves
here; Instantly's own guide asks for at least 1,000 recipients per version before calling one.

## The ladder, stopping at the first failure

| What the numbers say | The one thing to fix |
|---|---|
| sent under the plan | the block did not happen. Fix the block, nothing else |
| sent fine, replies near 0 | the people first, then the first line, in that order |
| replies land, no calls | the ask is too big; ask for 20 minutes and nothing else |
| calls but no money | that is G6, not this lane |

One change a week, never 2, and most weeks a named hold instead (`holding until <number>, week N`).
Two changes and next Sunday cannot tell you which one moved. The change briefs the next Run; it never
edits a batch already sending.

## The winner line

The day `squad/pipeline.md` shows money from a row whose source names this list, write that batch's
touch 1 first line, word for word, under `THE WINNER` in `squad/outreach-read.md`. At that moment,
never recalled later, on a finished batch or not. Nothing for the founder to do. Beat 5's move 2
copies that line into the next town.

## The file

`squad/outreach-read.md`. The winner block at the top is written the day money shows; the batch
sections below it are appended and never rewritten.

```
# Outreach read

## THE WINNER  (written the day money lands, word for word)
Batch <go date> · the first line: "<touch 1's first line>"

---

## Batch 2026-09-07 · finished 2026-09-23
50 people contacted · 3 replies · 1 call booked (pipeline)
Under 300 people, 3 against 5 is a coin; do not rewrite the email on it.
The stage that broke: <one line>
The Improve line: <one named change, or `holding until <number>, week N`, the founder's yes>
```

## The order on Sunday

Measure first, then Improve, then the post. This read runs **before** `/bip sunday`, so the Improve
line is decided before the founder writes the week, and the Sunday post carries it. Hand it over as a
line, not a total: `/bip sunday` adds nothing up and takes only what the founder says. Hand them the
4-week plan's own sentence to paste, both halves filled in, `Put this in week N's Measure: <n>
people contacted, <n> replies, <n> calls booked / Improve: <the line>`, so the plan's Measure cell
gets filled the same Sunday its numbers were read. On an unfinished batch the Measure half is `held
until batch <date> is past day 9`.

Never write `squad/90-day-plan.md`, the 4-week plan's file. Its outputs are closed and belong to one
skill.
