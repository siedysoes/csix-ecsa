# ECSA vs CEH & Other Certs

> **Independent, unofficial study resource.** EC-Council, CEH, ECSA, CPENT, LPT
> and the credentials of other issuers are trademarks of their respective
> owners. This site has no affiliation with or endorsement from any issuer, and
> it contains no official courseware, exam questions, or dumps. Everything below
> is a comparison of **purpose and evidence**, not career advice from a vendor.
>
> **Authorized work only.** No badge grants permission to touch a system you do
> not own or lack explicit written authorization to assess. This article
> contains no commands, payloads, exploit steps, or evasion instructions — only
> reasoning about what credentials signal and how employers may read them.

## Learning objectives

After working through this article you should be able to:

1. Distinguish a credential's **stated purpose** from the reputation it has
   acquired in job markets.
2. Explain why ECSA is best treated as a **legacy / historical VAPT path** in
   late 2026, without inventing a current version or exam format.
3. Compare ECSA, CEH, CPENT, OSCP-style practical credentials, and broad
   vendor-neutral credentials on audience, prerequisites, and skill evidence.
4. State a defensible answer to "what does this credential actually prove?"
   for each family, including what it does *not* prove.
5. Build an ASCII decision path from your current experience and target role to
   a short list of sensible credentials.
6. Read a job posting critically: separate hard requirements from preferences,
   and identify the evidence an employer is really asking for.
7. Justify a choice with a written worksheet instead of forum consensus or an
   issuer's marketing statistics.

If you cannot do items 4, 5, and 6, you are collecting acronyms rather than
making a decision. The goal is a defensible choice you can explain to a manager
or a client — not a badge that wins an argument online.

---

## First, a verified catalogue fact

When checked on **26 November 2026**, EC-Council's current certification
catalogue did **not** list ECSA. The catalogue presented the CEH and CPENT
families with AI-oriented labels — **CEH AI** and **CPENT AI** — together with
other current programs. The separate certification-administration site,
[cert.eccouncil.org](https://cert.eccouncil.org/), still uses the familiar CEH,
CEH (Practical), and CPENT names on its application pages, and its *Retired
Certifications* page includes historical ECSA entries. A CPENT FAQ on that site
also addresses what happens to people who already hold an ECSA credential.

Those observations are consistent, not contradictory:

- **Catalogue** = what an issuer currently promotes and sells.
- **Certification administration site** = eligibility, policy, verification,
  and the historical record of credentials already awarded.
- **Retired list** = a record that a program existed and when its exam was
  withdrawn; it is not an invitation to buy a new exam.
- **A held certificate** = a real historical achievement for its holder; it
  does not become a currently available program again.

Practical consequence: study material built around the old ECSA path can still
teach useful analysis and reporting habits, but you should not plan a 2026
purchase on the assumption that ECSA is a live, currently catalogued exam.
Verify on [eccouncil.org](https://www.eccouncil.org/) and
[cert.eccouncil.org](https://cert.eccouncil.org/) immediately before spending
money. Issuer menus, labels, and program boundaries change without notice.

---

## Compare purpose, not prestige

A credential is a **signal with a cost**. The signal is "somebody assessed me
against this issuer's defined scope, under this issuer's rules, at this point in
time." The cost is study time, fees, maintenance obligations, and the
opportunity cost of not learning something else. Neither the signal nor the
cost is the same across issuers.

The table below is deliberately broad. It describes typical positioning and
audience, not exam mechanics. Do **not** read it as a statement of question
counts, durations, pass marks, prices, version numbers, or renewal quotas —
those are issuer-controlled details that must be checked at the source.

| Credential family | Issuer | Primary purpose | Typical audience | Prerequisites to verify | Skills it is designed to evidence | Lab / practical emphasis | How an employer may read it |
|---|---|---|---|---|---|---|---|
| **ECSA** (legacy / historical VAPT path) | EC-Council | Structured vulnerability analysis and the penetration-test workflow | Learners continuing older VAPT study; holders of an existing ECSA credential | Not currently catalogued; historical eligibility varied — verify before assuming anything | Analysis of findings, report structure, engagement process | Historically mixed, with a practical track in the family; treat current mechanics as unverified | "Familiar with a structured VAPT process"; useful context, but not proof of a current exam |
| **CEH / CEH AI** | EC-Council | Broad map of ethical-hacking concepts and terminology | People building a wide first map of offensive security | Issuer lists experience or official-training routes; confirm current rule | Breadth across attack categories, vocabulary, basic process awareness | Concept-led, with separate practical options in the family | "Has seen the vocabulary"; rarely sufficient on its own for a hands-on role |
| **CEH (Practical)** | EC-Council | Demonstrate applied skills in an issuer-controlled environment | Candidates who already know the concepts and want a practical signal | Check current eligibility with the issuer | Applying knowledge in a bounded lab scenario | Practical by design | "Can work in a lab exercise"; still not the same as client-facing judgement |
| **CPENT / CPENT AI** | EC-Council | Advanced, multi-zone practical penetration testing with a reporting component | Practitioners with prior testing exposure | Issuer states no preset eligibility for the exam itself, but readiness is a different question | Multi-environment reasoning, adaptation, professional reporting | Strongly practical; issuer describes varied network zones and a report requirement | "Has survived a demanding practical assessment"; weigh against actual role needs |
| **OSCP-like practical credentials** | OffSec and similar hands-on issuers | Prove sustained hands-on problem solving under time pressure | Learners who learn by doing and can commit to long lab practice | Usually no formal gate, but substantial self-study is normal | Persistence, independent reasoning, documenting a path through a lab | Very high; lab performance is the core signal | "Probably comfortable in a hands-on role" — but check communication and scope skills separately |
| **CompTIA PenTest+** | CompTIA | Vendor-neutral penetration-testing fundamentals including scoping and reporting | People entering testing from support, admin, or security operations | Issuer publishes recommended experience; verify the current level | Engagement management, discovery, analysis, reporting, some practical tasks | Blended: knowledge plus performance-style tasks | "Has a structured fundamentals baseline"; useful where HR filters on vendor-neutral names |
| **CompTIA Security+ / ISC2 CC** | CompTIA / ISC2 | Broad security foundations, not penetration testing | Career changers and junior analysts | Generally entry-friendly; check issuer pages | Core security concepts, threat vocabulary, basic operations | Limited offensive lab emphasis | "Has foundational literacy"; not evidence of testing ability |
| **CISSP and similar broad security credentials** | ISC2 and other professional bodies | Governance, risk, architecture, and programme-level security leadership | Mid-career and management-track professionals | Typically experience-linked; check the current requirement | Policy, risk, control design, organisational decision-making | Not a penetration-test lab signal | "Understands security at organisational level"; may impress HR, but says little about hands-on testing |

**Vendor statistics are marketing claims.** Issuers and training partners
publish numbers about pass rates, salary effects, employer recognition, and
"world first" status. Treat those as claims made by a party with a commercial
interest, not as guarantees about your outcome. Accreditation announcements
are likewise issuer-reported facts about a program's process, not a ranking of
which credential is "best."

---

## What does the credential actually prove?

This is the question that cuts through nearly every argument. A credential
proves that a defined assessment was passed under defined conditions. It does
not prove judgement under ambiguity, respectful handling of client data, or the
ability to write a finding a engineer will fix.

| Credential family | Strongest defensible claim | What it does **not** prove on its own | Evidence that corroborates it |
|---|---|---|---|
| ECSA (legacy) | The holder completed an assessment in a historical VAPT program when that program was available | That the program is currently purchasable, or that the holder can run a live engagement today | Date on the certificate, issuer verification, a portfolio of safe lab reports |
| CEH / CEH AI | Familiarity with a broad offensive-security vocabulary and concept map | Deep practical competence, safe scope handling, or report quality | A practical credential, lab notes, a reviewed mock report |
| CEH (Practical) | Ability to complete the issuer's practical tasks under its rules | Client communication, legal judgement, or work outside the lab design | A second, differently designed practical assessment; supervised work |
| CPENT / CPENT AI | Ability to handle an issuer-described multi-environment challenge, including the report component issuer materials describe | That every real engagement resembles that challenge, or that the holder works within a RoE without supervision | Real engagement records with authorisation, client-facing reports reviewed by a senior |
| OSCP-like | Sustained hands-on problem solving in a lab under time constraints | Polished reporting, stakeholder management, or awareness of organisational risk | Written findings, retest experience, peer review |
| PenTest+ | Fundamentals across scoping, discovery, analysis, and reporting, with some performance-style tasks | Expert-level exploitation or extensive real-world range time | A lab portfolio plus a practical credential |
| Security+ / CC | Foundational security literacy | Any meaningful offensive-testing capability | Applied coursework, labs, an entry-level security role |
| CISSP-class | Broad organisational security understanding and experience exposure | Ability to run a technical test or write a technical finding | Demonstrated work in risk, architecture, or programme leadership |

Notice the repeated shape: **one assessment samples one slice of competence**.
 Employers who understand this look for a bundle of signals — credential,
 evidence of practice, references, and interview reasoning. A candidate who
 says "the certificate proves I can test your production network" has already
 failed the judgement part of the interview.

---

## An ASCII decision diagram

This is a **decision aid**, not a rulebook. Follow experience and target role
first; follow prestige last. Every "STOP" branch is a real outcome: it means
"fix the prerequisite or change the goal," not "try harder and hope."

```
                  +-----------------------------------+
                  | What is your current experience?  |
                  +----------------+------------------+
                                   |
        +--------------------------+---------------------------+
        |                          |                           |
  [0-1 years / student]     [1-3 years in IT/sec]      [3+ years in sec]
        |                          |                           |
        v                          v                           v
 +------------------+      +------------------+        +--------------------+
 | Do you want      |      | Do you want      |        | Is the goal        |
 | breadth first?   |      | a testing role?  |        | leadership/risk?   |
 +---+----------+---+      +---+----------+---+        +---+------------+---+
     |YES       |NO            |YES       |NO               |YES        |NO
     v          v              v          v                 v           v
 +---------+ +---------+  +---------+ +-----------+  +-----------+ +-----------+
 |Foundations| |Lab habits| |Scoping &| |Broad sec  |  |Broad org  | |Deep hands |
 |credential| |first:    | |reporting | |credential |  |credential | |on: CPENT/ |
 |(Sec+/CC) | |small lab | |baseline: | |(Sec+ then |  |(e.g. CISSP)| |OSCP-like  |
 |then re-  | |portfolio | |PenTest+  | |specialise)|  |then map   | |then pick  |
 |assess    | |+ one exam| |or CEH(P) | |later      |  |to role    | |a niche    |
 +----+-----+ +----+-----+ +----+-----+ +-----+-----+  +-----+-----+ +-----+-----+
      |            |            |             |              |            |
      +------------+------------+-------------+--------------+------------+
                                   |
                                   v
                    +-------------------------------+
                    | Can you name 3 artifacts you  |
                    | can show without permission?  |
                    +---------------+---------------+
                            |NO            |YES
                            v              v
                   [STOP: build     +-----------------------------+
                    lab reports,    | Read 10 real job postings;  |
                    do not buy      | mark required vs preferred; |
                    another exam]   | choose ONE gap to close     |
                                    +---------------+-------------+
                                                    |
                                                    v
                                     [Reassess in one quarter]
```

Two branches deserve special attention. A beginner who buys an advanced
practical credential before building lab habits usually pays twice: once for
the exam, once for the retake after discovering the gap. An experienced analyst
who chases a second broad credential instead of a specialty may gain HR
recognition but lose a quarter of focused skill-building. Neither mistake is
about intelligence; both are about choosing the wrong signal.

---

## Case study 1 — A beginner with no experience

**Context.** "Rani" finished a computing diploma and wants to move into
security. She has no security job, no home lab, and a modest budget. A training
advertisement tells her that one advanced practical badge is the "fastest route
to a penetration testing career." A local job page asks for a security
credential *or equivalent demonstrated knowledge*.

**Constraints.** She can study about twelve hours a week. She cannot afford
both a premium exam and a year of lab subscriptions. She lives in a region
where employers ask for vendor-neutral names more often than EC-Council names.
She also has a family-shared home network, so a carelessly configured virtual
machine could touch devices she does not own.

**Decisions.** Rani writes a one-page boundary for her own lab: named machines,
no bridged adapters, no cloud trials tied to a shared card, and a stop rule if
anything unexpected answers. She spends the first quarter on a foundational
security credential and on lab notes: an asset list, a hypothesis table, and a
short report written for a fictional defender. In the second quarter she reads
ten local postings. Six mention a broad foundation credential, two mention an
offensive credential as *preferred*, and none require ECSA. She concludes that
the "fastest route" claim is a marketing statement, not a local hiring rule.

For the third quarter she chooses a fundamentals-level testing credential with
a reporting component, because it matches the gap she can actually close:
scoping language and clear findings. She deliberately postpones an advanced
practical exam until she can complete a small lab exercise and explain her
evidence without guessing.

**What this teaches.** The right first purchase was not the most impressive
badge. It was the credential that matched the evidence she could build next.
Her lab boundary was as important as her study plan: being a beginner does not
suspend authorization rules. And the job postings — not the advertisement —
told her which names mattered locally.

---

## Case study 2 — An experienced analyst choosing a specialty

**Context.** "Mateo" has several years in a security operations centre. He is
comfortable with logs, alerts, and escalation. He wants to move into
consulting-style testing. His manager will sponsor one credential and one
conference. Colleagues argue between an EC-Council advanced practical path and
an OSCP-style lab credential.

**Constraints.** His work involves regulated data, so client confidentiality
and evidence handling are non-negotiable. He can study on weekday evenings but
not for long weekend blocks. He has good incident-response habits and weak
report-writing habits: his tickets are terse and rarely state prerequisites or
compensating controls.

**Decisions.** Mateo does not compare pass-rate claims. He defines the target
role by writing five tasks he wants to be trusted with: agree a scope, produce
a hypothesis list, demonstrate impact safely in a lab, write a defensible
finding, and handle a retest. He maps each credential to those five tasks. The
advanced EC-Council practical path scores highly on multi-environment reasoning
and report submission; the OSCP-style path scores highly on sustained lab work
but less explicitly on client-facing report structure.

He chooses the path with the explicit report requirement, then uses the
sponsored conference for a writing workshop rather than another exam voucher.
He validates the choice with his manager by showing the five-task map and
promising two artefacts: a redacted mock finding and a retest criterion. Six
months later he can show both. He still respects the other path; it simply
optimised for a different gap.

**What this teaches.** Specialisation is a decision about *evidence gaps*, not
about which community has the louder forum. Mateo's existing experience meant
he could skip foundational credentials. His weak spot was communication under
confidentiality constraints, so he bought training that targeted it. The
"loser" in the debate was not a bad credential — it was a poor fit for the
stated goal.

---

## Reading job postings critically

A posting is a loose negotiation, not a contract. Recruiters often copy a
wish-list from a previous hire, and the person who will interview you may care
about different things than the person who wrote the list. Your job is to
translate phrases into evidence requirements.

| Posting phrase | Usual underlying need | What to ask or show |
|---|---|---|
| "CEH or equivalent" | A vocabulary and breadth signal, often from an HR template | Ask what an equivalent demonstration looks like; offer lab notes or a report |
| "OSCP preferred" | Comfort with sustained hands-on work | Ask whether a different practical assessment or portfolio is accepted |
| "ECSA / LPT listed" | Possibly an older template or a legacy holder's qualification | Ask whether a current credential in the same family satisfies the intent |
| "Minimum N years experience" | A proxy for judgement under supervision | Describe specific engagements or lab-equivalent decisions, not just dates |
| "Strong reporting skills" | The team is drowning in unreadable findings | Bring a redacted finding with prerequisites, severity rationale, and retest criterion |
| "Understanding of frameworks" | They need shared language with auditors and clients | Name the frameworks you have actually read; do not claim fluency you lack |
| "Security clearance required" | A legal or contractual condition, not a skill | Ask about eligibility rules; this article is not legal or immigration advice |
| "Vendor-neutral certification required" | A procurement or HR filter | Check the issuer's current catalogue and the exact accepted names |

A useful habit is **three-column annotation**. Copy the posting into a table
with columns: *literal phrase*, *what I think it means*, *evidence I can show*.
If the third column is empty, you have found your study task. If the first
column contains a credential that is retired, write a question rather than an
assumption. Employers often appreciate a candidate who notices that their
template is stale — provided the question is polite and specific.

Remember that marketing claims cut both ways. An issuer's "most recognised"
claim, a bootcamp's salary statistic, and a forum's "everyone asks for X" are
all second-hand signals. Ten current postings from the region where you want to
work are a better sample than any of them, and even that sample is a snapshot,
not a promise.

---

## Practice by decision

Answer aloud before opening the key. These are scenario questions about
choices, not definitions.

1. A course seller says ECSA is "still the standard advanced exam" and offers a
   large discount today. What do you check before paying?
2. A posting requires "CEH or equivalent" but you hold a different practical
   credential. What is your next move?
3. You have no experience and want a hands-on role. Why is starting with a
   foundational credential defensible, and when would it be a delay?
4. A colleague says an OSCP-style credential proves someone can write a good
   client report. How do you respond?
5. You hold a legacy ECSA certificate from years ago. How do you describe it
   accurately on a CV?
6. An employer asks for "three years of penetration testing experience" and you
   have three years of SOC work. What evidence do you assemble?
7. Your manager offers to fund either an advanced practical exam or a report
   writing workshop. Your team's last ten reports were rejected for missing
   prerequisites. Which do you choose and why?
8. A vendor page claims its credential raises salaries by a large percentage.
   How do you treat that claim in a decision worksheet?
9. A job advert lists an issuer credential that is no longer in the current
   catalogue. What do you do with that information?
10. You are choosing between a broad management credential and a hands-on one.
    What question about your next role settles it fastest?
11. A learner wants to practise at home but the lab uses a bridge to the family
    router. What is the first decision, before any credential discussion?
12. After a rejected application, you are tempted to buy another badge. What
    should you do first?

<details>
<summary><strong>Answer key</strong></summary>

1. Open the issuer's current catalogue and certification administration site on
   the date of purchase; check whether ECSA is listed at all, what the current
   CEH/CPENT labels are, and what the seller's discount is actually for. Treat
   the sales claim as a claim, not a fact.
2. Ask what "equivalent" means to the hiring team and offer concrete evidence:
   a practical credential, lab notes, or a redacted report. Do not assume the
   acronym filter is literal, and do not pretend the CEH name is identical to
   your credential.
3. It is defensible because foundations reduce wasted lab time and improve
   scope/reporting language. It becomes a delay if you already hold those
   foundations or if the target role screens specifically for practical
   evidence — then build the lab portfolio and pursue a practical signal sooner.
4. Disagree gently: such credentials are strong evidence of lab persistence and
   problem solving, not of client-facing writing, severity rationale, or
   confidentiality judgement. Ask for a report sample if writing matters.
5. Name the credential as a historical achievement, give the award date, and
   avoid implying it is a currently purchasable program. If asked, point to
   the issuer's retired list and your current skills separately.
6. Pull actual artefacts: scopes you touched, hypotheses you wrote, findings
   you reviewed, escalations you handled, and retests you supported. Frame the
   gap as "testing-specific evidence" rather than "years missing".
7. The workshop. A repeated rejection reason is a measured gap; an advanced
   exam does not automatically fix writing. Fund the exam after the next
   report passes review.
8. Label it a vendor marketing claim. Record the source and date, exclude it
   from the decision score unless independently verified, and prefer local
   posting data.
9. Note the staleness, verify on the issuer sites, and ask the recruiter whether
   a current equivalent is acceptable. Do not buy a retired program on the
   strength of a stale template.
10. Ask: "Will I be accountable for a technical test next year, or for a
    security programme?" The first points to hands-on evidence; the second to
    broad organisational credentials.
11. Fix the boundary first: remove the bridge or otherwise isolate the lab,
    write down what is in scope, and confirm the network configuration. No
    credential decision matters until the lab is genuinely yours to use.
12. Ask for specific rejection feedback and compare it with ten postings. Buy a
    credential only if the feedback names a skill that credential demonstrably
    develops; otherwise build the missing artefact.

</details>

---

## Common mistakes worth memorising

- **Acronym collecting.** Adding letters faster than you add evidence.
- **Prestige shopping.** Choosing by forum volume instead of role requirements.
- **Retirement denial.** Treating a historical credential as a current purchase.
- **Format fetish.** Memorising exam mechanics while ignoring what the badge
  samples.
- **Single-signal hiring.** Assuming one credential proves scope discipline,
  reporting, and ethics at once.
- **Marketing math.** Turning issuer statistics into personal guarantees.
- **Template worship.** Copying a job posting's wish-list without asking what
  the team actually needs.
- **Permission drift.** Letting a lab exercise spill onto shared infrastructure
  because "it's only practice".
- **Sunk-cost stacking.** Buying another exam after a rejection instead of
  asking why the application failed.

---

## Reusable templates

Copy these into your notes. They are structures for honest decisions, not
completed answers.

### Credential decision worksheet

```
Goal role:            [one sentence]
Experience today:     [years + two concrete responsibilities]
Gap to close:         [ONE gap, stated as an observable behaviour]
Options considered:   [A / B / C]
Evidence each gives:  [what a verifier could conclude]
Evidence each lacks:  [what remains unproven]
Issuer verification:  [URL + date checked]
Local posting sample: [10 postings, required vs preferred counts]
Decision:             [one option + why the others were not chosen]
Review date:          [one quarter from now]
```

### Job posting annotation

| Literal phrase | My interpretation | Evidence I can show | Question to ask |
|---|---|---|---|
| | | | |

### Proof-of-work map

| Claim I want to make | Credential signal | Artefact signal | Who can verify |
|---|---|---|---|
| I can scope safely | | redacted scope + RoE | mentor / client |
| I can rank findings | | hypothesis table with rejected items | peer reviewer |
| I can report clearly | | one finding with prerequisites + retest | hiring manager |
| I can stop when needed | | incident note describing escalation | supervisor |

### Weekly study question

```
This week, did I produce an artefact a reviewer could criticise?
If no: I consumed content, not evidence.
```

---

## Glossary

| Term | Plain-language meaning |
|---|---|
| **Credential** | A third-party assessment recorded under an issuer's rules |
| **Issuer** | The organisation that defines, delivers, and verifies the assessment |
| **Catalogue** | The issuer's current list of offered programs — a snapshot, not history |
| **Retired program** | A program whose exam is no longer offered; existing holders keep their record |
| **Legacy path** | A historical route that still teaches useful habits but is not current |
| **Prerequisite** | A condition the issuer asks you to meet before assessment |
| **Vendor-neutral** | Not tied to one product vendor; still owned by a particular issuer |
| **Practical emphasis** | How much of the signal comes from performing tasks rather than recalling concepts |
| **Marketing claim** | A promotional statement by an interested party, not an independent guarantee |
| **RoE** | Rules of Engagement: the agreed limits, timing, contacts, and stop conditions |
| **Proof of work** | Artefacts — reports, lab notes, retest records — that support your claims |
| **Signal** | What an observer can reasonably infer from a credential or artefact |
| **Equivalent** | A posting's invitation to show different evidence for the same underlying need |

---

## References and verification

- EC-Council current catalogue and program pages — check the 26 Nov 2026
  observation yourself; labels and listings change:
  [eccouncil.org](https://www.eccouncil.org/).
- EC-Council certification administration — eligibility, retired programs,
  verification, policy, and statements about existing holders:
  [cert.eccouncil.org](https://cert.eccouncil.org/). Verify current rules
  before any purchase; do not rely on this article for formats, prices,
  pass marks, version numbers, or maintenance quotas.
- OffSec courses and certifications — current OSCP positioning and neighbouring
  practical credentials: [offsec.com](https://www.offsec.com/certifications/).
- CompTIA Security+ and PenTest+ — current focus, recommended experience, and
  exam documents: [comptia.org](https://www.comptia.org/certifications/).
- ISC2 CC and CISSP — entry-level and experience-linked broad credentials:
  [isc2.org](https://www.isc2.org/certifications).
- Your own target job postings — dated, regional, and saved as evidence. They
  are more relevant to your decision than a global claim about "the best" cert.
- Issuer statistics, accreditation announcements, and partner claims are
  **marketing claims** unless independently verified. Accreditation concerns a
  program's process; it is not a comparative ranking of holders.

This article is education, not legal, financial, tax, or regulatory advice.
It is not official course material and it does not replace issuer
documentation, a signed engagement agreement, or a qualified professional's
judgement. All case studies are fictional and contain no technical procedure.

## See also

- [What Is ECSA](what-is-ecsa.md)
- [Penetration Testing Methodology](pentest-methodology.md)
- [Scope, Authorization & Ethics](scope-and-ethics.md)
- [ECSA Exam Format & Versions](../exam/exam-format.md)
- [Training, Labs & Practice Range](../exam/training-and-labs.md)
- [Next Certifications & Skills](../career/next-steps.md)
- [Skills, Hiring & Reality Check](../career/reality-check.md)
- [Building a Safe Portfolio](../career/portfolio.md)
- Companion worksheet (CSIX companion site): [ECSA vs CEH & Other Certs](https://siedysoes.github.io/csix-ecsa/tools/credential-decision-worksheet/)
- Companion Indonesian edition: [ECSA vs CEH & Sertifikasi Lain](https://siedysoes.github.io/csix-ecsa/id/fundamentals/ecsa-vs-ceh/)
