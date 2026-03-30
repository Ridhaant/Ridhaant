<div align="center">

### Ridhaant Ajoy Thackur

**Systems Engineer · Quant Developer · FinTech Infrastructure · GenAI**

*Building things that run in the real world — not just on localhost.*

[![Email](https://img.shields.io/badge/Email-redantthakur%40gmail.com-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:redantthakur@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-ridhaant--thackur-0077B5?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/ridhaant-thackur-09947a1b0)
[![GitHub](https://img.shields.io/badge/GitHub-Ridhaant-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Ridhaant)

</div>

---

## ⚡ Who Am I?

```python
class Ridhaant:
    university   = "LNMIIT Jaipur — BTech CSE (Final Semester)"
    aptitude     = "JEE Mains 97.55 Percentile — Top 2.4% Nationally"
    flagship     = "AlgoStack: 30,595 lines · 16 concurrent processes · 3 live markets"
    approach     = "I write code that runs in production — not tutorials, not clones"
    looking_for  = "₹20+ LPA | FinTech · Quant · Systems · ML · GenAI | Remote-friendly"
```

Not a notebook researcher. Not a tutorial follower. I sole-authored a **30,595-line, 16-process live trading platform** handling NSE equity, MCX commodities, and Binance crypto simultaneously — running on a pinned 10-core CPU layout with GPU-accelerated strategy evaluation, enterprise TOTP-2FA authentication, self-healing process supervision, and zero-intervention cloud deployment.

---

## 🏗 What I've Built

<table>
<tr>
<td width="50%" valign="top">

### 🚀 [AlgoStack](https://github.com/Ridhaant/algostack) — Production Trading Platform
**30,595 lines · 16 processes · 3 markets**

The flagship. A fully self-hosted algorithmic research and alerting platform for Indian markets. ZeroMQ IPC bus, GPU-accelerated parameter sweep (2.35M evaluations/tick < 1ms), VADER NLP sentiment pipeline, enterprise TOTP 2FA, and zero-intervention cloud deployment — all from a single `.env` file.

`Python` `ZeroMQ` `CuPy/CUDA` `Plotly Dash` `Docker`

</td>
<td width="50%" valign="top">

### 📡 [nexus-price-bus](https://github.com/Ridhaant/nexus-price-bus) — Market Data Bus
**NSE + Binance → ZMQ → 16 subscribers**

Multi-source financial market data bus. Batches yfinance NSE equity, streams Binance WebSocket crypto, and publishes everything onto a named-topic ZMQ PUB/SUB bus with atomic JSON fallback. Sub-1ms latency, zero data corruption risk.

`Python` `ZeroMQ` `Binance WebSocket` `yfinance`

</td>
</tr>
<tr>
<td width="50%" valign="top">

### ⚡ [vectorsweep](https://github.com/Ridhaant/vectorsweep) — GPU Parameter Sweep
**12.48M evaluations · <1ms on GTX 1650**

GPU-accelerated vectorised strategy parameter sweep engine. Evaluates 32,000 X-deviation variants against a full intraday price series in a single pass. Auto-detects CuPy CUDA / Numba JIT / NumPy — identical code, optimal performance on any hardware.

`Python` `CuPy/CUDA` `Numba JIT` `NumPy`

</td>
<td width="50%" valign="top">

### 📰 [sentitrade](https://github.com/Ridhaant/sentitrade) — NLP Sentiment Pipeline
**130+ NSE keywords · 11 sectors · <1ms**

Real-time Indian financial news sentiment pipeline. Polls 4 RSS feeds, deduplicates by SHA-256, runs domain-adapted VADER NLP with Indian market keyword boosters, classifies into 11 NSE sectors, and publishes ZMQ PUSH signals.

`Python` `VADER NLP` `ZeroMQ` `feedparser`

</td>
</tr>
</table>

---

## 🔢 Numbers That Matter

<div align="center">

| Metric | Value |
|--------|-------|
| Lines of production Python code | **30,595** |
| Concurrent processes in AlgoStack | **16** |
| GPU evaluations per price tick | **2,352,000** |
| Latency (CuPy backend, GTX 1650) | **< 1ms** |
| NSE symbols tracked live | **38** |
| Enterprise auth codebase | **1,459 lines** |
| Self-healing watchdog | **1,025 lines** |
| National aptitude rank | **Top 2.4%** |

</div>

---

## 🛠 Tech Stack

**Systems & IPC**
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![ZeroMQ](https://img.shields.io/badge/ZeroMQ-DF0000?style=flat-square&logo=zeromq&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black)
![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=c%2B%2B&logoColor=white)

**ML & GPU**
![CUDA](https://img.shields.io/badge/CUDA-76B900?style=flat-square&logo=nvidia&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white)

**FinTech & Data**
![Plotly](https://img.shields.io/badge/Plotly-3F4F75?style=flat-square&logo=plotly&logoColor=white)
![Firebase](https://img.shields.io/badge/Firebase-039BE5?style=flat-square&logo=firebase&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-FF9900?style=flat-square&logo=amazon-aws&logoColor=white)

**GenAI & LLM**
![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=flat-square&logo=openai&logoColor=white)
![Anthropic](https://img.shields.io/badge/Anthropic_Claude-CC785C?style=flat-square)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square)

---

## 🏆 Architecture Philosophy

```
┌─────────────────────────────────────────────────────────────┐
│  sentitrade         nexus-price-bus        vectorsweep       │
│  (NLP signals)  ──► (price bus)       ──► (strategy sweep)  │
│  ZMQ PUSH           ZMQ PUB/SUB            finds best X     │
│                     ▲                      per symbol        │
│                     │                                        │
│               live prices                                     │
│               NSE + Binance                                   │
│                                                              │
│  Three layers. One complete algo-trading data stack.         │
└─────────────────────────────────────────────────────────────┘
```

> *"Zero shared database. Zero cloud subscriptions. Zero compromise on production quality."*

---

<div align="center">

**Available from mid-2025 · Open to ₹20+ LPA roles nationally & internationally**

*Systems Engineer · Quant Developer · FinTech · ML · GenAI*

[![LinkedIn](https://img.shields.io/badge/Connect_on_LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/ridhaant-thackur-09947a1b0)
[![Email](https://img.shields.io/badge/Email_Me-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:redantthakur@gmail.com)

[![](https://visitcount.itsvg.in/api?id=Ridhaant&icon=6&color=6)](https://visitcount.itsvg.in)

</div>
