<div align="center">

<!-- Animated Typing Header -->
<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=28&pause=800&color=00D4FF&center=true&vCenter=true&width=700&lines=Hi%2C+I'm+Ridhaant+%F0%9F%91%8B;Systems+Builder+%7C+Not+Tutorial+Follower;30%2C595+Lines+Live+in+Production;GPU+Inference+%3C1ms+%7C+16+Processes+%7C+3+Markets" />

<br/>

[![Email](https://img.shields.io/badge/Email-redantthakur%40gmail.com-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:redantthakur@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/Ridhaant)
[![Phone](https://img.shields.io/badge/Phone-%2B91--7021610641-25D366?style=flat-square&logo=whatsapp&logoColor=white)](tel:+917021610641)
[![GitHub](https://img.shields.io/badge/GitHub-Ridhaant-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Ridhaant)

</div>

---

- 🏗️ **Systems builder.** Sole-authored 30,595 lines of live Python across 16 concurrent processes.
- ⚡ **GPU engineer.** 2,352,000 vectorised evaluations/tick in <1ms on GTX 1650 (CuPy CUDA 12).
- 🔐 **Security engineer.** 1,459-line enterprise auth from scratch — TOTP 2FA, RBAC, multi-tenant, append-only audit.
- 🤖 **LLM integrator.** Claude + GPT-4o + Gemini in production — SHA-256 cached, env-only keys, graceful fallback.

---

## 🏗️ AlgoStack — Production Multi-Asset Trading Platform

<div align="center">

![Lines](https://img.shields.io/badge/Lines-30%2C595-00FF41?style=for-the-badge) ![Processes](https://img.shields.io/badge/Processes-16-00D4FF?style=for-the-badge) ![Markets](https://img.shields.io/badge/Markets-NSE+MCX+Binance-FF6B35?style=for-the-badge) ![GPU](https://img.shields.io/badge/GPU-%3C1ms-76B900?style=for-the-badge&logo=nvidia&logoColor=white)

</div>

A **sole-authored, 16-process live trading system** spanning 3 asset classes — with self-healing process supervision, ZeroMQ IPC, GPU-accelerated research, and enterprise auth.

| What I Built | The Numbers |
|:---|:---|
| **3 trading engines** running simultaneously (NSE equity, MCX commodity, Binance crypto) | 38 + 5 + 5 = **48 symbols live** |
| **9 GPU-accelerated sweep scanners** evaluating X-multiplier parameter grids in real-time | **2,352,000 evaluations/tick in <1ms** (CuPy CUDA) |
| **Self-healing supervisor** (`autohealer.py`, 1,025 lines) with market-calendar awareness | CPU-affinity pinned across **10 cores**, auto-restart |
| **Enterprise auth** (`enterprise_auth.py`, 1,459 lines) — TOTP 2FA, RBAC, multi-tenant | RFC 6238, 8 bcrypt backup codes, append-only audit |
| **ZeroMQ pub/sub IPC bus** with atomic JSON fallback | **16 subscribers, zero data loss** |
| **NLP sentiment pipeline** — VADER + 130 Indian market keyword boosters | 4 RSS feeds, SHA-256 dedup, 11-sector classifier |
| **Unified Dash UI** (373KB single-page) — engine + research views | Real-time P&L, sweep leaderboards, news feed |
| **3 Telegram alert bots** — one per asset class | EOD reports, feed staleness, tunnel health |

**➜ [View AlgoStack](https://github.com/Ridhaant/AlgoStack)**



## 📦 Extracted Libraries (from AlgoStack)

<table>
<tr>
<td width="50%">

### [⚡ VectorSweep](https://github.com/Ridhaant/VectorSweep)
**GPU parameter sweep library.** CuPy CUDA → Numba JIT → NumPy 3-tier auto-fallback. Evaluates 1,216,000 X-multiplier variants per tick in <1ms on GTX 1650. Vectorised boolean-mask evaluation — zero Python loops in the hot path.

</td>
<td width="50%">

### [🔷 Nexus Price Bus](https://github.com/Ridhaant/Nexus-Price-Bus)
**ZMQ pub/sub financial data bus.** Normalises NSE (yfinance batch), MCX (TradingView WS, 4-tier fallback), and Binance (WebSocket 1s) into one topic stream. 16 subscribers, SNDHWM backpressure, atomic JSON fallback — zero data loss.

</td>
</tr>
<tr>
<td width="50%">

### [🧠 SentiTrade](https://github.com/Ridhaant/SentiTrade)
**Indian market NLP pipeline.** 4 concurrent RSS feeds → SHA-256 dedup (O(1), 10K FIFO) → VADER + 130 domain keyword boosters (±5%/hit, ±0.5 cap) → 11-sector classifier → ZMQ PUSH signals. Optional Claude/GPT/Gemini enrichment.

</td>
<td width="50%">

### [🔒 SentinelVault](https://github.com/Ridhaant/SentinelVault)
**Security & enterprise auth.** 1,459-line self-hosted auth: TOTP 2FA (RFC 6238), RBAC (admin/analyst/readonly), multi-tenant filesystem isolation, 48-char tokenised resets, append-only audit logs. CI secret scanning + pre-commit hooks.

</td>
</tr>
</table>

---

## 🛠️ Tech Stack

<div align="center">
<img src="https://skillicons.dev/icons?i=python,cpp,c,java,js,ts,docker,linux,redis,postgres,fastapi,react,git,github,vscode&theme=dark" />
</div>

<br/>

| Layer | Technologies |
|:---|:---|
| **Languages** | ![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white) ![C](https://img.shields.io/badge/C-A8B9CC?style=flat-square&logo=c&logoColor=black) ![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white) ![JavaScript](https://img.shields.io/badge/JS-F7DF1E?style=flat-square&logo=javascript&logoColor=black) ![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=mysql&logoColor=white) ![CUDA](https://img.shields.io/badge/CUDA-76B900?style=flat-square&logo=nvidia&logoColor=white) ![Bash](https://img.shields.io/badge/Bash-4EAA25?style=flat-square&logo=gnubash&logoColor=white) |
| **Systems** | ![ZeroMQ](https://img.shields.io/badge/ZeroMQ-DF0000?style=flat-square&logo=zeromq&logoColor=white) ![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white) ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white) ![K8s](https://img.shields.io/badge/K8s-326CE5?style=flat-square&logo=kubernetes&logoColor=white) ![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=flat-square&logo=terraform&logoColor=white) ![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black) |
| **ML / GPU** | ![CuPy](https://img.shields.io/badge/CuPy_CUDA_12-76B900?style=flat-square&logo=nvidia&logoColor=white) ![Numba](https://img.shields.io/badge/Numba_JIT-00A3E0?style=flat-square&logo=llvm&logoColor=white) ![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white) ![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white) ![scikit-learn](https://img.shields.io/badge/sklearn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white) ![VADER](https://img.shields.io/badge/VADER_NLP-3fb950?style=flat-square) |
| **AI / LLM** | ![Anthropic](https://img.shields.io/badge/Claude-191919?style=flat-square&logo=anthropic&logoColor=white) ![OpenAI](https://img.shields.io/badge/GPT--4o-412991?style=flat-square&logo=openai&logoColor=white) ![Gemini](https://img.shields.io/badge/Gemini-4285F4?style=flat-square&logo=google&logoColor=white) ![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square) ![RAG](https://img.shields.io/badge/RAG_FAISS-009688?style=flat-square) |
| **FinTech** | ![Binance](https://img.shields.io/badge/Binance_WS-F0B90B?style=flat-square&logo=binance&logoColor=black) ![yfinance](https://img.shields.io/badge/yfinance-7B1FA2?style=flat-square) ![TradingView](https://img.shields.io/badge/TradingView_WS-131722?style=flat-square&logo=tradingview&logoColor=white) ![JSONL](https://img.shields.io/badge/JSONL_Ledger-000000?style=flat-square&logo=json&logoColor=white) |
| **Security** | ![TOTP](https://img.shields.io/badge/TOTP_2FA_RFC_6238-FF6B35?style=flat-square) ![RBAC](https://img.shields.io/badge/RBAC-7c3aed?style=flat-square) ![OAuth](https://img.shields.io/badge/OAuth_2.0-4285F4?style=flat-square&logo=google&logoColor=white) ![SHA-256](https://img.shields.io/badge/SHA--256-000000?style=flat-square) ![bcrypt](https://img.shields.io/badge/bcrypt-00599C?style=flat-square) |
| **Backend** | ![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white) ![Flask](https://img.shields.io/badge/Flask-000000?style=flat-square&logo=flask&logoColor=white) ![JWT](https://img.shields.io/badge/JWT-000000?style=flat-square&logo=jsonwebtokens&logoColor=white) ![Pydantic](https://img.shields.io/badge/Pydantic-E92063?style=flat-square&logo=pydantic&logoColor=white) |
| **Data** | ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white) ![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white) ![Plotly](https://img.shields.io/badge/Plotly_Dash-3F4F75?style=flat-square&logo=plotly&logoColor=white) ![Playwright](https://img.shields.io/badge/Playwright-2EAD33?style=flat-square&logo=playwright&logoColor=white) ![Selenium](https://img.shields.io/badge/Selenium-43B02A?style=flat-square&logo=selenium&logoColor=white) |

---



## 🔨 Currently Building

```
🔨  AlgoStack v11 — LLM-based signal commentary layer
🔨  vectorsweep — PyPI publish with ONNX Runtime backend
🔨  Transactions — Crypto wallet integration
🔨  Broker —  Broker api integration to execute trades
```

---

## 🎯 Looking For

Roles in: **Backend / Systems Engineering** · **ML Engineering** · **GenAI / LLM Systems** · **Quant Dev** · **FinTech Infrastructure** · **DevOps / SRE**

**Available:** Mid-2025 · Remote / Hybrid / Relocation OK

<div align="center">

[![Email](https://img.shields.io/badge/📧_redantthakur%40gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:redantthakur@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/Ridhaant)
[![Phone](https://img.shields.io/badge/📞_%2B91--7021610641-25D366?style=for-the-badge&logo=whatsapp&logoColor=white)](tel:+917021610641)

</div>
