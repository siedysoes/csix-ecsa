# Building a Safe Portfolio

A portfolio is a set of short, honest artefacts that show how you think. It is not a collection of exploits. For a beginner, two or three careful lab reports are more useful than a dozen copied scripts. This site is an **independent, unofficial study resource**, not affiliated with EC-Council; EC-Council, CEH, ECSA and LPT are trademarks of their owners.

## Golden rule: written permission or a lab you own

Every artefact you publish must come from:

- a system you own and control, such as a local virtual machine;
- a practice range whose terms you have read and followed; or
- a system where you hold **explicit written permission** that covers both the testing and the publication.

Never publish findings about a real organisation, a personal device, or someone else's account. Do not include personal data, real credentials, tokens, cookies, or customer information. If in doubt, leave it out. See [Scope, Authorization & Ethics](../fundamentals/scope-and-ethics.md).

## A report structure you can reuse

| Section | What to write |
|---|---|
| Title + date | A short, neutral name for the exercise |
| Scope statement | Exactly which systems and test window were in scope |
| Authorization note | Who approved it and where permission came from (paraphrased, no private details) |
| Methodology summary | A few lines on the phase, tools at a high level, and limits |
| Findings | One per issue: condition, impact, and conceptual severity with reasoning |
| Evidence | Sanitised screenshots or diagrams with names and data removed |
| Remediation | Practical, defensive suggestions a defender could apply |
| Lessons learned | What you got wrong, what you would repeat, what to study next |

Keep severity **conceptual**: explain your reasoning instead of claiming a formal score. A readable two-page report beats a hundred-page dump. For the phases behind the report, see [Penetration Testing Methodology](../fundamentals/pentest-methodology.md).

## CTF writeups: check the rules first

CTF writeups are fine **only when the event rules allow publishing**, and usually only after the event ends. Some competitions restrict sharing flags or solutions. Read the rules, wait when required, and never link a writeup to a live target. If the rules are unclear, ask the organisers or simply do not publish.

## A simple GitHub layout

```
portfolio/
├── README.md              # index: one line per project + link
├── lab-01-web-app/
│   ├── report.md          # the structured report above
│   ├── scope-and-authorization.md
│   └── evidence/          # sanitised images only
├── lab-02-network/
│   └── report.md
└── notes/
    └── what-i-learned.md
```

The `README.md` is the index: a short table of project, date, skills shown, and link. Keep code minimal and explanatory — this is a portfolio, not an exploit repository. Do not publish payloads or steps that would help someone attack a system they do not own.

## Before you hit publish

- [ ] Permission and lab ownership are clear.
- [ ] Screenshots contain no personal data or real identifiers.
- [ ] Findings are written so a non-specialist can follow them.
- [ ] Remediation advice is present and defensive.
- [ ] CTF rules permit the writeup.

## See also

- [Penetration Testing Methodology](../fundamentals/pentest-methodology.md)
- [Training, Labs & Practice Range](../exam/training-and-labs.md)
- [Careers After ECSA](ecsa-careers.md)
- [Next Certifications & Skills](next-steps.md)
- [Skills, Hiring & Reality Check](reality-check.md)
