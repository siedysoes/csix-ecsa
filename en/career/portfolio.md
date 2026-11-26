# Building a Safe Portfolio

> **Independent, unofficial study resource.** EC-Council, CEH, ECSA, LPT and
> other credential names are trademarks of their respective owners. This site is
> not affiliated with or endorsed by EC-Council and contains no official
> courseware, exam dumps, or copyrighted material. When EC-Council's catalogue
> was checked on **26 Nov 2026**, ECSA was not listed among current
> certifications; treat it as a **legacy / historical VAPT path** and verify
> credential claims on [eccouncil.org](https://www.eccouncil.org/) and
> [cert.eccouncil.org](https://cert.eccouncil.org/). Every artefact here must
> come from a system you own, a range whose rules you follow, or work covered by
> **explicit written permission that includes publication**. This article is
> about **process, judgment, evidence, and defence** — no commands, payloads,
> exploits, evasion instructions, or real target data. Education, not legal,
> financial, tax, or regulatory advice.

A portfolio is a small, curated set of records that lets someone judge how you think. It is not a screenshot scrapbook, a badge shelf, or a library of attack recipes. The useful question is not *"what did I find?"* but *"what boundary did I work inside, what did I observe, what did I infer, and what did a defender learn?"* Three carefully bounded write-ups with honest limitations beat twenty unresolved captures.

The design constraint is simple: **a portfolio must never create a new victim**. Publishing a finding about a real system can harm its users even when the original testing was authorised — testing permission and publication permission are separate decisions. Ownership of a screenshot is not ownership of the information inside it. If a detail is not needed for the reader's decision, leave it out. Artefact-first career thinking is developed in [Careers After ECSA](ecsa-careers.md); the permission boundary is covered in [Scope, Authorization & Ethics](../fundamentals/scope-and-ethics.md).

## Learning objectives

After working through this article you should be able to:

1. Explain four purposes a portfolio serves and name an artefact for each.
2. Classify an artefact as **publish / sanitise / withhold** with a stated reason.
3. Apply minimum-necessary disclosure to an image, a report, and a repository.
4. Narrate a lab exercise so a defender learns a control lesson, not a reproduction recipe.
5. Choose a repository structure and licence that do not republish other people's material.
6. Recognise privacy and employer-policy traps, including metadata and permission scope.
7. Score a portfolio against a reviewer's rubric and repair the weakest artefact.
8. Write an index entry, a redaction checklist, and a pre-publish decision record.

If you can do items 2, 3, and 4, your portfolio can be read safely. If you cannot, more artefacts only spread the risk.

---

## What a portfolio is for

Hiring is a risk decision: can you be trusted with a client's scope, a change window, and a report that drives expensive work? A portfolio answers with **evidence rather than adjectives**.

| Purpose | What the reader needs | Weak substitute |
|---|---|---|
| Prove judgment | A named boundary, a respected stop, an assumption refused | A list of tools used |
| Prove communication | One observation written for an engineer and for a manager | Raw output with no explanation |
| Prove learning over time | Dated revisions and a claim withdrawn after review | One polished document with no history |
| Prove restraint | Details deliberately omitted, with reasons | "I could have done more" with no support |

The audience matters. A **hiring reviewer** wants evidence and caution; a **defender or peer** wants a control lesson; **you** want a learning record that survives memory decay. One artefact can serve all three if it labels its source honestly. A **minimal viable portfolio** is three items: a bounded lab write-up, a methodology or control-design map, and a self-assessment containing a reviewer's correction.

**Claim accuracy.** If you studied ECSA-era material, say so with the year and the legacy status you verified with the issuer. Do not present it as a current program with a known version or format. The artefact carries the weight; the credential is context. For the phases behind the evidence, see [Penetration Testing Methodology](../fundamentals/pentest-methodology.md).

---

## Evidence types you can produce safely

An **artefact** is any dated record another person can inspect. These types carry the most weight.

| Artefact type | Safe version | Unsafe version |
|---|---|---|
| Lab notes | Owned VMs with fictional names; question, boundary, date, and observed / inferred / unknown columns | Notes naming a family member's device or a real address |
| Sanitised report | Synthetic organisation, regenerated evidence, limitation, owner and retest condition | Client report with logo, asset IDs, staff names, and URLs left in |
| Methodology map | Phase-to-gate chart naming artefacts, with no target detail | Engagement checklist with client-specific exceptions attached |
| Control design | Diagram of a proposed safeguard, its failure modes, and verification condition | Configuration copied from a live environment, including real values |
| Self-assessment | Dated reflection naming a withdrawn claim and a reviewer's change | Self-praise, or an invented score presented as authoritative |
| CTF note | Published after the event under its rules, reframed as a control lesson | Live flags, exact reproduction, or a link to a running platform |
| Evidence image | Regenerated screenshot with uniform synthetic labels | Cropped real capture whose tabs, metadata, or background identify someone |
| Timeline / journal | Your own activity log with generic labels and owned windows | Exported logs with usernames or another tenant's traffic |

**Lab notes** are raw material: keep them detailed and mostly private, then publish a derived note. A **methodology map** shows structure without exposure — phases, exit gates, and the artefact each produced. A **control design** points forward: the safeguard, the assumption it relies on, how it could fail, and what observation would show it works. A **self-assessment** records the claim you first made, the weakness in its evidence, and the revised claim; that demonstrates coachability better than a flawless report nobody challenged.

**Synthetic and fictional case studies** are legitimate when labelled. Synthetic means invented environment and identities; fictional composite means combined scenarios, with no implied real organisation. Do not launder a real incident into fiction by changing the name — industry, city, dates, and unusual details can still identify it. If the facts came from work, keep them out of public writing unless the owner approved the exact published text.

---

## The publish / sanitise / withhold decision

Apply three tests in order: **right to share** (do you own it, or is publication explicitly permitted?), **harm to others** (can it identify a person, customer, or system?), and **value to the reader** (does it teach a decision or a control?). A failed first or second test ends in withhold; so does a failed third — clutter is not portfolio material.

```
             +------------------------------------------+
             | Candidate artefact                       |
             +--------------------+---------------------+
                                  v
             +------------------------------------------+
             | 1. Owned, or explicit written permission  |
             |    to publish this version?              |
             +-------+-------------------------+--------+
                     |NO                       |YES
                     v                         v
          [ WITHHOLD — private ]    +-----------------------------+
          | never publish first    | 2. Can it identify a person,|
          |                        |    customer, or real system?|
          +------------------------+---+--------------+-----------+
                                        |YES           |NO
                                        v              v
                             +------------------+  +----------------+
                             | 3. Remove every  |  | 4. Teaches a   |
                             | identifier incl. |  | decision or    |
                             | metadata/history?|  | control?       |
                             +--+----------+----+  +--+--------+---+
                                |NO        |YES       |NO      |YES
                                v          v          v        v
                         [WITHHOLD] [SANITISE] [WITHHOLD] [PUBLISH]
                         | rebuild  | re-verify| no filler | label source
                         | synthetic| loop to  | or flags  | + limits
                         | lab      | step 2   | only      | + feedback
                         +----------+----------+-----------+----------+
```

**Withhold is a professional outcome**, not failure. Keep the item in a private evidence folder, use it to support an interview answer without showing it, and record why. When rights are unclear — unread competition rules, unchecked platform terms, a tutor's material you do not own — treat unclear as no. **Sanitise** means substitute equivalence-preserving fiction and re-check the whole artefact; if the lesson dies with the identifiers, rebuild the exercise. **Publish** only after a second person who did not produce the artefact has reviewed it: fresh eyes catch the username in a title bar the author stopped seeing.

---

## Minimum-necessary disclosure

**Minimum-necessary disclosure** means sharing only the detail the reader needs for the decision at hand. Decide the lesson first; then construct evidence that carries nothing else.

| Data class | Default action | Safe substitute |
|---|---|---|
| Names, usernames, email addresses | Remove | Role labels: operator, reviewer, owner |
| Hostnames, addresses, domains | Replace | Reserved fictional names such as `lab-a.example.test` |
| Engagement timestamps | Generalise | "Week 2 of the exercise" or an owned lab date |
| Real interface screenshots | Regenerate | Synthetic page with neutral labels, no live links |
| Tokens, keys, session values, personal records | Never publish or paste | A note that no real secrets were used |
| Internal paths and identifiers | Replace | Generic categories: configuration file, asset A |
| Log excerpts | Rewrite | One invented conceptual line |
| Logos and report templates | Remove | Your own plain title |
| Metadata and embedded data | Strip and verify | Freshly exported file with no hidden fields |
| Repository history | Treat as published | A clean repo starting from sanitised files |

Redaction fails predictably. A black box can leave selectable text; a crop can leave a reflection, browser tab, notification, or unique wallpaper. **Combinations re-identify**: industry, city, date, and role can point to one person even with every name gone. Unique error strings, unusual product versions, and internal codenames act as fingerprints. Prefer **regeneration over redaction** — build a harmless page with the same layout and photograph that instead. Treat every published file as immutable: assume it is cached and indexed within minutes, so the pre-publish pass matters more than a later apology.

If you discover a real weakness unintentionally, stop and report it privately through the owner's designated channel. Do not publish, hint at it, or reuse it as portfolio material. Any disclosure obligation is for the owner and applicable local rules to determine; this is not legal advice.

---

## Narrating a lab without weaponising it

Use a six-beat shape: **question** (what you wanted to learn); **boundary** (owned systems, exclusions, stop condition); **observation** (fact, date, generic source); **inference** (claim, explicitly separated); **limit** (what you did not establish and why it would need more evidence elsewhere); **defensive change** (control or check, plus how you would know it works).

```
Title:          [neutral, no target name]
Source:         [owned lab / range / authorised exercise]
Question:       [one sentence]
Boundary:       [included / excluded / stop condition]
Observation:    [fact, date, generic source]
Inference:      [claim, separated from fact]
Limit:          [what was NOT established]
Defensive idea: [control a defender could adopt]
Verify by:      [observable condition]
Feedback:       [reviewer role, date, change made]
```

Write at the level of **conditions and signals**, not steps: "an access check was missing on an internal function" teaches as much as a walkthrough and harms nobody. Avoid a "try this at home" tone that invites readers to point the technique at systems they do not own. Show unsuccessful paths — the discarded scanner result, the control that blocked you — because those are what defenders learn from. Keep severity a reasoned priority built from exposure, prerequisites, impact, and compensating controls, never a borrowed label.

**CTF writeups** need care. Read the event rules first, wait for any required period, and keep private if unclear. A flag is a receipt, not evidence of judgment; the artefact is the assumption exposed, the corresponding defensive check, and the question a puzzle cannot answer.

---

## Repository hygiene and licensing

A repository is a publication channel: **version history is public too**. Start clean, keep raw captures and client-derived material outside the public repository, and review the complete history before each share.

```
portfolio/
├── README.md                 # index: one line per project + link
├── notes/
│   ├── evidence-handling.md  # storage, retention, destruction
│   └── review-log.md         # who challenged what
├── lab-01-web/
│   ├── report.md             # sanitised six-beat narrative
│   ├── scope.md              # owned systems, exclusions, stop
│   └── evidence/             # regenerated synthetic images only
└── control-designs/
    └── role-separation.md    # diagram + verification condition
```

The `README.md` is the index; commit messages are part of the evidence trail, so describe the reasoning change. A file deleted in the newest revision may remain in earlier ones — late clean-up is not clean-up. Avoid forks or mirrors that copy material you do not control, and never store real credentials in examples, even in a private branch.

| Repository element | Safe habit | Common leak |
|---|---|---|
| Evidence folder | Regenerated images, neutral labels | Original capture with personal data |
| Issue tracker | Your questions and reviewer feedback | Pasted client tickets or colleague names |
| Commit history | Sanitised files from the first revision | Raw file committed early and "removed" later |
| Example configuration | Placeholders and invented values | Real token, internal address, customer ID |
| Documentation | Your own prose and diagrams | Course slides or vendor report template |

**Licensing** is about permission to reuse. By default your work is all rights reserved; to invite reuse, state a licence explicitly in a `LICENSE` notice and verify its terms from the licence text. But you cannot licence what you do not own: client templates, courseware, logos, platform screenshots, and a reviewer's comments belong to their owners. If employment or client terms require approval for external writing, obtain written approval for the specific text and images. Verify local terms; this is not legal advice.

Companion pages with exact titles will be available at placeholder paths; replace `siedysoes` when deploying:

- [Careers After ECSA](https://siedysoes.github.io/csix-ecsa/en/career/ecsa-careers.md)
- [Next Certifications & Skills](https://siedysoes.github.io/csix-ecsa/en/career/next-steps.md)
- [Skills, Hiring & Reality Check](https://siedysoes.github.io/csix-ecsa/en/career/reality-check.md)
- [Training, Labs & Practice Range](https://siedysoes.github.io/csix-ecsa/en/exam/training-and-labs.md)

---

## Publishing a write-up a defender can learn from

Lead with the decision, keep mechanics out of the executive page, and give the defender something to check on their own systems.

| Section | Defender's question | Safe content |
|---|---|---|
| Summary | Why read this? | Pattern, risk, and control in one paragraph |
| Source and boundary | Real or synthetic? | Lab label, owned systems, exclusions |
| Question / observation | What is known? | Hypothesis in plain language; synthetic evidence, generic labels |
| Inference / limitation | What is concluded? | Claim with prerequisites, confidence, and enumerated gaps |
| Defensive options | What can I change? | Two or three options with trade-offs and an owner |
| Verification | How do I know it worked? | An observable condition to check later |
| What I revised | Did review change it? | Reviewer role, date, corrected statement |

State priority as a **reasoned** judgement: exposure, prerequisites, business impact, and compensating controls, with a note that lab impact is illustrative. Include **positive findings** — controls that blocked you — so the write-up is not a failure catalogue. Use two review passes: a **technical pass** (is the inference supported, is the limitation honest, can a defender act?) and a **disclosure pass** (can anyone be identified directly or by combination, and does any file hide metadata or history?). Ideally different people do them; authors are the worst detectors of their own assumptions.

For a real engagement under permission, publish only excerpts approved in writing. If approval is refused, publish the methodology map, control design, or lesson learned — never a veiled version of the same facts. A reviewer respects a private-evidence explanation; they will not respect a "sanitised" report that still names the client's city and unusual internal tool.

---

## Privacy and employer-policy traps

| Trap | Why risky | Safer move |
|---|---|---|
| Screenshot on a work laptop | Wallpaper, tabs, or device name identify an employer | Regenerate in a personal synthetic environment |
| Blur-only sanitisation | Pixels, metadata, or reflections remain | Produce a fresh synthetic image |
| "Fictional" real case | Residual context re-identifies the source | Invented roles and reserved names |
| Client logo in a template | Confidential material you cannot licence | Plain template of your own |
| Testing permission = publishing permission | New audience, new harm | Ask for publication approval explicitly |
| Unread CTF rules | Live solutions can break the event | Read rules, wait, or keep private |
| Course material in a repo | You cannot republish it | Publish only your own notes |
| Named reviewer without consent | Privacy and consent issue | Role label and date; ask before quoting |
| Sensitive file left in history | Deletion does not remove revisions | Clean repository from the first revision |
| Upload to unapproved third-party tool | Data leaves your control and may be retained | Use approved storage only |
| "Just one real example" verbally | Discloses more than intended | Labelled synthetic example with a reason |
| Lab on a shared home network | Boundary may include someone else's device | Verify the boundary before publishing |

Before publishing, answer three questions in writing: **Who owns this? Who could be harmed by it? Who authorised publication of this exact version?** If any answer is unclear, the artefact stays private. Record the decision so you can explain it later.

---

## How reviewers evaluate a portfolio

Reviewers scan the index, open one artefact, then probe it in conversation. Make the strongest evidence easy to find.

| Dimension | Strong signal | Weak signal |
|---|---|---|
| Boundary clarity | Scope, exclusions, stop condition on page one | Boundaries absent or buried |
| Source honesty | "Synthetic lab" stated up front | Lab work described as client work |
| Evidence quality | Few relevant sanitised exhibits tied to claims | Many unexplained screenshots |
| Reasoning | Observation, inference, limitation separated | Conclusion presented as fact |
| Defensive value | Control options and verification condition | Nothing to change |
| Communication | Two summaries for two audiences | Jargon with no decision |
| Learning trajectory | Dated revisions and a withdrawn claim | One document, no history |
| Response to review | Correction recorded and applied | Defensive tone or none |
| Safety and restraint | Private material withheld with reason | Sensitive detail "forgotten" in repo |

A realistic **ninety-second scan** looks for a title, source label, date, boundary, and working link. Then a finding is tested: what was observed, what was assumed, what would prove a fix? The conversational probe — "what did you not do, and why?" — cannot be faked by polish. Self-score each artefact zero to two on these dimensions; a zero is a repair task, not a reason to start another project.

---

## Three fictional case studies

Fictional composites with no technical procedure — only context, constraints, decisions, and lessons.

### Case 1 — Ayu, the student with real-looking screenshots

**Context.** Ayu drafted a public write-up from an owned home lab. No passwords or customer records appeared, but a terminal title bar showed a hostname matching a local business, a browser tab showed her personal email, a notification revealed her network name, and the timestamp and product version were distinctive.

**Constraints.** She owned the lab, so testing permission was clear. Publication permission for the identifying cues was not hers to grant: the business name and her personal details affect other people or herself in a lasting way. Blurring would not remove all the signals.

**Decisions.** She withdrew the draft before indexing. Instead of blurring, she rebuilt the page in a fresh synthetic environment with reserved names and took new images. Originals went into a private folder with a withhold note. The public version states: "synthetic home lab; no external systems involved." A classmate performing the disclosure pass found a document property she had missed.

**What this teaches.** Lab ownership does not make every detail publishable. Harmless-looking cues combine into identification; regenerating evidence beats redacting it; recording a withheld item shows judgment.

### Case 2 — Rafi, the consultant with client data

**Context.** Rafi supports assessments at a fictional consultancy and wants real-world evidence. His draft report contains asset identifiers, internal URLs, staff roles, log excerpts, and the client's logo. The engagement letter permits discussion but is silent on publication; client policy requires written approval for external samples.

**Constraints.** He cannot publish the report, and renaming the client would not help because the technical details are distinctive. His employer requires review of external writing about client work.

**Decisions.** He requests written review and a client-approved sample; the client declines. He publishes three artefacts with no client facts: a methodology map with gates and stop conditions, a role-separation control design with a verification condition, and a labelled reflection on what review taught him about impact claims. The real report stays in approved storage and informs interview answers only in general terms.

**What this teaches.** Permission to work is not permission to show. When a real artefact cannot be shared, defensive ideas and reasoning still can be. Saying "I can't show that; here is the control lesson" is professional, not weak.

### Case 3 — Nia, the learner with only CTF flags

**Context.** Nia has many competition flags and solve notes, no client work, and no lab report. One competition forbids solutions until after the event; another discourages exact reproduction. Some notes contain platform URLs and teammate handles.

**Constraints.** Flags prove puzzle completion, not judgment about scope or defence. She cannot publish during a restricted window, and she has no reviewer.

**Decisions.** She waits for the rules to allow publication, then rewrites two notes as defensive lessons: an assumption in an access check and trust placed in unvalidated input. Flags, handles, and reproduction steps go; a limitation section explains what a puzzle cannot establish about production, and a verification condition covers each control. A third artefact is a self-assessment of the boundary questions she would ask before an assessment, reviewed by a study partner. All are labelled "training event; synthetic exercise".

**What this teaches.** The artefact is the reasoning, not the flag. Obey event rules, reframe competition work as a control lesson, and add the boundary discipline flags cannot demonstrate.

---

## Common mistakes worth memorising

- **Screenshot worship.** Captures treated as proof instead of evidence tied to a claim.
- **Lab laundering.** Dropping "lab" so synthetic work sounds like client work.
- **Permission confusion.** Assuming testing approval covers publication.
- **Blur theatre.** Redacting visible text while metadata and history remain.
- **Combination blindness.** Forgetting that place, date, and role can identify someone.
- **Flag hoarding.** Publishing receipts with no inference or defensive lesson.
- **Trophy inflation.** Listing a legacy credential as current because it sounds stronger.
- **Weaponised write-ups.** Teaching a route instead of the control that stops it.
- **History amnesia.** Deleting a file but ignoring earlier revisions.
- **Licence trespass.** Republishing courseware, templates, or a client document.
- **Quantity spiral.** Adding a tenth shallow artefact instead of repairing the second.
- **Review avoidance.** Publishing without a second pass, then blaming reviewers.

---

## Reusable templates and checklists

### Redaction checklist

- [ ] Source owned, synthetic, or covered by written publication permission.
- [ ] Permission covers this exact version, including images and quotes.
- [ ] No names, usernames, email addresses, or personal identifiers remain.
- [ ] No real hostnames, addresses, domains, or internal project names remain.
- [ ] No tokens, keys, session values, or personal records appear anywhere.
- [ ] Images regenerated or checked for tabs, notifications, reflections, backgrounds.
- [ ] File properties, embedded comments, and document metadata stripped and verified.
- [ ] Exported files reopened after cleaning to confirm the result.
- [ ] Log excerpts, if any, invented and conceptual.
- [ ] Logos, templates, third-party diagrams removed or replaced.
- [ ] Version history contains only sanitised content.
- [ ] CTF rules read and any waiting period ended.
- [ ] Reviewer consent obtained before naming or quoting anyone.
- [ ] Licence covers only material the author owns.
- [ ] Source label and limitations on the first page.
- [ ] A second person completed the disclosure pass.
- [ ] Private originals stored in an approved location with a retention decision.
- [ ] Withhold decision recorded with its reason, if applicable.

### Portfolio index template

| # | Artefact | Source label | Date | Skills shown | Defender lesson | Link | Review status |
|---|---|---|---|---|---|---|---|
| 01 | | owned lab / range / approved sample | | | | | self / peer reviewed |

```
Title:          [neutral name]
Source label:   [synthetic lab / training event / approved sample]
Date:           [YYYY-MM]
One-line claim: [what this artefact demonstrates]
Boundary:       [included; excluded; stop condition]
Skills:         [evidence handling, reasoning, communication]
Defender lesson:[control idea a reader can take away]
Link:           [relative path]
Review:         [reviewer role, date, change made]
Status:         [public / private — reason if private]
```

### Pre-publish decision record

```
Artefact:           [name and version]
Right to share:     [owned / range rules / written permission reference]
Publication scope:  [exact files and excerpts approved]
Harm check:         [who could be identified or affected]
Disclosure actions: [regenerated / removed / generalised / withheld]
Combination check:  [place + date + unusual detail reviewed]
Reviewers:          [technical pass / disclosure pass, dates]
Decision:           [PUBLISH / SANITISE / WITHHOLD] + one-sentence reason
Review date:        [when to look again]
```

### Evidence-handling note

```
Stored where:     [approved private location]
Who can access:   [roles]
Retention:        [how long, and why]
Private originals:[location; not linked from public index]
Destruction:      [owner, date or event, method agreed in policy]
```

---

## Practice by section

Rehearse each decision aloud before opening the key.

### Set A — Classification

**Q1.** Your owned-lab report has a screenshot showing your home network name. Publish, sanitise, or withhold?
**Q2.** A client says "feel free to talk about the project" but approves no text or images. Can you publish a sanitised report?
**Q3.** You solved a competition challenge and the rules are silent on write-ups. What next?

<details>
<summary><strong>Answer key — Set A</strong></summary>

**A1.** Sanitise: regenerate the image in a fresh synthetic environment, then repeat the disclosure pass, including metadata. If the lesson depends on that environment, rebuild rather than redact.

**A2.** No. Approval to discuss is not approval to publish a specific artefact. Request written approval of exact text and images, or publish methodology and control-design material with no client facts. Record the answer.

**A3.** Treat silence as no. Ask the organisers and wait, or keep the note private. Never publish live flags or exact reproduction steps.

</details>

### Set B — Narrative and defence

**Q4.** Rewrite for a defender without a recipe: "I reached an internal function that should not have been reachable."
**Q5.** Your write-up calls a finding "critical" because a tool said so. What is missing?
**Q6.** A peer says your impact claim is unsupported. What do you change first?

<details>
<summary><strong>Answer key — Set B</strong></summary>

**A4.** State condition and control: an internal function lacked an access check from the wider segment; restrict by role and network policy, then verify role assignments and segment reachability. Separate observation, inference, and limitation.

**A5.** A stated rationale: exposure, prerequisites, impact, compensating controls, evidence for each, and a note that the environment was a lab. A borrowed label is not a challengeable argument.

**A6.** Revisit the premise, not the adjective. Write what was observed, inferred, and what extra evidence is needed. Withdraw or qualify the claim and record the correction in the artefact.

</details>

### Set C — Repository and rights

**Q7.** A sensitive file was committed early and deleted later. Is the repository safe to publish?
**Q8.** Which files may you place under an explicit licence of your own?
**Q9.** Your employer requires review of external writing about work. You want to publish a lesson learned during employment. What do you do?

<details>
<summary><strong>Answer key — Set C</strong></summary>

**A7.** No. Earlier revisions still contain it. Start a clean repository with sanitised files from the first revision and check the whole history before sharing.

**A8.** Only what you own: your prose, diagrams, and synthetic examples. Client templates, courseware, logos, and reviewer comments are not yours to licence. Read the licence text itself.

**A9.** Request written review with the exact draft. If approval is withheld, publish only generic methodology or control-design content with no employer or client facts. Do not paraphrase confidential details into fiction.

</details>

### Set D — Review and accuracy

**Q10.** A reviewer cannot tell which index items are labs. What do you fix first?
**Q11.** Your CV says "ECSA — current". What is wrong and how do you fix it?
**Q12.** An interviewer asks for a real example; you only have synthetic work. What do you say?

<details>
<summary><strong>Answer key — Set D</strong></summary>

**A10.** Add a source label, date, and boundary line to every index entry. Fix the strongest artefact's page before adding new projects; reviewers scan first and read deeply second.

**A11.** It may misrepresent status. ECSA was not listed in EC-Council's current catalogue when checked on 26 Nov 2026. Verify on eccouncil.org and cert.eccouncil.org, then state "ECSA-era study, [year], legacy" or omit it and show artefacts. Do not invent a version or format.

**A12.** Say plainly it was a synthetic lab, then walk through boundary, observation, inference, limitation, and defensive change. Add that confidential material is withheld by design.

</details>

---

## Glossary

| Term | Plain-language meaning |
|---|---|
| **Artefact** | A dated record someone else can inspect to judge your work |
| **Boundary** | The line between what you may assess or share and what you may not |
| **Combination risk** | Identification caused by joining several harmless details |
| **CTF** | A capture-the-flag event; solving one proves puzzle completion, not assessment judgment |
| **Disclosure pass** | A review focused only on what a published artefact reveals |
| **Lab laundering** | Presenting synthetic work as if it were real client work |
| **Legacy credential** | A qualification from an earlier programme whose status must be verified with the issuer |
| **Minimum-necessary disclosure** | Sharing only the detail needed for the reader's decision |
| **Positive finding** | A control that worked and is worth recording |
| **Publication permission** | Explicit approval to share specific material with a specific audience |
| **Regeneration** | Rebuilding sanitised evidence instead of editing an original |
| **Retention decision** | A recorded choice about how long evidence is kept and when it is destroyed |
| **Sanitisation** | Removing or replacing identifying detail before sharing |
| **Withhold** | The deliberate choice not to publish, with the reason recorded |

---

## References and verification

- **EC-Council certification catalogue** — check whether ECSA is currently listed: [eccouncil.org](https://www.eccouncil.org/) and [cert.eccouncil.org](https://cert.eccouncil.org/). When checked on 26 Nov 2026 it was not listed; this article claims no current version, exam format, or renewal rule. Verify before writing any credential claim.
- **NIST SP 800-115, *Technical Guide to Information Security Testing and Assessment*** — public process reference; check its current status and any successor documents.
- **NIST NICE Cybersecurity Workforce Framework (SP 800-181)** — public vocabulary for describing security work; verify the current revision before citing categories.
- **PTES (Penetration Testing Execution Standard)** — public reference for engagement structure and deliverables; verify the current material.
- **OWASP ASVS and OWASP Testing Guide** — web-application references for framing control lessons; confirm the current release before using a checklist.
- **MITRE ATT&CK** — a knowledge base of adversary behaviour for defensive thinking, not instructions.
- **Platform documentation on licences and removing sensitive content from repositories** — documentation changes; read current official docs, and remember history and caches may retain copies.
- **Employer policies, contracts, engagement letters, competition rules, and local privacy rules** — these take precedence. Requirements vary by organisation and jurisdiction; verify locally. Education, not legal advice.

## See also

- [Scope, Authorization & Ethics](../fundamentals/scope-and-ethics.md)
- [Penetration Testing Methodology](../fundamentals/pentest-methodology.md)
- [Training, Labs & Practice Range](../exam/training-and-labs.md)
- [Careers After ECSA](ecsa-careers.md)
- [Next Certifications & Skills](next-steps.md)
- [Skills, Hiring & Reality Check](reality-check.md)
