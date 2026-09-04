# The numbers

Beat 4's detail. Measure, then Improve: two numbers, one interval said in words, one ladder, one
line that is a change or a hold.

## The pair, and the unit, before anything else

The 2 numbers are **delivered** and **replied**, which is the pair the 4-week plan's Measure cell
takes by name for this lane. Delivered is the people whose first touch landed: people contacted
minus the ones that hard-bounced. Before Gate A nothing reports a bounce, so `sent` stands in and
the table header says which of the 2 it is printing.

Both are counted in **people contacted**, never in messages sent. 50 people at 3 touches is 150
messages, so the 2 units are off by 3x, and a reply rate computed on messages is a third of the
truth. Every table header says which unit it is in.

**Do not get people by dividing a campaign total by 3.** `stop_on_reply` is true, so a person who
replied got 1 or 2 touches, and the divisor is never actually 3. People contacted is step 1's sent
count in `analytics_campaign_steps`, and delivered is that count minus step 1's bounces.

The benchmark to sit next to, said without a year on it: **about 3%** across the whole market, top
campaigns over 10%, and 58% of replies arriving off touch 1. A hand-cut list of named local
businesses lives in the friendlier half of that.

## The Wilson interval

Compute it, do not interpolate. At 95%, with `z = 1.96`, `p` the observed rate and `n` the people
contacted:

```
centre     = (p + z²/2n) / (1 + z²/n)
half-width = z/(1 + z²/n) × sqrt( p(1-p)/n + z²/4n² )
interval   = centre ± half-width
```

**Never the normal approximation** (`p ± z·sqrt(p(1-p)/n)`). At 3 replies out of 50 it returns a
negative lower bound, which is not a possible reply rate, and printing an impossible number in the
one place the product claims to be more honest than everyone else is the worst thing this skill
could do.

| Replies / people | Wilson 95% | In words |
|---|---|---|
| 0 / 50 | 0% to 7.1% | 0, up to about 1 in 14 |
| 1 / 50 | 0.4% to 10.5% | anywhere from almost never to 1 in 10 |
| 3 / 50 | 2.1% to 16.2% | 1 in 50 to 1 in 6 |
| 5 / 50 | 4.3% to 21.4% | 1 in 23 to 1 in 5 |
| 6 / 100 | 2.8% to 12.5% | 1 in 36 to 1 in 8 |
| 9 / 150 | 3.2% to 11.0% | 1 in 31 to 1 in 9 |
| 18 / 300 | 3.8% to 9.3% | 1 in 26 to 1 in 11 |

Print the interval **in words** under any batch below 300 people contacted, and add the line that
does the work: "Do not rewrite the email on this."

## Comparing 2 batches

**Name a difference only when the 2 Wilson intervals do not overlap.** When they overlap, print both
in words, say the 2 are not distinguishable yet, and say roughly how many people each side would
need for the difference they are hoping for:

| The change they hope for | People per side | Weeks at 50 a week |
|---|---|---|
| 3% to 4.5% | 2,514 | 101 |
| 3% to 6% | 748 | 30 |
| 3% to 9% | 245 | 10 |
| 3% to 15% | 88 | 3.5 |

Read the table honestly: nothing about a subject line resolves here. The 3 things that move a rate
far enough to see at this volume are **who is on the list**, **what the first line says about them**,
and **whether something real is attached**. Instantly's own guide asks for at least 1,000 recipients
per variant and warns by name against calling a winner at 100 sends off 8 replies against 5.

**Every printed comparison carries this sentence:** this is a before-and-after, not an experiment.
Different week, different list, no control.

## The ladder, stopping at the first failure

| What the numbers say | The one thing to fix |
|---|---|
| `sent` under the plan | the block did not happen. Fix the block, nothing else |
| sent fine, replies near 0 | the people first, then the first line, in that order |
| replies but nothing books | the ask is too big |
| calls but no money | that is G6, not this lane |

One change a week, never 2, and most weeks a named hold instead (`holding until <number>, week N`).
Two changes and next Sunday cannot tell you which one moved. The change briefs the next Run; it never
edits a batch already sending.

## The file

`squad/outreach-read.md`. The scoreboard block at the top is rewritten every run; the batch sections
below it are appended and never rewritten.

```
# Outreach read

## GATE A · the send gate
| # | Condition | State | Read from |

## GATE B · the scale gate
| # | Condition | State | Read from |
Self-reported: conditions 1, 2 and 3. Condition 4 is written by this skill when the money lands.

---

## Batch 2026-09-07 · finished 2026-09-23
delivered 48 people (of 50 contacted) · replied 3
Wilson 95%: 1 in 50 to 1 in 6.
The stage that broke: <one line>
The Improve line: <one named change, or `holding until <number>, week N`, the founder's yes>

### THE WINNING CUT  (written only when money lands, verbatim, at that moment)
The cut rule: "<verbatim from the list header>"
The first line: "<verbatim from touch 1>"
```

## The order on Sunday

Measure first, then Improve, then the post. This read runs **before** `/bip sunday`, so the Improve
line is decided before the founder writes the week, and the Sunday post carries it. Hand it over as a
line, not a total: `/bip sunday` adds nothing up and takes only what the founder says. Hand them the
4-week plan's own sentence to paste, both halves filled in, `Put this in week N's Measure: <n>
people delivered, <n> replies / Improve: <the line>`, so the plan's Measure cell gets filled the
same Sunday its numbers were read. On an unfinished batch the Measure half is `held until batch
<date> is past day 9`.

Never write `squad/90-day-plan.md`, the 4-week plan's file. Its outputs are closed and belong to one
skill.
