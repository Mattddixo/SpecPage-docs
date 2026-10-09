# Add API docs to a page

1. Edit a page, type `/spec` and choose **OpenAPI / Swagger docs (SpecPage)**.
2. Pick where the spec comes from: **Page attachment**, **Git or SwaggerHub**, **URL** or **Paste**. See [Where specs can come from](sources.md).
3. Check the preview on the right. It updates as you change settings.
4. Optionally adjust the **Display** tab ([Display options](display.md)) and look at the **Quality** tab ([Quality score](quality.md)).
5. Choose **Save**, then publish the page.

New to SpecPage? **Try a sample API** fills in a small spec for httpbin.org, a free public test API, so you can see everything working before you set up a source. Once an admin turns on Try it out and approves `httpbin.org`, you can send it real requests too.

## Paste a link instead

Paste a link to a spec file into the page and SpecPage inserts the macro with the settings filled in. This works for files named `openapi` or `swagger` (`.yaml`, `.yml` or `.json`) on github.com, gitlab.com or bitbucket.org, and for APIs on app.swaggerhub.com, as long as an admin has set up a connection that allows the repository. The macro shows "isn't set up yet" until you save it: select it, choose **Edit** (the settings are already filled in from the link), check the preview and choose **Save**.

## Several specs on one page

Insert the macro more than once. Each one loads and renders on its own.

## Search

When you save the macro, its endpoints are added to the page so Confluence search can find them. If the spec changes later, editors see a note on the page; edit the macro and choose **Save** to bring search up to date.
