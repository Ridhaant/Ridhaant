<div align="center">

## **Hybrid monorepo — six GitHub-ready products**

<img src="../assets/readme/integration-mesh.svg" alt="Hybrid monorepo" width="88%"/>

*One codebase · six recruiter stories · clear boundaries for splitting or starring separately*

[![Repos](https://img.shields.io/badge/Structure-6%20publish%20folders-58a6ff?style=for-the-badge)](./)
[![Hybrid](https://img.shields.io/badge/Pattern-Shared%20core%20%2B%20domains-a371f7?style=for-the-badge)](./)

</div>

---

## How to read this layout

This directory is the **portfolio spine**: each subfolder matches a **separate GitHub repository** you can publish (or keep as documentation-only). The **live implementation** lives in the **monorepo root** and is **shared** — that is the **hybrid** model:

| Repo folder | Domain | Lives in root as |
|-------------|--------|-------------------|
| **[AlgoStack](./AlgoStack/)** | Full trading stack | Engines, Dash, autohealer, config, Docker, etc. |
| **[SentinelVault](./SentinelVault/)** | Security & secret hygiene | `secrets_audit.py`, auth patterns, CI ideas |
| **[Nexus-Price-Bus](./Nexus-Price-Bus/)** | Price IPC | `ipc_bus.py`, `price_service.py` |
| **[VectorSweep](./VectorSweep/)** | X sweeps & GPU research | `scanner*.py`, `sweep_core.py`, `gpu_sweep.py`, … |
| **[SentiTrade](./SentiTrade/)** | Sentiment & news | `sentiment_analyzer.py`, `news_dashboard.py` |
| **[Ridhaant-main](./Ridhaant-main/)** | Profile & brand | `ABOUT_ME.md`, `assets/readme/*` |

---

## Architecture: hybrid integration

```mermaid
flowchart TB
    subgraph MONO[" Monorepo root (single clone) "]
        CORE["AlgoStack core"]
    end
    subgraph R1[" AlgoStack repo "]
        A1["Full platform"]
    end
    subgraph R2[" SentinelVault "]
        A2["Security narrative + audit files"]
    end
    subgraph R3[" Nexus-Price-Bus "]
        A3["IPC modules"]
    end
    subgraph R4[" VectorSweep "]
        A4["Scanners + sweep_core"]
    end
    subgraph R5[" SentiTrade "]
        A5["Sentiment modules"]
    end
    subgraph R6[" Ridhaant-main "]
        A6["Profile + visuals"]
    end
    CORE --> R1 & R2 & R3 & R4 & R5 & R6
    style MONO fill:#0d1117,stroke:#58a6ff,stroke-width:2px,color:#e6edf3
```

**You do not duplicate business logic** unless you intentionally split into separate remotes later. Until then, **`repositories/*`** holds **publish instructions**, **architecture**, and **recruiter-facing** copy aligned with each GitHub repo name.

---

## Upload order (suggested)

1. **AlgoStack** — primary repo (largest); pin on profile.  
2. **VectorSweep** & **Nexus-Price-Bus** — show **performance** + **systems** depth.  
3. **SentiTrade** — **data + NLP + optional GenAI**.  
4. **SentinelVault** — **security maturity**.  
5. **Ridhaant-main** — GitHub profile README + static site.

Each folder’s **`PUBLISH.md`** lists **exact paths** to copy when creating a standalone remote.

---

<div align="center">

**[← Monorepo home](../README.md)** · **[About me](../ABOUT_ME.md)**

</div>
