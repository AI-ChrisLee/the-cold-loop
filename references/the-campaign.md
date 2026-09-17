# The campaign · Instantly

1 output: 1 campaign, built through the founder's Instantly connector, left a Draft. The founder presses Launch.

## The mailbox, printed once

The first run prints this, word for word, and nothing else (the base line comes above it on a fresh run):

```
Before anything sends, your mailbox. You do this once:
1. Buy a sending domain close to your business name. Never send cold email from the domain your clients write to.
2. Add 1 Google Workspace seat on it (Business Starter, $8.40 a month on the Flexible plan) and make 1 address. Google's setup has you add 2 records of its own, 1 to verify the domain and 1 MX record to turn on Gmail. Add both the way it shows you.
3. At your domain registrar, add these 3 records, then forward the domain to your real website:
   SPF: a TXT record on @, v=spf1 include:_spf.google.com ~all
   DMARC: a TXT record on _dmarc, v=DMARC1; p=none
   DKIM: Google gives you this key 24 to 72 hours after Gmail turns on (Google Admin, Apps, Google Workspace, Gmail, Authenticate email). Add it at your registrar, then click Start authentication in Google Admin.
4. In Instantly: Email Accounts, Add new, Google, and copy the Client ID. In Google Admin: Security, API controls, Manage app access, Configure new app, paste the Client ID, pick Instantly, set it Trusted. Back in Instantly, sign in with that address, set the daily limit to 30, and turn warmup on. Instantly's free trial runs 14 days, then pauses warmup and deletes the trial account, and I can only reach Instantly on Growth ($47 a month), where Instantly puts its API. Buy Growth before you connect Instantly to Claude.
5. Tell me the sending address, or say not yet. I check your records and print pass or fail.
```

## The records

For the domain after the @ of the sending address. macOS and Linux use `dig +short TXT <name>` (`MX` for
the MX row); Windows uses `nslookup -type=TXT <name>` (`-type=MX`).

First the NS record: `dig +short NS <domain>`, Windows `nslookup -type=NS <domain>`. No nameserver comes
back: the domain is not registered, and no other record is looked up.

| Record | Name looked up | Pass |
|---|---|---|
| MX | `<domain>` | a value containing `google.com` |
| SPF | `<domain>` | a TXT value starting `v=spf1` |
| DKIM | `google._domainkey.<domain>` | a TXT value starting `v=DKIM1` |
| DMARC | `_dmarc.<domain>` | a TXT value starting `v=DMARC1` |

Print 4 lines, `MX: pass`, `SPF: pass`, `DKIM: fail`, `DMARC: pass`. A DKIM fail adds 1 line: "DKIM comes
24 to 72 hours after Gmail turns on. Add it then, click Start authentication, and tell me the address again."
Any other fail adds 1 line: "Add that record at your registrar. A new record can take a few hours to show.
Then tell me the address again."

## The connector

Loaded when tools ending in `list_accounts`, `create_campaign`, `update_campaign`,
`add_leads_to_campaign_or_list_bulk`, `get_campaign` and `list_leads` are on the list. Read the live list
every run. Missing: print this, word for word, and stop.

```
Your campaign needs the Instantly connector, and it isn't connected yet. It runs on Instantly's API, which comes with Growth ($47 a month). 3 steps:
1. In Instantly: Settings, Integrations, API Keys, Create API Key, scope All. Copy it.
2. In Claude, click Customize, then Connectors, then +, then Add custom connector.
3. Name it Instantly. URL: https://mcp.instantly.ai/mcp/<your API key>. Click Add. That URL works like a password: never share it.
Then quit Claude Code, open it again in this folder, and say "<the line you said>" again.
```

Never print the key or the URL with the key in it.

## The build: `create_campaign`

| Field | Value |
|---|---|
| `name` | `Cold · <WHO line 1> · <today>` |
| `sequences` | 1 sequence, 3 steps, `type` "email", 1 variant each, off `references/the-messages.md` |
| step delays | step 1 `delay` 3, step 2 `delay` 5, step 3 `delay` 0 |
| subjects | day 1's subject on step 1, `""` on steps 2 and 3 |
| `body` | HTML, 1 `<div>` a line, `<div><br /></div>` for a blank line |
| `email_list` | [the sending address] |
| `daily_limit` | 30 |
| `stop_on_reply` | true |
| `text_only` | true |
| `open_tracking` | false |
| `link_tracking` | false |
| `campaign_schedule` | Monday to Friday, 09:00 to 17:00, in the list town's time zone |

**The delays.** In Instantly the delay on a step is the wait before the NEXT step. 3, 5, 0 lands the emails on
about day 1, day 4 and day 9; a wait that ends on a weekend sends on Monday. The connector's own field note reads "before this step"; it is wrong, and 0, 3, 5 sends
day 4's email on day 1.

The schedule, in this shape:

```
{"schedules":[{"name":"Weekdays","timing":{"from":"09:00","to":"17:00"},"days":{"1":true,"2":true,"3":true,"4":true,"5":true},"timezone":"America/Chicago"}]}
```

`timezone` is the list town's, as a name like `America/Chicago`. Refused: the nearest one Instantly accepts.

A change from the Sunday read goes in through `update_campaign` on the same `id`, with all 3 steps and the
same delays.

## The leads: `add_leads_to_campaign_or_list_bulk`

- `campaign_id` the campaign's id, `skip_if_in_workspace` true. Never `list_id`: leads in a list send nothing.
- 1 lead a row: `email`, `company_name`, `website`, `phone`, and `custom_variables`
  `{"Reviews": <Reviews>, "City": <City>, "Batch": <Batch>}`.
- `Batch` is what lets Sunday's read count each batch in people.

## The read-back

`get_campaign`, then 1 screen, off what it returns and off the add call's reply for the 2 lead counts, never
off what was sent:

```
Campaign: <name>
Status: <Draft | Active | Paused | Completed>
Sender: <email_list off get_campaign, or (none attached) when the reply carries none>
Emails: 3, with a wait of 3 days, then 5 days
30 a day · stop on reply · text only
Monday to Friday, 9 to 5, <time zone>
Leads added: <n>, skipped: <n> (already in your workspace)
Built, not launched.
```

Status 0 is Draft, 1 Active, 2 Paused, 3 Completed. The last line prints only on a Draft; an Active campaign
ends on "Added to your running campaign."

The first build adds 2 lines:

```
You press Launch in Instantly yourself, the first time "Is my mailbox ready?" says Ready.
Instantly's own bounce auto-pause only starts after a campaign has sent 200 emails. Until then, "Read my batch." on Sunday is your brake.
```

## "Is my mailbox ready?"

Off `list_accounts` for the sending address. Ready = 14 or more whole days since `timestamp_warmup_start`,
and `stat_warmup_score` above 90. Both, because Instantly's own rule is both: a new mailbox can read 100 on
day 1. `warmup_status` not 1 means warmup is off: Not yet, and "Turn warmup on for <address> in Instantly."

```
Not yet.
Warmup: <n> days (needs 14). Score: <n> (needs above 90).
```

`1 day` when the count is 1.

```
Ready.
Warmup: <n> days. Score: <n>.
```

Ready, and the campaign still reads Draft, adds the Launch line and the yes:

```
Press Launch on <campaign name> in Instantly yourself.
When a reply says yes:
1. /the-demo <Company name>, <Website> off that row of squad/cold-list.csv, or his Instagram link when you sell content.
2. Record a Loom of the demo, under 2 minutes, your face on, and give /the-demo the link.
3. /the-close. THE MESSAGE is rewritten for him, with the Loom and your booking link.
4. Fill anything still in square brackets, like his first name, off his reply. Then send THE MESSAGE yourself, as your reply in that same Instantly thread.
The call runs off squad/sales.md.
```

## What never happens here

- `activate_campaign` and `campaigns_bulk_activate` are refused, at any size and on any wording.
- No write to the mailbox: not its warmup, not its daily limit, not its status.
- No lead is deleted. A lead who said stop stays in the workspace, and that keeps them out of every later batch.
- The only writes to Instantly are `create_campaign`, `update_campaign` and `add_leads_to_campaign_or_list_bulk`.
