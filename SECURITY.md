# Security policy

## Reporting a vulnerability

Email security@matt-lab.ca with a description, the steps to reproduce it, and what an attacker could do with it. Please don't open a public issue or post details before a fix is out.

You'll get an acknowledgement within 2 business days and updates as the issue is worked on. Fixes follow Atlassian's [Security Bug Fix Policy](https://developer.atlassian.com/platform/marketplace/security-bugfix-policy/) for Marketplace apps:

| Severity (CVSS) | Fixed within |
| --- | --- |
| Critical (9.0+) | 10 days |
| High (7.0 to 8.9) | 4 weeks |
| Medium (4.0 to 6.9) | 12 weeks |

Reports can also go through Atlassian's Marketplace bug bounty program on Bugcrowd, if SpecPage is enrolled.

## Testing

Test against your own Confluence site and your own data. Don't test against other customers' sites, run denial-of-service tests, or try to access data that isn't yours.

## Scope

In scope: the SpecPage app, as installed from the Atlassian Marketplace.

Out of scope: Atlassian's platform and products (report those to Atlassian), Git providers, and APIs that customers connect.

## Supported versions

SpecPage is a cloud app. Every site runs the latest version, so fixes reach all customers when they're deployed.

## How SpecPage is secured

SpecPage runs entirely on Atlassian Forge, with no servers of its own, and never sends customer data to the developer. It only contacts hosts a Confluence admin approves, and keeps Git tokens in Forge's encrypted secret storage, out of reach of the browser.

