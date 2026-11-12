# Keyless endpoints for demand evidence

Tested with the built-in WebFetch on 2026-11-11 (topic: a generic "bookmark manager"). Recheck before relying on one: these are third-party services and can change or block.

## Rules for every endpoint
- The privacy choice from the interview applies. Under "no web search" use none of these. Under "generalized only" put only category terms in the `<term>` slot, never the product name or mechanic.
- No key and no login. If an endpoint asks for either, stop and record UNVERIFIED in Gaps.
- WebFetch returns a small-model summary, not raw bytes. In the fetch prompt, ask for the exact field names and values, and copy that text as the ledger quote. A number counts as READ only if the quote contains it.
- Keep within the call budget. Rate limits: GitHub 60 requests per hour and 10 searches per minute per IP; iTunes about 20 per minute.
- These numbers are interest or adoption signals (E1 at best). They are not proof that people will pay.
- Record the date and the full URL in the ledger. Mark the source tier: official for the platform's own API, aggregator for estimates.

## Endpoints that worked
| Source | Signal | URL pattern | Fields to quote | Suits |
|---|---|---|---|---|
| Hacker News search (Algolia) | Community interest: points, comments, dates | `https://hn.algolia.com/api/v1/search?query=<term>&tags=story&hitsPerPage=10` (also `search_by_date`, `tags=show_hn`) | `nbHits`, per hit `title`, `points`, `num_comments`, `created_at`, `objectID` | apps, products, services, dev tools (skews technical) |
| Hacker News item | Re-check one thread | `https://hacker-news.firebaseio.com/v0/item/<id>.json` | `score`, `descendants`, `time`, `url` | same |
| GitHub repository search | Rival open-source projects | `https://api.github.com/search/repositories?q=<term>&sort=stars&per_page=10` | `total_count`, per repo `full_name`, `stargazers_count`, `open_issues_count`, `pushed_at` | apps, dev tools, self-hosted services |
| GitHub repository | Adoption and upkeep of one rival | `https://api.github.com/repos/<owner>/<repo>` | `stargazers_count`, `forks_count`, `open_issues_count`, `subscribers_count`, `created_at`, `pushed_at` | same |
| Apple iTunes search | Competitor apps with ratings | `https://itunes.apple.com/search?term=<term>&entity=software&limit=10&country=us` | `trackName`, `averageUserRating`, `userRatingCount`, `price`, `currentVersionReleaseDate` | apps, games (ratings are per country) |
| Apple iTunes lookup | One app by id | `https://itunes.apple.com/lookup?id=<appid>&country=us` | same fields | apps, games |
| Chrome Web Store listing | Users, rating, rating count | `https://chromewebstore.google.com/detail/<name>/<id>` | user count, rating, number of ratings | browser extensions |
| Steam store | Game price and review totals | `https://store.steampowered.com/api/appdetails?appids=<id>`; reviews: `https://store.steampowered.com/appreviews/<id>?json=1` | `price_overview`, `recommendations.total`, `metacritic.score`, `release_date` | PC games |
| npm downloads | Package downloads | `https://api.npmjs.org/downloads/point/last-month/<package>` | `downloads`, `start`, `end` | dev tools, libraries |
| PyPI downloads | Package downloads | `https://pypistats.org/api/packages/<package>/recent` | `last_day`, `last_week`, `last_month` (include mirrors and CI bots) | dev tools, libraries |
| Wikipedia search | Does the topic have an article; find its title | `https://en.wikipedia.org/w/api.php?action=query&list=search&srsearch=<term>&format=json&srlimit=5` | `totalhits`, result titles | any known concept |
| Wikipedia pageviews | Public interest over time | `https://wikimedia.org/api/rest_v1/metrics/pageviews/per-article/en.wikipedia/all-access/user/<Article_Title>/monthly/<YYYYMMDD>/<YYYYMMDD>` | monthly `views` | topics with an article; check the article was not renamed or redirected, and ignore the last partial month |

Weak or unreliable, use with a label: Product Hunt product pages (the summarizer once guessed unlabeled columns, so quote the labels), Similarweb free page (an estimate, vendor tier, one manual lookup per rival, scraping discouraged), npm search (loose text matches).

## Do not spend calls on these (refused or empty in testing)
reddit.com and old.reddit.com, Stack Exchange and Stack Overflow, web.archive.org (the availability API works but the snapshot cannot be opened), Google Trends (HTTP 429), Google Play listings and YouTube channel pages (no figures), Social Blade and AppBrain (HTTP 403), PullPush (HTTP 526). Record "expected to fail, not fetched" in Gaps. For evidence from these, use the manual paste step in the research skill.
