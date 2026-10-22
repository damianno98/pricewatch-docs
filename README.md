# PriceWatch

PriceWatch is a small, personal, non-commercial command-line tool that tracks the prices of products I plan to buy and notifies me when a price drops below a threshold I set.

## What it does

- Reads a short list of products I am interested in (for example, a single household appliance).
- Periodically checks their current prices in online shops and keeps a local price history.
- Sends me a push notification when a price falls below my chosen threshold.
- Shows the lowest current price for each tracked product.

## How it uses the Allegro REST API

- **Read-only.** It only searches public offers and reads their prices. It never creates, edits or buys anything and never accesses any Allegro user account data.
- **Authentication:** client credentials only (no user login, no personal data).
- **Low volume:** a handful of requests a few times per day, run from a single machine, with delays between requests and respect for rate limits.
- **No redistribution:** data is stored only in a local SQLite file on my own computer. It is not published, resold, shared or used for any other purpose.
- **No scraping of Allegro pages:** only the official API is used.

## User-Agent

Requests identify themselves as:

```
PriceMonitorDamian/1.0.0 (+https://github.com/damianno98/pricewatch-docs)
```

## Technical overview

- Language: Python 3
- Storage: local SQLite database
- Scheduling: cron, a few runs per day
- Notifications: push messages to the author's own phone

## Contact

Questions or concerns about this application's use of the API: please open an issue in this repository.
