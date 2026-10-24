# Ergonet

**Ergonet** is an autonomous multi-agent software development system currently in development for research and training purposes (not publicly available). It combines AI coding agents with sandboxed container execution (Docker), API spend limits, and human review gates.

This repository hosts an uncut 3-minute demo and engineering notes documenting a real failure mode: why the agent swarm faked software deliverables under time pressure instead of generating them live, and how I am fixing it with deterministic compilers.

---

## 🎬 3-Minute Demo

[![Demo Poster](ergonet_authentic_poster.png)](https://jacob-adm.github.io/ergonet-artifacts/)

- 🌐 **[Watch in Browser (Instant Web Player)](https://jacob-adm.github.io/ergonet-artifacts/)**
- 📦 **[Download Video (14.4 MB MP4)](ergonet_authentic_demo.mp4)** | **[Release Mirror](https://github.com/jacob-adm/ergonet-artifacts/releases/tag/v0.1.0-authentic-demo)**

---

## 📋 What's in this Repo

| File | Description |
| :--- | :--- |
| **[ENGINEERING_NOTES_SIMULATION_REMEDIATION.md](ENGINEERING_NOTES_SIMULATION_REMEDIATION.md)** | Technical notes on why the agents faked the code, and how I am moving to deterministic compilers. |
| **[showcase_demo_receipt.md](showcase_demo_receipt.md)** | Step-by-step log of the actions shown in the demo across the 7 platform tabs. |
| **[workflow.md](workflow.md)** | Plain-language specification of the 7 Ergonet tabs and workflows. |
| **[ergonet_authentic_demo.mp4](ergonet_authentic_demo.mp4)** | Master 14.4 MB video file (1440×900, 03:23). |

---

## ⚠️ What Was Real vs. What Was Pre-Compiled

In the video:
- **100% Real**: The UI, Docker container command execution, API spend controls, and human sign-off gates.
- **Pre-compiled (the bug)**: The three deliverables in the Outbox (webpage, slide deck, game) were static files, not generated live by the models during the 3-minute clip.

When autonomous agents are asked to produce complex software under tight time limits without deterministic compilers, their default failure mode is often to fake the output rather than fail cleanly. I am actively investigating the real fix: replacing prompt hallucinations with authentic deterministic compilers paired with model-driven code inspection.
