# SPGF Constitution v6.3 Draft

Status: Draft

Date: 2026-07-02

Supersedes: `SPGF_Constitution_v6.2.pdf` when approved.

Source Type: Canonical draft source.

## 1. Document Control

Control ID: `SPGF-DOC-CONTROL`

| Version | Date | Status | Owner | Summary |
| --- | --- | --- | --- | --- |
| v6.1 | Previous | Historical Reference | Project Owner | Prior constitution version containing governance sections later found missing from v6.2. |
| v6.2 | 2026-07-01 | Approved with Errata | Project Owner | Generalized the constitution but introduced material omissions tracked in `SPGF_Constitution_v6.2_ERRATA.md`. |
| v6.3 Draft | 2026-07-02 | Draft | Project Owner | Corrective draft restoring critical governance controls and introducing stable control IDs. |

Document status values:

- Draft: under preparation and not binding.
- Review: ready for owner review but not yet binding.
- Approved: binding reference for future projects.
- Approved with Errata: usable with known defects tracked separately.
- Deprecated: replaced by a newer approved version.

This draft is not approved until the Project Owner explicitly approves it and the approval is recorded in this Document Control section.

## 2. Purpose And Authority

Control ID: `SPGF-AUTHORITY`

SPGF defines reusable governance rules for software projects. It is intentionally project-neutral and must be customized through project-specific documents rather than by editing the general constitution for one project only.

If this constitution conflicts with Engineering Standards, project-specific standards, or implementation notes, this constitution governs unless the Project Owner explicitly approves an exception.

Engineering Standards explain how engineering work should implement SPGF controls. They do not replace this constitution.

## 3. Stable Control IDs

Control ID: `SPGF-STABLE-IDS`

SPGF references should prefer stable control IDs over fragile section numbers.

Required stable IDs include:

- `SPGF-DOC-CONTROL`: Document control, status, and versioning.
- `SPGF-AUTHORITY`: constitutional authority and conflict rule.
- `SPGF-PROFILE`: project profile classification.
- `SPGF-MANDATORY-BASELINE`: controls that never drop under any profile.
- `SPGF-QG`: quality gates.
- `SPGF-ARCH`: architectural principles.
- `SPGF-ADR`: architecture decision records.
- `SPGF-ROLES`: roles and responsibility ownership.
- `SPGF-DEBT`: technical debt governance.
- `SPGF-RISK`: risk and open question governance.
- `SPGF-DATA-SAFETY`: data safety, deletion, backup, and recovery.
- `SPGF-AMENDMENT`: constitution amendment authority.

Numeric section references may be used for readability, but they must not be the only traceability mechanism.

## 4. Project Profiles

Control ID: `SPGF-PROFILE`

Each project must be classified as `Lean`, `Standard`, or `Enterprise` before implementation begins.

### 4.1 Lean

Lean is allowed only when the project has limited operational risk, limited data sensitivity, and no critical business continuity exposure.

A project must not be classified as Lean by default if it includes any of the Standard triggers listed in section 4.2.

### 4.2 Standard

A project starts as Standard by default if it includes any of the following:

- Financial data.
- Inventory data.
- Health data.
- Sensitive personal data.
- Operational permissions or role-based access.
- Regulatory, audit, control, or management reports.
- Business workflows where wrong data can cause operational harm.
- Integration with production systems, including POS, ERP, accounting, delivery, payment, or inventory systems.

### 4.3 Enterprise

Enterprise is required when failure, breach, data loss, or downtime can affect multiple business units, regulated operations, external customers at scale, or contractual obligations.

### 4.4 Profile Escalation

When a project gains a Standard or Enterprise trigger during delivery, the profile must be re-evaluated before the related feature enters production.

Profile downgrades require explicit approval from the Project Owner or delegated governance owner.

## 5. Mandatory Baseline

Control ID: `SPGF-MANDATORY-BASELINE`

The following baseline never drops, regardless of profile, deadline pressure, team size, or implementation phase:

- Do not knowingly break an existing working system.
- Record accepted technical debt.
- Document qualifying architecture decisions.
- Protect sensitive or operationally important records from unsafe hard delete.
- Do not bypass data safety, access control, or recovery expectations without an approved exception.

This baseline is enforceable. It is not optional guidance.

## 6. Architectural Principles

Control ID: `SPGF-ARCH`

Architecture decisions and QG-3 reviews must be evaluated against these principles.

### 6.1 Single Responsibility

Each module, component, service, document, and decision should have one primary reason to change.

### 6.2 Loose Coupling

Systems should minimize unnecessary dependencies between modules, layers, services, and external systems.

### 6.3 High Cohesion

Related behavior and data should live together when doing so improves clarity and maintainability.

### 6.4 Separation Of Concerns

User interface, business rules, data access, integrations, and infrastructure concerns should be separated unless a documented exception is simpler and safer.

### 6.5 API First Where Integration Exists

When systems must integrate, contracts should be explicit and reviewed before implementation becomes difficult to change.

### 6.6 Database As Source Of Truth

For persisted business state, the authoritative database or approved data store must be treated as the source of truth. Derived files, caches, screens, and reports must not silently become competing sources of truth.

### 6.7 Observability By Design

Important workflows should produce enough logs, audit trails, metrics, or operational evidence to diagnose failures and prove what happened.

## 7. Roles And Responsibilities

Control ID: `SPGF-ROLES`

| Role | Core Responsibility | Required Authority |
| --- | --- | --- |
| Project Owner | Owns business priority, scope acceptance, profile approval, and constitution amendment approval. | Final approval for scope, profile, and constitutional changes. |
| Analyst | Classifies requirements, open questions, risks, business rules, and acceptance criteria. | May classify question criticality when delegated by the Project Owner. |
| Developer | Implements within approved requirements, standards, and quality gates. | May propose exceptions but must not self-approve governance bypasses. |
| Reviewer | Reviews changes for correctness, maintainability, test evidence, and governance compliance. | May block merge or release when baseline controls are violated. |
| Operations / Support Owner | Owns support readiness, backup readiness, restore expectations, and incident handling. | May block production release when operational readiness is incomplete. |
| Governance Owner | Maintains SPGF alignment, errata, decisions, and cross-document traceability. | May propose amendments; cannot approve constitutional changes unless also delegated by the Project Owner. |

For a solo developer or very small team, one person may hold multiple roles, but the role responsibilities still exist and must not disappear.

## 8. Quality Gates

Control ID: `SPGF-QG`

Quality Gates define minimum checkpoints before work proceeds to more expensive or risky stages.

QG-3 architecture review must reference `SPGF-ARCH` and any qualifying `SPGF-ADR`.

Prototypes, spikes, and preliminary modeling may start before all questions are closed only when unresolved questions are classified as non-critical by the Project Owner, Analyst, or delegated governance owner. The implementing developer alone must not classify their own blocker as non-critical for production work.

## 9. ADR Governance

Control ID: `SPGF-ADR`

An ADR is required when a decision is hard to reverse, affects architecture boundaries, introduces significant dependency, changes data ownership, changes integration contracts, accepts material risk, or creates deliberate technical debt.

Each ADR must include:

- Context.
- Decision.
- Alternatives considered.
- Consequences.
- Related SPGF control IDs.
- Related risks or technical debt, if any.

## 10. Open Questions, Risks, And Technical Debt

Control IDs: `SPGF-RISK`, `SPGF-DEBT`

Open Questions, Risks, and Technical Debt must be tracked separately but reviewed together.

Transition rules:

- An unanswered open question becomes a risk when delay can cause wrong design, wrong scope, wrong estimate, data loss, security weakness, or operational harm.
- A risk becomes technical debt when the team knowingly proceeds with a temporary compromise.
- A technical debt item becomes a blocker when its impact threatens data safety, security, production stability, or mandatory baseline controls.
- Stale register items must be reclassified during governance review.

## 11. Data Safety, Backup, And Disaster Recovery

Control ID: `SPGF-DATA-SAFETY`

Projects with operationally important, financial, inventory, personal, regulatory, or management data must define backup and recovery expectations before production use.

Minimum controls:

- Identify authoritative data stores.
- Define backup ownership.
- Define backup frequency.
- Define retention expectation.
- Define RPO: maximum acceptable data loss window.
- Define RTO: maximum acceptable recovery time.
- Define restore verification expectation.
- Document any intentional gap as risk or technical debt.

Profile expectations:

| Profile | Backup / DR Expectation |
| --- | --- |
| Lean | Explicitly state whether backup is required. If not required, record why data loss is acceptable. |
| Standard | Define backup frequency, retention, RPO, RTO, and restore verification for important data. |
| Enterprise | Define tested recovery procedures, ownership, escalation, monitoring, and periodic restore drills. |

Unsafe hard delete is not allowed for sensitive, financial, inventory, audit, or operationally important records unless explicitly approved and justified.

## 12. Constitution Amendment Authority

Control ID: `SPGF-AMENDMENT`

No amendment to this constitution is official unless explicitly approved and documented by the Project Owner or designated governance owner.

Candidate changes remain Draft or Review until approved.

Each constitutional amendment must document:

- Reason for change.
- Affected control IDs.
- Impact on Engineering Standards.
- Impact on project-specific documents.
- Version and approval date.

Tools, assistants, contributors, or developers may propose changes but must not silently convert a draft into an approved constitution.

## 13. Corrective Release Notes

Control ID: `SPGF-V6.3-CORRECTION`

This draft addresses the following critical v6.2 errata items:

| Errata Item | Status In This Draft | Resolution |
| --- | --- | --- |
| 1 | Addressed | Restored Document Control and status/version history. |
| 3 | Addressed | Unified Lean/Standard classification triggers. |
| 7A | Addressed | Restored high-level architectural principles and linked them to QG/ADR review. |
| 7B | Addressed | Restored roles and responsibilities matrix. |
| 7D | Addressed | Restored profile-aware Backup and DR policy. |
| 8 | Addressed | Added explicit constitution amendment authority. |

Important and verification items remain open unless separately resolved.
