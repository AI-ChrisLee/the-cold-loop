# The messages

Beat 2's cage and beat 3's files. Three touches, one voice, a footer on every one.

## The master email

- **Under 80 words.** A stranger reads the first line and the last line. Everything between them
  is on trial.
- **The first line is that row's own review count and town**, merged off the CSV as `{{Reviews}}`
  and `{{City}}`: "You have 318 Google reviews in Austin." It is the one fact the pull knows about
  that business and about nobody else on the list, and it says you looked. Not a compliment, not an
  introduction, not "I came across your website", and never a guess about what is wrong with them.
- **One ask, answerable yes or no, and the ask is 20 minutes on a call.** "Got 20 minutes this week
  for me to show you the fix on a call?" is a yes or a no. "Would you be open to a quick chat about
  your online presence?" is homework. The email's only job is the call; it never sells.
- **Twenty minutes needs a 20-minute door.** The cal.com link g6 made carries a 60-minute event
  type. Say once that the founder adds a 20-minute event type to that same link, and that the reply
  sends that one. A stranger who agreed to 20 minutes and lands on an hour books nothing.
- **No price.** The price belongs to the call, and the call belongs to `the-close`.
- **No attachment, no image, no tracking pixel.** Plain text, sent from a real mailbox.
- **The founder's own words.** A line the founder could not say out loud on a call does not go in.

## The 3 touches

| Touch | Day | What it carries |
|---|---|---|
| 1 | day 1 | their review count and town, the one ask |
| 2 | day 4 | something the first one did not say: a second thing seen, or what the fix looked like for someone else |
| 3 | day 9 | the shortest one. One line, one door, and the door closes politely |

In the campaign those 3 messages run as 3 steps about 2 days apart, so touch 3 lands a little
sooner than day 9 and the words do not change. The 9-day clock does not move.

**Never a bump.** "Just following up", "bumping this up your inbox", "did you see my last email" are
messages about the founder. Each touch earns its own send or it does not go.

Two lines on openers, and that is the whole of it: **do not open with yourself** ("I'm X and I help
Y do Z"), and **do not open with a question they have answered 40 times this month** ("Are you
happy with your current website?"). 58% of replies come from touch 1, so the first line is where the
work goes.

## The footer, on all 3, no exceptions

```
<Founder name> · <business name>
<postal address>
Not useful? Reply "stop" and I will not write again.
```

**This is a refusal.** CAN-SPAM has no volume threshold and, in the FTC's own words, "The law
makes no exception for business-to-business email." Every commercial message needs a valid
physical postal address and a clear opt-out that is easy to see, honoured within 10 business
days, and each message in violation runs up to $53,088. Say that once, in one line, the first
time the founder sees the footer.

No `postal address` row in the roots file: ask once. If the founder will not give one, write no
message and say why in one line. A mailbox service or a registered business address is fine; a
made-up address is worse than none.

**Both addresses are asked here, in one message.** The postal address, where the `postal address`
row is missing, since it goes under all 3. And the sending address: ask which mailbox these go out
of, once, here, and **the answer is a second free address on the
workspace the founder already owns**, never the address paying clients reply to and never the
mailbox they read every day. A founder with no clients today lands one off this lane in week 3, and
that client then writes back to whatever address the cold mail left from. Beat 3 will not build a
campaign on an address the founder has not named, so an unanswered row here stops the send. When
Gmail flags that mailbox, a second free Gmail replaces it in the row and its own warmup starts.

**The opt-out has to work.** An address that replies "stop" gets marked `stop` in
`squad/outreach-sent.md`, and beat 1's dedup drops it from every future list. That mark is the whole
mechanism, so never write a row without it.

## The batch's message file

`squad/cold-messages-<the batch's go date>.md`, written by beat 2 on the founder's word, for every
batch, whether or not a mail connector exists:

```
# Cold messages · batch <go date>

## Touch 1 · day 1
Subject: ...
<body with {{Reviews}} and {{City}} left as the merge fields, footer included>

## Touch 2 · day 4
## Touch 3 · day 9
```

The founder builds the campaign's 3 steps out of this file, pasted, while the mailbox warms. The
resume rule reads this file to know beat 2 finished, so a batch without one gets its messages
written again from the top rather than half-remembered.

## Nothing leaves by hand

No drafts, no mail connector. Every message on this lane leaves from the campaign, which is what
keeps the postal address and the opt-out on all 3 touches and threads touch 2 and touch 3 onto the
first. A day 4 that arrives as its own new message reads as a stranger writing twice, and that is
the message people mark as spam.

## The log

`squad/outreach-sent.md`, this skill's own memory. **One row per company per touch.** Touch 1's
rows are written at the go, `sent` empty; the weekly stamp fills `sent` and adds touches 2 and 3,
because nothing else on disk says which names entered on which day and the 9-day clock is counted
off those dates. The founder confirms once a week, never once a day:

```
# Outreach sent

batch · company · touch · sent · replied

2026-09-07 · Verdant Med Spa · 1 · 2026-09-08 · yes
2026-09-07 · Verdant Med Spa · 2 · 2026-09-11 ·
2026-09-07 · Lumen Aesthetics · 1 · 2026-09-08 ·
```

`batch` is the list's go date. `sent` stays empty until the founder says the week went out.
`replied` holds `yes`, or `stop` where the reply was stop, and nothing else. It is written at that
same weekly stamp, off the founder's own answer to one question, who replied this week: it is what
marks the opt-outs, and nothing else on disk carries it. A batch is **finished** 9 days after the
last name in it got touch 1, with all 3 touches sent on every row.
This file is the source of truth for which batch is finished, and it is the file every future pull
dedups against, on the company name. Once the campaign sends, Sunday's
stamp writes one row per week carrying the 2 totals the founder read off the campaign's own screen,
so the next Sunday has something to subtract from.

It holds names, not people. The day one of them replies or takes a call, the founder hands that to
`the-close`, and that skill writes the person's row in `squad/pipeline.md`. Nothing here writes
that file.
