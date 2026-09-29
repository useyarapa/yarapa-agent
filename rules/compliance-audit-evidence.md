# Compliance Audit Evidence

Use this rule with [`compliance-audit-scope-and-standards.md`](compliance-audit-scope-and-standards.md) when assessing framework requirements or controls.

## Prefer evidence that proves the claim

Use the strongest relevant source available. A useful starting order is:

1. live runtime, provider, IAM, or network state;
2. machine-enforced configuration and policy;
3. execution records, logs, monitoring, or audit trails;
4. CI/CD and repository configuration;
5. approved policies, procedures, and risk records;
6. tickets, reviews, approvals, reports, and training records;
7. interviews or uncorroborated statements.

The order depends on the claim. An approved record may be authoritative for a management-system requirement, while a technical enforcement claim needs technical evidence.

A policy proves that a policy exists. It does not prove runtime enforcement. A configuration shows its current setting; it does not establish that a recurring control operated throughout the audit period.

## Assess each requirement

For every applicable requirement or control:

1. Record its exact framework identifier and why it applies to the defined scope.
2. State the type of evidence needed without copying proprietary normative text.
3. Inspect current authoritative state first.
4. Sample historical records when operation over time matters.
5. Compare the evidence with the criterion and record verified facts separately from interpretation.
6. Assign one finding state using [`compliance-audit-findings-and-reporting.md`](compliance-audit-findings-and-reporting.md).

For each evidence item, record its source system, exact object or path, observed state, timestamp or period, scope relevance, and whether it supports design, implementation, or operating effectiveness.

## Match evidence to technical claims

When in scope and accessible, inspect the systems relevant to the control, such as identity and privileged access, cloud/network boundaries, encryption and key management, secrets, asset ownership, CI/CD permissions, dependencies and vulnerability remediation, application security, logging and alerting, backup and restore, incident response, change management, data flows and retention, third parties, and management-system records.

Do not mark a control verified from documentation alone when the claim depends on effective technical enforcement or repeated operation. State when evidence access or coverage is limited.

Evidence may be reused across frameworks, but determine applicability and outcome independently for each requirement. Shared evidence does not establish that requirements are equivalent.
