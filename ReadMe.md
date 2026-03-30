<div align="center">

```
██████╗ ██╗██████╗ ██╗  ██╗ █████╗  █████╗ ███╗  ██╗████████╗
██╔══██╗██║██╔══██╗██║  ██║██╔══██╗██╔══██╗████╗ ██║╚══██╔══╝
██████╔╝██║██║  ██║███████║███████║███████║██╔██╗██║   ██║
██╔══██╗██║██║  ██║██╔══██║██╔══██║██╔══██║██║╚████║   ██║
██║  ██║██║██████╔╝██║  ██║██║  ██║██║  ██║██║ ╚███║   ██║
╚═╝  ╚═╝╚═╝╚═════╝ ╚═╝  ╚═╝╚═╝  ╚═╝╚═╝  ╚═╝╚═╝  ╚═╝   ╚═╝
```

# Ridhaant Ajoy Thackur

### Systems Engineer · Quant Developer · FinTech Infrastructure · GenAI

*"I don't prototype. I ship — NSE equities, MCX commodities, Binance crypto, live."*

[![Email](https://img.shields.io/badge/redantthakur%40gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:redantthakur@gmail.com)
[![LinkedIn](https://img.shields.io/badge/ridhaant--thackur-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/ridhaant-thackur-09947a1b0)
[![GitHub](https://img.shields.io/badge/Ridhaant-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Ridhaant)

</div>

---

## ⚡ The 30-Second Pitch

```python
class Ridhaant:
    university   = "LNMIIT Jaipur — BTech CSE (Final Semester)"
    jee_rank     = "97.55 Percentile — Top 2.4% Nationally (2021)"
    flagship     = "AlgoStack v10.2 — 30,595 lines, 16 live processes, 3 markets, 0 crashes"
    stack        = ["Python", "ZeroMQ", "CuPy/CUDA", "Numba", "Plotly Dash", "Docker", "NLP"]
    style        = "Production-grade or nothing. No hello-world. No tutorial re-skin."
    looking_for  = "₹20+ LPA | FinTech · Quant · Systems · ML/GenAI | On-site or Remote"
    availability = "Immediate"
```

Not a notebook researcher. Not a clone-and-deploy developer.  
I **sole-authored a 30,595-line, 16-process live trading platform** — GPU-accelerated strategy sweeps, enterprise TOTP-2FA, self-healing process supervisor, zero-intervention Docker + ngrok cloud deploy — running NSE equity, MCX commodity, and Binance crypto simultaneously on a pinned 10-core CPU layout.

---

## 🏗 What I've Actually Built

### 🚀 AlgoStack v10.2 — Production Algorithmic Trading Platform

> **The flagship. 30,595 lines. 16 concurrent processes. 3 live markets.**

A fully self-hosted, real-money-ready algorithmic research and alerting platform for Indian markets. Every layer — from live price ingestion to GPU-accelerated parameter sweep to enterprise auth to cloud deployment — written and owned by one person.

```
┌──────────────────────────────────────────────────────────────────────────────┐
│                        AlgoStack v10.2 Architecture                          │
├──────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  INGESTION LAYER           IPC LAYER              STRATEGY LAYER             │
│  ─────────────────         ──────────             ───────────────            │
│  NSE (yfinance)    ──►    ZeroMQ PUB/SUB  ──►   sweep_core.py                │
│  MCX (TradingView) ──►    tcp://127.0.0.1        gpu_sweep.py                │
│  Binance (WS)      ──►    :28081                 best_x_trader.py            │
│                                ▼                                             │
│  NLP LAYER                SIGNAL LAYER           EXECUTION LAYER             │
│  ──────────                ────────────           ───────────────            │
│  sentiment_analyzer.py    Telegram alerts ──►   Plotly Dash UI               │
│  VADER + 130 keywords     ZMQ PUSH/PULL          unified_dash_v3.py          │
│  11 NSE sector tags                              ngrok public tunnel         │
│                                                                              │
│  INFRASTRUCTURE                                                              │
│  ──────────────                                                              │
│  autohealer.py    (self-healing process watchdog, 1,025 lines)               │
│  enterprise_auth.py (TOTP 2FA + Flask-Login, 1,459 lines)                    │
│  market_calendar.py (NSE/MCX session guard with holiday logic)               │
│  docker-compose.yml + .env  (zero-touch VPS deployment)                      │
│                                                                              │
│  10-core CPU pinned layout · 38 NSE symbols · 16 concurrent processes        │
└──────────────────────────────────────────────────────────────────────────────┘
```

**Technical depth that stands out:**
- `gpu_sweep.py` — CuPy CUDA kernel sweeps **2,352,000 parameter variants per tick** in < 1ms
- `autohealer.py` — PID-tree process watchdog with configurable restart policies; zero manual intervention
- `enterprise_auth.py` — TOTP-2FA (Google Authenticator compatible) with Flask-Login; production-grade auth on a personal project
- `unified_dash_v3.py` — Plotly Dash multi-tab live dashboard (equity + commodity + crypto + news) on single port
- ZMQ IPC bus eliminates shared-memory race conditions across all 16 processes

---

## 📦 Open-Source Library Extractions

These three repositories extract AlgoStack's core infrastructure into standalone, reusable libraries — independently installable, fully tested, and documented.

---

### 📡 [nexus-price-bus](https://github.com/Ridhaant/nexus-price-bus) — Financial Market Data Bus

```
NSE equity (yfinance · batch 10) ──►
                                     ZMQ PUB/SUB · tcp://127.0.0.1:28081 ──► 16 subscribers
Binance WebSocket · CoinGecko REST ──►
          ▲
          └── Atomic JSON fallback (os.replace, POSIX-safe, 0 bytes corruption risk)
```

**What it solves:** Moving financial market data from N sources to M consumers without HTTP overhead, race conditions, or coordination code.

| Concept | Implementation | Why It Matters |
|---------|---------------|----------------|
| **ZMQ PUB/SUB** | Named topics (`equity`, `crypto`, `all`), multipart frames, HWM=1000 | Sub-1ms inter-process latency vs ~5ms HTTP; N subscribers, zero publisher changes |
| **Atomic JSON writes** | Write to `.tmp` → `os.replace()` | Readers never see partial files; crash-safe by design |
| **Binance WebSocket fallback** | Primary WS → CoinGecko REST (5s cadence) on disconnect | 100% uptime price feed without paid API keys |
| **yfinance batching** | Groups of 10 symbols per `yf.download()` call | Eliminates N−1 redundant HTTP calls per poll cycle |

**Numbers:** Sub-1ms ZMQ publish latency · 16 concurrent subscribers · 0 bytes corruption on process crash · Eliminates 228+ API calls per session vs naive per-symbol polling

---

### ⚡ [vectorsweep](https://github.com/Ridhaant/vectorsweep) — GPU-Accelerated Strategy Parameter Sweep

```
                  ┌──────────────────────────────────────────────┐
  Input:          │  32,000 X-deviation variants                 │
  38 symbols      │  × 390 intraday ticks                        │
  1 price series  │  = 12,480,000 evaluations per session        │
                  └─────────────────┬────────────────────────────┘
                                    │
          ┌─────────────────────────▼──────────────────────────┐
          │             Auto-detected backend                  │
          │                                                    │
          │  CuPy / CUDA    Numba JIT    NumPy baseline        │
          │  GPU VRAM       LLVM+prange  C-compiled SIMD       │
          │  < 1ms / tick   ~40ms        ~250ms                │
          │  GTX 1650       4-core CPU   any hardware          │
          └────────────────────────────────────────────────────┘
```

**What it solves:** Backtesting 32,000 strategy configurations in the time it takes a `for`-loop to test one.

| Concept | Implementation | Why It Matters |
|---------|---------------|----------------|
| **Vectorised sweep** | Shape-(N,) NumPy arrays for all variants; boolean mask replaces branching | ~100× speedup vs Python for-loops for 32K variants |
| **Numba JIT** | `@njit(parallel=True, fastmath=True, cache=True)` with `prange` | LLVM-compiled; ~40ms for 12.5M evals; `cache=True` skips recompile |
| **CuPy CUDA** | Arrays in GPU VRAM; `cupy.where` per tick = one GPU pass over all N | < 1ms on GTX 1650; VRAM footprint 11MB / 4096MB = 0.27% |
| **Decimal X generation** | Python `Decimal` internally → `float64`; prevents step drift | Silently skipping the best X value is a backtest bug — Decimal eliminates it |
| **Backend auto-detection** | Import order: CuPy → Numba → NumPy; test allocation before commit | Same calling code on any hardware; caller reads `engine.backend` |

**Numbers:** 32K variants × 390 ticks = 12.48M evals/session · GTX 1650: < 1ms/tick · Numba: ~40ms vs NumPy ~250ms · VRAM: 11MB (0.27% of 4GB) · Decimal: eliminates endpoint drift across 1001-step ranges

---

### 📰 [sentitrade](https://github.com/Ridhaant/sentitrade) — Real-Time Indian Financial NLP Pipeline

```
  ET Markets RSS ──►
  Moneycontrol   ──►  SHA-256 dedup  ──►  VADER NLP + Indian keywords  ──►  ZMQ PUSH
  Business Std   ──►  cache (10K)         130+ lexicon, 11 NSE sectors      signal consumers
  LiveMint       ──►
```

**What it solves:** Turning raw financial news into machine-readable sector-tagged sentiment signals without a GPU inference server or labelled training data.

| Concept | Implementation | Why It Matters |
|---------|---------------|----------------|
| **Domain-adapted VADER** | Base score + ±5% per Indian keyword hit, capped ±0.5; ×1.2 amplifier for high-impact terms | VADER alone misses `"FII buying"` (bullish) and `"NPA rise"` (bearish) — 80% F1 with zero labelled data |
| **Sector classification** | 11 NSE sector keyword lists; multi-label (one article → multiple sectors) | Downstream strategies filter signals to held positions only |
| **SHA-256 deduplication** | `sha256(url)[:16]`; bounded FIFO cache (10K entries) | RSS feeds keep articles for days; O(1) lookup, predictable memory |
| **ZMQ PUSH/PULL** | Publisher binds; consumers connect; round-robin distribution | Work-queue semantics: each article processed by exactly one consumer |
| **Rolling aggregate API** | `pipeline.aggregate(window=20)` with recency weighting (last 20% of window = 30% weight) | Plug-in composite signal for trading logic; smooths noise spikes |

**Numbers:** 130+ Indian market keywords · 11 NSE sectors · SHA-256 dedup O(1) lookup · < 1ms/article · 4 simultaneous RSS feeds with per-feed rate limiting

---

## 🔗 How the Three Projects Form One Stack

```
sentitrade              nexus-price-bus             vectorsweep
(NLP signals)   ──►     (price bus)         ──►    (strategy sweep)
ZMQ PUSH                ZMQ PUB/SUB                consumes prices
                        ▲                           + sentiment
                        │                           finds best X
                   live prices                      per symbol
                   NSE + Binance

  Layer 1: What the market is saying  (sentiment → sector scores)
  Layer 2: What prices are doing now  (unified NSE + Binance feed)
  Layer 3: Which config profits most  (GPU sweep → optimal X per symbol)

  This is exactly how AlgoStack's sentiment_analyzer.py, ipc_bus.py,
  and sweep_core.py / gpu_sweep.py interact in production.
```

---

## 📊 Hard Numbers (Production, Not Benchmarks)

<div align="center">

| What | Number |
|------|--------|
| Lines of production Python authored | **30,595** |
| AlgoStack concurrent processes | **16** |
| GPU parameter evaluations per tick | **2,352,000** |
| CuPy latency per tick (GTX 1650) | **< 1ms** |
| NSE equity symbols tracked live | **38** |
| NLP keyword lexicon (Indian market) | **130+** |
| NSE sector classifiers | **11** |
| Enterprise auth codebase | **1,459 lines** |
| Self-healing watchdog | **1,025 lines** |
| ZMQ concurrent subscribers (tested) | **16** |
| vectorsweep evaluations per session | **12,480,000** |
| Numba JIT vs NumPy speedup | **~6×** |
| CuPy vs NumPy speedup | **~250×** |
| yfinance API calls eliminated per session | **228+** |
| JEE Mains national percentile | **97.55** |

</div>

---

## 🛠 Technical Depth by Domain

<details>
<summary><b>⚙️ Systems Engineering & IPC</b></summary>

- **ZeroMQ PUB/SUB & PUSH/PULL** — multi-process IPC with sub-1ms latency; HWM, multipart frames, topic filtering
- **Atomic file I/O** — `os.replace()` for POSIX-safe JSON writes; crash-proof by design
- **Thread-safe architecture** — multi-threaded price feeds, shared state via locks; deduplication without race conditions
- **Process affinity** — 10-core CPU pinning via `process_affinity.py`; prevents OS scheduler from interfering with latency-sensitive workers
- **Self-healing watchdog** — PID-tree tracking, configurable restart policy, `loguru` structured logs
- **Docker + docker-compose** — containerised deployment with `.env` config; zero manual steps on fresh VPS

</details>

<details>
<summary><b>⚡ GPU & High-Performance Computing</b></summary>

- **CuPy CUDA kernels** — drop-in NumPy replacement with GPU VRAM execution; `cupy.where` for vectorised conditionals on GPU
- **Numba JIT** — `@njit(parallel=True, fastmath=True, cache=True)` + `prange`; LLVM compilation to native CPU SIMD
- **NumPy vectorisation** — shape-(N,) broadcast operations replace Python loops; C-compiled SIMD execution
- **Backend auto-detection** — CuPy → Numba → NumPy fallback chain; identical API surface, optimal hardware usage
- **Decimal-exact numerics** — Python `Decimal` for parameter generation eliminates float64 accumulation drift in sweep ranges

</details>

<details>
<summary><b>📈 Quantitative Finance & Algo Trading</b></summary>

- **Parameter sweep engine** — exhaustive search over X-deviation strategy variants in vectorised single pass
- **Breakout strategy mechanics** — buy/sell level calculation, stop-loss, T1/T2 targets, brokerage deduction
- **Intraday P&L accumulation** — boolean mask exits (`any_exit = bt1 | bsl | st1 | ssl`), `np.where` for branch-free updates
- **NSE/MCX market calendar** — session guards (09:15–15:30 IST equity, 09:00–23:30 MCX), holiday exclusion
- **Multi-market orchestration** — equity, commodity, and crypto scanners running concurrently with shared IPC bus
- **Telegram alerting** — async multi-chat Telegram signal delivery (`tg_async.py`) with retry and rate limiting

</details>

<details>
<summary><b>🤖 NLP & Data Science</b></summary>

- **Domain-adapted VADER** — overlay Indian market keyword lexicon (130+ terms) as score boosts on top of social-media-trained base model
- **Multi-label sector classification** — 11 NSE sector keyword matchers; one article can tag Banking + IT simultaneously
- **RSS ingestion pipeline** — 4 concurrent feeds with per-feed rate limiting and error isolation
- **SHA-256 deduplication** — fixed-length 16-char hex keys, bounded FIFO eviction cache; O(1) lookup
- **Recency-weighted aggregation** — rolling sentiment window with non-uniform weights; suppresses stale signal persistence

</details>

<details>
<summary><b>🔐 Security & Auth Engineering</b></summary>

- **TOTP 2FA** — `pyotp` TOTP generation + Google Authenticator QR provisioning; timing-safe verification
- **Flask-Login session management** — cookie-based auth with `remember_me`; role gating on Dash routes
- **Enterprise auth layer** — 1,459 lines of production authentication code written for a personal side project

</details>

<details>
<summary><b>☁️ DevOps & Cloud Deployment</b></summary>

- **Zero-touch VPS deployment** — single `docker-compose up` from fresh Ubuntu; all secrets via `.env`
- **ngrok public tunnel** — programmatic tunnel creation + URL propagation to Telegram; dashboard accessible from any device
- **Health checks** — `health_check.py` HTTP probe + `wifi_keepalive.py` connectivity watchdog
- **Cloudflare & Render deployment** — documented deploy guides for free-tier cloud hosting

</details>

---

## 🧰 Tech Stack

**Core Languages**
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=c%2B%2B&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=mysql&logoColor=white)

**Systems & IPC**
![ZeroMQ](https://img.shields.io/badge/ZeroMQ-DF0000?style=flat-square&logo=zeromq&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black)
![WebSocket](https://img.shields.io/badge/WebSocket-010101?style=flat-square)

**GPU & High Performance**
![CUDA](https://img.shields.io/badge/CUDA%2FCuPy-76B900?style=flat-square&logo=nvidia&logoColor=white)
![Numba](https://img.shields.io/badge/Numba_JIT-00A3E0?style=flat-square)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)

**ML & Data Science**
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white)
![VADER NLP](https://img.shields.io/badge/VADER_NLP-5C4EE5?style=flat-square)

**FinTech & Markets**
![yfinance](https://img.shields.io/badge/yfinance-8B0000?style=flat-square)
![Binance](https://img.shields.io/badge/Binance_WS-F3BA2F?style=flat-square&logo=binance&logoColor=black)
![Plotly](https://img.shields.io/badge/Plotly_Dash-3F4F75?style=flat-square&logo=plotly&logoColor=white)

**Auth & Security**
![Flask](https://img.shields.io/badge/Flask--Login-000000?style=flat-square&logo=flask&logoColor=white)
![TOTP](https://img.shields.io/badge/TOTP_2FA-25D366?style=flat-square)

**GenAI & LLM**
![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=flat-square&logo=openai&logoColor=white)
![Claude](https://img.shields.io/badge/Anthropic_Claude-CC785C?style=flat-square)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square)

---

## 📊 GitHub Activity

<div align="center">

![Ridhaant's GitHub Stats](https://github-readme-stats.vercel.app/api?username=Ridhaant&theme=tokyonight&hide_border=true&include_all_commits=true&count_private=false)

![GitHub Streak](https://nirzak-streak-stats.vercel.app/?user=Ridhaant&theme=tokyonight&hide_border=true)

![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=Ridhaant&theme=tokyonight&hide_border=true&layout=compact)

</div>

---

## 💼 Roles I'm Built For

| Role | What I Bring |
|------|-------------|
| **Software Engineer** | 30K+ lines production Python · multi-process IPC · atomic I/O · Docker deploy |
| **Quant Analyst / Dev** | GPU parameter sweeps · vectorised backtests · live NSE/MCX/crypto strategy engine |
| **Data Scientist** | NLP pipelines · GPU acceleration · signal engineering · multi-source data ingestion |
| **FinTech Developer** | Live market feeds · Binance WebSocket · NSE equity · ZMQ bus · Telegram signals |
| **ML / GenAI Engineer** | GPU workloads · NLP adaptation · LLM tooling · Numba/CuPy low-level ML infra |
| **Automation Engineer** | Self-healing watchdog · process supervisor · zero-touch VPS deploy · health monitoring |

---

## 🎓 Education & Aptitude

**B.Tech Computer Science** — LNMIIT Jaipur *(Final Semester, 2021–2025)*

> **JEE Mains 2021 — 97.55 Percentile — Top 2.4% of 1.1 million candidates nationally**

---

<div align="center">

### Open to ₹20+ LPA Roles — Immediate Availability

*On-site (PAN India) · Remote · Hybrid*

*Systems Engineering · Quant Development · FinTech · ML/GenAI*

[![Connect on LinkedIn](https://img.shields.io/badge/Connect_on_LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/ridhaant-thackur-09947a1b0)
[![Email Me](https://img.shields.io/badge/Email_Me-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:redantthakur@gmail.com)

[![Profile Views](https://visitcount.itsvg.in/api?id=Ridhaant&icon=6&color=6)](https://visitcount.itsvg.in)

</div>
