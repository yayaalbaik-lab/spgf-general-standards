# Engineering Standards 23 v1.1 Errata

Status: Working Errata

Date: 2026-07-02

## Document Status

This file is an official repository-tracked errata and alignment register for `Engineering_Standards_23_v1.1.pdf`.

It is not part of the Engineering Standards document itself. It records corrections, severity classifications, and alignment notes that should be considered before producing the next corrected Engineering Standards release.

Traceability in this errata uses stable errata item IDs. New Engineering Standards section numbers should not be assigned here until the corrective source is drafted and approved.

## Classification

Governance and engineering standards alignment note.

Reason: The Engineering Standards must remain consistent with the SPGF Constitution errata, especially where operational obligations such as Backup/DR and support expectations affect daily engineering discipline.

## Severity Scale

| Severity | Meaning |
| --- | --- |
| Critical | Must be corrected before treating the next standards release as a reliable governing reference. |
| Important | Should be corrected before daily use, but does not alone invalidate the whole standards document. |
| Technical / Verification | Requires rendering, extraction, accessibility, or validation verification. |

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
| ES-7D | Critical | Independent Coverage Gap | Backup and DR must be treated as a critical operational standards area. |
| ES-7E | Important | Independent Coverage Gap | Support model remains important before daily operational use. |
| ES-7F | Important | Weakens Governance | Glossary and founding rationale improve adoption and consistency, but are not as severe as Backup/DR. |

## Confirmed Alignment Notes

### ES-7D. Backup And DR

Severity: Critical

Dependency Impact: Independent Coverage Gap

Backup and disaster recovery controls should be treated as critical in Engineering Standards.

Reason:

- They directly affect data protection and business continuity.
- Missing RPO/RTO expectations can leave projects without a clear recovery standard.
- The risk exists even if the omission does not directly break another section of the document.

Required correction:

- Define baseline backup, restore, RPO, and RTO expectations by project profile.
- Ensure Standard and Enterprise profiles have explicit recovery expectations.
- Require restore testing or verification where project data is operationally important.

### ES-7E. Support Model

Severity: Important

Dependency Impact: Independent Coverage Gap

The P1/P2/P3 support model should remain an important operational coverage area.

Reason:

- It matters before daily operational use.
- It defines incident priority and response expectations.
- It is generally less foundational than Backup/DR because the absence of support categories does not by itself define data-loss exposure.

Required correction:

- Add or restore a simple P1/P2/P3 support model.
- Scale response expectations by project profile.

### ES-7F. Glossary And Founding Rationale

Severity: Important

Dependency Impact: Weakens Governance

The glossary and founding rationale should be treated as important governance aids, not as a higher-severity item than Backup/DR.

Reason:

- They improve shared understanding, adoption, and consistent interpretation.
- They help keep terms such as QG, ADR, RTM, Profile, Technical Debt, Soft Delete, SSOT, RPO, RTO, P1, P2, and P3 aligned.
- Their absence weakens governance consistency, but does not by itself create the same operational continuity risk as missing Backup/DR controls.

Required correction:

- Add or restore a concise glossary.
- Keep glossary terms aligned with the SPGF Constitution.
- Include only enough founding rationale to explain the standards' role without duplicating the constitution.
