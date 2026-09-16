# The numbers

Beat 4's detail, and the job is coaching, not statistics. Three numbers off a finished batch, the
rung that broke, one thing to do this week.

## The 3 numbers, and the unit

**People contacted, replies, calls booked.** All 3 in **people**, never in messages sent. 50 people
at 3 touches is up to 150 messages, so the 2 units are off by 3x, and a reply rate computed on
messages is a third of the truth. Every table header says which unit it is in.

| Number | Where it comes from |
|---|---|
| people contacted | step 1's sent count on the campaign, read through the founder's Instantly connector as it reports it |
| replies | the campaign's reply count, read the same way |
| calls booked | rows in `squad/pipeline.md` whose source names this list and whose `next touch` or `what went out last` field carries the word call |

One source each, and no second source. Ask for the 2 campaign numbers in one message, count the
calls yourself, and ask for nothing else. No opens: open tracking is off in this lane.

**Calls booked come off the pipeline and nowhere else.** Instantly does not know a call happened. A
call the pipeline does not hold is a call `the-close` never logged, and the fix is to log it, not to
count it from memory.

The third field of a pipeline row is `the-close`'s bucket. It holds one of 7 words, none of them a
call, so it is never read for this number.

## The 9-day clock

A batch's number does not exist until 9 days after the last name in it got its first email. Before
that, say the batch is not finished, print the week's raw counts labeled as counts and not as a
rate, and stop. The clock starts at Launch, so it happens on the Sundays before the first batch
clears day 9, and on any Sunday the campaign ran out of names.

## The subtraction

**One campaign carries every batch,** so that screen reports campaign totals and never this batch's.
By the fourth batch imported, step 1's sent count reads 200 for a batch of 50.

- On the campaign's **first** batch nothing else has sent, so the screen's 2 totals are that batch's
  2 totals and nothing is subtracted.
- From the second batch on, subtract the 2 totals carried in the previous section of
  `squad/outreach-read.md`. The difference is this batch. Every section carries the totals it read,
  which is what makes the next one possible.
- **Never divide a campaign total by 3 to get people.** Stop sending on reply is on, so a person who
  replied got 1 touch or 2, and the divisor is never actually 3.

## The ladder, stopping at the first failure

| What the numbers say | The one thing to fix |
|---|---|
| contacted under the plan | the block did not happen. Fix the block, nothing else |
| contacted fine, replies near 0 | the people first, then the first line, in that order |
| replies land, no calls | the ask is too big; ask for 20 minutes and nothing else |
| calls but no money | that is G6, not this lane |

The rung names the change. Print it as one line, `Do this week: <the change>`, or a named hold
(`holding until <number>, week N`). Most weeks it is a hold, and that is the plan working.

**One change a week, and nothing else moves.** Two changes and next Sunday cannot tell which one
moved. The change briefs the next Run; it never edits a batch already sending.

What moves a number far enough to see at this size is **who is on the list**, **what the first line
says about them**, and **whether the ask is a call**. Nothing about a subject line resolves here.

## The winner line

The day `squad/pipeline.md` shows money from a row whose source names this list, write that batch's
touch 1 first line, word for word, under `THE WINNER` in `squad/outreach-read.md`. At that moment,
never recalled later, on a finished batch or not. Nothing for the founder to do. Beat 5's move 2 copies that line.

**Only money that is new this Sunday.** A money row already in the pipeline before the last section
in `squad/outreach-read.md` was written is old news, and nothing is written for it.

## The file

`squad/outreach-read.md`. The winner block at the top is written the day money shows; the batch
sections below it are appended and never rewritten.

```
# Outreach read

## THE WINNER  (written the day money lands, word for word)
Batch <go date> · the first line: "<touch 1's first line>"

---

## Batch 2026-08-24 · finished 2026-09-06

| People contacted | Replies | Calls booked |
|---|---|---|
| 50 | 4 | 0 |

Campaign totals as they read: <n> sent · <n> replies

**The rung that broke.** Replies land, no calls. The ask is too big.

**Do this week.** Put the 20 minutes in the first line, not the last.
```

## The order on Sunday

Measure first, then Improve, then the post. This read runs **before** `/bip sunday`, so the Improve
line is decided before the founder writes the week, and the Sunday post carries it. Hand it over as a
line, not a total: `/bip sunday` adds nothing up and takes only what the founder says. Hand them the
4-week plan's own sentence to paste, both halves filled in and **2 numbers, not 3**: `Put this in
week N's Measure: <n> people contacted, <n> replies / Improve: <the line>`, so the plan's Measure
line gets filled the same Sunday its numbers were read. Calls booked is the third number of the
read and it stays out of that line; the plan takes 2 numbers a lane, and OUTREACH's 2 are people
contacted and replies. On an unfinished batch the Measure half is `held until 9 days after batch
<date>'s last name went out`.

Never write `squad/4-week-plan.md`, the 4-week plan's file. Its outputs are closed and belong to one
agent.
