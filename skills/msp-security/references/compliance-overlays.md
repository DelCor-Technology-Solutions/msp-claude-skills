# Compliance Overlays for Regulated Clients

**Defaults you must review:** the "{{COMPANY_NAME}} posture" stances in this file are shipped
example defaults from a working MSP. Decide your own (Setup Decisions in SKILL.md), and fill in
the {{STATE}} law section with your attorney before relying on it.

What the regulated verticals in a typical small-MSP market add on top of the client baseline.
This file helps {{COMPANY_NAME}} spot the regime, ask the right questions, and scope the
technical controls {{COMPANY_NAME}} can deliver. It is not legal advice and it does not decide
whether a law applies.

**Standing rule for every overlay:** which regime applies to a client, what it requires of
them, and what {{COMPANY_NAME}}'s paper must say about it is a question for an attorney licensed
in {{STATE}}, routed through msp-legal. {{COMPANY_NAME}} delivers technical controls and
evidence; the client owns its compliance program. Never tell a client they are "compliant".

**Currency note:** regulations change. Facts below were current as of the kit's September 2026
release. Before relying on a date or threshold in client-facing material, verify it is still
current.

---

## Accounting and Tax Firms

**Likely regimes:** the FTC Safeguards Rule (tax preparers and many CPA firms count as
"financial institutions" under the Gramm-Leach-Bliley Act), IRS expectations for tax
professionals (Publication 4557, and the Written Information Security Plan the IRS expects
every tax pro to keep; Publication 5708 is the IRS's WISP template).

**What it adds to the baseline:**

- A **written information security program (WISP)** with a named "Qualified Individual"
  responsible for it. {{COMPANY_NAME}} can help draft the technical sections; the client owns
  and designates.
- **MFA for anyone accessing customer information** (the baseline already does this; note it
  in the WISP).
- **Encryption of customer information** at rest and in transit.
- Written risk assessment, access reviews, secure disposal of customer data (generally no
  later than two years after last use unless there is a reason to keep it), change management,
  activity logging, staff training, and oversight of service providers (that includes
  {{COMPANY_NAME}}).
- Written incident response plan and an annual written report to the owners or board.
  Smaller firms (fewer than 5,000 consumers' records) are exempt from some of these written
  elements; the attorney confirms which.
- **FTC notification:** a security event involving unencrypted information of 500 or more
  consumers must be reported to the FTC within 30 days of discovery (in effect since May 2024).
- Annual penetration testing and vulnerability scans every six months unless continuous
  monitoring is in place. If {{COMPANY_NAME}} does not sell penetration testing, refer to a
  partner.

**{{COMPANY_NAME}} posture (example default):** strong fit. Accounting is a common MSP target
vertical and the Safeguards Rule gives the security conversation a deadline. Lead with the
WISP, then the baseline gaps.

## Legal Practices

**Likely regimes:** {{STATE}}'s Rules of Professional Conduct (most states follow the ABA Model
Rules: competence including technology, and reasonable efforts to prevent unauthorized
disclosure of client information, Rule 1.6(c)), ABA Formal Opinions 477R (securing client
communications), 483 (duties after a data breach), and 512 (generative AI).

**What it adds:** confidentiality of client matters drives access control per matter or
practice group, encrypted email or secure portal for sensitive documents, careful vendor
selection (lawyers must supervise their vendors, which means {{COMPANY_NAME}}), and breach
duties to notify clients. Expect questions about where data is stored and who at
{{COMPANY_NAME}} can see it; the house standard is the answer. Firm-level ethics questions are
the firm's own counsel's call.

**{{COMPANY_NAME}} posture (example default):** strong fit. Expect a vendor security
questionnaire; answer only from the house standard and evidence.

## Healthcare (medical, dental, therapy, chiropractic, and similar)

**Likely regime:** HIPAA Security Rule, for covered entities and their business associates. An
MSP with access to systems holding ePHI is a business associate.

- **Hard gate:** no work touching ePHI until a BAA is signed (msp-legal; if you have not built
  a BAA yet, draft it with your attorney before the first healthcare client).
- The practice needs a documented risk analysis, risk management plan, access controls, audit
  controls, integrity and transmission security, and contingency (backup and recovery) plans.
  {{COMPANY_NAME}} supplies technical controls and evidence; the practice owns the program.
- **Pending change:** HHS proposed a major Security Rule update in January 2025 (MFA,
  encryption, asset inventory, network map, and restore-within-72-hours expectations would
  become explicit). As of mid-2026 it is not final; the federal agenda showed final action
  targeted for July 2027. The baseline already covers most of it, which is a selling point,
  not a compliance claim.
- Secure e-fax lives under Business Phones (msp-sales).

**{{COMPANY_NAME}} posture (example default):** fit, after the BAA exists and E&O plus cyber
coverage is bound. The compliance value factor applies (msp-pricing).

## Manufacturing and Defense Supply Chain

**Likely regime:** CMMC (Cybersecurity Maturity Model Certification) for companies holding
Department of Defense contracts. Level 1 covers Federal Contract Information and is a yearly
self-assessment against 15 basic safeguarding requirements; Level 2 covers Controlled
Unclassified Information (CUI) and maps to the 110 requirements of NIST SP 800-171. CMMC
requirements began appearing in DoD contracts in November 2025 on a phased rollout. ITAR or
export-controlled data adds its own requirements.

**{{COMPANY_NAME}} posture (example default):** Level 1 clients are a fit; the baseline covers
most of it and {{COMPANY_NAME}} can support the self-assessment evidence. Clients handling CUI
usually need a specialized environment (for example a government cloud tenant), a System
Security Plan, and possibly a third-party assessment. Unless your shop is built for that, it is
outside the delivery model: partner or refer, and say so plainly early in sales.

## Businesses Taking Card Payments

**Regime:** PCI DSS (currently version 4.0.1), a contractual standard from the card brands
enforced through the merchant's bank or processor.

**{{COMPANY_NAME}} posture (example default):** {{COMPANY_NAME}} does not sell payment
processing (msp-sales). The technical advice is to keep card data out of the client's
environment entirely: processor-hosted payment pages, standalone or point-to-point encrypted
terminals, never card numbers in email or spreadsheets. The client's annual self-assessment
questionnaire is between the client and its processor; {{COMPANY_NAME}} supplies facts about
the network and devices on request.

## Education and Childcare

Which regime applies (state childcare licensing requirements, state privacy law, and whether
federal education or children's privacy laws reach the client) is an attorney question, and
the answer shapes the DPA. Children's records and family information are the sensitive data:
tighten access to them, avoid personal devices for records, and treat any exposure as an
incident with attorney involvement early.

## {{STATE}} Law Touchpoints (every client in your state)

Fill this section in with your attorney (Setup Decision 10). The areas to cover, which most
states address in some form:

- **Reasonable security:** whether {{STATE}} requires businesses that keep residents' personal
  information to maintain reasonable security procedures and to dispose of that information
  securely when no longer needed. The baseline is {{COMPANY_NAME}}'s answer to "reasonable" for
  a small business; the attorney confirms.
- **Breach notification:** the deadline for notifying affected residents after a breach is
  determined, and the threshold at which the state attorney general must also be notified.
  This is the "short clock" msp-helpdesk warns about. Record the actual numbers and statute
  citation here.
- **Consumer privacy law:** whether {{STATE}} has a comprehensive consumer privacy act, its
  volume thresholds (most small clients will not meet them, but the attorney confirms per
  client), and whether data processing agreements should reference it.
- **Service providers:** whether state law expects businesses to require reasonable security
  from service providers who handle their residents' data. That is {{COMPANY_NAME}}, and it is
  one more reason the house standard exists.

---

## Quick Triage: Which Overlay?

Ask during discovery (msp-sales discovery questions already include compliance):

1. Do you prepare tax returns or provide financial services? (FTC Safeguards, IRS WISP)
2. Are you a law firm or do you hold privileged client material? (Legal ethics)
3. Do you handle patient health information? (HIPAA, BAA gate)
4. Do you hold any Department of Defense contracts or subcontracts? (CMMC)
5. Do you take card payments, and how? (PCI scope reduction)
6. Do you keep records about children, students, or other sensitive populations?
7. Does your cyber insurance policy or a client contract require specific controls?

Any yes: flag in the discovery notes, apply the compliance value factor per msp-pricing, and
route to msp-legal before the Order is drafted.
