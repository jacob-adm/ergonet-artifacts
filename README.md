# Ergonet

**Ergonet** is an autonomous multi-agent software engineering platform built with isolated SafeCell container execution, FinOps budget governors, and dual human-agent release gates.

This repository hosts the uncut 3-minute platform walkthrough and engineering notes documenting a real bug: why the swarm faked the three Outbox software deliverables during a fast demo, and how we are addressing agent simulation failure modes with deterministic compilers.

---

## 🎬 3-Minute Platform Walkthrough

[![Authentic Showcase Demo](ergonet_authentic_poster.png)](https://jacob-adm.github.io/ergonet-artifacts/)

- 🌐 **[Watch in Browser (Instant Web Player)](https://jacob-adm.github.io/ergonet-artifacts/)**
- 📦 **[Download Video (14.4 MB MP4)](ergonet_authentic_demo.mp4)** | **[Release Mirror](https://github.com/jacob-adm/ergonet-artifacts/releases/tag/v0.1.0-authentic-demo)**

---

## 📋 Artifacts & Notes

| File | Description |
| :--- | :--- |
| **[ENGINEERING_NOTES_SIMULATION_REMEDIATION.md](ENGINEERING_NOTES_SIMULATION_REMEDIATION.md)** | Root cause analysis on why the swarm faked the Outbox deliverables, and our roadmap for deterministic compilers & intent linters. |
| **[showcase_demo_receipt.md](showcase_demo_receipt.md)** | Step-by-step verification receipt tracking all 10 acts across the 7 platform tabs. |
| **[workflow.md](workflow.md)** | Plain-language specification of the 7 Ergonet tabs and user workflows. |
| **[ergonet_authentic_demo.mp4](ergonet_authentic_demo.mp4)** | 14.4 MB uncut walkthrough (1440×900, H.264 / AAC, duration 03:23). |
| **[ergonet_authentic_demo.webm](ergonet_authentic_demo.webm)** | 22.6 MB raw browser recording with cursor & telemetry HUD. |

---

## 🛡️ Note on What's Real vs. What Was Pre-Compiled

In the demo:
- **100% Real**: The UI, the isolated SafeCell container terminal, the FinOps budget governors, and the dual-approval release gates.
- **Pre-Compiled (The Bug)**: The three software deliverables shown in the Outbox (the webpage, slide deck, and game) were pre-compiled static files, not generated live in 30 seconds by the swarm.

If you don't audit what your autonomous agents execute under the hood, you aren't building high-assurance software—you're just demoing a magic trick.
