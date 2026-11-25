# Free Web Scraping Tools: Which Free Tiers Renew Monthly, Which Get Past Cloudflare, and What 1,000 Pages Really Costs

A free scraping plan is worth exactly as much as next month's refill. Three shapes show up in every list: managed APIs with a monthly credit allowance, open-source libraries with no license fee, and one-time trials. Only the first keeps working after month one.

ScraperAPI sits in that first group. The free plan pays out **1,000 API credits every month with 5 concurrent connections**, and a **7-day trial adds 5,000 credits** with no card required, so the first week of testing isn't throttled. On plain HTML those 1,000 credits buy 1,000 pages. On a page that needs JavaScript rendering they buy 100. Same plan, tenfold difference in output, and most roundups that quote "1,000 free calls" leave that part out.

The multiplier runs through everything below: what each free tier converts into, whether it survives Cloudflare, what open source really costs once proxies and browsers are on the bill, and the point where $49 a month is cheaper than a free stack that eats your weekends.

> **Quick pick.** If you need to scrape this month and next without paying, choose a managed API whose credits reset. ScraperAPI's free plan (1,000 credits/month, 5 concurrent threads) is the one to start on, and paid tiers begin at $49/month. 👉 [Check the current free-tier limits and plan prices](https://www.scraperapi.com/pricing/?fp_ref=coupons)

## The three kinds of "free", priced separately

They cost different things, and mixing them up is how people end up on a trial that quietly expires.

**A recurring free tier on a managed API.** You get a fixed allowance each month, the vendor runs the proxies and browsers, and you pay nothing until you exceed it. This is the only category where a zero-budget project can run indefinitely.

**An open-source library.** The license is free (BSD for Scrapy, Apache 2.0 for Playwright). Everything around it is not: proxy bandwidth, CAPTCHA solving and cloud compute are billed by someone, and the parsing code needs maintenance when a site changes its markup.

**A one-time trial.** Generous on day one, zero on day thirty-one. Fine for evaluating a vendor, useless as a permanent setup.

A fourth case gets filed under "free" without qualification: no-code tools with a free plan that caps task count or restricts runs to your own machine. Workable for a one-off export, not for anything scheduled.

## Free web scraping tools compared

Prices are the entry paid tier; free tiers are the recurring ones unless marked as a trial.

| Tool | Type | Free tier | Paid from | Best for |
| --- | --- | --- | --- | --- |
| ScraperAPI | Managed API | 1,000 credits/month recurring, 5 concurrent; 7-day 5,000-credit trial | $49/month | Plain HTML at low volume, with paid add-ons for rendering and bot bypass |
| Bright Data | Managed API | 5,000 credits/month, resets on the 1st, no card | $1.50 per 1,000 records; Scale plan $499/month for 384,000 | Protected sites at enterprise scale |
| ScrapingBee | Managed API | ~1,000 credits, one-time trial | $49/month | JS rendering through a REST call |
| Apify | Managed platform | $5/month in platform credits, recurring | $29/month | Prebuilt Actors and scheduled jobs |
| Firecrawl | Managed API | 1,000 credits/month | $16/month | Clean Markdown or JSON for LLM pipelines |
| Oxylabs | Managed API | 2,000-result trial, no card | $49/month covering up to 98,000 results | Unblocking hard targets via Web Unblocker |
| Crawl4AI | Open source, plus hosted cloud | Free self-hosted; cloud gives 1,000 credits/month | Cloud from $10/month | LLM-ready Markdown and adaptive crawls |
| Scrapy | Open-source framework | Free (BSD) | Self-hosted | High-volume crawling in Python |
| Beautiful Soup | Open-source library | Free | Self-hosted | Parsing HTML you already fetched |
| Playwright | Open-source browser | Free (Apache 2.0) | Self-hosted | Pages that need clicks and JavaScript |
| Octoparse | No-code | 10 tasks, one device, local runs, 50,000 rows exported per month | $69/month (annual) | Click-to-scrape without code |
| ParseHub | No-code | 5 projects, all public, data kept 14 days | $189/month | Multi-page structured extraction |
| Browse AI | No-code | 2 domains, 50 credits/month | $19/month (annual) | Simple change monitoring |
| Web Scraper | Browser extension | Unlimited local runs | Free | Small jobs from your own browser |

Two rows deserve a warning. ParseHub's free projects are **public**, and their data is deleted after 14 days, so it is not a free tier you can build a product on. Octoparse's free plan runs locally on one device, which means your laptop has to stay awake for every run.

## ScraperAPI's plans and what one credit actually buys

ScraperAPI lists six paid tiers plus a custom Enterprise plan. The free plan never expires; the trial is a separate 7-day boost on top of it.

| Plan | Credits per month | Monthly price | Annual billing | Get started |
| --- | --- | --- | --- | --- |
| Free | 1,000 | $0 | — | [Start on the free plan](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Hobby | 100,000 | $49 | $44.10/month | [Open the Hobby tier](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Startup | 1,000,000 | $149 | $134.10/month ($1,609.20/year) | [Open the Startup tier](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Scaling | 5,000,000 | $475 | — | [Open the Scaling tier](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Business · Professional · Advanced · Enterprise | Scaled above Scaling | Listed on the plan page | — | [See the full plan ladder](https://www.scraperapi.com/pricing/?fp_ref=coupons) |

The tier that matters for most readers is the free one, and its value depends entirely on what you point it at. ScraperAPI publishes a credit rate card, and the spread is wide.

| Request type | Credits per request |
| --- | --- |
| Standard HTML page | 1 |
| Amazon, Walmart, eBay | 5 |
| Google or Bing results | 25 |
| LinkedIn | 30 |
| Bot-protection bypass (Cloudflare, Cloudflare Turnstile, DataDome, PerimeterX/HUMAN, Akamai) | +10 |
| JavaScript rendering (`render=true`) | 10 |
| Premium proxies (`premium=true`) | 10 |
| Premium proxies plus JS rendering | 25 |
| Ultra premium (`ultra_premium=true`) | 30 |
| Ultra premium plus JS rendering | 75 |
| Geotargeting, sessions, device type, output format, auto-parsing | 0 |

Run the free 1,000 credits through that table: 1,000 plain pages, 100 rendered pages, 40 Google searches, or 33 LinkedIn pages. At the Startup tier, $149 for a million credits works out to roughly **$0.15 per 1,000 plain pages**; if every page needs rendering, the same $149 covers 100,000 pages, or $1.49 per 1,000. A rate card that looks cheap per credit can be fifteen times more expensive per page depending on your targets.

Two features keep this from becoming guesswork. The dashboard's Domain Cost Estimator prices a URL before you commit, and the `max_cost` parameter makes a request fail with a 403 rather than charge past your cap. Every response also reports its own cost in the `sa-credit-cost` header.

## Does the free tier still have credits next month?

This is the question that separates a real free plan from a demo, and it's usually buried.

ScrapingBee's roughly 1,000 credits are a **one-time trial**: once consumed, they don't refresh. Bright Data gives 5,000 credits a month that reset on the 1st, don't accumulate, and need no card. ScraperAPI gives 1,000 a month with the same no-rollover rule, plus 5,000 credits during the first seven days. None of the three carries unused credits forward, so size the plan against your monthly volume rather than your best month.

Worth knowing before you pick an annual plan anywhere: ScraperAPI delivers a full year's credits upfront on annual billing, so you can burn them on any schedule instead of waiting for a monthly reset. If your scraping is seasonal, that's a genuine advantage over monthly tiers.

On the paid side, running out of credits pauses your scraping until renewal by default. Auto-upgrade moves you to the next tier when the allowance is gone, and pay-as-you-go on Hobby, Startup and Business keeps requests flowing at a fixed per-credit rate up to a spending cap you set yourself. The cap is a limit, not a prepayment.

👉 [Start the 7-day trial, then keep the 1,000-credit free plan](https://www.scraperapi.com/pricing/?fp_ref=coupons)

## Will a free tool get past Cloudflare?

Usually not, and the free tiers that can are priced for it.

The defenses you'll meet on commercial targets are Cloudflare, DataDome, PerimeterX, Akamai and Imperva. An open-source stack has no answer built in. Playwright renders JavaScript perfectly well, but its headless Chromium is detectable by most enterprise anti-bot systems, and it ships without proxy rotation or fingerprint evasion. Scrapy needs `scrapy-splash` or a Playwright middleware for rendering and a separate proxy service for IP rotation. Beautiful Soup doesn't fetch pages at all.

What works: a managed service that sells bypass as a line item. ScraperAPI charges 10 extra credits for bot-protection bypass and names Cloudflare, Cloudflare Turnstile, DataDome, PerimeterX/HUMAN and Akamai in its rate card. Oxylabs sells Web Unblocker for CAPTCHAs and rotating browser fingerprints. Web Scraper Cloud advertises Cloudflare, Datadome, PerimeterX, Imperva, Akamai Bot Manager, hCaptcha and reCAPTCHA among the systems it handles. Crawl4AI, on the open-source side, ships an `enable_stealth` mode and an undetected-browser adapter, which is the closest a free library gets.

The practical consequence for a free plan: 1,000 credits stop being 1,000 pages the moment bypass or rendering enters the request. Treat a free tier on a protected target as a testing allowance, not a production one. If your target list is behind any of those five systems, budget for the multiplier before you budget for volume.

👉 [See how ScraperAPI prices rendering and bot bypass](https://www.scraperapi.com/pricing/?fp_ref=coupons)

## What open source actually costs

The license is the cheap part. The stack around it is where the money goes.

**Scrapy** is the throughput option: BSD-licensed, 500+ contributors, asynchronous enough to hold hundreds of concurrent requests, with XPath and CSS selectors built in and middleware for proxy rotation and retries. It does not render JavaScript and does not solve CAPTCHAs.

**Beautiful Soup** parses. You bring `requests` to fetch and `pandas` to shape the output, and it handles neither JavaScript nor sessions nor retries.

**Playwright** handles the modern web, including logins and clicks, under Apache 2.0. Each browser instance eats real RAM, so concurrency at any volume means paying for cloud compute, and none of the fingerprint problem is solved for you.

**Crawl4AI** is the most complete free option for LLM work: clean Markdown with headings, tables and citation hints, CSS/XPath/regex extraction without a model, LLM extraction through any LiteLLM provider, sessions, authenticated proxies with rotation, stealth mode, deep crawls with crash recovery, adaptive crawling that stops when it has enough, and an async dispatcher for many URLs at once. Its hosted cloud has a free tier of 1,000 credits a month at 10 requests a minute and 2 concurrent jobs, with paid plans from $10 a month.

Add it up and the honest comparison isn't "free versus $49". It's a monthly maintenance line for selectors and proxy plumbing, plus metered proxy bandwidth and CAPTCHA solving, against a plan price. My rule: if your targets sit behind bot management, or you'd spend more than a day a month keeping a proxy stack alive, the $49 tier is the cheaper line item. If you're crawling static, unprotected sites at volume and already run the servers, Scrapy stays the right tool and always will.

## Which tool for which job

- **A few hundred pages, once.** The Web Scraper browser extension runs locally with no page cap. If you write code, Beautiful Soup plus `requests` is faster to start than anything else.
- **Recurring checks on a handful of pages.** ScraperAPI's free 1,000 credits cover 1,000 plain pages a month. Browse AI's free plan handles 2 domains and 50 credits if you'd rather not touch code.
- **Pages behind a login.** Playwright or Selenium with a saved session, or a browser extension that reuses the session you're already logged into. Octoparse handles logins without code.
- **Cloudflare or DataDome in the way.** Managed bypass only: ScraperAPI credits, Oxylabs Web Unblocker, or Web Scraper Cloud. Everything else is a weekend you won't get back.
- **Feeding an LLM or RAG pipeline.** Crawl4AI self-hosted, or its cloud at $10 a month; Firecrawl at $16 a month if you want the whole pipeline as an API.
- **Hundreds of thousands of pages on your own infrastructure.** Scrapy, with Playwright bolted on only for the pages that need it.
- **Literally zero budget and no code.** Web Scraper extension for one-offs, ScraperAPI's free tier for anything that has to run again next month.

## Rules that don't change with the tool

Read `robots.txt` before you crawl; the standard was formalized as RFC 9309 in 2022 and most sites state their limits there. Respect rate limits and back off exponentially instead of hammering a host that just throttled you. Read the terms of service, because plenty of sites prohibit automated collection outright and commercial use may need written permission or a data licence. If personal data is involved, GDPR's rules on minimization, secure storage and retention apply to scraped records exactly as they apply to any other database.

## How to decide

Match the tool to the billing shape first, then to the target.

- Under about 1,000 plain pages a month, no bot protection: a free tier that renews, or a local extension.
- Any target behind Cloudflare, DataDome, PerimeterX, Akamai or Imperva: pick a tool that sells bypass, and count the credits per page before you count pages.
- Steady volume past a few hundred thousand pages: compare cost per 1,000 records, not cost per month. ScraperAPI's own numbers show why, at $0.15 per 1,000 plain pages versus $1.49 per 1,000 rendered ones.

Before you enter a card anywhere, confirm three things: whether the free allowance recurs or expires, what your specific target costs in credits, and whether a card is required at signup. On ScraperAPI, all three are answerable up front: 1,000 credits a month that reset and don't roll over, a 7-day trial of 5,000 credits with no card, a published rate card with a per-URL estimator, and a 7-day no-questions-asked refund on paid plans, with cancellation available from the dashboard at any time.

👉 [Compare the free plan with the paid tiers and pick your credit level](https://www.scraperapi.com/pricing/?fp_ref=coupons)
