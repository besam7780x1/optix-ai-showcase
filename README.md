# OPTIX AI: Stock & Options Analysis Platform

> 🔒 The source code is private. This repository is only a showcase. You can request access to the code or a live demo by messaging me on [LinkedIn](https://www.linkedin.com/in/bassam-alanzi-508b99325).
>
> ⚠️ This is an analysis and research tool. It does not place orders and it is not financial advice.

OPTIX AI is a full-stack platform for analyzing US stocks and options. It pulls real market data, runs a multi-timeframe technical-analysis engine, scans the market in the background for setups, and **backtests its own rules** to measure how accurate they are. Everything is shown on an Arabic dashboard that works on desktop and mobile.

## Modules
- **Technical-analysis engine.** RSI, MACD, EMA/SMA, VWAP, Bollinger Bands, ATR, ADX and relative volume. It also finds support and resistance, market structure, breakouts confirmed by volume, candlestick and chart patterns, and a volume profile. Every result comes with written reasons.
  - The formulas match TradingView: regular session only, and analysis uses the last completed candle only.
  - A trend is called only when **at least 3 independent components agree**, never from a single indicator.
- **Multi-timeframe analysis** across 6 timeframes (1m → daily), with a summary of how well they agree.
- **Options analyzer.** Full Calls/Puts chains with the Greeks (Delta, Gamma, Theta, Vega), IV, expected move, Max Pain, Put/Call ratio, **GEX with the gamma-flip level**, and unusual activity. Each contract is scored against the user's capital and risk limits.
- **Opportunity scanner.** Scans about 45 liquid tickers every 5 minutes during market hours. Each setup gets a **0–100 quality score** built from timeframe alignment, indicator confluence, momentum, volume, reward/risk and contract quality, with deductions for earnings risk.
- **Risk management.** Per-trade risk cap, daily loss limit, position-size calculator and a signal journal.
- **Backtesting engine.** It replays history candle by candle using the *same functions as the live scanner*, which avoids look-ahead bias. Option P&L is estimated with **Black-Scholes** pricing, spread and fees. Results are broken down by score, direction and ticker.
- **Live charts** built with TradingView Lightweight Charts, plus a watchlist that flags stale prices.
- **Production deployment.** Runs on a Linux server under systemd, with health-check and backup timers.

## Engineering principles
- **No fake data.** If data is missing, the app says so clearly.
- Every price is labeled with its source and timestamp.
- 20+ automated test modules (pytest).

## Tech stack
`Python` · `FastAPI` · `Uvicorn` · `SQLite` · `httpx` · `Alpaca Market Data API` · `JavaScript` · `Lightweight Charts` · `Black-Scholes model` · `pytest` · `Linux / systemd`

---

## بالعربي
**OPTIX AI** منصة لتحليل الأسهم والخيارات الأمريكية، تضم محرك تحليل فني على 6 أطر زمنية، ومحلّل خيارات يعرض الـ Greeks والـ GEX، وماسحًا آليًا للفرص يمنح كل فرصة درجة جودة، وأدوات لإدارة المخاطر، ونظام اختبار تاريخي يقيس دقة القواعد. تعمل المنصة بواجهة عربية على الحاسب والجوال.

**الكود المصدري خاص** ويُتاح عند الطلب. المنصة أداة تحليل فقط ولا تنفّذ أوامر تداول.

© All rights reserved. No part of this project may be copied or reused without written permission.
