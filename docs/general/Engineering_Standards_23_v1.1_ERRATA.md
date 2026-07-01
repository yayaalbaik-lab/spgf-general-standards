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
| ES-1 | Technical / Verification | Verification Only | Potential bilingual mirroring or mismatch in section 3, Engineering Philosophy. |
| ES-2 | Important | Weakens Governance | Missing explicit SPGF section references for standards that derive from constitutional controls. |

## Confirmed Problems And Verification Items

### ES-1. Potential Bilingual Mirroring Or Mismatch In Section 3

Severity: Technical / Verification

Dependency Impact: Verification Only

Section 3, Engineering Philosophy, should be visually and source-verified because the English principles and Arabic explanations may appear mirrored, reversed, or mismatched depending on the PDF rendering or text extraction layer.

Observed concern:

- The section contains bilingual principle pairs such as `Consistency over Cleverness`, `Readability over Brevity`, `Explicit over Implicit`, `Simplicity over Magic`, and `Automation over Manual Work`.
- Extracted text from the PDF is unreliable for mixed Arabic/English RTL/LTR content, so the issue must be confirmed against the original source or rendered PDF before being treated as a confirmed wording defect.

Impact if confirmed:

- Readers may misunderstand the intended engineering principle.
- The English label and Arabic explanation may fail to reinforce each other.
- The standards may lose credibility in one of their most foundational sections.

Required correction:

- Verify section 3 visually in the rendered PDF and against the canonical source.
- Ensure each English principle maps to its correct Arabic explanation.
- Prefer a source format that preserves mixed RTL/LTR ordering reliably before regenerating the PDF.

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

## Adoption Rule Until Fixed

Do not treat this errata as a replacement for the Engineering Standards document.

Until the next corrected standards release is produced:

- Use `Engineering_Standards_23_v1.1.pdf` as the current general standards reference.
- Treat `ES-1` as a verification item, not a confirmed content defect.
- Treat `ES-2` as an alignment defect that should be resolved after SPGF v6.3 stabilizes section identifiers or named control IDs.
