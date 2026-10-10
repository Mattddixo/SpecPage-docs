# Compare versions

**Changes** on a published page compares the spec with an earlier version and lists what changed, with breaking changes first. It's there for signed-in users on macros whose spec comes from Git or a page attachment.

1. Choose **Changes**.
2. For Git, choose a branch or tag from the list (the repository's first 100 of each), or choose **Other** to type a commit or another name. For SwaggerHub, type a version such as `1.2.0`. For an attachment, enter an older attachment version, or leave it empty for the previous version.
3. Choose **Compare**.

## What counts as what

**Breaking**: changes that can stop existing clients working. For example:

- an endpoint removed,
- a new required parameter, request body or request property,
- an optional parameter or request property made required,
- a type changed in a way existing values no longer fit (for example integer to string),
- a limit tightened on request values, such as a lower maximum length,
- a required property removed from a response.

**Check**: changes that may affect some clients. For example:

- an endpoint deprecated,
- an optional property removed from a response,
- a new value in a response enum (a client that switches on the values may not expect it).

**Other changes**: additions that don't affect existing clients, such as new endpoints or new optional parameters.

Each change shows the endpoint and where it is, for example `response 200 · items[].status` or `limit (query)`.

**Download as Markdown** saves the list for release notes or a change ticket. Very large specs with thousands of changes show the first 500, breaking ones first; the counts at the top cover everything.

Comparisons use the macro's saved settings, so they read from the same repository or page the macro already does.
