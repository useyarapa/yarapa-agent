# Compliance Audit Scope and Standards

Use this rule when performing an internal compliance audit, technical-control review, readiness review, or evidence-based gap assessment. A general question about a standard does not by itself call for an audit.

## Set the audit boundary

Choose the smallest audit mode that answers the request:

- **Repository review:** source, CI/CD, manifests, infrastructure as code, tests, and documentation.
- **Technical-control review:** repository evidence plus live provider, IAM, network, runtime, or configuration state.
- **Operating-effectiveness review:** time-bounded samples showing that controls operated repeatedly.
- **Readiness review:** management-system evidence and formally defined scope, with conclusions limited to readiness and gaps.
- **Cross-framework mapping:** reuse evidence artifacts while assessing each framework requirement separately.

Record the following before drawing conclusions:

- objective and framework;
- exact standard edition, amendments, and scheme documents used;
- organization, business unit, product, service, repositories, accounts, environments (including production and non-production boundaries), and data types in scope;
- third parties and responsibility boundaries;
- audit period or evidence window;
- exclusions and their justification;
- authoritative systems for policies, execution, runtime, IAM, incidents, and other evidence;
- access limitations and unavailable evidence.

When organizational or technical scope is incomplete, report the missing scope and perform only a limited review supported by accessible evidence. Repository evidence alone cannot establish organization-wide conformity or PCI DSS validation.

## Verify the normative baseline

Before each audit, check the official standards body or scheme owner for the current published edition, amendments, withdrawal status, and transition rules. Record the version actually assessed. Treat drafts as non-normative unless the user explicitly requests a draft-gap review. Separate scheme transition dates from normative requirements.

The ISO profile in [`iso-management-system-audits.md`](iso-management-system-audits.md) and the PCI DSS profile in [`pci-dss-audits.md`](pci-dss-audits.md) provide starting points, not substitutes for this live version check.

## Respect standards text and assessment limits

Use framework identifiers and your own evidence procedures. Do not invent requirement text or reproduce full ISO clauses, Annex A controls, or substantial copyrighted material. When exact normative criteria are needed and public official material is insufficient, ask the user to provide the licensed standard. Mark conclusions unsupported when criteria cannot be established.

An internal review is not a certification, formal attestation, QSA assessment, or legal opinion. Claim certification or formal compliance only when the appropriate independent evidence establishes it.
