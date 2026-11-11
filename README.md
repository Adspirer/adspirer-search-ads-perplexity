# Adspirer Search Ads for Perplexity

PPC advertising agent for Google and Bing. Research keywords and competitor ads, launch search campaigns, and optimize paid-search spending—with your approval.

This package connects Perplexity to the hosted Adspirer Search Ads MCP server and gives its agent the
skills to use it well. It covers Google Ads and Microsoft (Bing) Ads. It can change ad accounts, and only with your approval: campaigns are built paused, every change is shown first and read back afterwards.

## What's included

| File | Purpose |
| --- | --- |
| [connector.json](connector.json) | Connector details: name, URL, sign-in, logo, links |
| [LISTING.md](LISTING.md) | Paste-ready name, descriptions and submission notes |
| [AGENT.md](AGENT.md) | Agent instructions to paste into Perplexity |
| `skills/` | 16 Agent Skills (`SKILL.md` folders) |
| `dist/skills/` | The same skills as one zip each, for upload |
| `examples/` | Agent API request examples |

## Connect in Perplexity

1. Open **Settings → Connectors** and choose **Custom connector → Remote**.
2. Name it `Adspirer Search Ads` and enter the URL `https://mcp.adspirer.com/search-ads`.
3. Sign in with your Adspirer account in the browser window.
4. Connect your ad accounts at https://adspirer.ai/connections.

Custom connectors are reported to need a paid Perplexity plan, and admin permission in
organizations. Menu labels change; check Perplexity's help center if yours differ.

## Use with the Perplexity Agent API

A Project administrator adds the server once on the Project connectors page in the API Console
(server name, MCP URL, authentication, transport **Streamable HTTP**), then copies the connector
ID. Requests reference it by ID; see [examples/agent_api.py](examples/agent_api.py) and
[examples/agent_api.sh](examples/agent_api.sh).

Open question: Perplexity's documentation lists **API Key or None** as the authentication choices
for custom connectors in the API Console, and Adspirer Search Ads signs in with browser OAuth. This has not
been tested. If OAuth is not offered there, ask Perplexity (api@perplexity.ai) before relying on
the Agent API route; the app route above is the supported one.

Agent API connector calls run **without approval by default**. This connector can change ad accounts, so the examples set an approval policy and you should keep one on every request.

## Add the skills

Perplexity Computer is reported to import Agent Skills (`SKILL.md` folders); this has not been
tested with these skills. Each skill is in `skills/` and zipped in `dist/skills/`. Where skills
are not available, paste [AGENT.md](AGENT.md) into the Space or Computer instructions instead.

| Skill | Use it for |
| --- | --- |
| `adspirer-search-agent` | Coordinate Google and Microsoft paid-search tasks, preserve brand context, and route to focused Adspirer skills with approval before changes. |
| `adspirer-search-campaigns` | Plan and create user-approved paused Google Ads or Microsoft Advertising campaigns from research. |
| `adspirer-search-competitors` | Research public competitor ads and messaging for user-supplied domains through Adspirer Search Ads. |
| `adspirer-search-creative` | Write and refresh Google and Microsoft search-ad copy, using brand evidence, supported formats, and approval-controlled updates. |
| `adspirer-search-docs` | Answer questions about Adspirer itself — pricing, plans, quota and tool-call limits, what Adspirer can do, connecting an ad account, supported platforms and AI clients, security, and troubleshooting. Uses the official documentation at adspirer.com/docs rather than guessing. |
| `adspirer-search-google-ads` | Create and manage Google Ads campaigns through Adspirer — Search, Performance Max, Demand Gen, YouTube, and Display. Use for Google Ads keywords, search terms, quality score, bid strategies, sitelinks and extensions, PMax asset groups, or anything on Google/AdWords. Covers the asset-bundle expiry and ad-group-id traps. |
| `adspirer-search-google-analytics` | Analyze GA4 acquisition, landing pages, and conversion events for paid-search decisions using authorized Google Analytics properties. |
| `adspirer-search-google-search-console` | Research organic queries and landing-page search performance to inform paid-search planning with Google Search Console. |
| `adspirer-search-google-tag-manager` | Inspect Google Tag Manager tracking configuration and plan approved measurement fixes for search advertising. |
| `adspirer-search-keywords` | Research paid-search keyword opportunities, intent, match types, and negative-keyword candidates for Google Ads. |
| `adspirer-search-mcp` | Discover and safely use the Adspirer Search Ads MCP tools. Load before any tool call through this plugin. |
| `adspirer-search-measurement` | Audit search-ad conversion tracking and investigate performance using available Google Analytics, Search Console, and Tag Manager tools. |
| `adspirer-search-microsoft-ads` | Plan and manage Microsoft Advertising and Bing Ads campaigns through Adspirer's Search Ads connector. |
| `adspirer-search-optimize` | Analyze Google paid-search waste and budget pacing, inspect Microsoft campaigns, and apply only explicitly approved changes. |
| `adspirer-search-performance-review` | Read-only Google Ads reporting and Microsoft account inspection, scorecards, conversion checks, and evidence-backed recommendations. |
| `adspirer-search-setup` | Connect Google or Microsoft and optionally build a preserved, user-approved brand workspace from relevant files and live account data. |

## Example prompts

- "Research keywords for our product and show search volume and competition."
- "Which search terms are spending without converting in Google Ads this month?"
- "Draft a Google Search campaign for these keywords and build it paused for my review."

## Safety

- It can change ad accounts, and only with your approval: campaigns are built paused, every change is shown first and read back afterwards.
- **No purchases.** The agent never buys, upgrades, renews or starts a trial of a subscription or
  paid feature for you, including when it runs on its own with browser or payment tools. At a
  quota or plan limit it stops, explains and waits.
- **No unattended changes.** Scheduled or background runs are read-only.
- Sign-in is browser OAuth. Never paste tokens into chat.

An Adspirer account and an applicable plan are required; ad-platform permissions and usage limits
apply.

## Status

Built from https://github.com/Adspirer/adspirer-search-ads-cursor-plugin v1.0.4 on 2026-11-11. Not yet installed or tested in
Perplexity. Run `node scripts/validate.mjs` after editing.

## Support

- Support: support@adspirer.com
- Documentation: https://www.adspirer.com/docs
- Privacy: https://www.adspirer.com/privacy
- Terms: https://www.adspirer.com/terms
- Security: see [SECURITY.md](SECURITY.md)
