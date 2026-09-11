# Web Scraping Projects

My Python scraping projects explore three approaches: browser automation with Selenium, request-based crawling with Scrapy, and HTML parsing with Requests and Beautiful Soup. They include pagination, structured extraction, and file or database output.

The descriptions below reflect the checked-in implementations. **Not recently verified** means the scraper has not been checked against its target website in a recent live run; existing output files are historical examples.

| Project | Purpose | Technique | Output in the repository or implementation | Verification status |
| --- | --- | --- | --- | --- |
| [TikTok-Scraper](https://github.com/raziullah7/TikTok-Scraper) | Collect public profile video URLs and engagement metadata | Selenium, explicit waits, scrolling, URL deduplication, compact-count parsing | JSON to stdout or a chosen file; per-video error entries | Not recently verified |
| [Scraping-Twitter-with-Selenium](https://github.com/raziullah7/Scraping-Twitter-with-Selenium) | Historical experiment collecting user handles and tweet text from search results | Selenium, login flow, XPath, explicit waits, infinite scrolling, deduplication | Pandas export to `tweets_infinite_scrolling.csv` | Not recently verified |
| [Scraping-Audible-With-a-Headless-Bot](https://github.com/raziullah7/Scraping-Audible-With-a-Headless-Bot) | Extract audiobook titles, authors, and lengths across result pages | Headless Selenium, XPath, explicit waits, next-page navigation | Printed Pandas DataFrame; historical CSV files included, with CSV-writing calls currently commented out | Not recently verified |
| [Scraping-Audible-with-Scrapy](https://github.com/raziullah7/Scraping-Audible-with-Scrapy) | Extract audiobook catalogue metadata | Scrapy spider, XPath extraction, next-page requests | Structured title, author, and length items; CSV examples included | Not recently verified |
| [Scrapy-Crawler-for-SubsLikeScript](https://github.com/raziullah7/Scrapy-Crawler-for-SubsLikeScript) | Follow movie listing links and extract transcript records | Scrapy `CrawlSpider`, link-extraction rules, pagination, SQLite item pipeline | `transcripts.db` with title, plot, transcript, and URL; CSV example also included | Not recently verified |
| [Scraping-quotes.toscrape.com-Api](https://github.com/raziullah7/Scraping-quotes.toscrape.com-Api) | Collect quotes, authors, and tags from a practice site's JSON endpoint | Scrapy, JSON parsing, pagination using `has_next`; separate form-login exercise | Structured items with CSV and JSON examples included | Not recently verified |
| [Transcript-Scraper-of-Movies-with-Pagination](https://github.com/raziullah7/Transcript-Scraper-of-Movies-with-Pagination) | Follow movie links from the first two pages of an alphabetical listing | Requests, Beautiful Soup with lxml, pagination, per-link exception handling | Titles and transcripts printed to the terminal; text-file writing currently commented out | Not recently verified |
| [Beautiful-Soup](https://github.com/raziullah7/Beautiful-Soup) | Extract a title and transcript from a single movie page | Requests, Beautiful Soup with lxml, HTML element selection | UTF-8 text file named after the page title | Not recently verified |
| [Beginner-Project-ChocolateScraper](https://github.com/raziullah7/Beginner-Project-ChocolateScraper) | Extract product names, prices, and links from a chocolate catalogue | Scrapy, CSS selectors, next-page links | Structured product items with CSV and JSON examples included | Not recently verified |

## Where to start

- **Browser automation:** [TikTok's implementation and guide](https://github.com/raziullah7/TikTok-Scraper/tree/main/tiktok_selenium_scraper) includes a configurable CLI and helper tests.
- **Crawling with persistence:** [SubsLikeScript's spider](https://github.com/raziullah7/Scrapy-Crawler-for-SubsLikeScript/blob/main/TranscriptScraper/TranscriptScraper/spiders/transcripts.py) works with an enabled [SQLite pipeline](https://github.com/raziullah7/Scrapy-Crawler-for-SubsLikeScript/blob/main/TranscriptScraper/TranscriptScraper/pipelines.py).
- **API pagination:** [The quotes spider](https://github.com/raziullah7/Scraping-quotes.toscrape.com-Api/blob/main/api_project/api_project/spiders/quotes.py) follows the JSON response's pagination fields.
- **Comparing approaches:** The Audible projects demonstrate the same extraction task through [headless browser navigation](https://github.com/raziullah7/Scraping-Audible-With-a-Headless-Bot/blob/master/main.py) and [Scrapy requests](https://github.com/raziullah7/Scraping-Audible-with-Scrapy/blob/main/AudibleScraper/AudibleScraper/spiders/audible.py).

These are separate educational projects with their own setup assumptions and output formats. The collection shows the techniques explored; it is not a maintained scraping service or a claim that every target remains compatible.
