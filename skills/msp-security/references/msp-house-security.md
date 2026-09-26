# {{COMPANY_NAME}} House Security Standard

**Defaults you must review:** the cadences, counts, and review rules in this file are shipped
example defaults from a working MSP. Review and replace them with your own before relying on
them (see Setup Decisions in SKILL.md).

How {{COMPANY_NAME}} secures itself. Attackers target MSPs because one breach of the MSP
reaches every client at once; remote management tools and MSP credential stores have been the
entry point in several of the largest small-business ransomware events on record.
{{COMPANY_NAME}}'s own security is therefore part of every client's security, and it is held to
a higher bar than the client baseline.

Yardstick: the CISA/NSA/FBI and Five Eyes joint advisory AA22-131A, "Protecting Against Cyber
Threats to Managed Service Providers and their Customers", and CISA's MSP hardening guidance.
Unless marked inherited, every item is a recommended default until you confirm it.

---

## 1. Identity

- **Phishing-resistant MFA everywhere {{COMPANY_NAME}} can touch a client:** FIDO2 security
  keys or passkeys on your PSA and RMM, the credential vault, the partner or delegated-admin
  portals for client email and productivity tenants, {{COMPANY_NAME}}'s own email and
  productivity platform, your endpoint protection console, your Mac MDM, your DNS and hosting
  provider, backup consoles, domain registrars, and banking. SMS codes are not acceptable on
  these accounts where a stronger option exists.
- **Two security keys per person with privileged access** (one carried, one stored safely) so
  a lost key is not a lockout.
- **Named accounts only.** Every action in every tool traces to one person. No shared
  company-name or "admin" logins, in {{COMPANY_NAME}}'s tools or in client tenants.
- **Separate admin identities.** Staff do daily email and browsing on a normal account;
  privileged work happens under an admin identity.
- **{{COMPANY_NAME}}'s own break-glass accounts** for its email and productivity tenant and for
  the RMM: documented, sealed, and alerting on use.

## 2. Access Into Client Environments

- **Client email and productivity tenants:** where the platform offers partner-delegated admin
  with granular roles (through its partner program), use it with the narrowest roles that do
  the job and time-bound relationships renewed deliberately. Never a legacy broad delegation;
  never standing global admin through the partner relationship. Where a client-tenant admin
  account is required, it is named per {{COMPANY_NAME}} tech and MFA-protected.
- **Platforms without partner delegation:** named {{COMPANY_NAME}} admin accounts with
  delegated admin roles, not super admin, except the documented minimum.
- **Least privilege by default:** access is granted for the work and removed when the work
  ends. Review all {{COMPANY_NAME}} access into every client quarterly, timed with QBR prep.
- **No standing remote access paths** outside the RMM's remote access and ZTNA. No third-party
  remote tools left installed on client machines.

## 3. The RMM

The RMM can run code on every managed machine at every client. Treat it that way.

- MFA enforced for every RMM user; phishing-resistant where supported.
- Minimum number of users with rights to run scripts, push software, or change policies.
- **Script control:** scripts live in the RMM's script library with a named author and date.
  Any script run fleet-wide or across clients is reviewed by a second qualified person first
  (recommended default: the owner or a designated senior tech; a one-person shop sets its own
  rule in Setup Decisions). No pasting unreviewed scripts from forums into a fleet-wide run.
- Remote-access sessions are logged; unattended access requires the logged-in tech account.
- RMM audit logs reviewed monthly for unexpected logins, new users, API keys, and policy
  changes. API keys are named, scoped, and rotated when a person or integration leaves.
- Alerts on new RMM users, new API keys, and admin-level changes go to the owner and any
  designated senior tech.
- Know how to disable the RMM tenant-wide fast: the procedure is written down (msp-helpdesk,
  "if {{COMPANY_NAME}}'s own tooling is the suspected vector").

## 4. Credential Vault

- The only place client credentials live (inherited from msp-onboarding). Not in tickets,
  email, chat, text messages, spreadsheets, browser password stores, or AI prompts.
- Per-client vaults or folders so access can be scoped and audited per client.
- MFA and a strong master passphrase; emergency access configured so a second trusted person
  can recover the vault if the primary holder is unavailable.
- Credentials rotated when a person with access leaves {{COMPANY_NAME}}, when a client exits
  (msp-offboarding), and after any suspected exposure.
- Vault export or backup stored encrypted and offline, tested yearly.

## 5. {{COMPANY_NAME}} Devices

- Every {{COMPANY_NAME}} laptop and phone: full-disk encryption, endpoint protection, patched
  on the same weekly cycle as clients or faster, screen lock, managed by {{COMPANY_NAME}}.
- {{COMPANY_NAME}} devices are for {{COMPANY_NAME}} work. No family use, no personal software
  experiments on the machine that holds the vault session.
- Admin work on client environments only from {{COMPANY_NAME}}-managed devices.
- Lost or stolen device: treat as a security incident, revoke sessions and rotate what that
  device could reach.

## 6. {{COMPANY_NAME}}'s Own Email and Tenant

{{COMPANY_NAME}}'s own email and productivity platform meets the full client T1 baseline plus
the T2 items that apply: phishing-resistant MFA, conditional access, DMARC at enforcement,
advanced email protection, audit logging with alerts. Invoices and payment-change requests from
{{COMPANY_NAME}} tell clients to confirm by phone, because {{COMPANY_NAME}}'s brand is a
phishing target too.

## 7. Logging and Detection

- Audit logs for the RMM, the vault, the partner and delegated-admin portals,
  {{COMPANY_NAME}}'s tenant, and security consoles kept and exportable. Target at least 90 days
  searchable, longer where the platform allows (recommended default; confirm per tool).
- Alerts on {{COMPANY_NAME}}-side risky events (new admin, new API key, impossible-travel
  sign-in, mass script run) reach the owner and any designated senior tech.

## 8. Vendors and Supply Chain

Before adopting any tool that touches client environments or client data:

- Does it support MFA (ideally phishing-resistant) and SSO?
- Does it keep audit logs {{COMPANY_NAME}} can review and export?
- Does it have a public security page, a SOC 2 report or similar, and a history of handling
  incidents openly?
- Where is data stored, and can it be deleted on request (matters for the DPA and the
  post-exit retention period in msp-offboarding)?
- Does it need to be listed as a subprocessor in the DPA (msp-legal)?

Record the answer in your documentation system. Re-check when a vendor has a publicized breach.

## 9. AI Tooling

- No client credentials, secrets, API keys, or recovery keys in any AI tool.
- No regulated data (ePHI, taxpayer data, privileged legal material, card data, children's
  records) in AI tools unless the DPA and, where relevant, the BAA expressly allow it.
- Use generic or fictional client names in skill files, templates, and examples (no real client
  names anywhere in the kit).
- AI output that changes a client environment (scripts, policies) is reviewed by a human
  before it runs, same as any other script.

## 10. People and Process

- Everyone with privileged access completes a security refresher yearly and walks a phishing
  and social-engineering scenario with the team (someone calling as a client asking for a
  password reset is the classic MSP attack; verify by calling back a known number from
  documentation).
- **Help desk identity verification:** password resets, MFA resets, and access changes are
  verified by call-back to the number in the client's documentation, or by the client's
  designated contact, never on the strength of an inbound call or email alone.
- Any new employee or contractor gets a background check (recommended default),
  confidentiality and IP assignment paper (draft with your attorney through msp-legal), named
  accounts, and least-privilege access, removed the same day they leave.

## 11. Resilience and Response

- {{COMPANY_NAME}}'s own data (PSA and RMM, documentation, the vault, email, finance) backed up
  with an immutable or offline copy, restore tested at least yearly.
- **Tabletop exercise at least yearly:** walk the msp-helpdesk scenario where
  {{COMPANY_NAME}}'s tooling is the vector, including out-of-band client contact (phone numbers
  for every client's decision maker kept outside {{COMPANY_NAME}}'s email and RMM).
- Cyber and E&O insurance bound before first MSA signing (inherited gate, msp-legal). Know the
  carrier's notice requirements and breach hotline before they are needed.

## 12. Review Cadence (recommended defaults)

| What | How often |
|---|---|
| RMM audit log and user/API key review | Monthly |
| {{COMPANY_NAME}} access into every client (delegated-admin roles, admin accounts) | Quarterly |
| This house standard reviewed against current CISA MSP guidance | Yearly |
| Tabletop exercise | Yearly |
| Vault and {{COMPANY_NAME}} backup restore test | Yearly |
