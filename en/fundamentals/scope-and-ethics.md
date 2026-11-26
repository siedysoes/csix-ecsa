# Scope, Authorization & Ethics

Before anyone runs a tool, a penetration test needs a **written agreement** and
an ethical framework. This article explains what responsible authorization
looks like at a conceptual level. It is educational, authorized-testing-only
content, with no exploit commands, payloads, evasion techniques, or instructions
for attacking systems you do not own.

> Independent, unofficial study resource: EC-Council, CEH, ECSA, and LPT are
> trademarks of their respective owners. This site is not affiliated with
> EC-Council and contains no official course or exam content. A certificate
> never substitutes for permission.

## What the written agreement should cover

| Item | Why it matters |
|---|---|
| Named targets and explicit exclusions | Prevents accidental testing of systems nobody approved |
| Scope boundaries and test types | Separates allowed checks from out-of-bounds techniques |
| Agreed test windows | Reduces disruption during business-critical hours |
| Emergency contacts and escalation path | Gives defenders a fast way to stop or redirect work |
| Data-handling rules | Defines what evidence may be collected, stored, and shared |
| Stop conditions | Sets clear triggers to pause if risk appears |
| Reporting and deliverables | Clarifies who receives findings and when |
| Legal and jurisdictional considerations | Different locations may have different rules; seek local advice where needed |

The document is a starting point, not a shield. If reality changes — a new
service appears, ownership is unclear, or a test affects an unexpected system —
pause and get clarification in writing.

## Ethics during the engagement

Work only within the agreed scope and respect third parties. A shared host,
a cloud tenant, or a supplier's service may host data belonging to people who
never agreed to the test. Collect the minimum data needed to support a finding,
avoid exposing personal information, and handle evidence according to the
agreement. Do not run denial-of-service or destructive actions unless they were
explicitly agreed, and even then treat them with extreme care.

Be honest about what you observed. Do not exaggerate severity to impress a
client, hide a mistake, or claim access you did not achieve. Ethics also covers
how you communicate: findings should help defenders, not embarrass them.

## Evidence, storage, and aftercare

Keep notes that are accurate and reproducible, but store them securely and
remove material when the agreement no longer requires it. Report findings to
the authorized contacts, support remediation with practical context, and
retest only with permission. The defensive follow-up is the point of the
exercise.

## Legal differences and personal responsibility

Rules vary by country, region, and sector, and organizational policies can be
stricter than the law. If you are unsure whether an action is allowed, do not
proceed — ask the engagement owner or a qualified professional. Personal
curiosity is never a valid authorization.

EC-Council periodically updates the ECSA version and exam format; verify the
current details on [eccouncil.org](https://www.eccouncil.org/). Ethics and
authorization expectations also vary by organization and engagement.

## See also

- [Penetration Testing Methodology](pentest-methodology.md)
- [What Is ECSA](what-is-ecsa.md)
- [Building a Safe Portfolio](../career/portfolio.md)
- [Skills, Hiring & Reality Check](../career/reality-check.md)
