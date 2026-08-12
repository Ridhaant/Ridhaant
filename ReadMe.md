<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=28&pause=800&color=00D4FF&center=true&vCenter=true&width=760&lines=Hi%2C+I'm+Ridhaant+%F0%9F%91%8B;Systems+Builder+%7C+Not+Tutorial+Follower;37%2C228+Lines+Live+in+Production;24+Supervised+Processes+%7C+3+Live+Markets" />

<br/>

[![Email](https://img.shields.io/badge/Email-redantthakur%40gmail.com-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:redantthakur@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/ridhaant)
[![WhatsApp](https://img.shields.io/badge/WhatsApp-%2B91--7021610641-25D366?style=flat-square&logo=whatsapp&logoColor=white)](https://wa.me/917021610641)
[![GitHub](https://img.shields.io/badge/GitHub-Ridhaant-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Ridhaant)

</div>

---

| | |
|:---|:---|
| **Systems builder** | Sole-authored **37,228 lines** of live Python across 39 modules |
| **Reliability** | A **1,535-line supervisor** keeps **24 worker processes** alive across 3 markets, unattended |
| **GPU engineer** | Vectorised parameter sweeps with a 3-tier fallback: CuPy CUDA to Numba JIT to NumPy |
| **Security engineer** | **1,481-line** auth system from scratch — TOTP 2FA (RFC 6238), RBAC, CSRF, append-only audit |

---

## AlgoStack — Live Multi-Asset Trading Platform

<div align="center">

![Lines](https://img.shields.io/badge/Lines-37%2C228-00FF41?style=for-the-badge) ![Processes](https://img.shields.io/badge/Supervised_Processes-24-00D4FF?style=for-the-badge) ![Markets](https://img.shields.io/badge/Markets-NSE+MCX+Binance-FF6B35?style=for-the-badge) ![Python](https://img.shields.io/badge/Python-3.11-3776AB?style=for-the-badge&logo=python&logoColor=white)

</div>

A **sole-authored multi-process trading system** spanning three asset classes — with self-healing process supervision, ZeroMQ IPC, GPU-accelerated research and enterprise auth. Not a notebook and not a backtest: a system with a process whose only job is restarting the other processes when they die.

| What I built | Detail |
|:---|:---|
| **3 trading engines** running concurrently | NSE equity, MCX commodity, Binance crypto |
| **9 sweep scanners** evaluating parameter grids | Single vectorised pass, boolean-mask exits, no per-variant Python loop |
| **Self-healing supervisor** (`autohealer.py`, 1,535 lines) | Restarts 24 managed processes; market-calendar aware; CPU-affinity pinned |
| **ZeroMQ IPC bus** (`ipc_bus.py`) | 3 topics, HWM backpressure, atomic write + `os.replace` — no partial reads |
| **Enterprise auth** (`enterprise_auth.py`, 1,481 lines) | TOTP 2FA (RFC 6238), RBAC, CSRF, bcrypt backup codes, append-only audit |
| **Operations dashboard** (`unified_dash_v3.py`, 6,434 lines) | Live P&L, sweep leaderboards, engine health, classified news feed |

**Engineering details worth calling out:**

| | |
|:---|:---|
| **3-tier compute fallback** | Auto-detected at import — the GPU path degrades to Numba, then to NumPy, instead of failing on machines without CUDA |
| **Decimal-exact parameter grids** | float64 was silently accumulating drift across long step ranges and skewing sweep results. Switching grid generation to Python `Decimal` eliminated it |
| **Market-calendar-aware supervision** | Workers start and stop on trading sessions, not wall-clock time |

**[AlgoStack repository](https://github.com/Ridhaant/AlgoStack)**

---

## Extracted Open-Source Libraries

Four components generalised out of AlgoStack into standalone installable libraries:

| Library | What it does |
|:---|:---|
| **[VectorSweep](https://github.com/Ridhaant/VectorSweep)** | GPU-accelerated vectorised parameter sweeps, 3-tier CuPy/Numba/NumPy fallback |
| **[Nexus-Price-Bus](https://github.com/Ridhaant/Nexus-Price-Bus)** | Multi-source market data bus over ZeroMQ with atomic-write fallback |
| **[SentiTrade](https://github.com/Ridhaant/SentiTrade)** | Indian-market NLP sentiment pipeline — RSS ingest, SHA-256 dedup, domain lexicon |
| **[SentinelVault](https://github.com/Ridhaant/SentinelVault)** | Self-hostable auth platform — TOTP 2FA, RBAC, CSRF, audit logging |

---

## Tech Stack

| Layer | Technologies |
|:---|:---|
| **Languages** | Python, C++, C, SQL, JavaScript, Bash |
| **Systems & IPC** | ZeroMQ (PUB/SUB), Multiprocessing, Process supervision, CPU affinity, Backpressure tuning |
| **Compute** | CuPy / CUDA 12, Numba JIT, NumPy, SciPy, Pandas, Decimal arithmetic |
| **Backend** | FastAPI, Flask, REST, WebSockets, Plotly Dash |
| **Data** | PostgreSQL, SQLite, Supabase, JSONL append-only ledgers |
| **Infra** | Docker, Docker Compose, Linux, Git, Render, Cloudflare Tunnel |
| **Testing** | pytest, deterministic backend harnesses |

---

## Looking For

**Backend / Systems Engineering** · **Quantitative Development** · **FinTech Infrastructure** · **Platform / SRE** · **ML Engineering**

**Available:** Immediately &nbsp;·&nbsp; **Location:** Mumbai / Hybrid / Remote / International contract

B.Tech Computer Science & Engineering — LNMIIT Jaipur · JEE Mains 97.55 percentile

<div align="center">

[![Email](https://img.shields.io/badge/Email-redantthakur%40gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:redantthakur@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-ridhaant-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/ridhaant)

</div>
