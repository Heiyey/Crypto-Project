# 🚀 Crypto Tracker

A React single-page app for exploring live cryptocurrency market data. Browse the top 100 coins by market cap, search and sort them, and open a detail page for any coin with a 7-day price chart and key market stats.

**🔗 Live demo:** [crypto-project-rosy-theta.vercel.app](https://crypto-project-rosy-theta.vercel.app/)

## Features

- **Live market list:** top 100 cryptocurrencies by market cap from the CoinGecko API, loaded on page open and refreshed automatically every 30 seconds
- **Search:** filter by coin name or ticker symbol (e.g. `bitcoin` or `btc`)
- **Sorting:** by rank, name, price (low → high / high → low), 24h change, or market cap
- **Grid / list view toggle**
- **Coin detail page** (`/coin/:id`):
  - Current price with a 24h change badge (green ↑ / red ↓)
  - 24h high and low
  - Interactive 7-day price chart built with Recharts
  - Market cap, 24h volume, circulating supply and total supply
- **Readable numbers:** prices formatted as USD currency, large values shortened to `T` / `B` / `M`
- Loading spinner and a "coin not found" fallback state

## Tech Stack

| Area | Tools |
|---|---|
| UI | React 19, CSS |
| Routing | React Router 7 |
| Charts | Recharts |
| Data | [CoinGecko public REST API](https://www.coingecko.com/en/api) (no API key needed) |
| Tooling | Vite, ESLint |
| Deployment | Vercel |

## Getting Started

**Prerequisites:** Node.js 18+ and npm.

```bash
# Clone the repo
git clone https://github.com/Heiyey/Crypto-Project.git
cd Crypto-Project

# Install dependencies
npm install

# Start the dev server
npm run dev
```

Then open the URL Vite prints (usually `http://localhost:5173`).

Other scripts:

```bash
npm run build     # production build
npm run preview   # preview the production build locally
npm run lint      # run ESLint
```

## Project Structure

```
src/
├── api/
│   └── coinGecko.js      # API calls: market list, coin details, 7-day chart data
├── components/
│   └── CryptoCard.jsx    # Card shown in the grid/list for each coin
├── pages/
│   ├── Home.jsx          # Market list with search, sorting and view toggle
│   └── CoinDetail.jsx    # Coin page with price chart and stats
├── utils/
│   └── formatter.js      # Price and market-cap formatting helpers
├── App.jsx               # Routes
└── main.jsx              # Entry point
```

## What I Practiced

- Consuming a REST API and handling loading and error states
- Client-side routing with URL params (`/coin/:id`)
- Deriving filtered and sorted views from state with `useEffect`
- Transforming raw API data into chart-ready data for Recharts
- Organizing a React app into api, components, pages and utils layers

## Author

**Andrevis Jimenez** · Full Stack Developer
[Portfolio](https://andrevis.dev) · [LinkedIn](https://www.linkedin.com/in/andrevis-j-76762b243/) · [GitHub](https://github.com/Heiyey)

---

Market data provided by [CoinGecko](https://www.coingecko.com/).
