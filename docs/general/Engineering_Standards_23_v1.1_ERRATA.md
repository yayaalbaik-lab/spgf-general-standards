# Engineering Standards 23 v1.1 Errata

Status: Working Errata

Date: 2026-07-02

## Document Status

This file is an official repository-tracked errata and correction register for `Engineering_Standards_23_v1.1.pdf`.

It is not part of the Engineering Standards document itself and does not carry standards authority as an appendix. It records defects and alignment issues that should be reviewed before producing the next corrected Engineering Standards release.

Traceability in this errata uses stable errata item IDs such as `ES-1` and `ES-2`. New Engineering Standards section numbers should not be assigned here until the corrective source is drafted and approved.

## Correction Note

Earlier draft notes incorrectly reused SPGF Constitution errata items about Backup/DR, support model, glossary, and founding rationale as if they were Engineering Standards-specific findings.

That was a classification error. Those items remain relevant to the SPGF Constitution errata unless and until a distinct Engineering Standards defect is identified for them.

This file now tracks Engineering Standards-specific findings only.

## Classification

Engineering Standards defect / alignment register.

Reason: The Engineering Standards must remain readable, internally consistent, and explicitly traceable to the SPGF Constitution where it claims to implement or extend constitutional controls.

## Severity Scale

| Severity | Meaning |
| --- | --- |
| Critical | Prevents treating the standards as a reliable governing reference until corrected. |
| Important | Should be corrected before daily use, but does not alone invalidate the whole standards document. |
| Technical / Verification | Requires rendering, extraction, accessibility, or source verification before being treated as a confirmed content defect. |

## Dependency Impact Scale

| Dependency Impact | Meaning |
| --- | --- |
| Breaks Other Section | The defect directly prevents another section, control, or gate from functioning as intended. |
| Weakens Governance | The defect reduces enforceability, ownership, traceability, or decision discipline. |
| Independent Coverage Gap | The defect is missing important coverage, but does not directly break another section. |
| Verification Only | The item requires visual, extraction, accessibility, or source verification. |

## Priority Summary

| Item | Severity | Dependency Impact | Summary |
| --- | --- | --- | --- |
| ES-2 | Important | Weakens Governance | Missing explicit SPGF section references for standards that derive from constitutional controls. |

## Active Problems

### ES-2. Missing Explicit SPGF Section References

Severity: Important

Dependency Impact: Weakens Governance

The Engineering Standards state that they are an implementation extension of the SPGF Constitution, but the document does not consistently include explicit SPGF references for standards that derive from constitutional controls.

Impact:

- The relationship between constitution-level rules and engineering-level implementation becomes harder to audit.
- Future edits to the constitution may not be reflected in the standards.
- Reviewers cannot easily trace whether a coding, testing, documentation, or release rule implements a specific SPGF requirement.

Required correction:

- Add explicit SPGF references where a standard implements a constitutional control.
- Prefer stable named anchors or control IDs over fragile numeric section references.
- Avoid adding references to unstable v6.2 section numbers until the corrected constitution release is drafted and approved.
- After SPGF v6.3 is approved, run a reference alignment pass between the constitution and Engineering Standards.

## Resolved Verification Items

### ES-1. Section 3 Bilingual Mirroring Check

Severity: Technical / Verification

Dependency Impact: Verification Only

Status: Closed - no visual defect confirmed.

Verification date: 2026-07-02

Section 3, Engineering Philosophy, was visually checked in the rendered `Engineering_Standards_23_v1.1.pdf` page 1.

Result:

- `Consistency over Cleverness` maps correctly to Arabic text meaning consistency is more important than unfamiliar clever solutions.
- `Readability over Brevity` maps correctly to Arabic text meaning code clarity is preferred over brevity.
- `Explicit over Implicit` maps correctly to Arabic text meaning explicit behavior is better than implicit assumption.
- `Simplicity over Magic` maps correctly to Arabic text meaning unclear magic and complexity should be avoided.
- `Automation over Manual Work` maps correctly to Arabic text meaning repetitive work should be automated when practical.

Conclusion:

- The suspected issue appears to be a text extraction / RTL-LTR extraction artifact, not a visual defect in the PDF.
- No Engineering Standards correction is required for section 3 based on the rendered PDF.

## Adoption Rule Until Fixed

Do not treat this errata as a replacement for the Engineering Standards document.

Until the next corrected standards release is produced:

- Use `Engineering_Standards_23_v1.1.pdf` as the current general standards reference.
- Treat `ES-2` as an alignment defect that should be resolved after SPGF v6.3 stabilizes section identifiers or named control IDs.
