# Scope, Authorization & Ethics

> **Independent, unofficial study resource.** EC-Council, CEH, ECSA, LPT and
> other credential names are trademarks of their respective owners. This site
> is not affiliated with or endorsed by EC-Council and contains no official
> courseware, exam dumps, or copyrighted material. Every activity discussed
> assumes a lab you own or a system covered by explicit written permission.
> This article is about **process, judgment, evidence and defense** — no
> commands, payloads, exploit steps, or evasion instructions — and is
> **education, not legal advice**.

## Learning objectives

After working through this article you should be able to:

1. Distinguish request, permission, authority, and capability — and explain
   why all four must align before any work begins.
2. Write a scope statement naming inclusions, exclusions, owners, and the
   evidence of approval.
3. Identify third-party systems, shared infrastructure, and hidden data sets
   before they become scope violations.
4. Build rules of engagement (RoE) with a window, technique ceilings, contacts,
   data rules, stop conditions, and change control.
5. Apply a scope-decision gate at every new lead, including the decision to
   stop and escalate.
6. Handle evidence with data minimisation, a chain of custody, and a
   destruction plan.
7. Explain how privacy, ethics, and local law shape what a tester may do —
   and when to seek qualified advice.
8. Rehearse ethical decisions under pressure using the scenarios and template.

If you cannot do items 2, 4, and 5, you have technical skills looking for a
target, not a safe engagement.

---

## Why authorization is the first security control

An assessment is a deliberate exception to normal rules. Actions that would
otherwise be misuse are permitted for a limited purpose, by named people,
against named systems, during a limited time. The document making that
exception is not bureaucracy; it is the control that stops the exception
becoming an incident.

Four ideas are easy to confuse:

| Idea | Meaning | Failure when confused |
|---|---|---|
| **Request** | Someone asks for testing | Treating a wish as a green light |
| **Permission** | Someone says "yes" | Assuming the speaker may bind the organisation |
| **Authority** | That person can validly approve this system and data | Accepting approval from a requester with no mandate |
| **Capability** | You can technically reach the system | Using ability as a substitute for permission |

All four must be present. A requester may be sincere and still lack authority.
A signatory may control an application but not the shared platform beneath it.
Privileged credentials are not permission to use them for assessment. When in
doubt, the answer is "not yet", not "probably fine".

Authorization is **specific, time-bound, and revocable**. Specific means named
assets, not "our stuff". Time-bound means dates, hours, and a timezone, not
"until we are done". Revocable means the client can halt work and a stop
condition can pause it without debate. Last year's approval does not cover
this year's new environment.

Scope answers *what*. RoE answers *how, when, and with which limits*. The
contract carries legal and commercial terms; internal policy may be stricter.
When documents disagree, the strictest applicable rule wins and the conflict
is escalated in writing — never settled silently by the tester.

---

## The scope-decision gate

Every new lead — a discovered hostname, a "can you also check..." message, an
interesting result — passes the same gate. A failed gate is a **STOP**, not a
detour around the question.

```
  REQUEST or NEW LEAD
        |
        v
  Requester identified?
        | NO                --> [ STOP: no work until identified ]
        | YES
        v
  Written authority from empowered signatory?
        | NO                --> [ STOP: ask for signed approval ]
        | YES
        v
  Owner of every affected asset known?
        | UNKNOWN           --> [ STOP: confirm ownership first ]
        | KNOWN
        v
  Third party / shared tenant / other people's data affected?
        | YES               --> [ STOP: exclude or obtain separate approval ]
        | NO
        v
  Window, technique limits, and source rules agreed?
        | NO                --> [ STOP: agree in writing; narrow or reschedule ]
        | YES
        v
  Contacts, data handling, and stop conditions complete?
        | NO                --> [ STOP: complete the RoE ]
        | YES
        v
  Work proceeds strictly inside window and scope
        |
        v
  Stop event or scope change? -- YES --> [ PAUSE: stop, notify, record,
        |                                  await written resumption ]
        | NO
        v
  Evidence -> report -> client review -> retest -> written closure
```

The diagram is a decision aid, not a technical procedure. Its important
property: no branch says "continue quietly". A failed gate produces a question
to the named contact and an entry in the engagement log. "Just this once" is
how scope drift becomes an incident report.

---

## Scope elements: what must be written down

A scope statement is useful only if two readers would draw the same boundary.
Ambiguity is not flexibility; it is unallocated risk.

| Scope element | What must be written down | Why it matters |
|---|---|---|
| Entity and owner | Legal entity, business unit, accountable owner | Defines who carries risk |
| Named signatory | Name, role, authority evidence, signature date | Proves authority |
| In-scope assets | Exact hosts, ranges, apps, environments, sites, tenant IDs | Removes guesswork |
| Explicit exclusions | Partner portals, shared addresses, suppliers, production data, subsidiaries | Makes boundaries visible |
| Ownership map | Owner of each asset, including platform and data owners | Reveals hidden third parties |
| Environment status | Production, staging, lab, or copy — and whether copies hold real data | "Staging" is not harmless |
| Test window | Dates, hours, timezone, blackouts, maximum duration | Makes permission time-bound |
| Technique classes | Allowed, restricted, prohibited categories: state changes, DoS-type activity, data export, social engineering, physical and wireless work | Sets an intensity ceiling |
| Source rules | Agreed public sources, client material, excluded data | Keeps hypotheses traceable |
| Third-party conditions | Providers, tenants, processors, and who must consent | Prevents non-consensual harm |
| Data-handling rules | Evidence types, minimisation, storage, access, retention, destruction, transfer | Protects people |
| Contacts | Primary, technical, emergency, privacy/legal, escalation | Enables an immediate stop |
| Stop conditions | Triggers, who declares a stop, how work resumes | Removes improvisation |
| Communication | Check-in cadence, status channel, report recipients | Prevents surprises |
| Deliverables and retest | Draft, final, retest criterion, closure record | Completes the loop |
| Change control | How changes are requested, approved, dated, and recorded | Blocks verbal expansion |

Hand the statement to a colleague and ask which assets they would touch.
Different lists mean the scope is not finished.

---

## Who can authorise what

Authority is delegated, bounded, and documented. These are *typical* patterns,
not universal legal rules; charters, law, and contracts change the answer.

| Role or party | Can authorise | Cannot assume | Proof to retain |
|---|---|---|---|
| Business/system owner with delegated authority | Testing of owned systems and data | Shared platforms, supplier systems, other units | Delegation record |
| CISO or security leadership | Programme-level work within an approved mandate | Overriding law or provider terms | Signed RoE, policy reference |
| IT operations manager | Maintenance windows, lab access, timing | Legal exposure, third-party targets | Window approval, ticket |
| Application owner | Their app and non-production copies | Underlying shared infrastructure; real customer data | Inventory entry |
| Procurement and legal | Contract terms, cross-border clauses, notifications | Technical permission to touch systems | Signed contract or memo |
| Cloud/platform provider | Use of its platform under its terms | Consent for other tenants | Current provider policy |
| Other tenants | Their own tenant only | Waiving neighbours' rights | Separate consent or exclusion |
| Parent company | Group systems within its control | Binding a subsidiary or new acquisition | Corporate approval, asset list |
| Employee or developer | A personal lab they own and isolate | Any employer-controlled system | Personal lab note |
| Regulator or appointed auditor | Work inside its stated mandate | Unlimited access; removing duty of care | Engagement letter |
| Emergency contact | Halting or pausing active work | Expanding scope during an incident | Stop log entry |
| Tester | Their own lab only | Any client system, however reachable | Lab inventory |

Two rules follow. Approval from one owner does not **propagate** to assets
owned by another. The power to **stop** is broader than the power to expand:
almost anyone in the communication plan may halt work, but only an empowered
signatory through change control may authorise more of it.

---

## Third-party ownership: the boundary that moves

The most damaging scope failures are rarely dramatic. They involve a tester
following an ordinary lead onto infrastructure owned by someone who never
agreed to be tested.

- **Shared addresses and CDNs.** A hostname may resolve to an address used by
  many customers. A DNS record proves naming, not ownership; active checks can
  touch strangers' systems.
- **SaaS and managed services.** The application may belong to the client, the
  platform to a provider, and the data to the client's customers. Provider
  terms often restrict testing outright.
- **Processors and controllers.** A client may control the purpose of
  processing while a supplier operates the system; evidence may contain other
  organisations' records.
- **Subsidiaries and acquisitions.** A brand can look unified while legal
  entities, contracts, and approval chains remain separate.
- **People.** Staff names, customer records, tickets, and chat logs in
  evidence are personal data about people who did not consent to a test.
- **Discovered unknowns.** An unexplained host in the inventory is a question,
  not an invitation. Escalate it; do not probe it to learn what it is.

The safe pattern is **identify → record → exclude or obtain separate written
approval**. If neither is possible, report the constraint: *observed, not
tested, blocked by third-party ownership*. That is a professional outcome;
silently proceeding is not.

---

## Rules of engagement: the operational rulebook

The RoE turns scope into instructions a tester and a defender can both follow
under pressure. It should be short enough to read during an incident and
precise enough to settle arguments before they start.

1. **Window and intensity.** Dates, local hours, blackout periods, and a
   ceiling on how forceful checks may be. A technique permitted in principle
   can still be wrong in a production window.
2. **Environment rule.** Which environment may be used for each activity, and
   when a lab copy is preferred or mandatory.
3. **Technique categories.** Explicit allow/restrict/prohibit lists. Silence
   is not permission: if a category is unlisted, ask first.
4. **Source restrictions.** Agreed public sources and client-supplied
   material; externally obtained data excluded.
5. **Communication.** Daily check-in, escalation ladder, emergency phone, and
   one status channel. "No change" is a valid check-in.
6. **Stop conditions.** Named triggers, who declares a stop, and who may
   resume.
7. **Data rules.** What may be captured, where it is stored, who may access
   it, and when it is destroyed.
8. **Change control.** Any change to assets, timing, techniques, or contacts
   requires a dated written amendment.
9. **Closure.** Draft review, final report, retest criterion, evidence
   destruction, and written closure by both sides.

A well-written RoE protects defenders too: operations can distinguish
authorised activity from an intruder and know whom to call if something looks
wrong.

---

## Stop conditions and what to do when one fires

A stop condition is an agreed event that requires work to pause.

| Category | Example trigger | Immediate action |
|---|---|---|
| Technical | Service unstable or unusually slow | Pause, notify technical contact, record time |
| Scope | Out-of-scope or unknown system contacted | Stop activity, log asset, ask for decision |
| Data | Unexpected personal or third-party data exposed | Stop collection, secure holdings, notify privacy contact |
| Authorisation | Approval withdrawn or window expires | Cease work, confirm in writing, no informal resumption |
| Safety | Pressure to exceed limits, contact unreachable | Pause, escalate to named authority, document request |

The sequence is always **stop → preserve a factual note → notify the named
contact → await written instruction → resume only if authorised**. Never
delete evidence to make a stop event disappear, "finish quickly" before
telling anyone, or treat an unreachable contact as permission. A stop shows
the control works; hiding one turns a small problem into a serious one.

Mistakes belong in the same record. If you contacted the wrong asset, note
what happened, when, what was observed, and who was told. Prompt disclosure
is part of professional competence.

---

## Evidence and data handling

Evidence is not a trophy collection. Each item must answer a specific
question, contain the least data that answers it, and have a defined end of
life.

| Evidence type | Minimisation rule | Storage and access | Retention and destruction | Pitfall |
|---|---|---|---|---|
| Screenshots | Crop or redact identities | Agreed encrypted repository, named access list | While finding is open, then destroy | Full screen with customer data |
| Logs and time stamps | Keep only the relevant interval | Read-only store, custody record | Review period, then purge | Copying whole log sets |
| Configuration records | Export the relevant setting only | Access-controlled folder | Tie to finding; delete on closure | Including passwords or tokens |
| Asset inventory | Identifiers needed for scope mapping | Shared with named contact | Update at closure, then archive or destroy | Unflagged unexplained assets |
| Personal data | Avoid; redact names and IDs | Restricted access, documented basis where relevant | Delete at earliest permitted point | Treating staff data as harmless |
| Credentials or secrets | Never collect; note exposure instead | Not stored in evidence packs | Not applicable — do not retain | "Proving" a point with a live secret |
| Third-party data | Exclude or get separate approval | Segregated store if approved | Follow the strictest rule | Assuming client consent covers a supplier |
| Working notes | Facts first, inferences separate | Same controls as final evidence | Convert to report or delete | Raw notes in personal storage |
| Reports and drafts | Label drafts and assumptions | Controlled distribution list | Per contract and policy | Unapproved mailing lists |
| Backups and copies | Count as evidence too | Inventory and control access | Destroy with the primary set | Forgetting a laptop copy |

Three habits make this operational: maintain a **chain of custody** (who held
each item, when, and why), apply **data minimisation** before capture, and
agree retention and destruction in advance — confirming it at closure,
including copies and backups.

---

## Ethics and privacy during the engagement

A code of ethics is a set of commitments you can be held to when nobody is
watching. Professional bodies publish their own codes; read the current text
that applies to you rather than treating this list as authoritative.

1. **Authorised purpose only.** No reuse of access or data for curiosity,
   personal gain, or a later job.
2. **Competence and honesty.** Do not claim skills, findings, or access you
   lack; label assumptions and stop when work exceeds your ability.
3. **Do no unnecessary harm.** Choose the smallest action that answers the
   question; prefer lab copies and non-destructive observation.
4. **Respect third parties.** People whose systems or data you encounter have
   rights even when they are not your client.
5. **Privacy by default.** Collect the minimum, redact identities, and treat
   personal data as a responsibility, not a research resource.
6. **Confidentiality.** Share findings only with authorised recipients; never
   post evidence or customer details in public channels.
7. **Integrity in reporting.** Do not inflate severity, downplay real risk,
   or hide a mistake.
8. **Manage conflicts.** Disclose competing interests, gifts, or pressure
   that could distort judgment; decline work you cannot do ethically.
9. **Accountability.** Record decisions, own errors, escalate promptly when a
   boundary is crossed.
10. **Responsible communication.** Use agreed channels and coordinated
    disclosure; never publish unverified details or exploit material.

Privacy needs special emphasis. An assessment can expose far more personal
information than its purpose requires: names in tickets, customer emails in
logs, location data in exports. Before keeping anything ask: *Is it needed for
the finding? Is there a less identifying version? Does the data plan cover it?*
If any answer is unclear, do not keep it. Staff monitoring, call recording,
and access to employee devices may also be governed by employment rules and
workplace agreements stricter than the contract.

Ethics also governs pressure. A client who says "we are paying for a critical
finding" is asking for a distorted report. Restate the evidence model, show
the reasoning, and offer legitimate options: fix, accept with an owner, or
test a deeper hypothesis in a newly agreed window.

---

## Legal variation and the limits of this article

Law is territorial and sector-specific. Rules on unauthorised access,
interception, workplace monitoring, privacy, data transfer, and regulator
notification differ by country and sometimes by state or province. A practice
routine in one jurisdiction may be unlawful in another. Policy, professional
codes, provider terms, and collective agreements can be stricter still.

Determine which jurisdictions apply to the tester, the client entity, the
systems' locations, and the people whose data is involved. Check restrictions
on cross-border evidence storage, sector rules for health, finance,
telecommunications, education, or public systems, and whether the engagement
needs a specific contract clause, works council consultation, or regulator
notification. When uncertain, ask the client's legal or privacy contact and,
where appropriate, a qualified professional in the relevant jurisdiction.

This article is educational and is **not legal, financial, tax, or regulatory
advice**. It cannot tell you whether an action is lawful where you live or
work. Authority in a document does not override the law, and the law does not
replace written authority: both must be satisfied.

Credential context: ECSA was **not listed in EC-Council's current certification
catalogue when checked on 26 Nov 2026**. Treat it here as a **legacy /
historical VAPT path**, not a current programme with a fixed version or exam
format. Verify live details on [eccouncil.org](https://www.eccouncil.org/) and
[cert.eccouncil.org](https://cert.eccouncil.org/), and read any current
ethics material from the official source, not from this page.

---

## Three worked case studies

These cases are fictional and deliberately contain no technical procedure.
Each shows a decision point where judgment matters more than tooling.

### Case 1 — The verbal green light

**Context.** An internal IT manager tells a consultant, "Go ahead and test the
customer portal tonight — we trust you." The portal is partner-hosted; the
company holds a support contract but not ownership. No document, window, or
emergency contact exists.

**Constraints.** The consultant may test the company's own application. The
partner has not consented, provider-side approval is unlikely, and the manager
is offended by hesitation.

**Decisions.** The consultant declines active work on the portal, asks who owns
the platform and who may sign for the company's application, and offers a
lab-only exercise on a company-owned copy while paperwork is prepared. The
verbal request is logged in the engagement tracker. The next day the CISO
issues a signed scope for the company-owned application, excluding the partner
portal.

**What this teaches.** Permission, authority, and ownership are different
things. Politeness under pressure is how a boundary is held. A one-day delay
is cheaper than an unauthorised interaction with a partner's production
system.

### Case 2 — One tenant among many

**Context.** A client requests assessment of a web application. Early
inventory shows its public name resolves to an address shared with unrelated
customers, and the front end is run by a supplier. The client owns one tenant
and its data — nothing else.

**Constraints.** Platform terms restrict active testing; other tenants gave no
consent. The client wants pre-launch reassurance and suggests "a few quick
checks" on the shared address.

**Decisions.** The tester records the shared address, marks the asset
*third-party owned — not tested*, and pauses active work there. They offer a
dedicated staging environment, a provider-approved arrangement, or a
configuration review using client-supplied records only. No other tenant's
data is captured. The report states the limitation and what remains
unverified.

**What this teaches.** A hostname is not ownership. An incomplete test with a
clear limitation beats a complete-looking test that harmed strangers; the
duty runs to the other tenants too.

### Case 3 — Twenty minutes past the window

**Context.** The window ends at midnight. At 23:50 a lead appears; at 23:55 the
on-call manager says "stay on, we need the answer"; at 23:58 the application
responds more slowly.

**Constraints.** The RoE ends at midnight and prohibits state changes. The
manager is senior, but change control names the CISO for extensions. The lead
may point to an excluded service.

**Decisions.** The tester stops at midnight, records the lead as an unverified
hypothesis, notifies the technical contact about the slowdown, and sends a
status note: window closed, lead documented, no extension approved. They
decline the verbal extension and request a new written window. The client
later confirms the lead involved an excluded service.

**What this teaches.** A time box is a safety control, not a suggestion.
Pressure to extend is a signal to slow down. An unfinished lead correctly
recorded is a success; an unrecorded one becoming tomorrow's "quick check"
is not.

---

## Practice by section

Answer aloud before opening each key. The aim is to rehearse decisions, not
memorise definitions.

### Authority and scope

**Q1.** A colleague says, "My director said it's fine — just look at the
server." What next?
**Q2.** A CISO approves "all company systems" by email. What do you ask?
**Q3.** An in-scope domain also hosts a partner's customer portal. Decide.

<details>
<summary><strong>Answer key</strong></summary>

**A1.** No active work. Ask who is empowered to approve that server, request
dated written approval naming it, and offer a lab alternative. A relayed
sentence is not authority.
**A2.** Ask for the exact assets, environments, exclusions, window, technique
limits, and contacts. "All systems" is not a scope statement.
**A3.** Record the portal as excluded with owner and reason; do not interact
with it. Testing it requires separate approval from its owner or provider.

</details>

### Changes, windows, and stops

**Q4.** Mid-engagement a manager verbally adds a subnet. What do you say?
**Q5.** Ten minutes remain and a promising lead appears. Decide.
**Q6.** A service degrades during a check. Give the first three actions.

<details>
<summary><strong>Answer key</strong></summary>

**A4.** "Happy to include it once the change is in writing with a new window,
owner, and contact." Until then it stays out; log the request.
**A5.** Stop at the end of the window, record the lead as unverified, and ask
for a new approved window. No "just one more".
**A6.** Stop, notify the named contact immediately, and record time and
observation. Resume only with explicit authorisation.

</details>

### Third parties and data

**Q7.** An in-scope hostname resolves to a shared address. Continue?
**Q8.** A screenshot contains customer names and emails. What before storing?
**Q9.** The client wants all evidence kept indefinitely. Respond.

<details>
<summary><strong>Answer key</strong></summary>

**A7.** No active checks. Record the observation, flag the asset third-party
owned, and request a dedicated environment, separate approvals, or a
configuration-only review.
**A8.** Crop or redact if the finding still holds; otherwise find a less
identifying form. Store the minimal version in the agreed repository.
**A9.** Cite the agreed retention plan and the risk of indefinite personal-data
retention; offer a defined review period with a named owner. Exceptions need a
documented decision by the data owner and legal/privacy contact.

</details>

### Ethics, law, and reporting

**Q10.** A friend offers a leaked dataset "to help with scoping". Use it?
**Q11.** The client insists a finding be labelled *informational* because
"only three people use it". Handle it.
**Q12.** Counsel elsewhere says local notification rules apply to your
evidence. What changes?
**Q13.** You realise you touched an out-of-scope host. What now?

<details>
<summary><strong>Answer key</strong></summary>

**A10.** No. Externally obtained stolen or personal data is outside agreed
source rules and raises legal and ethical issues. Decline and record the offer.
**A11.** Reopen the evidence and severity model: exposure, prerequisites,
impact, compensating controls. Correct the report if wrong; otherwise record
the client's position with your rationale. Never silently relabel a finding.
**A12.** Apply the stricter rule to storage, transfer, access, or notification
with the legal/privacy contact; amend the RoE before continuing and seek local
advice.
**A13.** Stop, preserve a factual note of what was contacted and when, notify
the named contact promptly, and ask for instruction. Do not delete the record.

</details>

---

## Common mistakes worth memorising

- **"Just checking"** — curiosity or a verbal yes treated as authorization.
- **Signatory shopping** — asking until someone agrees, without checking
  authority over the asset.
- **Implicit subdomains and subnets** — assuming a name includes everything
  around it.
- **Shared-address blindness** — forgetting other tenants behind one address.
- **Staging mythology** — assuming a test copy holds no real data.
- **Silent expansion** — following an interesting lead without an amendment.
- **Window drift** — "five more minutes" until the time box means nothing.
- **Evidence hoarding** — whole logs, full screens, or live secrets to "prove"
  a point.
- **Contact ambiguity** — not knowing who to call when a stop is needed.
- **Severity theatre and retention amnesia** — inflating findings; forgetting
  copies when destroying evidence.

---

## Reusable templates

Copy these into your notes. They are structures, not completed work; their
value comes from being filled in honestly before testing starts.

### Rules of engagement checklist template

```
ENGAGEMENT
[ ] ID / name; client legal entity and unit; tester and subcontractors named
[ ] Version, date, and change history recorded

AUTHORITY
[ ] Named signatory, role, evidence of authority, signature date
[ ] Signed agreement / RoE reference and date
[ ] Delegation documented where signatory is not the owner
[ ] Authority confirmed for each owned asset

SCOPE
[ ] In-scope assets exact: hosts, ranges, apps, environments, sites, tenants
[ ] Explicit exclusions listed
[ ] Ownership map per asset, including platform and data owners
[ ] Production / staging / lab / copy status recorded
[ ] Real data in non-production copies checked
[ ] Third parties excluded or separately approved

WINDOW AND TECHNIQUE LIMITS
[ ] Dates, hours, timezone, blackout dates, maximum duration
[ ] Allowed technique categories
[ ] Restricted categories and approval route
[ ] Prohibited categories stated explicitly
[ ] Agreed information sources listed

COMMUNICATION
[ ] Primary, technical, emergency, privacy/legal contacts
[ ] Escalation ladder and out-of-hours route
[ ] Check-in cadence and status channel
[ ] Report recipients and draft-review process

STOP CONDITIONS
[ ] Instability / slowdown trigger
[ ] Out-of-scope contact trigger
[ ] Sensitive or third-party data trigger
[ ] Withdrawal / expiry / safety triggers
[ ] Who declares a stop and who may resume

DATA HANDLING
[ ] Permitted evidence types; minimisation and redaction rules
[ ] Storage location and encryption expectations; named access list
[ ] Transfer / cross-border restrictions checked
[ ] Retention period and destruction date agreed
[ ] Copies and backups included in destruction plan
[ ] Chain-of-custody method agreed

CHANGE CONTROL AND CLOSURE
[ ] Written amendment required for scope/time/technique change
[ ] Draft, final report, retest criterion defined
[ ] Evidence destruction confirmation planned
[ ] Written closure by both parties planned
[ ] Signatures: client ............ tester ............
```

### Scope-change request (send, do not say)

```
Engagement: [ID] | Requested by: [name, role] | Date/time: [..]
Change: [exact asset / timing / technique] | Reason: [one line]
Owner of new asset: [name] | Authority evidence: [reference]
New window needed: [yes/no] | Third party affected: [yes/no]
Decision: [approved / declined / review] | Approved by: [..]
ChangeLog entry: [version, date]
```

### Stop-event record

```
Engagement: [ID] | Stop time and timezone: [..]
Trigger: [technical / scope / data / authority / safety]
Facts only: [what happened] | Asset or data involved: [..]
Immediate actions: [stop / notify / preserve]
Contact notified and time: [..] | Instruction: [..]
Resume authorised in writing? [yes/no — reference]
```

### Evidence register row

| ID | What it shows | Source and time | Minimal form | Custodian | Retention | Destroyed / date |
|---|---|---|---|---|---|---|
| E-01 | | | | | | |

---

## Glossary

| Term | Plain-language meaning |
|---|---|
| **Authorization** | Valid, documented permission for specific work on specific systems |
| **Authority** | The legitimate power to grant that permission |
| **Scope** | The exact assets, environments, and activities permitted |
| **RoE** | Rules of Engagement: how, when, and with which limits |
| **Test window** | Agreed dates and hours for active work |
| **Stop condition** | Predefined event that requires a pause and escalation |
| **Escalation** | Routing a decision to the named person who can resolve it |
| **Change control** | Written process for altering scope, timing, or techniques |
| **Third party** | A party whose systems or data are involved but who is not the client |
| **Shared responsibility** | Client, provider, and tenants each control different parts of a service |
| **Data minimisation** | Keeping only the least data needed for a finding |
| **Personal data** | Information about an identifiable person, even in a technical log |
| **Chain of custody** | Record of who held evidence, when, and why |
| **Retention** | How long evidence is kept before agreed destruction |
| **Conflict of interest** | A competing interest that could distort judgment |
| **Exclusion** | An asset named out of scope, not merely omitted |

---

## References and verification

- EC-Council programme information and catalogue:
  [eccouncil.org](https://www.eccouncil.org/) and
  [cert.eccouncil.org](https://cert.eccouncil.org/). Verify the live catalogue,
  programme status, and any code-of-ethics text there. ECSA was not listed when
  checked on 26 Nov 2026; treat claims about a current version or exam format
  with caution.
- PTES — a community methodology covering pre-engagement interactions and RoE;
  check its current published version.
- NIST SP 800-115, *Technical Guide to Information Security Testing and
  Assessment* — general guidance; confirm current status and successors.
- ISO/IEC 27001 and 27002 — governance and control references; verify the
  current edition with the standards body.
- OWASP documentation — application-security context, not authorization rules;
  check current releases.
- Your jurisdiction's data-protection authority, sector regulator, employment
  rules, provider terms, and signed engagement documents override any general
  article, including this one.
- Companion CSIX pages (placeholders — replace with the published owner):
  [Lingkup, Otorisasi & Etika](https://siedysoes.github.io/csix-ecsa/id/fundamentals/scope-and-ethics.md)
  and [What Is ECSA](https://siedysoes.github.io/csix-ecsa/en/fundamentals/what-is-ecsa.md).

This page is an independent study aid, not legal advice, not official course
material, and not a substitute for an authorised engagement agreement or
qualified professional judgment in your jurisdiction.

## See also

- [Penetration Testing Methodology](pentest-methodology.md)
- [What Is ECSA](what-is-ecsa.md)
- [ECSA vs CEH & Other Certs](ecsa-vs-ceh.md)
- [Skills, Hiring & Reality Check](../career/reality-check.md)
- [Building a Safe Portfolio](../career/portfolio.md)
