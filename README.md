# SerpAPI vs ScraperAPI: Which One Is Cheaper at Your Monthly Volume? Plans, Credit Math, and the Crossover Point (Full Pricing Tables)

At 5,000 Google searches a month, SerpAPI costs $75 and ScraperAPI costs $149. Past roughly 15,000 searches a month the ordering flips: ScraperAPI's Startup plan covers about 40,000 SERPs for $149 ($3.73 per 1,000), while SerpAPI's next step above 15,000 searches is $275 for 30,000. Everything below is the plan math for both tools, the credit rules ScraperAPI hides in its docs rather than its pricing page, and the point where each one stops being the sensible buy.

Prices are USD, billed monthly, read from both vendors' pricing pages in early November 2026. Annual ScraperAPI pricing is the same page with the 10% annual discount applied.

> **Quick picks**
> - Pure Google SERP work under ~15,000 searches a month: SerpAPI Developer ($75 for 5,000) or Production ($150 for 15,000).
> - Mixed scraping that includes SERP, or more than ~15,000 SERPs a month: ScraperAPI Startup ($149 for ~40,000 SERPs), Business ($299) once you need country targeting outside the US and EU.
> - E-commerce or directory targets (Amazon, Walmart, Etsy, Zillow): ScraperAPI, where Business's 3M credits cover roughly 600,000 Amazon product pages at 5 credits each.
>
> 👉 [Compare ScraperAPI's plans on the official pricing page](https://www.scraperapi.com/pricing/?fp_ref=coupons)

## ScraperAPI plans and prices

ScraperAPI sells credits, not searches, and the credit cost per request changes with the target site and the parameters you switch on. The "≈ Google SERPs" column below uses the documented rate of 25 credits per Google or Bing search, with no rendering or premium proxy added.

| Plan | Credits/month | ≈ Google SERPs | Price/month (annual) | Limits that affect real use |  |
| --- | --- | --- | --- | --- | --- |
| Hobby | 100,000 | ~4,000 | $49 ($44.10) | 20 threads, US/EU targeting only, hard stop at 0 credits | [ Hobby pricing](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Startup | 1,000,000 | ~40,000 | $149 ($134.10) | 50 threads, US/EU targeting only, no pay-as-you-go | [ Startup pricing](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Business | 3,000,000 | ~120,000 | $299 ($269.10) | 100 threads, 50+ countries, DataPipeline and async scraper included | [ Business pricing](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Scaling | 5,000,000 | ~200,000 | $475 ($427.50) | 200 threads, pay-as-you-go overflow unlocks here | [ Scaling pricing](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Enterprise | Custom | Custom | Custom quote | Negotiated volume, concurrency and targeting | [ Request Enterprise pricing](https://www.scraperapi.com/pricing/?fp_ref=coupons) |

There's a 7-day trial with 5,000 credits that doesn't ask for a card. ScraperAPI's current pricing material advertises the trial and nothing more; a recurring monthly free allowance isn't confirmed there, so plan on paying after day seven.

Annual billing takes exactly 10% off every tier. On Hobby that's about $59 saved across the year, on Scaling about $570. Nothing else changes between monthly and annual: same credits, same thread caps, same geo restrictions.

## SerpAPI plans and prices

SerpAPI bills per successful search. Failed, errored and cached searches don't count, and a response with 100 results costs the same as one with zero.

| Plan | Searches/month | Price/month | Per 1,000 | Hourly cap |
| --- | --- | --- | --- | --- |
| Free | 250 | $0 | — | 50/hr |
| Starter | 1,000 | $25 | $25.00 | 200/hr |
| Developer | 5,000 | $75 | $15.00 | 1,000/hr |
| Production | 15,000 | $150 | $10.00 | 3,000/hr |
| Big Data | 30,000 | $275 | ≈$9.17 | 6,000/hr |
| Searcher | 100,000 | $725 | ≈$7.25 | 20,000/hr |
| Volume | 250,000 | $1,475 | $5.90 | 50,000/hr |
| Infrastructure | 500,000 | $2,750 | $5.50 | 100,000/hr |
| Cloud 1M | 1,000,000 | $3,750 | $3.75 | 110,000/hr |
| Enterprise | Custom | Custom quote | Custom | Custom |

Two details matter more than the headline price. Unused searches expire at each billing reset, so a spiky workload pays for its peak month every month. Hourly caps also constrain speed: Starter allows 200 searches an hour, which is 3.3 a minute no matter how many of your 1,000 searches are left. If a job has to finish fast, you may need a bigger plan than your monthly volume suggests.

SerpAPI runs on month-to-month terms with no annual discount published, cancels any time, offers Automatic Early Renewal for when you burn through a plan mid-cycle, and refunds in full within 7 days if you've used under 20% of your searches. Faster response modes cost extra: Ludicrous Speed bills at 2× the plan rate and Ludicrous Speed Max at 4×.

## Why the $12.25 vs $25 comparison falls apart at 5,000 requests

$12.25 per 1,000 is Hobby's rate, and Hobby holds about 4,000 Google searches. The rate only exists at exactly 4,000 searches, because 100,000 credits divided by 25 credits per SERP leaves no room above it. A team that needs 5,000 searches a month can't buy Hobby twice; it has to move to Startup at $149, which at full capacity is $3.73 per 1,000 but at 5,000 actual searches works out to $29.80 per 1,000. SerpAPI sells those same 5,000 searches for $75.

Here's the honest side-by-side, assuming pure Google SERP volume and no rendering or premium proxies:

| Monthly Google SERPs | SerpAPI plan and cost | ScraperAPI plan and cost |
| --- | --- | --- |
| 1,000 | Starter, $25 | Hobby, $49 |
| 5,000 | Developer, $75 | Startup, $149 |
| 15,000 | Production, $150 | Startup, $149 |
| 30,000 | Big Data, $275 | Startup, $149 |
| 40,000 | Searcher, $725 | Startup, $149 |
| 100,000 | Searcher, $725 | Business, $299 |
| 200,000 | Volume, $1,475 | Scaling, $475 |

The crossover sits between 10,000 and 15,000 SERPs a month. Below it, SerpAPI is cheaper and faster and returns more fields. Above it, ScraperAPI's flat credit pools win by a wide margin, because SerpAPI's pricing jumps in steps (15,000 → 30,000 → 100,000) while ScraperAPI's Startup plan absorbs anything up to 40,000 searches for the same $149.

The comparison only holds while SERP is all you're buying. ScraperAPI credits are shared across every request type, which changes the arithmetic in both directions.

## What one ScraperAPI credit actually buys

This is the part that decides whether the cheap-looking plan is cheap. ScraperAPI's documentation sets credit costs per domain and per parameter:

- Plain HTML page: 1 credit.
- Amazon, Walmart, eBay: 5 credits.
- Google and Bing SERP: 25 credits.
- LinkedIn: 30 credits.
- Adding `render=true` or `premium=true`: 10 credits each. Both together: 25. `ultra_premium=true` alone is 30, and with rendering it's 75.
- Anti-bot bypasses (Cloudflare, DataDome, PerimeterX, Akamai): 10 credits on top.

So Hobby's 100,000 credits is 4,000 Google searches, 10,000 JavaScript-rendered pages, or 100,000 plain fetches. A Google SERP that needs rendering plus premium proxies is 50 credits, which cuts Hobby to 2,000 searches.

Six rules sit in the docs and FAQ rather than the pricing table:

1. **Credits don't roll over.** Whatever is left at the billing reset is gone.
2. **Pay-as-you-go starts at Scaling ($475).** On Hobby, Startup and Business, hitting zero stops requests until you renew or upgrade.
3. **Country targeting outside the US and EU needs Business ($299).** Hobby and Startup are locked to US/EU geo.
4. **404s consume credits, and so do cancelled requests** once processing has started.
5. **DataPipeline costs 6 credits for a basic request** versus 1 credit through the standard API.
6. **There are no proactive usage alerts.** You check the dashboard yourself.

The last one is workable if you build around it: every response carries an `sa-credit-cost` header telling you exactly what that request cost, so you can log spend per job instead of guessing. It also has a URL-cost endpoint that returns the credit price of a request before you send it.

If you're planning a mixed workload where SERP is a small slice, the shared credit pool is the reason to pick ScraperAPI at all. A Hobby plan running 2,000 SERPs (50,000 credits) and 50,000 plain page fetches fits inside $49, which no per-search SERP API can match.

👉 [Start the 7-day, 5,000-credit trial and price your own URLs](https://www.scraperapi.com/?fp_ref=coupons)

## Speed and SERP field depth

A public benchmark that several affiliate write-ups reproduce puts SerpAPI at ~1.96s average response and ScraperAPI's SERP endpoint at ~11.20s, roughly six times slower. The same test scored output richness at 3.8/5 for SerpAPI and 1.8/5 for ScraperAPI, with these per-feature results:

| SERP feature | ScraperAPI | SerpAPI |
| --- | --- | --- |
| People Also Ask | Yes | Yes |
| Sitelinks | 0% | 80% |
| Publication dates | 0% | 80% |
| Video carousels | 0% | 92% |
| Discussion forums | 0% | 48% |
| News results | 0% | 4% |
| AI Overview detection | 0% | 68% |

Treat this as one data point, not two. The identical numbers appear across multiple posts that share a template and affiliate links, so it's a single benchmark being repeated rather than independent verification. What it does align with is ScraperAPI's own documentation: its AI Overview tutorial walks you through Selenium and custom HTML extraction rather than a parsed field, and Google AI Mode is a separate endpoint. The 0% figure is consistent with that.

The other half of the picture is coverage. SerpAPI returns structured JSON for 80+ engines and verticals: Google Search, Maps, Shopping, Flights, Hotels, News, Trends, Scholar, Patents, Lens, Jobs, plus Bing, Baidu, Yandex, Yahoo, DuckDuckGo, YouTube, Amazon and app stores. ScraperAPI's structured data endpoints cover Google Search, News, Maps, Shopping and Jobs, and it has no documented parsed endpoint for Google Videos, autocomplete, Translate, knowledge panels or field selection. Its strength is everywhere else: Amazon, Walmart, eBay, Zillow, LinkedIn, Etsy and arbitrary URLs.

Where ScraperAPI does hold up on structured data: its Amazon endpoint returns 18+ fields (price, rating, images, BSR, seller info, reviews) at about 98% success and 5 credits per request. Reported success rates on other targets: Zillow 100% at 10.5s, Etsy 99% at 4.8s, Walmart 93% at 11.4s, LinkedIn 95% at 17.8s. Instagram and Booking.com came back at 0%.

## Which tool fits which job

**Rank tracking and AI visibility monitoring.** You need sitelinks, publication dates, video carousels, forum results and AI Overview presence query by query. ScraperAPI's SERP endpoint returns organic results, PAA and related searches and stops roughly there. SerpAPI is the tool, and at typical agency volumes (5,000 to 15,000 keywords a month) it's also the cheaper one.

**E-commerce and multi-site scraping.** ScraperAPI is the only one of the two that scrapes Amazon, Walmart, Etsy and Zillow with pre-parsed output at 5 credits a request. Business at $299 covers about 600,000 Amazon product pages, plus proxy rotation across 40M+ IPs in 50+ countries and JS rendering on the same credit balance. SerpAPI's Amazon endpoint is a search-results product, not a catalogue scraper.

**Pure SERP under 5,000 searches a month.** Buying ScraperAPI here costs you $149 for a job SerpAPI does for $75, and you give up sitelinks, dates, video carousels and AI Overviews in the process. Hobby at $49 only works if you genuinely need 4,000 searches or fewer, which is a narrow band.

**SERP as a minority of a bigger scraping job.** Hobby or Startup, depending on total volume. This is the scenario the per-1K comparisons ignore, and it's where ScraperAPI's shared credit pool earns its price.

## Questions people ask before choosing

**Can ScraperAPI replace SerpAPI?**
For organic results, PAA, related searches and structured JSON, yes, at 25 credits per search. For sitelinks, publication dates, video carousels, forum results and AI Overviews, the benchmark above says no, and ScraperAPI's own docs treat AI Overview extraction as a Selenium job rather than a built-in field.

**Is there a free plan or only a trial?**
ScraperAPI advertises a 7-day trial with 5,000 credits and no credit card. A recurring free monthly allowance isn't confirmed in the current pricing material, so treat the trial as an evaluation window and budget for a paid tier afterwards. SerpAPI's free tier is 250 searches a month, recurring.

**What happens when credits run out mid-month?**
On Hobby, Startup and Business, requests fail until renewal or an upgrade. Scaling ($475) and above add pay-as-you-go overflow at a fixed per-credit rate. SerpAPI handles the same situation with Automatic Early Renewal, which triggers a new billing cycle the moment your searches hit zero.

**Can I get AI Overviews from ScraperAPI?**
Not from the SERP endpoint as a parsed field. The official route is rendering the page and extracting the HTML yourself, which also means 10+ credits per request instead of 25 and your own parsing logic.

**How much does annual billing save?**
Exactly 10% on every ScraperAPI plan: $44.10, $134.10, $269.10 and $427.50 per month effective for Hobby through Scaling. Nothing else changes. SerpAPI doesn't publish an annual discount.

## Before you check out

Pick by volume and job, in this order:

- Under ~15,000 Google searches a month and SERP is the whole job: SerpAPI, Developer at $75 for 5,000 or Production at $150 for 15,000. Refund window is 7 days if you've used under 20%.
- Over ~15,000 searches a month: ScraperAPI Startup at $149 covers 40,000 SERPs. At 100,000+ move to Business, which is also the first tier with country targeting beyond the US and EU.
- Mixed scraping with SERP as a side task: Hobby at $49, sized on total credits rather than search count.
- Anything above 120,000 SERPs or an unpredictable monthly peak: Scaling at $475, because it's the first plan where running dry doesn't stop your pipeline.

Two things to settle before paying. If your targeting falls outside the US and EU, Hobby and Startup are unusable, so budget $299 minimum. If your volume swings month to month, weigh the lack of usage alerts and the no-rollover rule against annual billing: the 10% saving is real, but only if you're confident you'll use the credits every month.

👉 [Check current ScraperAPI plans and start the 5,000-credit trial](https://www.scraperapi.com/?fp_ref=coupons)
