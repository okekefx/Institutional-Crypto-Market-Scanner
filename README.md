# Institutional-Crypto-Market-Scanner
This repository contains a production-ready crypto market scanning engine built in Python.  The system monitors major crypto assets, evaluates market conditions using multi-factor logic, and generates risk-managed trade signals delivered via Telegram — all while handling real-world issues like API rate limits, retries, cooldowns, and logging.


🧠 Key Engineering Highlights

✔ Fault-tolerant API integration
✔ Cron-based automated execution
✔ Cooldown system to prevent signal spam
✔ Structured logging & error recovery
✔ Multi-factor scoring engine
✔ Trade level generation (Entry / SL / TP1 / TP2)
✔ Telegram messaging (signals + summaries)
✔ CSV-ready architecture for analytics & backtesting


🏗️ System Architecture

Scheduler (cron)
     ↓
Market Data Fetcher (CoinGecko API)
     ↓
Signal Evaluation Engine
     ↓
Risk & Trade Level Generator
     ↓
Cooldown Manager
     ↓
Telegram Notification System
     ↓
Logs + Trade Journal


🔍 What the Scanner Does

• Scans multiple assets (BTC, ETH, SOL)
• Fetches real-time market data
• Scores trades using:
Momentum
Volume
Market capitalization
Liquidity ratios
Directional structure
• Automatically skips:
Low-quality setups
Cooldown-protected symbols
Failed API fetches
• Sends:
Trade signals
No-trade explanations
Full scan summaries


📊 Sample Signal Output

⚡ INSTITUTIONAL SIGNAL ⚡
PAIR: BTC-USD
DIRECTION: LONG
ENTRY: 76455.00
STOP LOSS: 75690.45
TP1: 77984.10
TP2: 79513.20
RISK/REWARD: 1:4.00
SCORE: 8/14
🧮 Scoring Logic (Overview)
Factor	Points
Momentum (24h change)	0–4
Volume strength	0–3
Market cap tier	0–3
Liquidity ratio	0–2
Directional structure	0–2
Total Possible	14
Signals are only generated when a minimum score threshold is met.


🛡️ Reliability Features

• API retry logic with exponential backoff
• Graceful handling of rate limits & timeouts
• Persistent cooldown state (JSON-based)
• Crash-safe execution
• Structured logging with timestamps


⚙️ Tech Stack

Language: Python 3
APIs: CoinGecko REST API
Messaging: Telegram Bot API
Automation: Cron (VPS)
Logging: Python logging module
Storage: JSON (cooldowns), CSV-ready


🚀 How It Runs

Deployed on a VPS
Triggered automatically via cron
Executes scan every cycle
Sends alerts to Telegram
Logs results for analysis


📁 Project Structure

scanner/
├── scanner.py        # Main scanning engine
├── cooldowns.json    # Persistent cooldown state
├── signals.log       # Structured logs
├── backtester.py     # (Optional) Backtesting module
├── tester.py         # Strategy testing utilities
└── README.md


🧪 Testing & Iteration

The design supports:

Backtesting
Trade journaling
Performance analytics
Strategy iteration

This makes it suitable for continuous improvement workflows.


⚠️ Disclaimer

This project is for educational and engineering demonstration purposes only.
It does not constitute financial advice or a trading recommendation.


👋 About the Author

Built by a systems-focused engineer with interest in:

Python backend development
Data-driven decision systems
Automation & reliability engineering

Open to:

Backend roles
Python engineering
Data / analytics roles
Systems & DevOps-adjacent work

📬 Feel free to connect or reach out.
