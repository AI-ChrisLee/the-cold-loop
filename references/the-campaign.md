# The campaign

Beat 3's Instantly detail, and beat 5's moves. One mailbox, one campaign, 30 a day, and the
founder's hand on one word a week.

## The one honest sentence

**Once the founder launches it, the send runs overnight on Instantly's servers, from their own
mailbox, on a list they approved.** The pull still needs a person to say go, and the read still
takes a minute on Sunday. The send is the leg that runs while they sleep.

## The gate, in one line

The warmup's own health reading, read on Sunday. A new sending address cannot open a campaign; it
gets flagged. The founder turns warmup on in Instantly on day one, the squad builds the campaign
the same sitting through the founder's connector and leaves it **paused**, and every Sunday
"Is my mailbox ready?" reads the health through that connector. The first Monday it reads ready,
the founder presses Launch. One reading, one day a week, and nothing leaves by hand in the meantime.

## The account, by the founder's hand

Day one, in this order, on Instantly's own screens: make the account, **Email Accounts > Add new**
and connect a second free address on the workspace the founder already owns, open that account's
settings and set the daily campaign limit to 30, turn warmup on and leave it. The health score is read on Sundays and nowhere else.

**That is the only step in the browser, because connecting a mailbox is a sign-in to Google or
Microsoft.** The campaign, the leads and the Sunday reads run through the founder's own Instantly
connector. Check it off the live tool list every run, and read that list rather than a tool name
written here. Not connected: print the click path and wait.

> Claude app, Settings, Connectors, Add custom connector, name it Instantly,
> `https://mcp.instantly.ai/mcp`, then sign in with the Instantly account.

The free trial holds 250 contacts, so the fifth batch fills it.

## The settings

| Setting | Value | Why |
|---|---|---|
| Stop sending on reply | on | a reply ends the sequence for that person. Nobody gets touch 2 after answering |
| Open tracking | **off** | the pixel costs deliverability, and it is why this lane has no open rate |
| Provider matching | **on** | Google mailboxes into Google inboxes lands better |
| Daily limit | 30, the same number already set on the mailbox | one mailbox sending 30 a day reads as a person |
| The steps | 3, waiting 3 days then 5 so they land on day 4 and day 9, the subject left empty on steps 2 and 3 | an empty subject threads them onto the first, so it reads as one conversation |
| The schedule | the founder's own hours, Monday to Friday | mail arriving at 3am from a one-person business reads as what it is |
| The footer | on every step | the postal address and the opt-out do not become optional here |

Run the spam checker on step 1 before launching and take its swaps.

**Say this out loud, because it is the most useful safety fact in the lane:** Instantly's own High
Bounce Auto-Pause is on by default at 5%, but its help article says a campaign must send at least 200
emails before that check runs. A founder sending 30 a day has no automatic brake for the first
week of sending. **You are the brake**: read the bounce off that campaign every Sunday through
the connector, and stop the next import over 2%.

## What it costs a month

| Item | Cost |
|---|---|
| Instantly, once the free trial's 250 contacts run out | the workspace's own billing screen names the price. Read it there before subscribing; the trial itself costs nothing, and the fifth batch imported is what fills it |
| A second sending address on the workspace the founder already owns, beat 5's move 1 | free |
| Apify, a weekly 120-place pull | about $2 a month, inside the free $5 credit |

Print this before the founder subscribes to anything, not after. A member on a small budget deserves
the number in front of the step.

## The build, in 2 calls, and the button the founder presses

- **Create the campaign**, named for this list, carrying the whole sequence at once: step 1 at
  delay 0, step 2 at delay 3, step 3 at delay 5, the subject empty on steps 2 and 3, the footer on
  every step, and the settings above.
- **Add the 50 leads to that campaign**, read straight off `squad/cold-list.csv`, with
  `skip_if_in_workspace` on so nobody already sitting in another campaign in that workspace gets
  it twice. `references/the-list.md` carries the CSV's 8 columns and the 2 the day 1 step merges.

**Never a Lead List.** Instantly gates Lead Lists to Hyper Growth and above, so a member on the
trial or on Growth cannot open one, and leads sitting in a list are not in a campaign and send
nothing. The 50 go into the campaign, every time.

**The campaign is created as a draft and never activated here.** `activate_campaign` is a refusal
at any size and on any wording.

The steps come from `squad/cold-messages-<that batch's go date>.md`, the footer on every one. No
message file for that batch means beat 2 never finished, and the touches get written there rather
than recalled here.

**The bounce number is read off the campaign, through the connector, every Sunday.** Over 2%
nothing new goes in until it comes down. Sustained bounce over 2% pushes every message from that
domain toward spam. Before the first import nothing has sent yet, so the warmup reading is the
gate instead.

**Launch is the founder's, on the founder's hand.** Print what was built, the 50 names in, the 3
steps and their delays, the daily limit, the window, the sending address and the word paused, then
stop. From the second week on the campaign is already running, the week's 50 are added to it the
same way, and there is nothing to launch.

## The second mailbox, beat 5's move 1 only

The signal opens it: one batch whose first line booked 2 or more calls, or one paying client from
this list, read off `squad/pipeline.md`. Never before.

- **A second free address on the workspace the founder already owns.** It goes into warmup the day
  it is made and onto the campaign about 2 weeks later, when its own health reads good, the same
  gate the first mailbox passed.
- The daily limit rises by the new mailbox's own number, never the first mailbox's, and the founder
  raises it in Instantly.
- **Do not send cold from the address paying clients reply to.** Both mailboxes stay addresses
  clients do not write to.
- A second domain waits until both mailboxes are full: 14 days sending nothing while SPF, DKIM and
  DMARC settle and the domain ages, then a ramp over about 6 weeks. Two free addresses carry this
  lane long past where a member is today.

## What is never built

An Apify schedule: the Apify MCP publishes no schedule tool, and a weekly pull takes minutes by hand
in the same session where the list is approved. A scheduled task for the send: it is skipped
whenever the laptop sleeps and fires when the lid opens, which is the moment the founder could type
the command. An auto-reply agent: every reply is answered by the founder, in their own words, with
`the-close`'s draft in front of them, because a stranger wrote back to a person.

**The standing rule, quoted wherever a schedule comes up:** a routine that only reads, only drafts or
only reduces spend may be scheduled. A routine that sends, spends more or publishes never runs
unattended.

## The file

`squad/outreach-routine.md`, written by beat 5:

```
# Outreach routine
opened <date> on <the signal: 2 calls off batch <go date>'s first line | a paying client from batch <go date>>

Campaign: <name> · launched <date the founder pressed Launch>
Mailboxes: <address> at <n> a day · <second address, or none yet> at <n> a day
Move 1, the daily number: <date, or not yet> · <what was added>
Move 2, the second town: <date, or not yet> · <town>
Cost a month: <total, itemised>

The week: Monday the pull and the rank, you say go, the campaign keeps sending, Sunday the read.
Replies: by your hand, always.
```
