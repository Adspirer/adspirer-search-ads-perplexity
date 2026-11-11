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

1. In Perplexity, open **Computer** and choose **Connectors** in the left sidebar.
2. Choose **+ Custom connector** in the top-right corner.
3. Enter the name `Adspirer Search Ads`, a short description, and the MCP server URL `https://mcp.adspirer.com/search-ads`.
4. Tick **I understand custom connectors can introduce risks** and choose **Add**.
5. Perplexity opens the Adspirer authorization page. Sign in and approve access.
6. Connect your ad accounts at https://adspirer.ai/connections.

Custom connectors need a Perplexity Pro, Max or Enterprise plan. The full guide with screenshots
is at https://www.adspirer.com/docs/ai-clients/perplexity.

## Use with the Perplexity Agent API

A Project administrator adds the server once on the Project connectors page in the API Console
(server name, MCP URL, authentication, transport **Streamable HTTP**), then copies the connector
ID. Requests reference it by ID; see [examples/agent_api.py](examples/agent_api.py) and
[examples/agent_api.sh](examples/agent_api.sh).

Authentication: Perplexity's API Console offers **API Key** or **None** for custom connectors.
Use an Adspirer API key (starts with `sk_live_`), created at https://adspirer.ai/keys; it gives
the same access as browser sign-in. Revoke it there when you no longer need it. This route has not
been tested end to end.

Agent API connector calls run **without approval by default**. This connector can change ad accounts, so the examples set an approval policy and you should keep one on every request.

## Add the skills

Perplexity Computer supports Agent Skills:

1. In Perplexity, open **Computer** and choose **Skills** in the left sidebar.
2. Choose **+ Create skill** in the top-right corner.
3. In the **Upload skill** dialog, upload a skill: the `SKILL.md` file from a folder in `skills/`,
   or that skill's zip from `dist/skills/`, which also carries its `references/` files.
4. The skill appears in your Skills list, and Perplexity applies it when a request matches.

Upload `adspirer-search-mcp` first; the other skills refer to it. If you upload `SKILL.md` on its
own, its `references/` files are not included, so prefer the zip. You can also paste
[AGENT.md](AGENT.md) into a Space's instructions as a short always-on version.

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
