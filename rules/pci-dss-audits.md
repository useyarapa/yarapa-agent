# PCI DSS Audits

Use this profile with [`compliance-audit-scope-and-standards.md`](compliance-audit-scope-and-standards.md), [`compliance-audit-evidence.md`](compliance-audit-evidence.md), and [`compliance-audit-findings-and-reporting.md`](compliance-audit-findings-and-reporting.md) for a PCI DSS technical review, gap assessment, or readiness review.

## Establish PCI scope first

Do not make a PCI DSS compliance or validation conclusion until the cardholder-data environment (CDE) scope is established. Determine:

- whether the entity is a merchant, service provider, or both;
- payment channels and acceptance methods;
- account-data flows and where cardholder data or sensitive authentication data is received, processed, stored, or transmitted;
- CDE components and systems connected to or able to affect the CDE;
- segmentation boundaries and validation evidence;
- third-party service providers and responsibility allocation;
- the applicable validation path (such as SAQ or ROC) using current PCI SSC, acquirer, or other authoritative guidance.

If these boundaries are unresolved, report `PCI scope: UNKNOWN` and limit work to a pre-scope technical review.

## Verify the PCI DSS edition and criteria

The PCI SSC Document Library listed [PCI DSS v4.0.1](https://www.pcisecuritystandards.org/document_library/) on 2026-09-29. Verify the current publication, supporting documents, and applicable validation path before each assessment. Use the official standard and testing procedures as normative criteria; the summaries below are navigation aids.

Organize evidence around the applicable requirement domains: network security controls; secure configurations; stored account-data protection; transmission cryptography; malware protection; secure systems and software; business-need access restriction; user identification and authentication; physical access; logging and monitoring; security testing; and organizational security policies and programs.

## Verify CDE controls and responsibilities

- Test controls in the CDE; enterprise defaults do not prove CDE enforcement.
- Treat segmentation as a security-boundary claim that requires evidence and testing.
- Do not assume tokenization, hosted payment pages, or a payment service provider automatically removes all PCI scope.
- Verify third-party responsibilities and evidence; outsourcing does not transfer every responsibility.
- Distinguish the Defined Approach from the Customized Approach where applicable.
- For frequency-based requirements, inspect recurring evidence for the assessment period and targeted risk analyses when required.
- Apply effective dates and transition rules from the current official materials; do not rely on a prior transition interpretation.

Evidence may include CDE inventories and data-flow diagrams; network/security-control rules and reviews; configuration baselines; account-data retention and display controls; cryptographic settings; endpoint and application protections; identity and privileged access; physical-security records; logs and monitoring; scans, penetration and segmentation tests; incident-response and training records; and third-party responsibility matrices and attestations.

PCI DSS validation can use SAQs, ROCs, and AOCs according to the entity's path. A technical gap assessment is not an AOC or formal validation. Do not claim "PCI certified" or "PCI compliant" without the appropriate authorized evidence.
