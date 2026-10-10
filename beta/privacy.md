# SpecPage privacy notice

Last updated: 8 October 2026

SpecPage is a Confluence Cloud app built on Atlassian Forge. This notice explains what it stores, where data goes, and how long it's kept. It applies to the beta and will be updated before the app is listed on the Atlassian Marketplace.

## The short version

- SpecPage runs entirely on Atlassian's Forge platform. It has no servers of its own, and **nothing is sent to the developer**: no analytics, no tracking, no copies of your specs or pages.
- The only personal data it stores is Atlassian account IDs: of admins who change its settings, for the activity log, and of users who send Try it out requests, for the request log (which admins can turn off).
- Data leaves your Atlassian site only for hosts your Confluence admin approves (your Git provider, spec URLs, and APIs for Try it out).

## What's stored, and where

Everything below is kept in your site's Forge app storage, which Atlassian hosts and encrypts. It stays with your installation.

| What | Why | How long |
| --- | --- | --- |
| App settings (on/off switches, cache time, retention) | To run the app | Until changed or the app is removed |
| Git connections: name, provider, API address, allowed repositories and spaces | To read specs from Git | Until the admin deletes the connection |
| Git access tokens and webhook secrets | To read private repositories and check webhooks | Kept in Forge's encrypted secret storage, never sent to the browser; deleted with the connection |
| Copies of specs loaded from Git or URLs | Faster pages | Up to 24 hours, as set by the admin (or not at all) |
| One record per SpecPage macro: title, version, number of endpoints, source label, page and space IDs, and the hosts it needs approved (its Try it out servers, or the host a spec URL loads from) | The API list for each space, the site-wide catalog, and host suggestions in SpecPage settings | Removed when the macro is removed from its page, or after 90 days unviewed if the page is hidden from everyone |
| Spec hosts a saved macro was refused because they aren't approved, or that an editor suggested: the host name and the macro's page and macro IDs. Suggestions an admin dismissed: the host name | Host suggestions in SpecPage settings | 30 days; dismissed suggestions until the app is uninstalled |
| Activity log: time, admin's Atlassian account ID, what changed (for site settings the new value, such as on or off; for Git connections field names only; never tokens) | So admins can see who changed what | The latest 200 changes, or 30 to 365 days if the admin sets a limit |
| Try it out request log: time, the user's Atlassian account ID, method, host, path and the API's response status. Never query strings, headers, request bodies, responses or credentials | So admins can see who sent which request, and misuse can be traced | 30 days by default; admins can choose 7 or 90 days, or turn it off, which deletes it. At most 2,000 requests a day are kept one by one |
| Rate-limit counters for Try it out | To stop abuse | Keyed by a salted hash of the account ID, never the ID itself; expire after 10 minutes |

Specs attached to pages stay as Confluence attachments, under Confluence's own permissions. Signed-in users read them as themselves; for guests, the app reads them from the page they're already viewing.

## Account IDs and Atlassian's privacy reporting

The activity log and the Try it out request log store Atlassian account IDs, which are personal data. Names are looked up from Atlassian when a log is shown and never saved. As Atlassian requires, the app reports these IDs to Atlassian's personal data reporting API about once a week. When an account is closed, its ID is removed from both logs, and its entries show "Former user".

## Data sent outside your Atlassian site

Only to hosts your Confluence admin has approved, and only for these purposes:

- **Git providers** (GitHub, GitLab, Bitbucket, Azure DevOps, SwaggerHub): to read spec files, using the connection's token.
- **Spec URLs**: to read specs, if the admin has turned URL sources on.
- **Try it out**: when a signed-in reader sends a test request, it goes through the app to the API they're testing, along with any credentials they typed (for example an API key or access token). Those credentials stay in the page's memory and are never saved by the app.

Admins approve each host in the SpecPage settings, Atlassian asks them to confirm, and they can revoke hosts at any time in Atlassian Administration.

## Logs

The app writes short operational messages to Atlassian's Forge logs, which the developer can read for troubleshooting: counts, status codes, how long a request took, the reference shown with an error message (such as `SP-7K3QX9`), and error text that can include a host name. Logs never include tokens, credentials, spec content or account IDs. Atlassian keeps Forge logs for a limited time under its own policies.

## Uninstalling

Before the app is uninstalled, it removes every account ID from its activity log and deletes the Try it out request log. Atlassian keeps an app's storage for 28 days after uninstalling (so it can be restored on request) and then deletes it.

## Your rights

For access to or deletion of data in your site's SpecPage storage, your Confluence admin can delete connections and change retention settings, or contact us at the address below. Atlassian's own handling of your account is covered by Atlassian's privacy policy.

## Contact

support@matt-lab.ca
