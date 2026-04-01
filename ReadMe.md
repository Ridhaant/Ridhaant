# Ridhaant Ajoy Thackur

**Software engineer · Quantitative & fintech · ML · Automation · GenAI · Security-aware builder**

I design and ship **production-grade systems** where performance, observability, and clean boundaries matter: trading stacks, data pipelines, model-driven workflows, and automation that survives real-world failure modes.

---

## What I build

- **Quant & fintech platforms**: multi-asset engines (equity / commodities / crypto), risk-aware paper execution, unified dashboards, and calibration tooling (X-multiplier sweeps, GPU-backed exploration where it pays off).
- **Data & ML**: feature pipelines, evaluation discipline, and pragmatic model deployment — not notebook-only demos.
- **Automation & reliability**: supervised process fleets, IPC between services, health checks, and defensive defaults so teams can operate without heroics.
- **GenAI integration**: assistant-style UX and optional LLM tooling **behind explicit API keys** — never embedded in source for public repos.
- **Cybersecurity mindset**: least privilege, secret hygiene, environment-based configuration, and separation of public code from credentials (see [SentinelVault](integrations/SentinelVault/README.md) in this monorepo’s documentation map).

---

## Featured repositories (portfolio)

| Project | One-line pitch |
|---------|----------------|
| **AlgoStack** | Core multi-asset stack: engines, scanners, unified Dash, autohealer supervision — **this repository**. |
| **Nexus Price Bus** | Decoupled price/event IPC — pairs with `ipc_bus.py` / ZMQ endpoints. |
| **VectorSweep** | Large-scale X-multiplier and vectorized sweep research (CPU/GPU). |
| **SentiTrade** | Sentiment and narrative signals feeding research and UI layers. |
| **SentinelVault** | Security playbook: secrets, access patterns, and safe publication. |
| **Profile / personal site** | *(e.g. Ridhaant-main)* — landing page and links; keep in sync with GitHub. |

Replace the table links with your live GitHub URLs when you publish.

---

## Operating principles (what recruiters see in the code)

1. **No secrets in git** — tokens, chat IDs, SMTP, and tunnel keys live in `.env` only.  
2. **Named configuration** — multipliers, ports, and limits are centralized (`config.py`, `.env.template`).  
3. **Observable systems** — logs, dashboards, and health paths reflect operating state.  
4. **Honest scope** — paper/research modes are labeled clearly; production brokerage integration requires your own compliance review.

---

## Contact

Use the email and links on your GitHub profile README or personal site. For recruiting: I’m interested in roles spanning **software engineering, quantitative development, fintech, ML engineering, automation, and secure platform work**.
