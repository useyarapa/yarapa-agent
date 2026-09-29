# Compliance Audit Remediation

Use this rule when turning an evidence-based finding into a remediation recommendation or verifying an approved correction. Audits are read-only by default.

## Recommend before changing

Do not modify repositories, cloud resources, policies, tickets, CI, IAM, or runtime as part of an audit. First report the finding and recommend the minimum proven remediation. Prefer the official or default behavior, then a widely adopted proven pattern; design a bespoke control only when those do not fit.

Before an authorized actor changes a system, obtain separate approval for an exact Change Set. Describe:

- affected system, object, and control;
- current verified state and target state;
- evidence supporting the gap;
- expected impact, side effects, and dependencies;
- rollback or reversal strategy when relevant;
- verification criteria;
- scope that the change will leave untouched.

## Re-verify the approved change

After the approved change is performed:

1. Read the current state again.
2. Confirm that only approved fields or resources changed.
3. Repeat the original evidence test.
4. Check operating evidence when the requirement cannot be proven immediately.
5. Update the finding state while preserving the earlier evidence trail.

If verification is incomplete, state that clearly and keep the finding open.
