# Compliance Audit Findings and Reporting

Use this rule with [`compliance-audit-scope-and-standards.md`](compliance-audit-scope-and-standards.md) to report evidence-based assessment results.

## Assign one primary state per assessed item

- `VERIFIED` — sufficient evidence supports the requirement for the assessed scope and period.
- `PARTIAL` — some required elements are supported, but material implementation or evidence is incomplete.
- `GAP` — evidence demonstrates that the requirement is not met in the assessed scope.
- `N/A` — the requirement does not apply, with an explicit scope or applicability reason.
- `UNKNOWN` — evidence is insufficient or inaccessible, so no conclusion is justified.

Missing evidence is `UNKNOWN`, not `GAP`, unless the requirement requires a retained record and the record's absence is verified. Keep finding state separate from risk priority. Use the organization's approved severity method; if none is established, report `NOT ASSIGNED`.

## Separate observation from interpretation

Label reasoning as needed:

- **Fact:** directly observed state.
- **Inference:** interpretation supported by evidence but not directly proven.
- **Hypothesis:** plausible explanation that still needs verification.
- **Verified root cause:** cause demonstrated by configuration, runtime state, logs, a reproducible test, or an authoritative record.

Describe a proven gap precisely. Do not present an inference or hypothesis as a fact or root cause.

## Make findings reproducible

For each material finding, include:

- framework, exact edition, requirement identifier, and applicability rationale;
- state, approved priority or `NOT ASSIGNED`, scope, and evidence period;
- evidence source, object/path, observation, timestamp, and evidence type;
- verified facts, relevant inference or hypothesis, and the proven gap;
- root cause only when established;
- minimum remediation recommendation and the evidence that would close the finding;
- scope left untouched by the assessment or proposed remediation.

## Structure the report

Include the objective, audit mode, scope and limitations, editions used, evidence sources and window, coverage summary by framework or domain, material findings, unknowns and access blockers, cross-framework evidence reuse with limitations, remediation order based on prerequisites and causal dependencies, and a re-verification plan.

Report counts by state and identify uncovered scope. Do not turn the results into a compliance percentage unless the framework explicitly defines that metric and the calculation is justified. An internal readiness or technical review is not a certificate, formal attestation, or independent validation.
