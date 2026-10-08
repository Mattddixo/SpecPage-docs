# Activity log

**Activity** at the bottom of SpecPage settings lists changes to SpecPage's settings, connections, webhooks and approved hosts, newest first: when, who, and what.

- Connection changes list field names only (for example "token" changed), never values.
- Site settings record the new value (for example `tryItOutEnabled=true`), since those are switches and times.
- Host approvals and removals are recorded when they're made from SpecPage settings. Changes made directly in Atlassian Administration don't appear.

## How long entries are kept

**Keep activity log for** in the general settings: **Latest 200 changes** (the default), or 30, 90, 180 or 365 days. Older entries are deleted daily. The log never holds more than 200 changes.

## Download CSV

**Download CSV** saves the log for an audit or a ticket. Times are in UTC. Cells that start with characters a spreadsheet would treat as a formula are escaped, so the file is safe to open in Excel or Google Sheets.

## People who leave

The log stores each admin's Atlassian account ID; names are looked up when the log is shown. When someone's Atlassian account is closed, their ID is removed from the log and their entries show **Former user**. What happened, and when, stays.
