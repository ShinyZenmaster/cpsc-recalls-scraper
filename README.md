[Cpsc Recalls Scraper](https://apify.com/parseforge/cpsc-recalls-scraper?fpr=data)

![ParseForge Banner](https://images.apifyusercontent.com/RHzPvdHJ2joNXJHSWjeziGDTOTaycOsfmbNq9q8ZVRM/w:1800/cb:1/aHR0cHM6Ly9yYXcuZ2l0aHVidXNlcmNvbnRlbnQuY29tL1BhcnNlRm9yZ2UvYXBpZnktYXNzZXRzL21haW4vYmFubmVyLmpwZw.webp)

# ⚠️ CPSC Consumer Product Recalls Scraper

> 🚀 Collect structured recall data from the U.S. Consumer Product Safety Commission, including hazards, remedies, manufacturers, retailers, and images. 100 recalls in about 1.5 seconds.

> 🕒 Last updated: 2026-04-23

CPSC Recalls Scraper pulls consumer product recall records from SaferProducts.gov. Each record includes the recall title, date, product name, hazard description, remedy instructions, number of units affected, manufacturer names, countries of origin, retailer names, UPC codes, and image URLs. You can filter by date range and search by keyword to find recalls related to specific products or hazard types.

Retailers use this to monitor recalls daily and pull affected products from shelves. Compliance teams build audit-ready databases of recalls in their product categories. Insurance professionals assess product liability exposure. Journalists and consumer advocates track safety trends. If you need recall data in a structured format instead of browsing HTML pages one at a time, this actor delivers it in seconds.

| Target | U.S. Consumer Product Safety Commission (CPSC) |
| --- | --- |
| Use Cases | Product safety monitoring, retail compliance, liability assessment, consumer advocacy |

---

## 📋 What it does

- ⚠️ **Recall details.** Full descriptions, hazard types, and injury reports for every recalled product.
- 🏭 **Manufacturer data.** Company names and countries of origin for tracing supply chain exposure.
- 🏪 **Retailer information.** Which stores and distributors sold the recalled products.
- 🔧 **Remedy instructions.** What consumers should do: refund, repair, replacement, or disposal.
- 🔍 **Search and filter.** Narrow results by date range and keyword to find exactly what you need.

Each record gives you 25+ fields covering the full recall lifecycle: what was recalled, why, how many units, who made it, who sold it, and what consumers should do about it.

> 💡 **Why it matters:** The CPSC publishes hundreds of recalls per year. Manually checking the website daily and copying data into spreadsheets is slow and error-prone. This actor automates the entire process and delivers clean, structured records.

---

## 🎬 Full Demo

*🚧 Coming soon: a 3-minute walkthrough showing how to go from sign-up to a downloaded dataset.*

---

## ⚙️ Input

| Input | Type | Default | Behavior |
| --- | --- | --- | --- |
| `maxItems` | integer | `10` | Maximum recalls to return. Free users are limited to 10. Paid users can set up to 1,000,000. |
| `dateFrom` | string | Last 12 months | Only include recalls from this date (YYYY-MM-DD format). |
| `dateTo` | string | Today | Only include recalls up to this date (YYYY-MM-DD format). |
| `searchQuery` | string | - | Filter recalls by keyword in title or description (e.g. "battery", "children", "fire"). |

**Example: recent children's product recalls.**

```
{
  "maxItems": 100,
  "dateFrom": "2026-01-01",
  "searchQuery": "children"
}
```

**Example: all battery-related recalls in 2025.**

```
{
  "maxItems": 500,
  "dateFrom": "2025-01-01",
  "dateTo": "2025-12-31",
  "searchQuery": "battery fire"
}
```

> ⚠️ **Good to Know:** The SaferProducts.gov database contains thousands of recalls going back many years. The default date range covers the last 12 months. Expand the range by setting an earlier dateFrom value.

---

## 📊 Output

Each record contains **25+ fields**. Download as CSV, Excel, JSON, or XML.

### 🧾 Schema

| Field | Type | Example |
| --- | --- | --- |
| 🔗 `url` | string | `"https://www.cpsc.gov/Recalls/2026/..."` |
| 📋 `title` | string | `"Children's Toys Recalled Due to Choking Hazard"` |
| 📅 `recallDate` | string | `"2026-04-02"` |
| 📦 `productName` | string | `"Beestech Spiral Tower Toy"` |
| ⚠️ `hazard` | string | `"Small parts pose choking hazard"` |
| 🔧 `remedy` | string | `"Contact seller for refund"` |
| 📊 `numberOfUnits` | string | `"About 500"` |
| 🏭 `manufacturers` | array | `["Beestech"]` |
| 🏪 `retailers` | array | `["Amazon.com"]` |
| 🌍 `manufacturerCountries` | array | `["China"]` |
| 📸 `images` | array | `["https://cpsc.gov/...jpg"]` |
| 🏷️ `recallNumber` | string | `"26365"` |

### 📦 Sample records

 
 
 

---

## ✨ Why choose this Actor

|  | Capability |
| --- | --- |
| ⚡ | **Fast collection.** 100 recalls in about 1.5 seconds. |
| 📊 | **25+ fields per record.** Hazards, remedies, manufacturers, retailers, UPC codes, and images. |
| 🔍 | **Keyword search.** Find recalls by product type, hazard, or brand name. |
| 📅 | **Date filtering.** Narrow results to any time period you need. |
| 🏭 | **Supply chain data.** Manufacturer names and countries of origin for traceability. |
| 📸 | **Image URLs.** Direct links to recall-related product images. |
| 🔄 | **Schedulable.** Run daily to catch new recalls as they are published. |

> The CPSC publishes 400 to 500 consumer product recalls per year. Staying on top of them manually requires daily visits to the website.

---

## 📈 How it compares to alternatives

| Approach | Cost | Coverage | Refresh | Setup |
| --- | --- | --- | --- | --- |
| **⭐ CPSC Recalls Scraper** *(this Actor)* | $5 free credit, then pay-per-use | All CPSC recalls, 25+ fields | **Live per run** | ⚡ 2 min |
| Official API (direct) | Free | Full, but requires pagination code | Real-time | 30 min |
| Manual browsing | Free (your time) | One recall at a time | Manual | Slow |
| Third-party data providers | $200+/month | Varies | Daily or weekly | Days |

Pick this actor when you need structured recall data without writing API integration code or parsing HTML.

---

## 🚀 How to use

1. 📝 **Sign up.** [Create a free account with $5 credit](https://console.apify.com/sign-up?fpr=vmoqkp) (takes 2 minutes).
2. 🌐 **Open the Actor.** Go to the CPSC Recalls Scraper page on the Apify Store.
3. 🎯 **Set input.** Enter a date range and optional keyword filter. Set your max items.
4. 🚀 **Run it.** Click **Start** and let the Actor collect your data.
5. 📥 **Download.** Grab your results in the **Dataset** tab as CSV, Excel, JSON, or XML.

> ⏱️ Total time from signup to downloaded dataset: **3-5 minutes.** No coding required.

---

## 💼 Business use cases

| ### 🏪 Retail Compliance     - Monitor recalls daily to remove affected products from shelves - Cross-reference UPC codes against your inventory system - Build internal recall notification workflows - Maintain audit trails for regulatory inspections | ### 🏭 Manufacturing and Supply Chain     - Track recalls from competitors in your product category - Monitor manufacturer countries for supply chain risk - Identify recurring hazard types in your industry - Feed data into product safety management systems |
| --- | --- |
| ### ⚖️ Legal and Insurance     - Research recall history for product liability cases - Assess exposure by tracking units recalled per manufacturer - Build databases of hazards for risk modeling - Monitor remedy compliance rates over time | ### 📰 Research and Journalism     - Investigate product safety trends across categories - Track recall volumes by country of origin - Analyze which retailers appear most frequently in recalls - Build data-driven stories about consumer safety |

---

---

## 🌟 Beyond business use cases

Data like this powers more than commercial workflows. The same structured records support research, education, civic projects, and personal initiatives.

| ### 🎓 Research and academia     - Empirical datasets for papers, thesis work, and coursework - Longitudinal studies tracking changes across snapshots - Reproducible research with cited, versioned data pulls - Classroom exercises on data analysis and ethical scraping | ### 🎨 Personal and creative     - Side projects, portfolio demos, and indie app launches - Data visualizations, dashboards, and infographics - Content research for bloggers, YouTubers, and podcasters - Hobbyist collections and personal trackers |
| --- | --- |
| ### 🤝 Non-profit and civic     - Transparency reporting and accountability projects - Advocacy campaigns backed by public-interest data - Community-run databases for local issues - Investigative journalism on public records | ### 🧪 Experimentation     - Prototype AI and machine-learning pipelines with real data - Validate product-market hypotheses before engineering spend - Train small domain-specific models on niche corpora - Test dashboard concepts with live input |

## 🤖 Ask an AI assistant about this scraper

Open a ready-to-send prompt about this ParseForge actor in the AI of your choice:

- 💬 [**ChatGPT**](https://chat.openai.com/?q=How%20do%20I%20use%20the%20CPSC%20Consumer%20Product%20Recalls%20Scraper%20by%20ParseForge%20on%20Apify%3F%20Show%20me%20input%20examples%2C%20output%20fields%2C%20common%20use%20cases%2C%20and%20how%20to%20integrate%20it%20into%20a%20workflow.)
- 🧠 [**Claude**](https://claude.ai/new?q=How%20do%20I%20use%20the%20CPSC%20Consumer%20Product%20Recalls%20Scraper%20by%20ParseForge%20on%20Apify%3F%20Show%20me%20input%20examples%2C%20output%20fields%2C%20common%20use%20cases%2C%20and%20how%20to%20integrate%20it%20into%20a%20workflow.)
- 🔍 [**Perplexity**](https://perplexity.ai/search?q=How%20do%20I%20use%20the%20CPSC%20Consumer%20Product%20Recalls%20Scraper%20by%20ParseForge%20on%20Apify%3F%20Show%20me%20input%20examples%2C%20output%20fields%2C%20common%20use%20cases%2C%20and%20how%20to%20integrate%20it%20into%20a%20workflow.)
- 🅒 [**Copilot**](https://copilot.microsoft.com/?q=How%20do%20I%20use%20the%20CPSC%20Consumer%20Product%20Recalls%20Scraper%20by%20ParseForge%20on%20Apify%3F%20Show%20me%20input%20examples%2C%20output%20fields%2C%20common%20use%20cases%2C%20and%20how%20to%20integrate%20it%20into%20a%20workflow.)

## ❓ Frequently Asked Questions

### 💳 Do I need a paid Apify plan to run this actor?

No. You can start right now on the free Apify plan, which includes **$5 in free monthly credit**. That is enough to run this actor several times and explore the output before committing to anything. Paid plans unlock higher limits, more concurrent runs, and larger datasets. [Create a free Apify account here](https://console.apify.com/sign-up?fpr=vmoqkp) to get started.

### 🚨 What happens if my run fails or returns no results?

Failed runs are not charged. If the source site changes, proxies get rate-limited, or a specific input matches nothing, re-run the actor or open our [contact form](https://tally.so/r/BzdKgA) and we will investigate. You can also check the run log in the Apify console to see why the run stopped.

### 📏 How many items can I scrape per run?

Free users are limited to **10 items per run** so you can preview the output and confirm the actor works for your use case. Paid users can raise `maxItems` up to **1,000,000** per run. [Upgrade here](https://console.apify.com/sign-up?fpr=vmoqkp) if you need full scale.

### 🕒 How fresh is the data?

Every run fetches live data at the moment of execution. There is no cache or delay: the records you get reflect what the source returned at that moment. Schedule the actor to maintain a rolling snapshot of the data you need.

### 🧑‍💻 Can I call this actor from my own code?

Yes. Apify exposes every actor as a REST endpoint and ships first-class SDKs for [Node.js](https://docs.apify.com/sdk/js) and [Python](https://docs.apify.com/sdk/python). You can start a run, read the dataset, and handle webhooks from your own app in a few lines. All you need is your Apify API token.

### 📤 How do I export the data?

Every Apify dataset can be downloaded in one click from the console as CSV, JSON, JSONL, Excel, HTML, XML, or RSS. You can also pull results programmatically via the [Apify API](https://docs.apify.com/api/v2) or stream them into BigQuery, S3, and other destinations through built-in integrations.

### 📅 Can I schedule the actor to run automatically?

Yes. Use the Apify scheduler to run the actor on any cadence, from hourly to monthly. Results are saved to your dataset and can be delivered to webhooks, email, Slack, cloud storage, or automation tools such as Zapier and Make.

---

## 🔌 Automating CPSC Recalls Scraper

Control the scraper programmatically for scheduled runs and pipeline integrations:

- 🟢 **Node.js.** Install the `apify-client` NPM package.
- 🐍 **Python.** Use the `apify-client` PyPI package.
- 📚 See the [Apify API documentation](https://docs.apify.com/api/v2) for full details.

The [Apify Schedules feature](https://docs.apify.com/platform/schedules) lets you trigger this Actor on any cron interval. Set up a daily run to catch new recalls as soon as they are published.

## 🔌 Integrate with any app

CPSC Recalls Scraper connects to any cloud service via [Apify integrations](https://apify.com/integrations):

- [**Make**](https://docs.apify.com/platform/integrations/make) - Automate multi-step workflows
- [**Zapier**](https://docs.apify.com/platform/integrations/zapier) - Connect with 5,000+ apps
- [**Slack**](https://docs.apify.com/platform/integrations/slack) - Get run notifications
- [**Airbyte**](https://docs.apify.com/platform/integrations/airbyte) - Pipe data into your warehouse
- [**GitHub**](https://docs.apify.com/platform/integrations/github) - Trigger runs from commits
- [**Google Drive**](https://docs.apify.com/platform/integrations/drive) - Export datasets straight to Sheets

You can also use webhooks to trigger downstream actions when a run finishes.

---

## 🔗 Recommended Actors

- [**💊 FDA Recalls Scraper**](https://apify.com/parseforge/fda-recalls-scraper) - Collect food, drug, and device recall data from the FDA
- [**📜 Federal Register Scraper**](https://apify.com/parseforge/federal-register-regulatory-notices-rules-scraper) - Extract regulatory notices and rules
- [**💰 Grants.gov Scraper**](https://apify.com/parseforge/grants-gov-scraper) - Search federal grant opportunities
- [**📋 GSA eLibrary Scraper**](https://apify.com/parseforge/gsa-elibrary-scraper) - Government contract and schedule data
- [**✈️ FAA Aircraft Registry Scraper**](https://apify.com/parseforge/faa-aircraft-registry-scraper) - Aircraft registration lookup by N-number

> 💡 **Pro Tip:** browse the complete [ParseForge collection](https://apify.com/parseforge) for more data scrapers and tools.

---

**🆘 Need Help?** [**Open our contact form**](https://tally.so/r/BzdKgA) to request a new scraper, propose a custom data project, or report an issue.

---

> **⚠️ Disclaimer:** this Actor is an independent tool and is not affiliated with, endorsed by, or sponsored by the U.S. Consumer Product Safety Commission (CPSC). All trademarks mentioned are the property of their respective owners. Only publicly available data is collected.