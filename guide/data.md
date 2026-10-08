# Your data

SpecPage runs entirely on Atlassian Forge. Everything it stores is in your site's Forge app storage, hosted and encrypted by Atlassian, and follows your site's data residency location. Nothing is sent to the SpecPage developer. The privacy policy lists every item and how long it's kept.

## Where your specs live

SpecPage doesn't keep the master copy of anything. Specs stay where they are: in your Git repositories, SwaggerHub, at their URLs, as page attachments, or (for pasted specs) in the macro's settings on the page. SpecPage only keeps short-lived cached copies of Git and URL specs.

## Exporting

- **Specs**: **Download** on any macro saves the spec as JSON. Attachments and pasted specs are part of the Confluence page and are exported with it.
- **Activity log**: **Download CSV** in SpecPage settings.
- **Settings and connections**: shown in SpecPage settings. Tokens can't be exported; they're never sent back to the browser.

## Deleting

While SpecPage is installed, an admin can:

- delete a connection, which deletes its token and webhook secret;
- choose **Clear cache** to drop cached specs;
- set a retention period for the activity log;
- remove a macro from a page, which removes it from the API catalog.

To delete everything, uninstall SpecPage. Before it's removed, SpecPage deletes the account IDs from its activity log. Atlassian keeps an app's storage for 28 days after an uninstall, in case you reinstall and ask for it back, and then deletes it.

For a deletion request, contact support@matt-lab.ca.
