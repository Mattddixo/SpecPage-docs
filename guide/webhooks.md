# Webhooks

Without a webhook, a spec from Git is fetched again once the cache time passes (10 minutes by default). With a webhook, your Git provider tells SpecPage about each push and the next page view loads the new version.

## Turn it on

1. In **SpecPage settings → Connections**, choose **Webhook** on the connection, then **Turn on webhook**.
2. Copy the **Webhook URL** and the **Secret**. The secret is shown once; choose **New secret** if you lose it.
3. Add a webhook in your Git provider as below.

The webhook URL is specific to the connection. Every request is checked against the connection's secret before anything in it is read, and only pushes to repositories on the connection's allowed list refresh anything.

## GitHub

Repository (or organization) **Settings → Webhooks → Add webhook**:

- **Payload URL**: the webhook URL
- **Content type**: `application/json`
- **Secret**: the secret
- **Which events**: **Just the push event**

## GitLab

Project (or group) **Settings → Webhooks → Add new webhook**:

- **URL**: the webhook URL
- **Secret token**: the secret
- **Trigger**: **Push events** (add **Tag push events** if you document tags)

## Bitbucket Cloud

Repository **Settings → Webhooks → Add webhook**:

- **URL**: the webhook URL
- **Secret**: the secret
- **Triggers**: **Repository push**

## Azure DevOps

Project **Settings → Service hooks → Create subscription → Web Hooks**:

- **Trigger**: **Code pushed** (optionally limited to a repository or branch)
- **URL**: the webhook URL
- **Basic authentication username**: anything
- **Basic authentication password**: the secret
- **Resource details to send**: **All**. With less detail SpecPage can't tell which repository changed, so it refreshes every repository on the connection, which still works.

## Turning it off

**Turn off** stops accepting pushes and deletes the secret. Deleting the connection does the same.
