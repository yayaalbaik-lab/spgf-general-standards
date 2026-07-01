# SPGF Constitution v6.2 Errata

Status: Open

Date: 2026-07-01

## Summary

`SPGF_Constitution_v6.2.pdf` is currently not a safe replacement for `v6.1` without a corrective release.

The v6.2 document successfully generalized the constitution and removed project-specific wording, but it also omitted several governance sections that were materially present in v6.1. This creates a risk of SSOT drift between the constitution, the engineering standards, and project-specific governance documents.

## Classification

Governance defect.

Severity: High.

Reason: The issue affects the governing source of truth for future projects.

## Confirmed Problems

### 1. Missing Or Changed Section References

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

### 2. Material Sections Missing From v6.2

The following governance areas were present in v6.1 or discussed as part of the SPGF framework, but are absent or materially underrepresented in the current v6.2 PDF:

- Why SPGF Exists / founding rationale.
- Framework glossary.
- High-level architectural principles:
  - Single Responsibility.
  - Loose Coupling.
  - High Cohesion.
  - Separation of Concerns.
  - API First.
  - Database as Source of Truth.
  - Observability by Design.
- Roles and Responsibilities Matrix.
- Engineering metrics:
  - ADR Density.
  - Risk burn-down time.
  - Technical Debt Volume.
  - RTM coverage.
- Backup and disaster recovery policy:
  - Backup strategy.
  - RPO.
  - RTO.
- Support model:
  - P1.
  - P2.
  - P3.
- Constitution update impact policy, if not fully preserved.

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

## Adoption Rule Until Fixed

Do not treat `SPGF_Constitution_v6.2.pdf` as a complete replacement for v6.1.

Until v6.3 is produced:

- Use v6.2 only for its generalization improvements.
- Refer back to v6.1 for omitted governance content.
- Avoid creating new section references against v6.2 numbering.
- Prefer named anchors or stable IDs over numeric section references.

