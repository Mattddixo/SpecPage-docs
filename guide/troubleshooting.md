# Troubleshooting

Messages are shown on the page with a hint. Editors see the full detail; readers see a plain "not available" for problems only an admin can fix.

| Message | What to do |
| --- | --- |
| SpecPage isn't allowed to contact *host* yet. | An admin needs to approve the host in SpecPage settings (Atlassian asks to confirm). |
| SpecPage doesn't have the approved host lists yet. | An admin needs to open SpecPage settings once. This also fixes things after hosts were changed in Atlassian Administration. |
| *host* isn't on SpecPage's list of approved spec hosts / Try it out hosts. | The host is approved, but for a different purpose. Add it to the right list. |
| The repository "*repo*" isn't allowed for the connection "*name*". | Ask an admin to add it to the connection's **Allowed repositories**. |
| The Git connection "*name*" isn't enabled for this space. | The connection is limited to other spaces. An admin can add this space. |
| The Git connection "*name*" has no access token. | An admin needs to add a token, or choose **No token** for a public repository. |
| Access to *file* was denied (HTTP 401/403). | The token has expired or can't read that repository. |
| *file* wasn't found (HTTP 404). | Check the repository, branch and file path. A token without access to a private repository also gets 404. |
| *host* didn't respond within *n* seconds. | The host is slow or down. **Refresh** to try again. |
| *file* is larger than *n* MB. | Specs up to 20 MB can be shown (2 MB for editing in the macro settings). Split the spec into files with relative `$ref`s, or trim it. |
| The attachment "*name*" wasn't found on this page. | It was renamed or deleted. Edit the macro and choose the file again. |
| *Method* requests can't be sent from this page. | The host is read-only: an admin can change its **Try it out can send** choice in SpecPage settings. Or the page is set to read requests only: an editor can untick **Only send read requests from this page**. |
| Try it out is turned off for this page. | An editor can untick **Hide Try it out on this page** in the macro's **Display** tab. |
| No **Try it out** button on a page | Open the macro's **Display** tab: the Try it out line says why. |
| Too many requests in a short time. | Wait the number of seconds shown. |
| The SpecPage subscription for this site isn't active. | A Confluence admin needs to renew the subscription. |

## Search doesn't find new endpoints

Confluence indexes the endpoint list saved with the macro. Edit the macro and choose **Save**.

## The page shows an old version of the spec

Choose **Refresh**. If it happens often, shorten the cache time or turn on a [webhook](webhooks.md).

## Still stuck

Under the message, choose **Copy details** and paste the result into an email to support@matt-lab.ca, with the page URL and what you expected to happen. The details hold the message you saw, its **Reference** (such as `SP-7K3QX9`), where and when it happened and your browser, and nothing else. If copying doesn't work, send the reference. See the support policy.
