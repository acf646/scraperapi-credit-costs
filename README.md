# ScraperAPI credit cost: why one request can burn 75 credits, what 1,000 Google searches really cost, and which plan to buy (plan and parameter tables)

A plain page costs 1 credit. Amazon, Walmart and eBay cost 5. Google and Bing cost 25, LinkedIn costs 30, and any page where ScraperAPI has to break Cloudflare, Cloudflare Turnstile, DataDome, PerimeterX or Akamai adds 10 on top. On the $49 Hobby plan that works out to **$0.49 per 1,000 plain pages** and **$12.25 per 1,000 Google searches**.

Those two numbers explain most of the “where did my credits go” threads. What follows is the complete credit table, the parameter prices (including the combined tiers that do not add up the way you would expect), the real cost per 1,000 requests on each of the seven plans, and the billing rules that catch people out after they have already paid.

> **Most readers should start on Hobby: $49/month for 100,000 credits.** That covers 100,000 plain pages, 20,000 Amazon pages or 4,000 Google searches per month. If search engines are your main target, skip Hobby and look at Startup or above. 👉 [See all seven plans with current monthly and annual pricing](https://www.scraperapi.com/pricing?fp_ref=coupons)

## All seven plans, side by side

| Plan | Credits per month | Monthly price | Annual (per month) | Threads | Link |
| --- | --- | --- | --- | --- | --- |
| Hobby | 100,000 | $49 | $44.10 | 20 | [Select Hobby](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Startup | 1,000,000 | $149 | $134.10 | 50 | [Select Startup](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Business | 3,000,000 | $299 | $269.10 | 100 | [Select Business](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Scaling (Most Popular) | 5,000,000 | $475 | $427.50 | 200 | [Select Scaling](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Professional | 10,500,000 | $975 | $877.50 | 300 | [Select Professional](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Advanced | 21,500,000 | $1,975 | $1,777.50 | 500 | [Select Advanced](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Enterprise | 22,000,000+ | Custom | Custom | 500+ | [Request an Enterprise quote](https://www.scraperapi.com/pricing?fp_ref=coupons) |

Annual billing takes exactly 10% off every plan and is available on all of them. Enterprise is quoted per account.

Two differences matter more than the credit volume. **Geotargeting outside the US and EU starts at Business ($299)**, and it is country-level, not city-level. **Analytics history** is capped at 30 days on Hobby and Startup and unlimited from Business up.

There is also a free plan with 1,000 credits and a maximum of 5 concurrent connections, plus a 7-day trial with 5,000 credits that does not ask for a card. Both are for testing only.

## What each request costs in credits

Credits are charged per request, and the number depends on the domain you hit plus the parameters you send. A request does not always cost one credit.

| Target | Credits per request |
| --- | --- |
| Standard page | 1 |
| Amazon, Walmart, eBay | 5 |
| Google, Bing (all subdomains) | 25 |
| LinkedIn | 30 |
| Cloudflare bypass | +10 |
| Cloudflare Turnstile bypass | +10 |
| DataDome bypass | +10 |
| PerimeterX / Human bypass | +10 |
| Akamai bypass | +10 |

The bypass surcharge is applied automatically when ScraperAPI switches on the bypass logic. You do not request it, and you cannot opt out of it per request. A standard page behind Cloudflare costs 1 + 10 = 11 credits.

Parameter pricing:

| Parameter | Credits per request |
| --- | --- |
| `premium=true` | 10 |
| `render=true` | 10 |
| `screenshot=true` | 10 |
| `premium=true` + `render=true` | 25 |
| `ultra_premium=true` | 30 (paid plans only) |
| `ultra_premium=true` + `render=true` | 75 (paid plans only) |
| `wait_for_selector`, `country_code`, `session_number`, `device_type`, `output_format`, `keep_headers=true`, `autoparse=true` | 0 |

### The combined options are fixed tiers, not sums

Read the two combined rows again. `premium=true` is 10 and `render=true` is 10, but sending both costs 25, not 20. `ultra_premium=true` is 30 and `render=true` is 10, but together they cost 75, not 40.

These are priced as packages. If you are estimating a run by adding up parameters, you will be off by 25% on premium plus rendering and by nearly half on ultra premium plus rendering. Use the published tier number.

The tier structure also gives you a cheaper path for JavaScript-heavy pages. A rendered page with premium IPs is 25 credits. The same page with ultra premium IPs and rendering is 75 credits, three times the cost, which only makes sense when premium proxies already failed on that domain.

`ultra_premium` is marked as paid-plan only, and Hobby counts as a paid plan, so it is available at $49.

## What 1,000 requests actually cost on each plan

The credit cost per domain never changes with your plan. What changes is the price of a credit.

| Plan | $ per 1,000 credits | 1,000 plain pages | 1,000 Google searches |
| --- | --- | --- | --- |
| Hobby | $0.49 | $0.49 | $12.25 |
| Startup | $0.149 | $0.15 | $3.73 |
| Business | ≈$0.0997 | $0.10 | $2.49 |
| Scaling | $0.095 | $0.10 | $2.38 |
| Professional | ≈$0.0929 | $0.09 | $2.32 |
| Advanced | ≈$0.0919 | $0.09 | $2.30 |

Figures are calculated from the plan prices above and the official credit costs, not measured.

The Google column is where the plan choice shows up. The same search costs 25 credits on every plan, so 1,000 searches run $12.25 on Hobby and roughly $2.30 on Advanced. That is a fivefold difference in unit price for identical data. If SERP scraping is a serious part of your workload, the larger plan pays for itself through the price per credit rather than through extra features.

At the other end, 1,000 LinkedIn profiles cost $14.70 on Hobby and 1,000 rendered pages cost $4.90. Run the same arithmetic across your own mix before comparing plan sizes.

## Where the billing rules bite

**Credits do not roll over.** Your balance resets on each renewal date and unused credits are lost. A quarterly crawl that needs 300,000 credits once will still pay for three Hobby months, and two of them will be idle.

**Hobby, Startup and Business do not have overage billing.** When credits run out, requests come back as 429 and scraping pauses until renewal. There is no surprise invoice, and there is also no automatic continuation. Your options are to upgrade, wait, or ask support for a custom plan.

**Pay-as-you-go starts at Scaling ($475).** It bills extra usage at a fixed per-credit rate on top of the subscription, with a monthly spending cap you set in the dashboard. Professional, Advanced and Enterprise include it too. The published pages do not list the PAYG per-credit rate, so confirm it in the dashboard before you build a workflow that depends on it.

Watch the plan cards on the pricing page here. They show a “Pay as you go” tick on every tier, including Hobby, while the page’s own FAQ and the plan comparison both limit PAYG to Scaling and above. The FAQ is the accurate source. 👉 [Compare the Scaling plan and its pay-as-you-go option](https://www.scraperapi.com/pricing?fp_ref=coupons)

**Auto-upgrade is opt-in and available on Hobby, Startup, Business, Scaling and Professional.** Turn it on and your account moves to the next tier when credits run dry instead of returning 429s. That is convenient and also the easiest way to double a monthly bill without noticing.

**Concurrency limits return 429 as well.** Send more simultaneous requests than your thread count and the excess is refused, not queued, with no extra charge. Hobby allows 20 threads, Advanced 500.

**Custom Enterprise deals carry a floor on Ultra Premium.** Accounts on a discounted custom agreement pay a higher credit cost per request on Ultra Premium domains, so that the effective price still meets a minimum of $3 per 1,000 requests without rendering and $7 per 1,000 with rendering. A negotiated discount does not make ultra premium cheap.

## Check the cost before you run the job

Three tools give you the real number instead of an estimate:

Every response includes an `sa-credit-cost` header showing what that specific request consumed. Log it and you have a per-URL price list after a day of running.

The cost endpoint at `/account/urlcost` accepts the same parameters as a normal request, including `premium`, `render` and `ultra_premium`, so you can price a request exactly before sending it at scale.

The Domain Cost Estimator in the dashboard prices any URL, and the `max_cost` parameter caps what a single request is allowed to spend.

Use them on ten representative URLs from each target site rather than on the homepage. The homepage is usually the cheapest page on a domain. Product pages, search results and anything behind a bot wall are where the credits go. 👉 [Open the pricing page and start with the 7-day, 5,000-credit trial](https://www.scraperapi.com/pricing?fp_ref=coupons)

## DataPipeline is priced on a separate table

If you schedule jobs in DataPipeline rather than calling the API directly, the project page shows its own credit estimates, and parameter combinations are priced in different tiers than single API requests. A plain request inside a project is still 1 credit. Price the job from the estimate shown on the project page, not from the API table above.

## FAQ

**Does one request equal one credit?**
No. Only a plain page on an unprotected domain costs 1. Amazon is 5, Google and Bing are 25, LinkedIn is 30, and bypass or rendering parameters push it higher, up to 75 for ultra premium with rendering.

**Do unused credits carry over to the next month?**
They do not. The balance resets at each renewal. Upgrades and downgrades are available at any time from the billing page, and annual plans can renew early for a fresh batch.

**Does `render=true` always add 10 credits?**
On its own, yes. Combined with `premium=true` the pair costs 25 rather than 20, and combined with `ultra_premium=true` it costs 75 rather than 40.

**Will a bigger plan reduce the credits each request costs?**
No. The multiplier is set by the domain and parameters. A bigger plan lowers the price per credit, from $0.49 on Hobby to about $0.092 on Advanced.

**Is there a refund?**
Yes, 7 days, no questions asked. The trial is 7 days with 5,000 credits and no card required, so you can price your real targets before paying anything.

## Which plan fits your workload

Scraping ordinary pages at modest volume: **Hobby at $49** gives 100,000 credits, which is 100,000 plain pages or about 20,000 Amazon pages.

Scraping Google or Bing regularly: 100,000 credits buys only 4,000 searches, so either cut frequency or move up. **Startup at $149** brings the cost of 1,000 searches down to about $3.73.

Needing proxies outside the US and EU: **Business at $299** is the entry point, and targeting is country-level only.

Needing a safety net past your monthly allowance: **Scaling at $475** is the cheapest plan with pay-as-you-go.

Testing before committing: the free 1,000 credits or the 7-day trial, then decide.

Two things to confirm before you pay. Price your actual target URLs with the cost endpoint or the Domain Cost Estimator, because a list of “normal” pages usually contains a few expensive ones. And if you are considering annual billing for the 10% discount, check that your monthly volume really fills the tier, since unused credits expire rather than accumulate.

👉 [Check the live ScraperAPI pricing page for current plan prices and the trial signup](https://www.scraperapi.com/pricing?fp_ref=coupons)
