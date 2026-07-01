# SPGF Constitution v6.2 Errata

Status: Working Errata

Date: 2026-07-01

## Document Status

This file is an official repository-tracked errata and correction register for `SPGF_Constitution_v6.2.pdf`.

It is not part of the constitution itself and does not carry constitutional authority as an appendix. It is a governed work item used to track defects before producing a corrected constitution release, recommended as `v6.3`.

Once the corrective release is approved, resolved items should be integrated into the constitution source, referenced in Document Control, and this errata should be closed, archived, or superseded.

Traceability in this errata uses stable errata item IDs such as `1`, `7A`, and `8`. New constitution section numbers should not be assigned here until the corrective `v6.3` source is drafted and approved.

## Summary

`SPGF_Constitution_v6.2.pdf` is currently not a safe replacement for `v6.1` without a corrective release.

The v6.2 document successfully generalized the constitution and removed project-specific wording, but it also omitted several governance sections that were materially present in v6.1. This creates a risk of SSOT drift between the constitution, the engineering standards, and project-specific governance documents.

## Classification

Governance defect.

Severity: High.

Reason: The issue affects the governing source of truth for future projects.

## Severity Scale

| Severity | Meaning |
| --- | --- |
| Critical | Prevents adopting v6.2 as a final governing reference until corrected. |
| Important | Must be fixed before daily governance use, but does not alone invalidate the whole document. |
| Technical / Verification | A rendering, extraction, accessibility, or validation concern; requires verification but may not be a content defect. |

## Dependency Impact Scale

| Dependency Impact | Meaning |
| --- | --- |
| Breaks Other Section | The defect directly prevents another section, control, or gate from functioning as intended. |
| Weakens Governance | The defect reduces enforceability, ownership, traceability, or decision discipline. |
| Independent Coverage Gap | The defect is missing important coverage, but does not directly break another section. |
| Verification Only | The item requires visual, extraction, accessibility, or rendering verification. |

## Priority Summary

| Item | Severity | Dependency Impact | Summary |
| --- | --- | --- | --- |
| 1 | Critical | Weakens Governance | Missing Document Control and Versioning. |
| 2 | Important | Breaks Other Section | Missing or changed section references. |
| 3 | Critical | Breaks Other Section | Lean / Standard classification inconsistency. |
| 4 | Important | Weakens Governance | Mandatory baseline is not strong enough. |
| 5 | Important | Weakens Governance | Quality Gate flexibility lacks decision ownership. |
| 6 | Important | Weakens Governance | Open Question / Risk / Technical Debt transition rule is missing. |
| 7A | Critical | Breaks Other Section | Missing high-level architectural principles needed by QG-3 and ADR review. |
| 7B | Critical | Weakens Governance | Missing Roles and Responsibilities Matrix. |
| 7C | Important | Independent Coverage Gap | Missing engineering metrics. |
| 7D | Critical | Independent Coverage Gap | Missing Backup and DR policy. |
| 7E | Important | Independent Coverage Gap | Missing support model. |
| 7F | Important | Weakens Governance | Missing framework glossary and founding rationale. |
| 8 | Critical | Weakens Governance | Constitution change approval authority is missing. |
| 9 | Technical / Verification | Verification Only | PDF extraction and table accessibility issue. |

## Confirmed Problems

### 1. Missing Document Control And Versioning

Severity: Critical

`v6.2` does not contain a formal Document Control section or Versioning Table equivalent to the v6.1 document status/version table.

Missing controls include:

- Version number history.
- Date.
- Author/owner.
- Summary of changes.
- Document status values such as Draft, Review, Approved, Deprecated.

Impact:

- There is no authoritative explanation of what changed from v6.1 to v6.2.
- Material omissions can happen without explicit approval.
- The constitution weakens its own SSOT discipline.

Required correction:

- Restore a Document Control section as section 1 or an equivalent front-matter block.
- Add a changelog row for v6.2 and later v6.3.
- Mark v6.2 as superseded or approved-with-errata once v6.3 exists.

### 2. Missing Or Changed Section References

Severity: Important

Any document that refers to older SPGF sections such as:

- `SPGF §4`
- `SPGF §5`
- `SPGF §7`
- `SPGF §10.1`
- `SPGF §12`
- `SPGF §13.1`
- `SPGF §13.2`
- `SPGF §13.3`

may now point to the wrong section or to content that no longer exists in v6.2.

This violates the SSOT principle because cross-document references become unreliable.

Note: The current `Engineering_Standards_23_v1.1.pdf` in this repository did not expose these references during quick text inspection, but earlier or external copies may still contain them and must be checked before adoption.

### 3. Lean / Standard Classification Inconsistency

Severity: Critical

The v6.2 profile classification language is inconsistent:

- Section 4 describes Lean exclusion in terms of financial, inventory, or regulatory-sensitive data.
- Section 5 expands Standard triggers to include health data, personal sensitive data, operational permissions, and regulatory reports.

Impact:

- Readers may classify a project as Lean using the narrower section 4 rule even when section 5 implies Standard.

Required correction:

- Unify the classification rule across all profile sections.
- The Standard trigger list should consistently include at least: financial data, inventory data, health data, sensitive personal data, operational permissions, regulatory/control reports, and high operational impact.

### 4. Mandatory Baseline Is Not Strong Enough

Severity: Important

The v6.2 text mentions the core non-negotiables in prose, but it does not preserve the strong v6.1 style of a standalone mandatory baseline that never drops regardless of profile.

Impact:

- Teams may treat the baseline as descriptive guidance instead of an enforceable rule.

Required correction:

Restore a standalone section equivalent to v6.1 §13.3:

- Does not drop under any profile.
- Is not left to subjective judgment under pressure.
- Includes at least:
  - Do not break an existing working system.
  - Register technical debt.
  - Document qualifying ADRs.
  - Protect sensitive records from unsafe hard delete.

### 5. Quality Gate Flexibility Needs Decision Ownership

Severity: Important

Section 6 allows early prototypes, spikes, or preliminary designs before all questions are closed. This is useful, but it does not define who is allowed to classify an open question as non-critical.

Impact:

- A developer under delivery pressure may incorrectly label unresolved questions as non-critical and proceed.

Required correction:

- State that criticality is classified by the Project Owner, Analyst, or delegated governance owner, not solely by the implementing developer.
- Require unresolved critical questions to remain blockers for production development of sensitive workflows.

### 6. Open Question / Risk / Technical Debt Transition Rule Is Missing

Severity: Important

Section 9 correctly distinguishes Open Question, Risk, and Technical Debt, but does not define transitions between them.

Impact:

- Old open questions can remain in the wrong register even after they become real risks.
- Accepted uncertainty may become hidden debt without being reclassified.

Required correction:

Add transition rules:

- An unanswered open question becomes a risk when delay can cause wrong design, wrong scope, or operational harm.
- A risk becomes technical debt when the team knowingly proceeds with a temporary compromise.
- Register reviews must reclassify stale entries.

### 7. Material Sections Missing From v6.2

Severity: Critical

The following governance areas were present in v6.1 or discussed as part of the SPGF framework, but are absent or materially underrepresented in the current v6.2 PDF.

They should not be treated as one uniform defect. Some omissions break other controls directly, while others are important independent coverage gaps.

#### 7A. Missing High-Level Architectural Principles

Severity: Critical

Dependency Impact: Breaks Other Section

Missing or materially absent principles include:

- Single Responsibility.
- Loose Coupling.
- High Cohesion.
- Separation of Concerns.
- API First.
- Database as Source of Truth.
- Observability by Design.

Impact:

- QG-3 checks architecture and ADR quality, but v6.2 lacks a clear architectural baseline for judging those ADRs.
- Architecture decisions become harder to accept or reject consistently.

Required correction:

- Restore the architectural principles as a dedicated section with stable identifiers.
- Link QG-3 and ADR review language to these principles.

#### 7B. Missing Roles And Responsibilities Matrix

Severity: Critical

Dependency Impact: Weakens Governance

The current v6.2 PDF does not preserve a sufficient roles and responsibilities matrix.

Impact:

- Ownership of decisions, approvals, reviews, and exceptions becomes ambiguous.
- This compounds defects in QG ownership and constitution amendment authority.

Required correction:

- Restore a roles and responsibilities matrix covering at least Project Owner, Analyst, Developer, Reviewer, Operations/Support Owner, and Governance Owner where applicable.

#### 7C. Missing Engineering Metrics

Severity: Important

Dependency Impact: Independent Coverage Gap

Missing or materially underrepresented metrics include:

- ADR Density.
- Risk burn-down time.
- Technical Debt Volume.
- RTM coverage.

Impact:

- Governance remains descriptive but loses measurable health indicators.

Required correction:

- Restore the engineering metrics section or explicitly move it to Engineering Standards with a stable cross-reference.

#### 7D. Missing Backup And DR Policy

Severity: Critical

Dependency Impact: Independent Coverage Gap

Missing or materially underrepresented controls include:

- Backup strategy.
- RPO.
- RTO.
- Restore testing expectations.

Impact:

- Projects with operational or business-critical data lack a baseline continuity rule.
- Loss, corruption, or unavailability of important project data may have no defined recovery expectation.

Required correction:

- Restore a profile-aware Backup and DR section, with stronger expectations for Standard and Enterprise profiles.

#### 7E. Missing Support Model

Severity: Important

Dependency Impact: Independent Coverage Gap

The P1/P2/P3 support model is missing or materially underrepresented.

Impact:

- Incident priority and response expectations are left to ad hoc judgment.

Required correction:

- Restore a simple support model that can scale by profile.

#### 7F. Missing Framework Glossary And Founding Rationale

Severity: Important

Dependency Impact: Weakens Governance

Missing or materially absent content includes:

- Why SPGF Exists / founding rationale.
- Framework glossary.

Impact:

- Readers lose shared definitions for terms such as QG, ADR, RTM, Profile, Technical Debt, Soft Delete, and SSOT.
- The constitution becomes easier to reinterpret inconsistently across projects.
- This weakens adoption and consistency, but does not by itself break a concrete operational control in the same way as missing Backup and DR expectations.

Required correction:

- Restore the founding rationale and glossary near the beginning of the document.
- Keep glossary definitions aligned with Engineering Standards.

### 8. Constitution Change Approval Authority Is Missing

Severity: Critical

Section 14 discusses periodic review and candidate changes, but it does not clearly define who approves final amendments to the constitution.

Impact:

- A tool, assistant, or contributor could effectively rewrite the constitution without explicit owner approval.

Required correction:

- State that no amendment to the constitution is official unless explicitly approved and documented by the Project Owner or designated governance owner.
- Candidate changes must remain Draft/Review until approved.

### 9. PDF Extraction And Table Accessibility Issue

Severity: Technical / Verification

Visual inspection of the current `SPGF_Constitution_v6.2.pdf` shows that the profile and QG tables are broadly readable in the rendered PDF. However, text extraction from the PDF is unreliable for Arabic and mixed RTL/LTR content.

Impact:

- Automated review, search, quoting, and cross-reference validation become unreliable.
- This can hide broken references or make table content appear reordered.

Required correction:

- For v6.3, generate the constitution from a canonical text source such as Markdown/HTML.
- Preserve the source file in the repository.
- Verify both visual rendering and extracted text.
- Avoid relying only on PDF output as the source of truth.

## Impact

If v6.2 is adopted as-is:

- Projects may lose architectural governance that existed in v6.1.
- Engineering Standards may reference constitution sections that no longer exist.
- Future project-specific documents may inherit incomplete governance.
- The SSOT principle becomes weakened by the constitution itself.

## Required Correction

Create a corrective release, recommended as `v6.3`, that:

1. Restores all materially important sections from v6.1.
2. Keeps the generalization improvements from v6.2.
3. Adds stable section identifiers that should not change casually between versions.
4. Adds a reference map from v6.1 sections to v6.3 sections.
5. Reviews Engineering Standards against the corrected constitution and updates references.
6. Clearly documents what was removed, restored, renamed, or intentionally deferred.
7. Restores Document Control and status/version history.
8. Defines amendment approval authority.
9. Adds transition rules for Open Questions, Risks, and Technical Debt.
10. Stores the canonical source text in the repository alongside generated PDFs.

## Adoption Rule Until Fixed

Do not treat `SPGF_Constitution_v6.2.pdf` as a complete replacement for v6.1.

Until v6.3 is produced:

- Use v6.2 only for its generalization improvements.
- Refer back to v6.1 for omitted governance content.
- Avoid creating new section references against v6.2 numbering.
- Prefer named anchors or stable IDs over numeric section references.
