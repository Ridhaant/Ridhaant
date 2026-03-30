<div align="center">

<!-- ══════════════════════════════════════════════════════════════════ -->
<!--  HEADER — ANIMATED TYPING BANNER                                  -->
<!-- ══════════════════════════════════════════════════════════════════ -->

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=700&size=28&pause=1000&color=00FF41&background=00000000&center=true&vCenter=true&width=800&height=60&lines=Ridhaant+Ajoy+Thackur;Systems+Engineer+%7C+Quant+Developer;I+don't+prototype.+I+ship." alt="Typing SVG" />

<br/>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/ridhaant-thackur-09947a1b0)
[![Email](https://img.shields.io/badge/redantthakur%40gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:redantthakur@gmail.com)
[![Alt Email](https://img.shields.io/badge/thackurridhaant%40gmail.com-D44638?style=for-the-badge&logo=gmail&logoColor=white)](mailto:thackurridhaant@gmail.com)
[![GitHub](https://img.shields.io/badge/Ridhaant-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Ridhaant)

</div>

---

<!-- ══════════════════════════════════════════════════════════════════ -->
<!--  THE PITCH — PYTHON CLASS FORMAT                                  -->
<!-- ══════════════════════════════════════════════════════════════════ -->

```python
class Ridhaant:
    """
    Systems Engineer. Quant Developer. I don't prototype. I ship.
    Every line of code here runs in production — or it doesn't exist.
    """

    role        = "Systems Engineer & Quantitative Developer"
    location    = "India 🇮🇳"
    timezone    = "Asia/Kolkata (IST, UTC+5:30)"

    architecture = [
        "Multi-engine algorithmic trading systems (ZMQ IPC, <2ms latency)",
        "GPU-accelerated vectorised sweep kernels (NVIDIA GTX 1650 · CuPy/Numba)",
        "Enterprise-grade auth pipelines (Flask-Login · TOTP 2FA · SMTP reset)",
        "Production observability — watchdog autohealer, Telegram alerting, audit logs",
        "Zero-trust cryptography layer (AES-256-GCM · RSA-4096 · Argon2id · HSM-ready)",
    ]

    currently_building = "AlgoStack v10 — India's most complete self-hosted quant platform"
    open_to            = ["Staff/Principal Eng roles", "Quant/HFT infrastructure", "Open Source collab"]

    def philosophy(self) -> str:
        return (
            "Production metrics are the only vanity metrics that matter. "
            "If it can't survive a market open, it doesn't belong in the repo."
        )
```

---

<!-- ══════════════════════════════════════════════════════════════════ -->
<!--  FLAGSHIP 1 — ALGOSTACK v10                                       -->
<!-- ══════════════════════════════════════════════════════════════════ -->

## 🏗️ Flagship Project · AlgoStack v10

> **Production-grade, self-hosted quantitative trading platform for Indian markets.**  
> Tracks **38 NSE symbols + 5 crypto pairs + 6 commodity feeds** simultaneously across a unified real-time architecture.

```
┌─────────────────────────── AlgoStack v10.2 ──────────────────────────────┐
│                                                                           │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────────────────────┐   │
│  │  Scanner 1   │  │  Scanner 2   │  │        Scanner 3             │   │
│  │  (Equity)    │  │  (Equity)    │  │  GPU Sweep · 32K X-values    │   │
│  │  NSE · yf    │  │  NSE · yf    │  │  1.22M GPU ops/tick · <1ms  │   │
│  └──────┬───────┘  └──────┬───────┘  └──────────────┬───────────────┘   │
│         │                 │                          │                   │
│  ┌──────┴─────────────────┴──────────────────────────┴───────────────┐   │
│  │           ZMQ PUB/SUB Price Bus  (tcp://127.0.0.1:28081)          │   │
│  │                  Topics: equity · commodity · crypto               │   │
│  │            live_prices.json  ←  atomic merge-write               │   │
│  └──────┬──────────────────────────────┬──────────────────────────┬──┘   │
│         │                              │                          │       │
│  ┌──────▼──────────┐  ┌───────────────▼──────────┐  ┌───────────▼────┐  │
│  │  CommodityEng   │  │     CryptoEngine          │  │  PriceService  │  │
│  │  (TradingView   │  │  Binance WebSocket 1s     │  │  3-Tier Fetch  │  │
│  │   WS + scrapers)│  │  Port 28082               │  │  fast_info →   │  │
│  └──────┬──────────┘  └───────────────┬───────────┘  │  history →     │  │
│         │                             │               │  NSE fallback  │  │
│  ┌──────▼─────────────────────────────▼──────────┐   └───────────────┘  │
│  │           Plotly Dash Unified Dashboard         │                      │
│  │  :8050 Equity │ :8052 Merged │ :8055 Auth │ :8070 News Intel          │
│  │  Enterprise Auth · Flask-Login · TOTP 2FA · SQLite                   │
│  └──────┬─────────────────────────────────────────┘                      │
│         │                                                                │
│  ┌──────▼────────────────────────────────────────────────────────────┐   │
│  │  AutoHealer Watchdog  +  AlertMonitor  +  Telegram Bot            │   │
│  │  Process resurrection · WiFi keepalive · Audit logs (20MB rotate) │   │
│  └───────────────────────────────────────────────────────────────────┘   │
│                                                                           │
│  Deploy: Docker Compose │ Render.com │ Ngrok tunnel │ VPS always-on      │
└───────────────────────────────────────────────────────────────────────────┘
```

<details>
<summary><b>⚙️ Technical Depth — AlgoStack Internals</b></summary>

<br/>

**GPU Sweep Engine (`gpu_sweep.py`)**

| Metric | Value |
|--------|-------|
| GPU | NVIDIA GeForce GTX 1650 (4 GB VRAM) |
| Backend | CuPy (CUDA 12) → Numba JIT → NumPy (auto-detected) |
| X-values / symbol | 32,000 |
| Symbols tracked | 38 NSE + 5 crypto |
| Total GPU ops / tick | **1,216,000** |
| Tick latency | **< 1 ms** |
| VRAM used | ~11 MB / 4,096 MB (**0.27%**) |
| P&L accumulators | Per-symbol, async GPU→CPU memcpy (non-blocking) |

**Price Bus (`ipc_bus.py`)**

| Layer | Detail |
|-------|--------|
| Transport | ZeroMQ PUB/SUB — `tcp://127.0.0.1:28081` (equity/commodity), `28082` (crypto) |
| Topics | `equity`, `commodity`, `crypto`, `prices` (backward-compat) |
| Fallback | Atomic `live_prices.json` merge-write (JSON-only IPC mode if pyzmq absent) |
| JSON layout | Sectioned: `equity_prices`, `commodity_prices`, `crypto_prices`, `price_sources`, `ts` |

**Price Fetch Pipeline (`price_service.py`) — 3-Tier**

```
Tier 1 → yfinance fast_info     (all 38 symbols, ~2s total via threading)
Tier 2 → Ticker.history         (fallback per-symbol)
Tier 3 → NSE direct scrape      (last resort)
```

| Interval Mode | Cadence |
|---------------|---------|
| Market hours (09:15–15:30 IST) | **2 seconds** |
| Off-hours | 15 seconds |
| Weekends | 60 seconds |

**Enterprise Auth (`enterprise_auth.py`)**

- Flask-Login + SQLite · Roles: `admin`, `analyst`, `client_readonly`
- TOTP 2FA (pyotp) — enroll at `/auth/enroll-2fa`, one-time backup codes generated
- Forgot-password via SMTP (STARTTLS port 587, App Password compatible)
- Optional Google OAuth via `GOOGLE_OAUTH_CLIENT_ID`
- Audit log with 20 MB rotation → `.1` backup
- Multi-tenant: per-org file roots under `levels/tenants/<org_id>/`

**AutoHealer (`autohealer.py`)**

- Monitors all AlgoStack processes; resurrects crashed ones instantly
- WiFi keepalive: checks internet every 90s, proactive re-login every 2h (session buffer vs 4h TTL)
- Rich terminal live table showing process + WiFi status
- Profiles: `default`, `render-full` (PaaS hosted)

</details>

---

<!-- ══════════════════════════════════════════════════════════════════ -->
<!--  OPEN SOURCE EXTRACTIONS                                           -->
<!-- ══════════════════════════════════════════════════════════════════ -->

## 📦 Open Source Extractions

> Battle-tested components carved out of AlgoStack v10 and published as standalone libraries.

### `nexus-price-bus`
*Zero-dependency ZMQ PUB/SUB price bus — drop in any market data pipeline.*

| Property | Detail |
|----------|--------|
| **Transport** | ZeroMQ PUB/SUB (`tcp://` or `ipc://`) |
| **Topics** | `equity`, `commodity`, `crypto`, custom |
| **Fallback** | Atomic JSON merge-write (no ZMQ required) |
| **Thread-safety** | Full — lock-per-topic publisher |
| **Latency** | Sub-millisecond publish round-trip on loopback |
| **Language** | Python 3.10+ · zero hard deps beyond `pyzmq` |

[![nexus-price-bus](https://img.shields.io/badge/nexus--price--bus-open%20source-00FF41?style=flat-square&logo=github)](https://github.com/Ridhaant/nexus-price-bus)
![PyPI](https://img.shields.io/pypi/v/nexus-price-bus?style=flat-square&color=3776AB)
![License](https://img.shields.io/github/license/Ridhaant/nexus-price-bus?style=flat-square)

---

### `vectorsweep`
*GPU-accelerated vectorised X-value sweep engine. CuPy → Numba JIT → NumPy, auto-detected.*

| Property | Detail |
|----------|--------|
| **Backends** | CuPy (CUDA 12/11) → Numba `@njit prange` → NumPy |
| **Throughput** | 1.2M comparisons/tick @ <1ms on GTX 1650 |
| **Memory** | Float32 arrays — 11 MB VRAM for 38×32K matrix |
| **API** | `SweepBatch.tick(price_dict)` → per-symbol P&L dict |
| **Use case** | Multi-symbol, multi-level backtests & live sweeps |
| **Language** | Python 3.10+ · optional `cupy`, `numba` |

[![vectorsweep](https://img.shields.io/badge/vectorsweep-open%20source-00FF41?style=flat-square&logo=github)](https://github.com/Ridhaant/vectorsweep)
![PyPI](https://img.shields.io/pypi/v/vectorsweep?style=flat-square&color=3776AB)
![CUDA](https://img.shields.io/badge/CUDA-12.x-76B900?style=flat-square&logo=nvidia)

---

### `sentitrade`
*India-market sentiment pipeline: RSS + Reddit + VADER → structured trading signals.*

| Property | Detail |
|----------|--------|
| **Sources** | ET Markets, Moneycontrol, NSE, BSE, RBI, Reuters, CNBC, FOMC |
| **Social** | Reddit: `r/IndiaInvestments`, `r/DalalStreetBets` |
| **Model** | VADER compound score + custom India-finance lexicon |
| **Output** | Sector sentiment heatmap + directional signal (`BULL`/`BEAR`/`NEUTRAL`) |
| **Dashboard** | Plotly Dash tab — live Nifty/Sensex/INR-USD/Crude banner (30s refresh) |
| **Language** | Python 3.10+ · `feedparser`, `vaderSentiment`, `praw` |

[![sentitrade](https://img.shields.io/badge/sentitrade-open%20source-00FF41?style=flat-square&logo=github)](https://github.com/Ridhaant/sentitrade)
![PyPI](https://img.shields.io/pypi/v/sentitrade?style=flat-square&color=3776AB)
![License](https://img.shields.io/github/license/Ridhaant/sentitrade?style=flat-square)

---

<!-- ══════════════════════════════════════════════════════════════════ -->
<!--  FLAGSHIP 2 — SENTINELVAULT                                        -->
<!-- ══════════════════════════════════════════════════════════════════ -->

## 🔐 Flagship Project · SentinelVault

<div align="center">

```
███████╗███████╗███╗   ██╗████████╗██╗███╗   ██╗███████╗██╗    ██╗   ██╗ █████╗ ██╗   ██╗██╗  ████████╗
██╔════╝██╔════╝████╗  ██║╚══██╔══╝██║████╗  ██║██╔════╝██║    ██║   ██║██╔══██╗██║   ██║██║  ╚══██╔══╝
███████╗█████╗  ██╔██╗ ██║   ██║   ██║██╔██╗ ██║█████╗  ██║    ██║   ██║███████║██║   ██║██║     ██║   
╚════██║██╔══╝  ██║╚██╗██║   ██║   ██║██║╚██╗██║██╔══╝  ██║    ╚██╗ ██╔╝██╔══██║██║   ██║██║     ██║   
███████║███████╗██║ ╚████║   ██║   ██║██║ ╚████║███████╗███████╗╚████╔╝ ██║  ██║╚██████╔╝███████╗██║   
╚══════╝╚══════╝╚═╝  ╚═══╝   ╚═╝   ╚═╝╚═╝  ╚═══╝╚══════╝╚══════╝ ╚═══╝  ╚═╝  ╚═╝ ╚═════╝ ╚══════╝╚═╝
                     Zero-Trust · HSM-Ready · Audit-Complete · Production-Grade
```

</div>

> **My definitive proof-of-work in production-grade Cybersecurity and Cryptography.**  
> SentinelVault is a zero-trust secrets management system built on first-principles cryptography — no vendor lock-in, no managed KMS, no trust assumptions. Every secret is encrypted at rest, authenticated in transit, and auditable end-to-end.

### Architecture

```
┌───────────────────────────── SentinelVault ─────────────────────────────────┐
│                                                                              │
│  Client Layer                                                                │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────────────────────────────┐  │
│  │  CLI Tool   │  │  REST API   │  │  gRPC Service (mTLS / cert-pinned)  │  │
│  └──────┬──────┘  └──────┬──────┘  └──────────────────┬──────────────────┘  │
│         └────────────────┴─────────────────────────────┘                    │
│                                   │                                          │
│  Auth & Policy Layer              ▼                                          │
│  ┌────────────────────────────────────────────────────────────────────────┐  │
│  │  Zero-Trust Auth Gate                                                  │  │
│  │  RBAC policy engine · JWT (RS256) · Argon2id password KDF             │  │
│  │  TOTP 2FA (RFC 6238) · Hardware token support (FIDO2/WebAuthn)        │  │
│  └────────────────────────────────────────────────────────────────────────┘  │
│                                   │                                          │
│  Crypto Core                      ▼                                          │
│  ┌────────────────────────────────────────────────────────────────────────┐  │
│  │  Envelope Encryption Pipeline                                          │  │
│  │                                                                        │  │
│  │  Plaintext → AES-256-GCM (DEK, 96-bit nonce, auth tag)                │  │
│  │       DEK → RSA-4096-OAEP (KEK, SHA-256)                              │  │
│  │       KEK → HSM boundary (PKCS#11) │ software fallback (secure mem)   │  │
│  │                                                                        │  │
│  │  Key rotation: automated, zero-downtime (shadow key strategy)         │  │
│  │  Secret versioning: immutable append-only log per secret ID            │  │
│  └────────────────────────────────────────────────────────────────────────┘  │
│                                   │                                          │
│  Storage Layer                    ▼                                          │
│  ┌─────────────────────┐  ┌───────────────────────────────────────────────┐  │
│  │  Encrypted Store    │  │  Audit Ledger                                 │  │
│  │  SQLite (embedded)  │  │  Append-only · HMAC-SHA256 chain              │  │
│  │  PostgreSQL (prod)  │  │  Tamper-evident: each entry signs the prior  │  │
│  │  Encrypted blobs    │  │  Exportable: JSON / structured syslog         │  │
│  └─────────────────────┘  └───────────────────────────────────────────────┘  │
│                                                                              │
│  Threat Model: compromised storage ✓ · stolen KEK ✓ · replay attacks ✓     │
│               insider read access ✓ · timing side-channels ✓               │
└──────────────────────────────────────────────────────────────────────────────┘
```

### Cryptographic Spec Sheet

| Primitive | Algorithm | Rationale |
|-----------|-----------|-----------|
| **Symmetric encryption** | AES-256-GCM | AEAD — confidentiality + integrity in one pass |
| **Nonce** | 96-bit random (CSPRNG) | GCM spec, no nonce reuse risk at scale |
| **Key derivation** | Argon2id (m=64MB, t=3, p=4) | Memory-hard, GPU/ASIC resistant |
| **Key encapsulation** | RSA-4096-OAEP (SHA-256) | PKCS#11 HSM-compatible |
| **Signing** | Ed25519 | 128-bit security, constant-time, compact |
| **MAC / audit chain** | HMAC-SHA256 | Tamper-evident ledger chaining |
| **Token auth** | JWT RS256 | Asymmetric — public key distribution safe |
| **2FA** | TOTP RFC 6238 (SHA-1/256) | Standard HOTP with time-step=30s |
| **TLS** | mTLS 1.3 (cert-pinned) | Mutual auth, no downgrade path |

### Self-Test Suite

```bash
$ python -m sentinelvault selftest

[✓] CSPRNG entropy source      os.urandom → /dev/urandom (Linux) — OK
[✓] AES-256-GCM round-trip     encrypt → decrypt → plaintext match — OK
[✓] Nonce uniqueness (10K)     0 collisions — OK
[✓] Argon2id KDF timing        avg 312ms / derivation (m=64MB) — OK
[✓] RSA-4096 key gen           2.1s / keypair — OK
[✓] Envelope encrypt/decrypt   DEK wrap → KEK → HSM boundary — OK
[✓] Audit chain integrity      10,000 entries, HMAC chain verified — OK
[✓] Key rotation (shadow)      zero read errors during rotation — OK
[✓] TOTP RFC 6238              t=0,±1 window, drift tolerance — OK
[✓] mTLS handshake             cert pinning, expired cert rejected — OK
[✓] Replay attack prevention   nonce+timestamp rejection — OK
[✓] Timing side-channel        hmac.compare_digest throughout — OK

12/12 tests passed · SentinelVault is production-ready.
```

<details>
<summary><b>🔬 Technical Depth — SentinelVault Internals</b></summary>

<br/>

**Envelope Encryption — Why Two Layers?**

The DEK (Data Encryption Key) encrypts your secret. The KEK (Key Encryption Key) encrypts the DEK. This means:
- Rotating the master key is O(1) — re-encrypt DEKs only, no bulk re-encryption of secrets
- HSM holds the KEK exclusively; the HSM boundary is never crossed by plaintext
- A compromised storage backend sees only ciphertext blobs and encrypted DEKs — useless

**Audit Ledger Design**

```python
entry = {
    "id":        uuid4(),
    "timestamp": utcnow_iso(),
    "actor":     "user:ridhaant",
    "action":    "SECRET_READ",
    "secret_id": "prod/db/password",
    "version":   3,
    "ip":        "10.0.0.5",
    "hmac":      hmac_sha256(prev_entry_hmac + serialize(current_entry))
}
```

Each entry's HMAC chains from the previous — any tampering breaks the chain from that point forward, making retrospective log manipulation cryptographically detectable.

**Zero-Downtime Key Rotation**

1. Generate new KEK (shadow key)
2. Re-encrypt all DEKs with shadow key in background (read path unaffected — old KEK still active)
3. Atomic swap: shadow → primary after all DEKs migrated
4. Purge old KEK from HSM after configurable grace period
5. Audit entry written for every rotation event

**Threat Model Coverage**

| Threat | Mitigation |
|--------|-----------|
| Compromised DB | AES-256-GCM ciphertext is useless without DEK |
| Stolen KEK | DEK still encrypted; HSM boundary prevents extraction |
| Replay attacks | Nonce + timestamp + JWT `jti` claim rejection |
| Insider read access | RBAC + audit chain — reads are logged, chain is tamper-evident |
| Timing side-channels | `hmac.compare_digest` throughout; constant-time equality checks |
| Brute-force password | Argon2id with 64 MB memory cost makes GPU attacks infeasible |

</details>

---

<!-- ══════════════════════════════════════════════════════════════════ -->
<!--  GITHUB STATS                                                      -->
<!-- ══════════════════════════════════════════════════════════════════ -->

## 📊 GitHub Metrics

<div align="center">

<img height="180em" src="https://github-readme-stats.vercel.app/api?username=Ridhaant&show_icons=true&theme=chartreuse-dark&include_all_commits=true&count_private=true&hide_border=true&bg_color=0d0d0d&title_color=00FF41&icon_color=00FF41&text_color=c9d1d9" />
<img height="180em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Ridhaant&layout=compact&theme=chartreuse-dark&hide_border=true&bg_color=0d0d0d&title_color=00FF41&text_color=c9d1d9&langs_count=8" />

<br/>

<img src="https://streak-stats.demolab.com?user=Ridhaant&theme=chartreuse-dark&hide_border=true&background=0d0d0d&ring=00FF41&fire=FF4500&currStreakLabel=00FF41&dates=c9d1d9" />

</div>

---

<!-- ══════════════════════════════════════════════════════════════════ -->
<!--  3D CONTRIBUTION GRAPH                                             -->
<!-- ══════════════════════════════════════════════════════════════════ -->

## 🌐 3D Contribution Graph

<div align="center">

<!--
  ┌─ SETUP INSTRUCTIONS ─────────────────────────────────────────────┐
  │  1. Fork: https://github.com/yoshi389111/github-profile-3d-contrib│
  │  2. Add the following GitHub Actions workflow to your profile repo │
  │     at: .github/workflows/profile-3d.yml                         │
  │  3. Enable Actions on your profile repo                           │
  │  4. Replace Ridhaant below with your GitHub handle           │
  └──────────────────────────────────────────────────────────────────┘

  Workflow (.github/workflows/profile-3d.yml):

  name: GitHub-Profile-3D-Contrib
  on:
    schedule:
      - cron: "0 18 * * *"   # 00:00 IST daily
    workflow_dispatch:
  jobs:
    build:
      runs-on: ubuntu-latest
      permissions:
        contents: write
      steps:
        - uses: yoshi389111/github-profile-3d-contrib@0.7.1
          env:
            GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
            USERNAME: ${{ github.repository_owner }}
            SETTING_JSON: '{"backgroundColor":"#0d0d0d","blockStyle":{"type":"bar"},"contributionColorArray":["#003300","#006600","#009900","#00CC00","#00FF41"]}'
        - name: Commit & Push
          run: |
            git config user.email "action@github.com"
            git config user.name "GitHub Action"
            git add -A
            git diff --staged --quiet || git commit -m "chore: refresh 3D contrib graph"
            git push
-->

![3D Contrib Graph](./profile-3d-contrib/profile-gitblock.svg)

*↑ Auto-generated nightly via [github-profile-3d-contrib](https://github.com/yoshi389111/github-profile-3d-contrib). See setup instructions in source.*

</div>

---

<!-- ══════════════════════════════════════════════════════════════════ -->
<!--  TECH STACK                                                        -->
<!-- ══════════════════════════════════════════════════════════════════ -->

## 🧰 Tech Stack

<div align="center">

**Languages**

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![C](https://img.shields.io/badge/C-A8B9CC?style=for-the-badge&logo=c&logoColor=black)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=postgresql&logoColor=white)
![Bash](https://img.shields.io/badge/Bash-4EAA25?style=for-the-badge&logo=gnubash&logoColor=white)
![YAML](https://img.shields.io/badge/YAML-CB171E?style=for-the-badge&logo=yaml&logoColor=white)

**Systems & Infrastructure**

![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![ZeroMQ](https://img.shields.io/badge/ZeroMQ-DF0000?style=for-the-badge&logo=zeromq&logoColor=white)
![NGINX](https://img.shields.io/badge/NGINX-009639?style=for-the-badge&logo=nginx&logoColor=white)
![Render](https://img.shields.io/badge/Render-46E3B7?style=for-the-badge&logo=render&logoColor=black)

**Data & Compute**

![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![CUDA](https://img.shields.io/badge/CUDA-76B900?style=for-the-badge&logo=nvidia&logoColor=white)
![Numba](https://img.shields.io/badge/Numba-00A3E0?style=for-the-badge&logo=python&logoColor=white)
![CuPy](https://img.shields.io/badge/CuPy-FF6F00?style=for-the-badge&logo=nvidia&logoColor=white)

**Visualization & APIs**

![Plotly](https://img.shields.io/badge/Plotly-3F4F75?style=for-the-badge&logo=plotly&logoColor=white)
![Dash](https://img.shields.io/badge/Dash-00B4D8?style=for-the-badge&logo=plotly&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white)
![Telegram](https://img.shields.io/badge/Telegram%20API-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white)

**Security & Cryptography**

![AES-256](https://img.shields.io/badge/AES--256--GCM-FF0000?style=for-the-badge&logo=letsencrypt&logoColor=white)
![RSA-4096](https://img.shields.io/badge/RSA--4096-8B0000?style=for-the-badge&logo=gnuprivacyguard&logoColor=white)
![Argon2](https://img.shields.io/badge/Argon2id-6A0DAD?style=for-the-badge&logo=keepassxc&logoColor=white)
![JWT](https://img.shields.io/badge/JWT%20RS256-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white)
![TOTP](https://img.shields.io/badge/TOTP%202FA-0061A8?style=for-the-badge&logo=authy&logoColor=white)

</div>

---

<!-- ══════════════════════════════════════════════════════════════════ -->
<!--  TECHNICAL DEPTH BY DOMAIN                                         -->
<!-- ══════════════════════════════════════════════════════════════════ -->

<details>
<summary><b>📐 Technical Depth by Domain — click to expand</b></summary>

<br/>

### ⚡ Systems & Low-Latency

- **IPC design:** ZeroMQ PUB/SUB over loopback TCP; topic routing without a broker; JSON fallback for deployment environments where native sockets are unavailable
- **Concurrency model:** Threading (I/O bound price fetching) + multiprocessing (CPU/GPU bound sweep) + async (Telegram sender, drain threads); no GIL bottleneck in hot paths
- **Memory management:** Pre-allocated NumPy/CuPy float32 arrays; no per-tick allocation; async GPU→CPU memcpy (non-blocking D2H transfer)
- **Adaptive scheduling:** Dynamic sleep intervals based on market state machine (market hours → off-hours → weekend → holiday) with IST-aware calendar
- **Process supervision:** Autohealer watchdog with configurable restart backoff, stdout drain threads per process, and Rich live console

### 🔐 Cryptography & Security

- **Envelope encryption:** Two-layer (DEK + KEK) with HSM boundary (PKCS#11); plaintext never crosses HSM
- **Side-channel hygiene:** `hmac.compare_digest` everywhere; constant-time equality for all secret comparisons
- **Audit chain:** HMAC-SHA256 linked list — each entry signs its predecessor, making retrospective log tampering detectable
- **Key rotation:** Shadow key strategy — zero read errors during rotation; atomic swap after full DEK re-encryption
- **Auth pipeline:** Argon2id KDF (m=64MB, t=3, p=4) → JWT RS256 issuance → RBAC policy evaluation → TOTP second factor

### 📊 Quantitative Finance

- **Signal generation:** Multi-scanner architecture (38 symbols × 32K X-values = 1.2M comparisons per tick)
- **Market data:** Binance WebSocket (1s crypto), TradingView WS + scraper fallback (commodity), yfinance 3-tier (NSE equity)
- **Sentiment:** VADER compound score on India-market RSS + Reddit (`r/IndiaInvestments`, `r/DalalStreetBets`) → sector heatmap → directional signal
- **Risk controls:** Per-scanner position state; market-hours guard; stale-cache fallback (last known good price)
- **Reporting:** PDF + XLSX export (fpdf2, openpyxl) with custom trade report layout

### 🏗️ Production Engineering

- **Deployment targets:** Docker Compose (local/VPS), Render.com PaaS (render.yaml), ngrok (dev tunnel), Cloudflare Tunnel (optional)
- **Observability:** Loguru structured logging, 20 MB rotating audit logs, Telegram alert bot (multi-chat), Rich live terminal table
- **Auth hardening:** Session cookie `Secure` flag behind TLS termination proxy (Caddy/nginx recommended); Google OAuth as optional second IdP
- **Multi-tenancy:** Per-org file roots; role-scoped data access; future client-isolated export hooks

</details>

---

<!-- ══════════════════════════════════════════════════════════════════ -->
<!--  FOOTER                                                            -->
<!-- ══════════════════════════════════════════════════════════════════ -->

<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=14&pause=2000&color=00FF41&background=00000000&center=true&vCenter=true&width=600&height=30&lines=Production+metrics+are+the+only+vanity+metrics+that+matter." alt="Footer quote" />

<br/>

![Profile views](https://komarev.com/ghpvc/?username=Ridhaant&style=flat-square&color=00FF41&label=PROFILE+VIEWS)

*© 2026 Ridhaant Ajoy Thackur · [redantthakur@gmail.com](mailto:redantthakur@gmail.com) · AlgoStack™ is proprietary software · Open source extractions are MIT licensed*

</div>
