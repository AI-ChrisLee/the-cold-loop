# The Sunday read

1 section appended to `squad/outreach-read.md`: every batch counted, 1 change line. The 4-week plan reads it.

## Nothing sent yet

`get_campaign` reads Draft, or the `cold campaign` row reads `batches none`, or every filter returns 0 leads:
print this, write no section, and stop.

```
Nothing has sent yet, so there is nothing to read. Press Launch the first time "Is my mailbox ready?" says Ready.
```

## The counts, in people

Off `list_leads` on the campaign's id, 1 filter at a time, 100 a page, every page. Each lead is counted
under the `Batch` in its custom variables.

| Number | Filter |
|---|---|
| Contacted | `FILTER_VAL_CONTACTED` |
| Replied | `FILTER_VAL_REPLIED` |
| Bounced | `FILTER_VAL_BOUNCED` |
| Still waiting | `FILTER_VAL_NOT_CONTACTED`, then `FILTER_VAL_ACTIVE`, 2 calls, added together |

People, never messages. 50 people at 3 emails is up to 150 messages, and a rate on messages makes every
number look 3 times smaller than it is. No opens: open tracking is off.

A batch is **finished** when none of its leads is still waiting, about 9 days after its last day 1 email.
Before that it prints as `still sending` and never moves the change line.

Bounce = Bounced ÷ Contacted, per batch, to 1 decimal.

## The yeses and the calls, typed

This agent never reads a reply, so it cannot see who said yes or who got on a call. 1 message, 1 line a batch
with at least 1 reply:

```
Batch <date>: <n> replied. How many said yes, and how many calls happened so far? "Same" keeps last week's numbers.
```

The founder reads them off the Instantly inbox and the calendar. A batch with no reply is 0 and 0, not asked.
A batch not asked this week carries last week's numbers.

## The change line, first match wins

Rules 2 and 3 count only the 2 newest finished batches added on or after the `emails` date on the
`cold campaign` row, the batches that got today's emails. Fewer than 2 such batches: rules 2 and 3 wait.

| # | When | The line |
|---|---|---|
| 1 | a batch that finished since the last section (there it read `still sending`, or was not there) bounced over 2% | `Hold: no go this week. Batch <date> bounced <n>%.` |
| 2 | those 2 batches have 0 replies between them | `Change: a new problem line in day 1.` |
| 3 | those 2 batches have replies and 0 yeses | `Change: a smaller free thing in day 1.` |
| 4 | anything else | `Same again. Nothing changes this week.` |

Yeses with no calls are rule 4: the gap is in the demo and the message after it, not in this campaign.

1 change a week, nothing else moves. With 2 changes, next Sunday cannot tell which one moved the number.

A `Hold:` stops "Build my outreach list." for 7 days. A `Change:` goes into the next "Build my cold campaign."

## The file

`squad/outreach-read.md`. The title once, then 1 section a Sunday, appended, never rewritten:

```
# Outreach read

## <YYYY-MM-DD>

| Batch | Contacted | Replied | Bounced | Yes | Calls | State |
|---|---|---|---|---|---|---|
| <date> | <n> | <n> | <n> (<n>%) | <n> | <n> | finished |
| <date> | <n> | <n> | <n> (<n>%) | <n> | <n> | still sending |

In people, not messages.

<the change line>
```

Print the same table and the change line in chat, then the path.
