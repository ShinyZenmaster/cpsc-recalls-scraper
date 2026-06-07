[Cpsc Recalls Scraper](https://apify.com/fortuitous_pirate/cpsc-recalls-scraper?fpr=data)

## Overview

Scrape product recall data from the U. S. Consumer Product Safety Commission (CPSC) SaferProducts.

## Features

- Search by keywords to find specific results
- Filter results by category or type
- Export data in JSON, CSV, or Excel formats
- Captures pricing information
- Captures images and media URLs
- Control output volume with configurable result limits

## Use Cases

- **Track** - Track federal government data releases and updates
- **Build** - Build datasets for policy research and analysis
- **Monitor** - Monitor regulatory changes and compliance requirements
- **Aggregate** - Aggregate public government data for transparency projects

## Input Parameters

| Parameter | Type | Description | Default |
| --- | --- | --- | --- |
| `searchQuery` | string | Search term to filter recalls by title (e.g., 'baby', 'furniture', 'toy') |  |
| `productName` | string | Filter recalls by product name (e.g., 'chair', 'crib', 'stroller') |  |
| `company` | string | Filter recalls by manufacturer, retailer, or importer name |  |
| `dateFrom` | string | Start date for recall search (YYYY-MM-DD format, e.g., '2024-01-01') |  |
| `dateTo` | string | End date for recall search (YYYY-MM-DD format, e.g., '2024-12-31') |  |
| `maxItems` | integer | Maximum number of recalls to return | `100` |

## Output Example

Each result contains structured data like this:

```
{
  "title": "Sample Government - Federal Result",
  "agency": "Department of Commerce",
  "date": "2025-01-15",
  "description": "Detailed description of the item...",
  "documentUrl": "https://example.com/item/12345",
  "category": "Standard",
  "url": "https://example.com/item/12345"
}
```

## Pricing

This actor uses pay-per-result pricing:

- **$0.001** per result
- **$1.00** per 1,000 results

No monthly fees. You only pay for what you scrape. [Apify Free plan](https://apify.com/pricing) includes $5/month in platform credits.

## How to Run

### Apify Console

1. Go to the [CPSC Product Recalls Scraper](https://apify.com/fortuitous_pirate/cpsc-recalls-scraper) actor page
2. Configure your input parameters
3. Click **Start** and wait for the results
4. Download data in JSON, CSV, or Excel format

### API

```
curl -X POST "https://api.apify.com/v2/acts/fortuitous_pirate~cpsc-recalls-scraper/runs?token=YOUR_API_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"maxItems": 10}'
```

### Python SDK

```
from apify_client import ApifyClient

client = ApifyClient("YOUR_API_TOKEN")
run = client.actor("fortuitous_pirate/cpsc-recalls-scraper").call(
    run_input={"maxItems": 10}
)

for item in client.dataset(run["defaultDatasetId"]).iterate_items():
    print(item)
```

## Integration

Connect CPSC Product Recalls Scraper with your existing tools and workflows:

- **API access** - Programmatic access via [Apify API](https://docs.apify.com/api/v2)
- **Webhooks** - Get notified when scraping completes
- **Scheduling** - Set up recurring runs on any schedule
- **Zapier / Make** - Connect with 5,000+ apps via [Apify integrations](https://apify.com/integrations)
- **Python / Node.js SDKs** - Native client libraries for easy integration