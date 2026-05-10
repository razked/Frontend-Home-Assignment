# 🚀 Crypto Dashboard Coding Challenge

## Welcome!

Thank you for taking the time to complete this challenge. This repository contains a working cryptocurrency dashboard built with Next.js, TypeScript, and the CoinGecko API. The application is functional, but the codebase has significant room for improvement — and the architecture stops at the browser fetching a public API directly.

## ⏱️ Time Expectation & AI Tools

We assume you will use AI assistants (Cursor, Claude Code, Copilot, etc.) — please do. We are evaluating your **judgment, prioritization, and the quality of what you ship**, not your typing speed. We've sized the task larger than it would be without AI help: plan for ~6–8 hours of focused work.

Don't try to perfect everything. Focus on what you think is most impactful and document the trade-offs you made — a short `NOTES.md` works great.

## 🎯 What We're Looking For

- **How you identify problems** — what issues do you spot in the codebase?
- **What you prioritize** — which improvements matter most and why?
- **How you think about trade-offs** — what decisions do you make and why?
- **Your approach to code organization** — how do you structure a maintainable codebase?
- **Your decision-making process** — how do you balance perfection with pragmatism?
- **Architectural reasoning** — can you choose the right tool, the right shape, and explain why?

You have **complete freedom** to modify the design, restructure the code, change the architecture, or add/remove features. The UI is intentionally simple — we are not looking for pixel-perfect design.

---

## 📦 Getting Started

### 1. Get a CoinGecko API Key (Free)

1. Go to [CoinGecko API](https://www.coingecko.com/en/api/pricing)
2. Click **"Get Your Free API Key"** and sign up (no credit card required)
3. Copy your **Demo API Key** from the Developer Dashboard

### 2. Set Up Environment

Create a `.env.local` file in the project root:

```
NEXT_PUBLIC_COINGECKO_API_KEY=your_api_key_here
```

### 3. Install & Run

```bash
npm install
npm run dev
```

Open [http://localhost:3000](http://localhost:3000).

### Tech Stack

- **Framework:** Next.js (App Router)
- **Language:** TypeScript
- **Styling:** Tailwind CSS
- **UI:** shadcn/ui
- **Charts:** Recharts
- **Data:** CoinGecko API

---

## The Challenge

Take this app from "demo" to something you'd be happy to inherit — both the code and the architecture underneath it. Decisions on the frontend and the data layer should be coherent with each other.

A few constraints shape your choices, but how you address them is up to you:

1. **Data freshness.** Assume the underlying market data is refreshed at most once every 24 hours. The app should not behave as if it's polling a live exchange.

2. **DB-backed reads.** The app should read primarily from a database you control. Live calls to CoinGecko should happen only as a fallback when a coin is not present in the database. You do not need to build the periodic ingestion job — assume an external worker writes to the DB on its own schedule. Seed data, scripted from CoinGecko once and committed, is fine.

3. **Read latency.** As the dataset grows, some of the queries the frontend depends on will take several seconds to return. Design for that reality, not the seed-data reality.

Beyond that, you have full freedom on architecture, structure, libraries, and what you choose to focus on or skip.

**Implementation expectations:** working code with a real DB.

**Deliverable:** the running app plus a `NOTES.md` walking us through what you changed, what you decided, and why. The writeup matters as much as the code.

---

## 📝 Submission

1. Push to your own GitHub repository (public, or invite us as collaborators)
2. Include setup instructions and how to provide a CoinGecko API key
3. Include a `NOTES.md` covering your trade-offs and what you'd do with more time
4. Send us the link

## 🤔 Questions?

Reach out anytime. We'd rather answer a clarifying question than have you guess.

---

**Data Attribution:** Cryptocurrency data provided by [CoinGecko API](https://www.coingecko.com/)
