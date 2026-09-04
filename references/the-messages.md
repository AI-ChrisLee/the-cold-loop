# The messages

Beat 2's cage and beat 3's files. Three touches, one voice, a footer on every one.

## The master email

- **Under 125 words.** A stranger reads the first line and the last line. Everything between them
  is on trial.
- **The first line is that row's broken thing**, in their noun and their town. Not a compliment,
  not an introduction, not "I came across your website."
- **One ask, answerable yes or no.** "Want me to send a 2-minute video showing the fix?" is a yes or
  a no. "Would you be open to a quick chat about your online presence?" is homework.
- **No price.** The price belongs to the call, and the call belongs to `the-close`.
- **No attachment, no image, no tracking pixel.** Plain text, sent from a real mailbox.
- **The founder's own words.** A line the founder could not say out loud on a call does not go in.

## The 3 touches

| Touch | Day | What it carries |
|---|---|---|
| 1 | day 1 | the broken thing, the one ask |
| 2 | day 4 | something the first one did not say: a second thing seen, or what the fix looked like for someone else |
| 3 | day 9 | the shortest one. One line, one door, and the door closes politely |

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

**This is a refusal, not a preference.** CAN-SPAM has no volume threshold and, in the FTC's own
words, "The law makes no exception for business-to-business email." Every commercial message needs a
valid physical postal address and a clear, conspicuous opt-out, honoured within 10 business days,
and each message in violation runs up to $53,088. Say that once, in one line, the first time the
founder sees the footer.

No `postal address` row in the roots file: ask once. If the founder will not give one, write no
message and say why in one line. A mailbox service or a registered business address is fine; a
made-up address is worse than none.

**The other address, asked in the same message.** No `sending address` row in the roots file: ask
which mailbox these go out of, once, here. It is never the address paying clients reply to. No
clients yet and the mailbox they already use is the answer; clients already and it is a second free
alias or mailbox on the workspace they own. Beat 3 will not draft from an address the founder has
not named, so an unanswered row here stops the morning later.

**The opt-out has to work.** An address that replies "stop" gets marked `stop` in
`squad/outreach-sent.md`, and beat 1's dedup drops it from every future list. That mark is the whole
mechanism, so never write a row without it.

## The daily file

`squad/cold-batch-<date>.md`, written only where the founder's mailbox is not reachable through
their own mail connector:

```
# <date> · 30 messages, 3 cohorts

## Touch 1 · 10 new names
### <Company> · <email>
Subject: ...
<body, footer included>

## Touch 2 · the cohort from <date, 4 days back>
## Touch 3 · the cohort from <date, 9 days back>
```

Where the mail connector exists, the same content goes in as **drafts**, each follow-up threaded
onto the original message. A draft is not a send. The founder presses send.

## The log

`squad/outreach-sent.md`, stamped once a week, never once a day:

```
# Outreach sent

| Batch | Company | Email | Touch 1 | Touch 2 | Touch 3 | Replied | Note |
|---|---|---|---|---|---|---|---|
| 2026-09-07 | ... | ... | 2026-09-08 | 2026-09-11 | 2026-09-16 | 2026-09-12 | |
```

`Batch` is the list's cut date. A batch is **finished** when the last name is past day 9. `Note`
carries `stop` when someone opts out, and nothing else. This file is the source of truth for the
read and for both gates, and it is the file every future pull dedups against.
