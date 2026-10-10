# Display options

The **Display** tab in the macro settings controls what readers see. The preview updates as you change things.

| Option | What it does |
| --- | --- |
| **Title** | Leave empty to use the title from the spec. |
| **Show only these tags** | Show only operations with the ticked tags. |
| **Show only these paths** | Tick the groups of paths to show, for example `/payments`, which also covers `/payments/{id}`. Each shows how many operations it holds. Leave all unticked to show everything. |
| **Hide deprecated operations** | Leave out operations marked as deprecated. |
| **Expand operations** | **Show tags, collapse operations**, **Expand everything** or **Collapse everything**. |
| **Maximum height** | **Grow with content**, or a fixed height with a scroll bar. |
| **Show API description and contact details** | The block at the top with the description, version and contact links. |
| **Show servers and authorization bar** | The server picker and **Authorize** button. |
| **Show schemas section** | The list of schemas at the bottom. |
| **Show operation search box** | A filter box above the operations. |
| **Show code samples** | cURL, JavaScript, Python, Go, Java and C# for each endpoint, plus any samples in the spec (`x-codeSamples`). |
| **Try it out** | A line saying whether readers can send requests from this page and, if not, why: off for the site, the API's host isn't approved, or the spec doesn't say where the API is. It's on by itself when the site allows it and the host is approved. See [Try it out](try-it-out.md). |
| **Hide Try it out on this page** | Turns it off for this page only. |
| **Only send read requests from this page** | Shown when the API's host allows every method. Keeps this page to GET, HEAD and OPTIONS. |
| **Server URL for "Try it out" (optional)** | Overrides the spec's servers, for example to point at a staging environment. Needed when the spec only has relative server URLs like `/v1`. |

Filters affect what readers see, the [Quality score](quality.md), and what Confluence search indexes. They don't change the spec itself; **Download** on the page still gives the full spec.

The docs follow Confluence's light or dark theme automatically.
