# 4. User journeys

This page walks through the main end-to-end flows on GBlock. Each journey is
described from the member's perspective: what you do, what the platform does,
and where the gates are.

Use this as a reference. You do not need to read it top to bottom the first
time; jump to the journey you are trying to complete.

---

## Journeys in this page

1. [Onboarding](#onboarding)
2. [Browse the dealflow](#browse-the-dealflow)
3. [Place a sale block](#place-a-sale-block)
4. [Guarantee and vouch for members](#guarantee-and-vouch-for-members)
5. [Run a deal thread](#run-a-deal-thread)
6. [Manage a data room](#manage-a-data-room)
7. [Send an invitation](#send-an-invitation)
8. [Request a payout](#request-a-payout)
9. [File a complaint](#file-a-complaint)
10. [Enable 2FA](#enable-2fa)

---

## Onboarding

The first session after you register by email or receive an invitation.

```text
Registration form or invitation email
  └─ Magic link (click within 30 minutes)
       └─ Profile incomplete?
            ├─ Yes → Complete profile → Choose your paths → Cabinet home
            └─ No  → Cabinet home
```

**What you do:**

1. Click the magic link in the email.
2. If prompted, complete your profile.
3. Choose your paths: **Data Room & Scoring**, **Ambassador**, **Apply for
   Residency**. You can take one, two or all three, and each path asks for its
   own consent.
4. Arrive at the cabinet home.

**What the platform does:**

- Verifies the signed, single-use token and authenticates you.
- Never reveals whether an email is already registered.
- Routes you to profile completion if anything is missing, otherwise straight
  to the cabinet.

At the end of onboarding you are a **Registered** member, **Anonymous** trust
tier, **Member** reputation tier (0-49 Volume), with the welcome grant in
your pocket: 30 starting reputation, or 40 plus a vouch gift if you arrived
through an invitation. What you can do next depends on which paths, statuses
and tiers you add. See [User roles and statuses](02-user-roles-and-statuses.md).

---

## Browse the dealflow

Finding opportunities as a buyer. Available to Residents (Anonymous, Vouched,
and Verified trust tiers all qualify). Ambassadors can look at the Secondary
Market and the Demand Board read-only, but do not see the dealflow.

**Step 1. Open Dealflow.**

The dealflow overview lists active sale blocks. Each block is a private package
of assets or an opportunity a member has placed. You see a safe preview: enough
to decide whether you want to know more, not enough to act on without going
through access review.

**Step 2. Open a block.**

A block detail page shows the safe preview plus any terms the seller has chosen
to expose. You do not see seller contact details and you cannot transact on
this page.

**Step 3. Request access.**

If a block interests you, request access. This is a deliberate, reviewable
action. The seller and the operator review your request.

**Step 4. Express interest.**

If your access is approved, you can express buyer interest in the block. This
puts you on the path to a mediated deal thread with the seller.

```text
Dealflow overview → Block detail → Request access → Express interest
                                              └─→ Mediated introduction → Deal thread
```

**What the platform does behind the scenes:**

- Gates the block detail behind trust checks appropriate to the block's
  visibility rules.
- Records the access request for seller and operator review.
- Never reveals your identity to the seller until a mediated introduction is
  established.

---

## Place a sale block

Offering an opportunity to the network as a seller. This journey is gated by
the **Trust Gate**, which is why your Trust Tier matters.

**Precondition:** You must be a Resident and at least **Vouched** (two
guarantees from Verified members) or **Verified** (KYC passed). Anonymous
members cannot place blocks. See the
[access matrix](02-user-roles-and-statuses.md#the-full-access-matrix).

**Step 1. Open the Seller Dashboard.**

The dashboard lists your existing blocks (draft, active, stale, expired,
removed, rejected, archived) and gives you a path to create a new one.

**Step 2. Draft a new block.**

Open the **Create Block** page and fill in the details of the opportunity. You
remain in draft until you submit.

**Step 3. Submit for review.**

When you submit, the **Trust Gate** evaluates you:

- **Verified seller:** the block goes active, with a 72-hour freshness window,
  and no guarantor requirement.
- **Vouched seller:** the block goes active, with a 24-hour freshness window,
  and two Verified guarantors required.
- **Anonymous seller:** the block is **blocked**. The platform puts it in a
  waiting state with an explanation. You cannot proceed until your Trust Tier
  changes.

**Step 4. Manage the block.**

Creating, editing, submitting, renewing (extending freshness) and closing a
block all require **re-authentication** (a fresh magic-link confirmation
within the last 10 minutes). See
[Trust and safety - Re-authentication](07-trust-and-safety.md#re-authentication).

**Step 5. Review incoming access requests.**

When buyers request access, you review them. Approved requests move toward a
mediated introduction.

**Block lifecycle:**

```text
draft → submitted → under_review → active → stale_warning → expired
                     ↓
                 rejected / manually_removed / archived
```

A block that is not renewed before its freshness window closes moves through
`stale_warning` into `expired`. This keeps the dealflow current and rewards
sellers who maintain their listings.

---

## Guarantee and vouch for members

Backing another member. This is how the network grows trust without a
centralized gatekeeper. There are two instruments: **guarantees** (the Vouched
trust path) and **vouches** (the Resident status path, delivered through the
waitlist).

### Guarantees (Vouched path)

**Precondition:** to guarantee someone into the **Vouched** trust tier, you
must be **Verified**, and the member needs guarantees from two Verified
members (two is the minimum threshold, not a cap).

**Step 1. Receive a guarantee request.**

A member requests a guarantee from the Guarantee Board. You see the request in
your cabinet.

**Step 2. Accept (with re-authentication).**

Accepting requires re-authentication. When you accept:

- The member enters a probation period (Standard 30 days, Founding 14 days,
  Extended 60 days). No reputation is locked up front, but while the guarantee
  is active **50% of the ward's negative reputation events land on you too**.

**Step 3. Probation.**

During probation the ward is under supervised observation. If the ward commits
a trust violation, the ward is penalized and the probation is extended.

**Outcomes:**

- **Success:** the ward completes probation in good standing and the guarantee
  is recorded as completed. For a Residency applicant, this completes their
  admission as a Resident.
- **Violation:** three violations by the ward lead to revocation of the
  guarantee and a reputation impact for you.

### Vouches (Resident path)

**Precondition:** you must have completed KYC. Any KYC-approved member can
give a candidate's **first vouch**; the **decisive second vouch** — the one
that completes Resident status — must come from a **KYC-verified Resident**.

**How it works:**

1. A waitlist candidate receives your vouch. You stake 10 of your Volume
   capacity, and the candidate gains +10 reputation while you gain +5. How many
   vouches you can hold is your Volume capacity divided by ten.
2. When the candidate holds two qualifying vouches (at least one from a
   Resident), their Resident status completes.
3. If a vouch is later revoked, the stake is not returned, revoking costs a
   further 5 Volume, the reputation granted to both sides is clawed back plus a
   penalty for you, and two revocations within 30 days put your vouching on hold
   for operator review. Vouch responsibly.

This is the core of shared accountability. Do not back someone you cannot
stand behind.

---

## Run a deal thread

The mediated introduction flow that follows an approved access request. This is
where buyer and seller actually communicate, but always inside a governed
channel.

**Step 1. Access approved.**

After a buyer's access request is approved by the seller and the operator, a
mediated introduction is created.

**Step 2. Deal thread opens.**

The deal thread is a private, in-platform channel between buyer and seller. You
find your active deals under **Deals** and **Threads** in the cabinet, and open
a specific deal on its detail page.

**Step 3. Communicate.**

Exchange messages, share context, and request additional materials. Direct
off-platform contact is not part of the flow; the thread is the channel.

**Step 4. Reach an outcome.**

The thread progresses toward an outcome (interest confirmed, terms discussed,
declined, or no longer relevant). Once resolved, the thread is archived.

**Step 5. Raise a problem.**

If something goes wrong in a deal, you can file a complaint about that deal or
open a dispute from the thread itself. The thread stays open while the
operator looks into it. See [Trust and safety](07-trust-and-safety.md#complaints).

What GBlock does not do here: it does not settle any transaction, move funds,
or custody assets. The thread exists to mediate the introduction and the
conversation, nothing further.

---

## Manage a data room

The member-controlled Virtual Data Room (VDR). This is the project axis of
GBlock: a place to consolidate diligence materials for an opportunity you are
representing or backing. Pricing, allowances and scoring are covered in
[Data Rooms, scoring and subscriptions](12-data-rooms-scoring-and-subscriptions.md).

**Step 1. Create or open a data room.**

Any onboarded member in good standing can open a Data Room for their own
company. A room about someone else's company (the secondary market, including a
company you back as an investor) needs full Resident status. The room belongs to
**you, its creator**. The company record behind it is shared, so different people can open
their own rooms for the same company. Your first room is free.

**Step 2. Upload documents.**

You upload diligence documents (financials, legal, cap table, commercial,
reports). Office files (DOCX, XLSX, PPTX) can be uploaded, but at launch they are
not shown to recipients, so share documents you want investors to open as PDF. Files are stored through signed cloud URLs; access is controlled by
you as the room owner. Uploads require re-authentication. When you, as owner,
upload the first document to a room of your own company, your
[Data Room functions](02-user-roles-and-statuses.md#data-room-functions-the-founder-extension)
switch on silently.

**Step 3. Grant access.**

You grant access to specific members. Access can be:

- **Direct:** granted to a named member.
- **Unlisted token:** a shareable token that lets a holder view the room
  without you naming them individually. Unlisted tokens are switched off at
  launch; use direct grants.

Granting and revoking access require re-authentication. You can also invite
teammates to the room by email with one of the team roles (Owner, Editor,
Member); the invited person gets a "this is not me" option if the invitation
reached the wrong address.

Any link that leads to your room doubles as a referral link — see
[Silent Data Room referrals](11-silent-dr-referral.md).

**Step 4. Control capabilities.**

You can toggle download permissions, revoke access, set document visibility,
and view the scoring report for the project.

**Step 5. Scoring and the public catalog.**

Each project has a deterministic scoring report combining two dimensions:
**Potential** (0-150) and **Readiness** (0-150). A scoring is started from the
company's Data Room, which collects the project information the scoring is
based on.

Ordering a scoring and publishing to the public project catalog require a
**Pro** room _(rolling out; see
[Free and Pro rooms](12-data-rooms-scoring-and-subscriptions.md#free-and-pro-rooms-rolling-out))_.
Publication to the catalog requires **a valid scoring and a completed company
profile** (description, sector, and similar public fields).
Without them, the room still works exactly as before for investors you granted
direct access to — it just does not appear in the catalog.

**Scoring validity.** A scoring does not expire with time. It stays valid while
it was produced by the current scoring engine version, and it is shown publicly
while the room is Pro. If it stops being valid or the room goes back to Free,
the room keeps working: grants stay live, content stays available. What changes
is visibility — the room leaves the catalog and the scoring placeholder is
marked until you renew or the room is Pro again.

**Step 6. Closing a room — two different doors.**

When you are done with a room, you choose:

- **Delete permanently** — documents are removed and investor grants are
  revoked.
- **Archive** — investors keep read access to the materials, and the room's
  subscription (if it has one) is paused while it is archived. Archiving is a
  soft close, not a removal.

**Handing a room over.** You can offer a room to another member. The transfer
only happens if the recipient accepts, and both the offer and the acceptance
require re-authentication.

<p align="center">
  <img src="../images/dataroom.png" alt="Data room interface" width="720" />
</p>

---

## Send an invitation

Growing the community as an Ambassador or Resident.

**Precondition:** You must have invitation rights (Ambassador, Resident, or
Ambassador-Resident).

**Step 1. Open Send Invite.**

From the cabinet, open the **Send Invite** page.

**Step 2. Enter the recipient's email.**

The system reserves 10 reputation points from you as a stake.

**Step 3. The recipient receives a magic link.**

They click it within 30 minutes, onboard, and (after their own activation)
become a Registered member.

**Step 4. Stake returns.**

When the invitation activates or expires, your 10 points return (automatically,
at the latest 30 days after the invite was sent). If the invitee misbehaves,
you may face a reputation impact. This is shared accountability applied to
invitations.

Referral rewards, where applicable, are tracked under **Referrals** in the
cabinet. Reward candidates move through pending, locked, approved, released,
and suppressed states. Rewards are paid only from confirmed non-transactional
TECH HY revenue, become releasable 30 days after the revenue they come from,
and reward balances are credited in a monthly batch on the 1st of the month.
See [Payouts and rewards](10-payouts-and-rewards.md).

---

## Request a payout

Turning your reward balance into a withdrawal. There is no self-service
withdrawal button: every payout is a reviewed request to the operator.

**Step 1. Open the Wallet.**

Your reward balance shows what is available to request.

**Step 2. Submit a payout request.**

From the wallet, submit a payout request. The minimum request is **$50**. You
provide a **USDT (BEP-20)** destination address. Without verified KYC, payouts
are limited to **$150 within any 30 days** for the same payout address and any
linked accounts, and a request above that needs KYC. With KYC a request can be
up to $1,500 _(rolling out)_. One payout request is allowed per calendar month,
so that is also the monthly limit.

**Step 3. Operator review.**

The operator reviews your request in a queue. First response within one
business day; approved payouts are sent within 20 business days.

**Step 4. Notification with the transaction hash.**

When the payout is sent, you receive a notification containing the on-chain
transaction hash. If a request is rejected, your balance is untouched and you
can see the reason.

The full rules — limits, SLA, currencies, and what happens on rejection — are
in [Payouts and rewards](10-payouts-and-rewards.md).

---

## File a complaint

Reporting misconduct or quality issues. The complaint flow is designed to be
safe for the reporter. Filing a report goes through the operator.

**Step 1. Open Report.**

From the cabinet, open **Report**.

**Step 2. Pick a category.**

The categories are KYB / KYC, Misrepresentation, Off-platform, Harassment,
Privacy, Fraud, and Other. The category helps the operator route your report.

**Step 3. Contact the operator.**

The Report page shows the operator contact address (`start@techhy.me`). Write
to it quoting the category and include identifiers, dates, and any supporting
context. Evidence and operator notes are kept internal and are never visible to
other members. The reporter's identity is not exposed to the subject of the
complaint.

If the problem is about a specific deal, you can also file a complaint or open
a dispute directly from that deal's thread.

**Step 4. Operator review.**

The operator reviews the complaint and may act on it (warn, restrict, revoke a
guarantee, remove a block, adjust reputation). The reporter may receive status
updates through notifications.

See [Trust and safety - Complaints](07-trust-and-safety.md#complaints).

---

## Enable 2FA

Activating voluntary two-factor authentication for a 0.1x reputation accrual
bonus and stronger account protection.

**Step 1. Open Settings → 2FA.**

From the cabinet, go to **Settings** and then **2FA**.

**Step 2. Enable (with re-authentication).**

Enabling TOTP 2FA requires re-authentication. You scan the QR code with an
authenticator app and verify a code.

**Step 3. Verify and confirm.**

Once verified, 2FA is active on your account. From this point your reputation
accrual rate rises by 0.1x (for example, Verified trust tier goes from 1.2x to
1.3x).

**Disabling 2FA** also requires re-authentication, and you lose the accrual
bonus. See [Trust and safety - 2FA](07-trust-and-safety.md#two-factor-authentication).

---

## Where to go next

- **The rules behind every gate above:** [User roles and statuses](02-user-roles-and-statuses.md)
- **What the cabinet looks like, page by page:** [Platform tour](06-platform-tour.md)
- **The numbers behind Volume and the tier catalog:** [Reputation economy](05-reputation-economy.md)
- **Payout rules in detail:** [Payouts and rewards](10-payouts-and-rewards.md)
- **Data Room pricing, scoring and subscriptions:** [Data Rooms, scoring and subscriptions](12-data-rooms-scoring-and-subscriptions.md)
