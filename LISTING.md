# Adspirer Search Ads — Perplexity listing details

| Field | Value |
| --- | --- |
| Name | Adspirer Search Ads |
| MCP server URL | `https://mcp.adspirer.com/search-ads` |
| Transport | Streamable HTTP |
| Sign-in | OAuth 2 in the browser (PKCE); no API key |
| Category | Marketing / Advertising |
| Read-only | No — changes need user approval |
| Logo (1:1) | https://storage.googleapis.com/adspirer-images-v1/brand/adspirer-logo-square.png |
| Website | https://www.adspirer.com |
| Documentation | https://www.adspirer.com/docs |
| Privacy | https://www.adspirer.com/privacy |
| Terms | https://www.adspirer.com/terms |
| Support | support@adspirer.com |

## Short description

PPC advertising agent for Google and Bing. Research keywords and competitor ads, launch search campaigns, and optimize paid-search spending—with your approval.

## Long description

Adspirer Search Ads connects Perplexity to your advertising accounts through a hosted MCP server. It covers
Google Ads and Microsoft (Bing) Ads. It can change ad accounts, and only with your approval: campaigns are built paused, every change is shown first and read back afterwards. The agent never purchases or upgrades a subscription on your behalf. Sign-in
is browser OAuth with your Adspirer account; ad accounts are connected at
https://adspirer.ai/connections. An Adspirer account and an applicable plan are required.

## Example prompts

- "Research keywords for our product and show search volume and competition."
- "Which search terms are spending without converting in Google Ads this month?"
- "Draft a Google Search campaign for these keywords and build it paused for my review."

## Getting listed

Perplexity has no self-serve directory for third-party connectors. Users add Adspirer Search Ads as a
custom connector with the URL above. To ask for it to be offered as a managed connector, email
api@perplexity.ai:

```
Subject: Managed connector request: Adspirer Search Ads

Hi Perplexity team,

We'd like to request Adspirer Search Ads as a managed connector.

PPC advertising agent for Google and Bing. Research keywords and competitor ads, launch search campaigns, and optimize paid-search spending—with your approval.

- MCP server: https://mcp.adspirer.com/search-ads (Streamable HTTP, browser OAuth with PKCE)
- Platforms: Google Ads and Microsoft (Bing) Ads
- Writes require user approval; campaigns are created paused.
- Logo: https://storage.googleapis.com/adspirer-images-v1/brand/adspirer-logo-square.png
- Website: https://www.adspirer.com
- Docs: https://www.adspirer.com/docs
- Contact: support@adspirer.com

It already works as a custom remote connector in the Perplexity app. Please let us know what
you need from us for review.

Thanks,
Abhi
```
