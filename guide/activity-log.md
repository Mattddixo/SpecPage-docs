# Activity and request logs

SpecPage settings has two logs: **Activity**, for changes admins make, and **Try it out requests**, for requests users send to APIs.

## Activity

**Activity** at the bottom of SpecPage settings lists changes to SpecPage's settings, connections, webhooks and approved hosts, newest first: when, who, and what.

- Connection changes list field names only (for example "token" changed), never values.
- Site settings record the new value (for example `tryItOutEnabled=true`), since those are switches and times.
- Host approvals and removals are recorded when they're made from SpecPage settings. Changes made directly in Atlassian Administration don't appear.

### How long entries are kept

**Keep activity log for** in the general settings: **Latest 200 changes** (the default), or 30, 90, 180 or 365 days. Older entries are deleted daily. The log never holds more than 200 changes.

### Download CSV

**Download CSV** saves the log for an audit or a ticket. Times are in UTC. Cells that start with characters a spreadsheet would treat as a formula are escaped, so the file is safe to open in Excel or Google Sheets.

### People who leave

The log stores each admin's Atlassian account ID; names are looked up when the log is shown. When someone's Atlassian account is closed, their ID is removed from the log and their entries show **Former user**. What happened, and when, stays.

## Try it out requests

**Try it out requests** lists requests users sent to APIs through Try it out, one day at a time, newest first: when, who, the method, host and path, and the API's response status (or **No response** if it timed out or couldn't connect). Use it to answer "who called this API from Confluence?", or to follow up if an API owner reports unexpected traffic.

- It records only requests SpecPage actually sent. Requests SpecPage refused (host not approved, read-only, rate limit) aren't listed.
- It never records query strings (where API keys often go), headers, request bodies, responses or credentials.
- Pick a day, filter by person, host or path, and **Download CSV** for that day.
- At most 2,000 requests a day are recorded one by one. Past that, SpecPage counts the extra requests and says how many there were.

**Keep Try it out request log for** in the general settings: 7, 30 (the default) or 90 days, or **Off**. Turning it off deletes the log straight away. Like the activity log, it stores account IDs, not names, and removes the IDs of closed accounts.
