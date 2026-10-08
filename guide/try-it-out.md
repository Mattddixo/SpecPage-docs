# Try it out

Try it out lets signed-in readers send real requests to an API from the docs and see the response. A Confluence admin turns it on for the site and approves the API hosts it may call. After that it appears by itself on every page whose spec points at an approved host. Page editors can hide it on their page, and the macro editor's **Display** tab says whether it's on and why not if it isn't.

## Using it

1. Expand an operation and choose **Try it out**.
2. Fill in the parameters and body.
3. If the API needs credentials, choose **Authorize** and enter them. API keys, Basic and Bearer auth work, and OAuth client credentials and password flows get a token for you.
4. Choose **Execute**.

OAuth sign-in flows that open a pop-up window (authorization code, implicit, OpenID Connect) can't run inside Confluence. If the spec uses them, paste an access token from your identity provider into the **OAuth access token** box above the docs instead.

File uploads work, and image or PDF responses come back as downloads.

## Read-only mode

By default, Try it out only sends read requests: GET, HEAD and OPTIONS. Write operations don't show an **Execute** button, and a note above the docs says why. An admin can let a host have every method (handy for sandbox APIs) with its **Try it out can send** choice in SpecPage settings. A page editor can keep their page to read requests even then. If a spec lists several servers and any of them is read-only, the page is too.

OAuth token requests from the **Authorize** button still work in read-only mode.

## How requests are sent

Requests go through SpecPage on Atlassian's servers instead of straight from your browser, which avoids the cross-site (CORS) errors other tools run into. That means:

- requests only go to hosts an admin has approved for Try it out, over https;
- redirects aren't followed;
- cookies, browser-identifying headers and client-IP headers (`X-Forwarded-For` and similar) are removed;
- in read-only mode, requests that ask the API to treat them as another method (`X-HTTP-Method-Override`, `_method`) are refused;
- request bodies are limited to 400 KB (350 KB for files), text responses to 4 MB and file responses to 3 MB;
- each user can send a burst of about 20 requests, then one every 3 seconds; if you hit the limit, the message says how long to wait.

Credentials you type (API keys, tokens, client secrets) stay in the page's memory and are gone when you leave the page. SpecPage never saves or logs them.

The API sees requests coming from Atlassian's IP addresses, not yours.
