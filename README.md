# Page Time Machine · Wayback Diff + AI · No Login · $2.5/1K

See how any web page looked in the past, as **clean text**, and **what changed** from one version to the next. Versions come from several web archives in one run: the **Internet Archive Wayback Machine**, **Arquivo.pt** and **Common Crawl**, plus the list of **archive.today** snapshots. Optionally, an **AI summary** says in plain words what changed ("Starter plan went from $49 to $39"). It also tells you if the page was **deleted** and where its last good copy is.

**[Run it on Apify](https://apify.com/pomlabs/page-time-machine?utm_source=github&utm_medium=readme&utm_campaign=page-time-machine)**: no install, no login, free credit on a new Apify account.

## What you get

- **Distinct versions only**: the Wayback CDX `collapse=digest` trick plus a text fingerprint, so 200 identical captures don't cost you 200 rows
- **Clean text** of each version (main content, without menus, scripts and the Wayback toolbar), with the page title and size
- **What changed**: lines added and removed versus the previous version, and a similarity score
- **AI summary** of each change (optional): 1 to 4 bullet points about prices, plans, products, people, claims and policies
- **Was it deleted?** The live URL is checked today (online, deleted 404/410, redirected, blocked) and the last archived version is returned
- **Several archives in one run**: Wayback Machine, Arquivo.pt (strong on European and Portuguese-language sites), Common Crawl (last 2 monthly crawls) and archive.today (snapshot dates and links)
- **Keyword filter**: keep only versions that mention a word ("refund", "free plan", a person's name)
- **Date range**: from/to as YYYY, YYYY-MM or YYYY-MM-DD; versions are spread evenly over the period, always with the first and the last

## Pricing

**No login, no API key. You pay only for versions delivered: $0.0025 per version ($2.50 per 1,000).** Identical versions are skipped and never charged.

That is the free-plan price; Apify paid plans (Bronze, Silver, Gold) pay less per item.

## Call it by API

```bash
curl -X POST "https://api.apify.com/v2/acts/pomlabs~page-time-machine/run-sync-get-dataset-items?token=YOUR_APIFY_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"urls": ["https://apify.com/pricing"]}'
```

Python:

```python
from apify_client import ApifyClient

client = ApifyClient("YOUR_APIFY_TOKEN")
run = client.actor("pomlabs/page-time-machine").call(run_input={"urls": ["https://apify.com/pricing"]})
for item in client.dataset(run["defaultDatasetId"]).iterate_items():
    print(item)
```

## Use it from Claude, Cursor or any MCP client

```bash
claude mcp add page-time-machine "https://mcp.apify.com?tools=pomlabs/page-time-machine" -t http
```

## More Actors by Pom Labs

- [YouTube Transcript Scraper: Translate, No Login · $3/1K](https://apify.com/pomlabs/youtube-transcript-scraper?utm_source=github&utm_medium=readme&utm_campaign=page-time-machine)
- [Instagram Transcript Scraper: Reels, TikTok, Facebook, Hook](https://apify.com/pomlabs/social-video-transcript?utm_source=github&utm_medium=readme&utm_campaign=page-time-machine)
- [Reddit Scraper: Deleted & Removed, Mods, Hidden Profiles](https://apify.com/pomlabs/reddit-posts-comments-scraper?utm_source=github&utm_medium=readme&utm_campaign=page-time-machine)
- [LinkedIn Company Scraper (No Cookies): Posts, Similar Companies](https://apify.com/pomlabs/linkedin-company-scraper?utm_source=github&utm_medium=readme&utm_campaign=page-time-machine)
- [YouTube Comments Scraper + Replies, Shorts · No API Key · $1/1K](https://apify.com/pomlabs/youtube-comments-scraper?utm_source=github&utm_medium=readme&utm_campaign=page-time-machine)
- [Instagram Profile Scraper: Exact Followers, Reels Views](https://apify.com/pomlabs/instagram-profile-data?utm_source=github&utm_medium=readme&utm_campaign=page-time-machine)
- [LinkedIn Profile Scraper (No Cookies) + Similar Profiles](https://apify.com/pomlabs/linkedin-profile-scraper?utm_source=github&utm_medium=readme&utm_campaign=page-time-machine)
- [Threads Scraper: Keyword Search, Posts & Profiles · No Login](https://apify.com/pomlabs/threads-scraper?utm_source=github&utm_medium=readme&utm_campaign=page-time-machine)
- [AliExpress Scraper: Exact Units Sold, Prices, Search · $1/1K](https://apify.com/pomlabs/aliexpress-scraper?utm_source=github&utm_medium=readme&utm_campaign=page-time-machine)
- [AI Brand Visibility Tracker - ChatGPT, Claude & Perplexity](https://apify.com/pomlabs/ai-brand-visibility?utm_source=github&utm_medium=readme&utm_campaign=page-time-machine)
- [Mercado Livre & Amazon BR Coupon Code Checker](https://apify.com/pomlabs/mercadolivre-coupon-checker?utm_source=github&utm_medium=readme&utm_campaign=page-time-machine)
- [Video Downloader: TikTok No Watermark, Instagram, YouTube, X](https://apify.com/pomlabs/video-downloader?utm_source=github&utm_medium=readme&utm_campaign=page-time-machine)
- [NSFW Image Detector & Image Tagger - Moderation + Categories](https://apify.com/pomlabs/image-moderation-tagger?utm_source=github&utm_medium=readme&utm_campaign=page-time-machine)
- [Google Trends Scraper: Related Queries, No 429 · $2/1K](https://apify.com/pomlabs/google-trends-scraper?utm_source=github&utm_medium=readme&utm_campaign=page-time-machine)

Full documentation, input fields and output format: [Page Time Machine · Wayback Diff + AI · No Login · $2.5/1K on Apify](https://apify.com/pomlabs/page-time-machine?utm_source=github&utm_medium=readme&utm_campaign=page-time-machine).
