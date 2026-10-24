# Ergonet End-User Happy Path Workflows

> Authoritative end-user operational workflows across Ergonet's core interface tabs.
> Formatted in standard User Story and strict Gherkin (Arrange-Act-Assert) syntax.

---

### Tab 1: Swarm Topology Canvas (The Team Board)
**User Story**: As an engineering operator, I want to inspect active agent nodes and toggle execution enclaves so that I can observe multi-agent topology and isolate agent compute environments.
- **Given** the operator is on the Swarm Topology tab with the primary agent graph loaded
- **When** the operator selects an agent node and switches the active enclave from `us-east-prod-enclave` to `staging-sandbox-02`
- **Then** the canvas updates node telemetry and boundary indicators to reflect the target enclave
  - **And** all subsequent agent commands run strictly within the selected enclave context

### Tab 2: Canvas Co-Pilot (The Control Room)
**User Story**: As an engineering operator, I want to open the persistent Co-Pilot drawer and adjust reasoning parameters so that I can prompt agents with tailored reasoning effort.
- **Given** the operator is viewing the topology canvas
- **When** the operator opens the Co-Pilot drawer and selects Reasoning Effort `HIGH`
- **Then** the drawer displays real-time agent thought telemetry and model dispatch controls
  - **And** operator prompts are dispatched directly to the active swarm session

### Tab 3: SafeCell Workbench (The Workbench)
**User Story**: As an engineering operator, I want to browse workspace source files and execute isolated terminal commands so that I can verify code changes without host environment escape.
- **Given** the operator navigates to the SafeCell Workbench tab
- **When** the operator inspects a source file in the tree and runs a command in the container terminal
- **Then** the file content renders with syntax highlighting in the viewer
  - **And** the terminal executes the command inside PathTrust hardware isolation

### Tab 4: Lineage Snapshots (The Safety Net)
**User Story**: As an engineering operator, I want to capture a cryptographic pre-flight snapshot so that I can instantly restore working state if an agent run fails.
- **Given** the operator is preparing to launch an autonomous agent task
- **When** the operator triggers "Create Pre-Flight Snapshot" on the Recovery Snapshots tab
- **Then** a two-phase atomic snapshot is recorded with a SHA-256 Merkle root
  - **And** the snapshot appears in the lineage ledger with one-click rollback availability

### Tab 5: Enterprise FinOps (The Penny Counter)
**User Story**: As a FinOps administrator, I want to monitor spend velocity and configure daily budget ceilings so that autonomous swarms cannot incur runaway token costs.
- **Given** the operator is on the FinOps Ledger tab
- **When** the operator sets the daily budget ceiling to $50.00 and enables the fail-closed killswitch
- **Then** real-time token spend velocity and cost projections update immediately
  - **And** all autonomous runs automatically fail closed if aggregate spend exceeds the threshold

### Tab 6: Integrations Hub (Border Patrol)
**User Story**: As a platform security engineer, I want to review tool allowlists and git repository connections so that external integrations adhere to zero-trust boundaries.
- **Given** the operator navigates to the Integrations Hub tab
- **When** the operator reviews enclave tool grants and tests the Bitbucket repository webhook
- **Then** active tool permissions are displayed with granular read/write indicators
  - **And** the webhook connection returns a healthy handshake confirmation

### Tab 7: Deliverables Outbox & PR Gate (The Two-Key Lock)
**User Story**: As an engineering lead, I want to inspect release artifacts and apply my human approval signature so that no code merges to `main` without dual review.
- **Given** an agent run has finished producing release artifacts
- **When** the operator inspects artifact checksums on the Outbox tab and signs the dual-approval gate
- **Then** the PR receipt records both the automated agent check and human approval
  - **And** the delivery package is certified for production deployment
