# Set up SpecPage

You need to be a Confluence administrator. Open **Confluence settings**, then **SpecPage settings** in the left menu.

Nothing needs setting up for page attachments or pasted specs: editors can use those straight after install. The settings below are for Git, URLs and Try it out.

## General

| Setting | What it does | Default |
| --- | --- | --- |
| **Allow specs from URLs** | Lets editors load a spec from an https URL on a host ticked for **Spec URLs** under **Approved hosts**. | Off |
| **Cache specs from Git and URLs for** | How long a fetched spec is reused before SpecPage asks the source again: off, or 5 minutes to 24 hours. | 10 minutes |
| **Keep activity log for** | **Latest 200 changes**, or 30, 90, 180 or 365 days. | Latest 200 |
| **Keep Try it out request log for** | Who sent which Try it out request: 7, 30 or 90 days, or **Off** (which deletes it). See [Activity and request logs](activity-log.md). | 30 days |

**Clear cache** makes every page fetch its spec again on the next view.


## Connections

A connection lets SpecPage read specs from one Git provider account. Choose **Add connection** and fill in:

- **Provider**: GitHub (including GitHub Enterprise Server), GitLab (cloud or self-managed), Bitbucket Cloud, Azure DevOps, or SwaggerHub (cloud or on-premise).
- **API URL** and **Web URL**: filled in for the cloud versions. Change them for GitHub Enterprise Server (`https://HOST/api/v3`), self-managed GitLab (`https://HOST/api/v4`) or SwaggerHub on-premise (`https://HOST/v1`).
- **Authentication** and **Access token**: a read-only token is enough. Choose **No token** for public repositories (or public SwaggerHub APIs).
- **Allowed repositories**: one per line. `owner/*` allows every repository for that owner. Editors can only use repositories on this list.
- **Limit to spaces (optional)**: comma-separated space keys. Empty means all spaces.
- **Default branch (optional)**: used when an editor leaves the branch empty.

Tokens are kept in Forge's encrypted secret storage and never sent to the browser. Changing a connection's provider or API address asks for the token again, so a saved token is never sent to a different host.

**Test** loads a spec through the connection (enter a repository, branch and file path), which checks the token and the host in one go. When you save a connection, SpecPage asks Atlassian to approve the connection's host; Atlassian shows its own confirmation.

Recommended token permissions:

| Provider | Token |
| --- | --- |
| GitHub | Fine-grained token with **Contents: Read** on the allowed repositories |
| GitLab | Project or group access token with **read_repository** (or **read_api**) |
| Bitbucket Cloud | Repository, project or workspace access token with **Repositories: Read** (Bearer), or an Atlassian API token with your account email (Basic) |
| Azure DevOps | Personal access token with **Code: Read** |
| SwaggerHub | Your SwaggerHub API key |

## Approved hosts

SpecPage can't contact anything outside your Atlassian site until you approve it. **Approved hosts** lists every host, with a tick for what each one is used for:

- **Spec URLs**: editors may load specs (and absolute `$ref`s) from it.
- **Try it out**: readers may send test requests to it. If an API uses OAuth, add the identity provider's token host too.
- **Used by: Git connection**: Git and SwaggerHub API addresses, added for you when you save a connection.

**Suggested by your API docs** lists hosts that macros on your pages need and that aren't approved for that yet: the servers their specs point Try it out at, and hosts editors tried to load a spec URL from. Each shows how many macros want it, with a button to approve it for that use. It shows counts only, never page names. It's the easiest way to set things up: add some macros, then come back here.

To add a host yourself, type it (`api.example.com`, or a wildcard like `*.example.com`), tick what it's for, and click **Approve**. Atlassian asks you to confirm once. After that, ticking or unticking a use takes effect straight away with no further approval, for example when an API serves its own spec and you want it for both. Unticking a host's last use, or clicking **Remove**, revokes its approval. You can also review approvals in **Atlassian Administration → Apps → Connected apps**.

## Try it out

**Allow "Try it out"**, at the top of **Approved hosts**, turns Try it out on for the site (it's off after install, and saves as soon as you switch it). Then it works on its own: any page whose spec points at a host ticked for **Try it out** gets it, for signed-in users. Guests and anonymous visitors never can. Page editors can hide it on their page.

Each Try it out host has a **Try it out can send** choice:

- **Read requests only** (the default for every new host): GET, HEAD and OPTIONS. Test requests can't change data.
- **Every method**: POST, PUT, PATCH and DELETE too. Use it for sandbox or test APIs.

OAuth token requests from the **Authorize** button work either way. Page editors can keep their own page to read requests, but can't allow more than the host does.

Try it out requests are sent from Atlassian's servers, not the reader's computer. Don't approve an API that trusts Atlassian's IP addresses unless every signed-in user may call it. See [Try it out](try-it-out.md) for the full set of safeguards.

## How the lists are kept

SpecPage keeps a copy of the lists so it can check each request against the right one. If you change hosts in Atlassian Administration, open SpecPage settings once so the copy catches up.

## Next steps

- [Turn on webhooks](webhooks.md) so pushes refresh docs straight away.
- Tell editors to type `/spec` on a page and insert **OpenAPI / Swagger docs (SpecPage)**.
