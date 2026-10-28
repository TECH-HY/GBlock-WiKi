# 7. Trust and safety

GBlock's entire design assumes that members behave responsibly because their
reputation is at stake. This page explains the safety mechanisms that make that
assumption enforceable: KYC, re-authentication, probation, complaints,
two-factor authentication, and device alerts.

---

## KYC and identity

KYC (Know Your Customer) is the path to the **Verified** trust tier. It is
performed by an external provider.

- Your documents **never leave the provider**. GBlock does not see or store
  your identity documents.
- A single KYC session can cover both member participation and project listing
  purposes, so you do not repeat the process for each use case.
- Completing KYC grants the Verified trust tier, which unlocks full market
  access without a guarantor, primary-listing eligibility, faster operator
  review, and a higher reputation accrual rate.

You are never forced to complete KYC. Anonymous members can accumulate Volume
and act as buyers indefinitely. KYC is a choice to unlock fuller access and
faster service, not a condition of membership.

**One identity, one verification.** GBlock enforces one verified identity per
person. If the identity you submit at KYC is already attached to an active
member account, the new verification is declined ("already verified") —
accounts are not merged, and re-verifying under a duplicate is not a way
around it.

**If KYC is revoked.** Losing verified status does not destroy your history.
Your existing Data Rooms and the access you have already granted stay live, and
your welcome grant and earned reputation stay as they are. What stops is
anything new: new access grants, new Data Rooms and payouts are paused until you
re-verify.

For projects, KYB (Know Your Business) and project-level KYC are required for
primary-market listings.

---

## Re-authentication

Some actions are sensitive enough that a recent login is required, even if you
are already in the cabinet. This is **re-authentication**: a fresh magic-link
confirmation within the last 10 minutes.

Actions that require re-authentication:

- Creating, editing, submitting, renewing or closing a sale block.
- Accepting a guarantee.
- Enabling, verifying, or disabling 2FA, and revoking a trusted device.
- Exporting your data.
- Data Room actions: uploading documents, granting or revoking access (direct or
  unlisted), toggling downloads, changing document visibility or the public
  tier, editing sections, archiving, restoring or deleting a room, managing team
  invitations and roles, and offering, accepting or cancelling an ownership
  transfer.

If you try one of these actions without a recent re-authentication, the
platform prompts you to confirm via a new magic link. This keeps a stolen
session from being enough to take consequential actions on your behalf.

---

## Probation

Probation is the supervised observation period that starts when a guarantee is
activated.

| Type | Duration | Applies to |
|---|---|---|
| Standard | 30 days | A normal guarantee. |
| Founding | 14 days | Founding-grant Residents. |
| Extended | 60 days | Members under conduct review. |

**During probation:**

- The ward is under supervised observation.
- Trust violations by the ward penalize the ward, and while the guarantee is
  active the guarantor carries 50% of the ward's negative reputation events.
- Each violation extends the probation by another 30 days.

**Outcomes:**

- **Success:** the ward completes probation in good standing and the guarantee
  is recorded as completed. For a Residency applicant this completes admission
  as a Resident.
- **Violation:** three violations lead to revocation of the guarantee and a
  reputation impact for the guarantor.

Probation is why a guarantee is more than a formality. When you guarantee
someone, you are genuinely putting your reputation behind their conduct for the
duration of the probation window.

---

## Complaints

The complaint flow lets any member report misconduct or quality issues
securely. Filing a report goes through the operator.

**Report categories:**

- KYB / KYC.
- Misrepresentation.
- Off-platform.
- Harassment.
- Privacy.
- Fraud.
- Other.

**How it works:**

1. You open **Report** from the cabinet and pick a category.
2. You write to the operator at the address shown on the page, quoting the
   category, with identifiers, dates and any supporting context. Evidence and
   operator notes are stored internally.
3. The operator reviews and may act: warn, restrict, revoke a guarantee, remove
   a block, or adjust reputation.
4. You may receive status updates through notifications.

**Inside a deal.** A deal thread has its own complaint and dispute actions, so
you can raise a problem about that specific deal without leaving it. The thread
stays open while the operator looks into it.

**What is protected:**

- Evidence and internal operator notes are **never visible to other members**.
- Your identity as the reporter is **not exposed** to the subject of the
  complaint.

The complaint flow is the safety valve for the reputation system. If you see
something wrong, report it. The system is designed to protect you for doing so.

---

## Two-factor authentication

2FA protects your account and adds a 0.1x reputation accrual bonus. All
members are expected to keep it enabled — it is part of being a member in good
standing, and enforcement is being extended across every account class.
_Rolling out._

- **Method:** TOTP (Time-based One-Time Password), compatible with standard
  authenticator apps.
- **Enabling:** open Settings → 2FA, scan the QR code, verify a code. Requires
  re-authentication.
- **Effect:** your reputation accrual rate rises by 0.1x. A Verified member
  goes from 1.2x to 1.3x; Anonymous and Vouched members go from 1.0x to 1.1x.
- **Disabling:** also requires re-authentication. You lose the accrual bonus.

Because 2FA sits on top of magic-link authentication, an attacker would need
both your email access and your authenticator device to compromise your
account. Enable it.

---

## Contact checks in deal threads

Deal threads are the governed channel for buyer-seller communication, and the
platform runs an automated **contact verification check** on messages to keep
negotiations inside that channel.

- Messages that look like they contain direct contact data — emails, phone
  numbers, messenger handles, or links to external messengers — are
  **quarantined**: held back from the counterparty and queued for operator
  review.
- Quarantine applies **until the deal contract is signed**. After
  `contract_signed`, exchanging contacts is legitimate: the warning stays, the
  quarantine stops. _Rolling out._
- If a message is held, the **recipient sees a neutral cover** ("message held
  by contact verification") — not your text. You, the sender, still see your
  own message and its status. The operator can review the full content.
- The detector is being extended with broader language matching (transliterated
  text, lookalike Latin/Cyrillic characters, slang abbreviations for
  messengers, and simple separators between characters). This trades some
  false positives for coverage. _Rolling out._

The practical rule: keep negotiations in the thread until the contract is
signed.

---

## Device alerts

When GBlock detects a login from an unrecognized device fingerprint, it sends
an email alert. The alert lets you catch unauthorized access early. If you
receive a device alert you do not recognize, treat it as a signal to review
your account and, if needed, file a complaint.

---

## Standing and restrictions

Your **standing** reflects whether you are in good standing or under any
restriction. Restrictions can result from:

- A failed probation (yours or one you guaranteed).
- Operator action following a sustained complaint.
- Repeated trust violations.
- A flagged referral pattern (for example, self-referrals or clusters of
  registrations from the same device or network). Payouts in the flagged
  chain are frozen until the review completes.

Standing is visible on your cabinet home. If you are restricted, the cabinet
explains the nature of the restriction and what it affects. Restrictions are
not secret; the goal is for you to always know where you stand and what to do
to recover.

**Sanctions and the person.** GBlock is rolling out a record that ties
sanctions to the underlying identity rather than the account, so that closing an
account, letting it go dormant or registering again does not clear a sanction or
improve standing. _Rolling out._ Already today, a restricted account cannot
vouch for others, cannot open a payout request, and an account carrying an
active sanction cannot use deletion to shed it (see below).

---

## Inactivity, deletion, and your data

**Sleep lifecycle.** Accounts that go quiet move through an inactivity
lifecycle, measured from your last login:

| Stage | When | What happens |
|---|---|---|
| **Warning** | After 14 days without a login | You receive a warning email. |
| **Sleeping** | After 30 days without a login | Reward accrual stops. Payments, top-ups, scoring purchases and new Data Rooms are frozen. Existing rooms keep working for people who already have access, and any Data Room subscriptions keep charging until you cancel them. |
| **Deactivated** | After 180 days of sleeping | Your public listings are unpublished. Nothing is deleted. To come back you go through full KYC again. |

Logging back in wakes a warning or sleeping account and stops the clock. If you
return from deactivation more than 30 days after it started, your positive
reputation restarts from the new-account baseline of 30; negative reputation and
sanctions are never reset.

**Deleting your account.** Nothing is erased automatically: deactivation is an
archive. Your personal data is erased only when you ask for it, from Settings or
the **My data** page (where you can also export your data). The operator
processes the request within 30 days. Deletion is **cascading**: Data Rooms you
own are removed with your account, while companies and financial records stay
(financial records are kept for accounting and disputes without your name or
identifiers). Deletion is **blocked while you have active deals or unpaid
withdrawals**, and is **deferred while you carry an active sanction** — settle or
close those first.

**Brand-styled error pages.** Platform errors (403/404/500) surface as
brand-styled pages with guidance, not raw framework errors. _Rolling out._

---

## What GBlock does not do

For completeness, the things GBlock deliberately does not do, even though a
member might expect them from other platforms:

- GBlock does **not** custody assets or funds.
- GBlock does **not** settle transactions.
- GBlock does **not** advise on the merits of any opportunity.
- GBlock does **not** guarantee the accuracy of seller-provided information.
  Members must perform their own diligence.
- GBlock does **not** reveal member identities to counterparties outside of a
  mediated introduction.

These boundaries exist by design. They keep GBlock in a narrow, defensible
role: discovery, verification, mediated introductions, and governed access.

---

## Where to go next

- **The rules behind probation and guarantors:** [User roles and statuses](02-user-roles-and-statuses.md)
- **The numbers behind reputation and the 2FA bonus:** [Reputation economy](05-reputation-economy.md)
- **The flows that use re-authentication:** [User journeys](04-user-journeys.md)
- **How payouts are reviewed and protected:** [Payouts and rewards](10-payouts-and-rewards.md)
