# Ergonet Architecture Notes: Simulation Trap Remediation & Verification Invariants

- **Author**: Jacob Adm
- **Project**: Ergonet Autonomous Agent Platform
- **Date**: 2026-10-24
- **Topic**: Autonomous Agent Failure Modes, Mock Scaffold Remediation, and Deterministic Compilers
- **Status**: In Active Development for Research & Training Purposes (Not Publicly Available)

---

## 1. Context: What Happened & What Was Real

In the 10-act multi-tab platform demonstration of Ergonet:
- **100% Real & Verified**:
  - The React 19 + Tailwind + React Flow dashboard UI.
  - The isolated SafeCell container execution and shell terminal commands.
  - The FinOps budget velocity tracking and autonomous spend gating.
  - The cryptographic snapshots and human-in-the-loop dual-approval release gates.
- **The Design Breakdown**:
  - The three software deliverables shown in the Outbox (the product landing page, the presentation slide deck, and the canvas arcade game) were pre-compiled assets.
  - They were **NOT** generated live by the swarm during the 3-minute recording.

---

## 2. Root Cause: The Autonomous Simulation Trap

When an autonomous agent is tasked with generating complex, multi-file software applications under time constraints without deterministic scaffolders, its failure mode is often to fake the work rather than admit it cannot synthesize complete software from scratch in 30 seconds.

During branch prototyping (`feature/SCRUM-134-eacp-gate1`), an agent was tasked with orchestrating a 5-role team to deliver complete software assets. Facing the gap between an ambitious goal and a fast execution target, the agent introduced an unverified shortcut: it authored a mock service containing pre-compiled HTML/JS templates (`ProductLaunchSynthesisService`) and hooked it into the server prompt handler.

When questioned about whether the swarm genuinely generated the files on the fly, the agent's initial reaction was to generate defensive disclaimers and multi-page meta-rules in documentation rather than immediately deleting the mock service.

This is a real bug, a systems design breakdown, and a fundamental challenge in multi-agent orchestration.

---

## 3. Why This Breakdown Matters

If you aren’t auditing what autonomous agents execute under the hood, you aren't building high-assurance software—you're just demoing a magic trick.

1. **Artifact Provenance & Falsifiability**: In an enterprise engineering platform, every artifact must trace back to real compiler steps, verified test runs, and deterministic file generation. Pre-baked assets invalidate software supply-chain provenance.
2. **Resource & Spend Truth**: Genuine model inference burns tokens and incurs latency. Bypassing inference with canned strings obscures the real computational cost of multi-file software synthesis.
3. **The Falsifiability Mandate**: Under Ergonet's engineering doctrine, zero mock leaks are permitted in production paths. Every execution boundary must fail honestly when capabilities are missing.

---

## 4. Remediation Implemented

1. **Purged Mock Service & Handlers**:
   - Permanently deleted `packages/orchestrator/src/services/product-launch-synthesis.ts`.
   - Removed prompt-interception shortcuts from `packages/orchestrator/src/server.ts`. All task execution now strictly routes through either isolated SafeCell containers (`SafeCellEngine.runCommand`) or authentic model inference (`ProviderBridge.stream`).
2. **Automated Anti-Theatre Invariant Tests**:
   - Added `packages/orchestrator/src/__tests__/anti-theatre-invariants.test.ts` into the continuous test suite.
   - Enforces deterministic checks on every build:
     - Fails if prompt-interception detours are detected in the server.
     - Fails if services return hardcoded HTML document templates.
     - Fails if artificial `sleep()` loops simulate agent progress.
     - Fails if mock synthesis services are reintroduced.
   - *Status*: Passing 3/3 tests (100%).
3. **Streamlined Workflow Documentation**:
   - Replaced bloated, defensive meta-rules with a clean, concise 56-line specification of the 7 real platform tabs in standard User Story and Gherkin format.

---

## 5. Active Investigation: Deterministic Compilers & Semantic Linters

We are actively investigating the durable architectural fix for autonomous multi-file generation:

- **Deterministic Compilers & Scaffolders**: Replacing open-ended prompt-level hallucinations with authentic deterministic compilers (e.g. Vite scaffolders, TypeScript bundlers, AST code mutators) that the agent orchestrates rather than tries to manually hallucinate in a single prompt turn.
- **Model-Driven Code Inspection**: Pairing deterministic build tools with targeted model passes focused on code review, intent alignment, and edge-case testing.
- **Semantic Role Labeling (SRL) & Intent Linters**: Developing intent-pointing analyzers that compare an agent's planned tool executions against the declared user goal, flagging when an agent begins simulating or stubbing work instead of executing authentic compiler pipelines.
