# 🚀 Crypto Dashboard Coding Challenge

## Welcome!

Thank you for taking the time to complete this coding challenge. This repository contains a working cryptocurrency dashboard built with Next.js, TypeScript, and the CoinGecko API. The application is functional, but the codebase has significant room for improvement — and the architecture stops at the browser fetching a public API directly.

The challenge has **two parts**:

- **Part 1 — Frontend Refactor:** turn the existing codebase into something you'd be happy to inherit.
- **Part 2 — Fullstack Extension:** introduce caching and a backend data layer, with the public API as a fallback.

You can submit Part 1 alone, or Part 1 + Part 2. Part 2 is where we expect senior candidates to spend most of their time thinking about architecture and trade-offs.

## ⏱️ Time Expectation & AI Tools

We assume you will use AI assistants (Cursor, Claude Code, Copilot, etc.) — please do. We are evaluating your **judgment, prioritization, and the quality of what you ship**, not your typing speed. Because of that, we've sized the tasks larger than they would be without AI help:

- **Part 1:** ~3–4 hours of focused work
- **Part 2:** ~4–6 hours of focused work

Don't try to perfect everything. Focus on what you think is most impactful and document the trade-offs you made — a short `NOTES.md` works great.

## 🎯 What We're Looking For

- **How you identify problems** — what issues do you spot in the codebase?
- **What you prioritize** — which improvements matter most and why?
- **How you think about trade-offs** — what decisions do you make and why?
- **Your approach to code organization** — how do you structure a maintainable codebase?
- **Your decision-making process** — how do you balance perfection with pragmatism?
- **Architectural reasoning (Part 2)** — can you choose the right tool, the right shape, and explain why?

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

## Part 1 — Frontend Refactor

Refactor the existing codebase. Define what "better" means here, and demonstrate it. We're far more interested in *what you choose to change and why* than in covering any particular set of fixes.

**Deliverable:** the same app, refactored. A short note on what you changed and why is appreciated.

---

## Part 2 — Fullstack Extension

Currently the browser calls CoinGecko directly on every page load, every refresh, and every chart tab switch. That's fine for a demo and bad for everything else. In this part you'll design the data layer that should sit between the UI and the public API.

### 2a — Caching

**Assume the underlying market data is refreshed at most once every 24 hours.** Given that cadence:

1. **Identify** which caching layers make sense for this app. Don't add layers that don't earn their keep at a 24-hour refresh rate.
2. **Justify** each choice in a short writeup — what it solves, what it costs, and what could go wrong (stale data on the refresh-day boundary, cache stampedes, busting strategy, etc.).
3. **Implement at least one layer end-to-end** so we can see the pattern you'd actually use in production.

### 2b — Backend Data Layer

The dashboard should read primarily from a **database you control**, falling back to the live CoinGecko API only when a coin is missing from the DB. You do **not** need to build the periodic ingestion job — assume some external worker populates the DB on its 24-hour schedule.

We want to see your thinking on:

- **DB choice** — what database, and why, for this workload?
- **Schema** — how you model the data.
- **Indexing** — which queries you're optimizing for, and how the indexes support them.
- **Read API** — the shape of the queries / endpoints the frontend calls.
- **Fallback path** — when a coin is requested that isn't in the DB, the backend should fetch it live from CoinGecko, return it to the client, and (optionally) write it back. The code should make swapping or extending the data source clean.

**Implementation expectations:** a working backend with a real DB. Seed data can be scripted from CoinGecko once and committed — no live ingestion required.

**Deliverable:** working code plus a short `NOTES.md` walking us through your choices for the bullets above. The writeup matters as much as the code here.

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
