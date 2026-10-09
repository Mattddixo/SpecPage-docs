# Where specs can come from

SpecPage reads OpenAPI 3.0, 3.1 and 3.2, Swagger 2.0, and AsyncAPI 2 and 3, in YAML or JSON. A spec split across several files with relative `$ref`s is merged automatically, as long as the other files sit in the same place (the same page, or the same repository and branch).

## Page attachment

Attach a `.yaml`, `.yml` or `.json` file to the page and choose it from the list. From the macro settings you can also:

- **Upload file…** to attach a new spec (or a new version of an existing one),
- **Edit file** to change the attachment in an editor with YAML/JSON highlighting and inline errors, then save it as a new attachment version. If someone saved a newer version while you were editing, you're warned before overwriting.

Uploads and edits go to Confluence as you, so the page's normal permissions apply. Attachments are never cached, because who can read them depends on page permissions. Specs up to 20 MB can be shown, and up to 2 MB edited in the macro settings.

## Git or SwaggerHub

Choose a **Connection** (set up by an admin), then:

- **Repository**: picked from the connection's allowed list (filled in when it allows just one). If the admin allowed a whole workspace or group, like `acme/*`, type the repository, for example `acme/payments` (GitLab subgroups and Azure DevOps `organization/project/repository` work too).
- **Branch, tag or commit**: leave empty for the default branch.
- **File path**: for example `api/openapi.yaml`.

For SwaggerHub, enter the API as `owner/api-name` and an optional **Version**; leave the version empty for the API's default.

Or paste a link to the file into **Paste a link to the file (optional)** and choose **Fill in**.

Specs from Git are cached for the time the admin chose (10 minutes by default). Choose **Refresh** on the page to fetch the latest straight away, or ask an admin to turn on a [webhook](webhooks.md).

## URL

Available when an admin has turned on **Allow specs from URLs**. The URL must start with `https://` and its host must be ticked for **Spec URLs** in the admin's **Approved hosts**. For private repositories, use a Git connection instead.

## Paste

Paste the spec straight into the editor. Up to 100,000 characters; for anything bigger, save it as an attachment (there's a **Save as attachment** button). Pasted specs can't use relative `$ref`s, because there's nowhere to load the other files from.
