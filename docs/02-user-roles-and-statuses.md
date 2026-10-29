# 2. User roles and statuses

GBlock does not have a single "user role." Membership is described by **three
independent axes** that combine to determine what you can do. Confusing them is
the most common newcomer mistake, so this page is the longest in the wiki.

> **Read this page carefully.** Almost every question about "why can't I do X"
> is answered by which axis is blocking you.

---

## The three axes at a glance

| Axis | Question it answers | Possible values |
|---|---|---|
| **Status** | _How did you become a member, and what base rights do you have?_ | Registered, Ambassador, Residency applicant, Resident (plus the silent Data Room functions) |
| **Trust Tier** | _How proven is your identity, and what market actions does that unlock?_ | Anonymous, Vouched, Verified |
| **Reputation Tier** | _How much long-term reputation have you accumulated, and what rewards and service levels come with it?_ | Member, Core, Principal, Partner, Vanguard |

The three axes are independent. A Resident can still be Anonymous (no KYC). A
Vanguard-tier member can be Vouched rather than Verified. Your access at any
moment is the **intersection** of all three.

---

## Axis 1 — Status

Status defines how you entered GBlock and the baseline rights you received.
There is **one identity and one cabinet**: you do not choose a "role" on a
sign-up form. After your first login you pick one or more **paths** inside the
cabinet, and the paths are not mutually exclusive — you can take all of them.

| Path in the cabinet | What it is for |
|---|---|
| **Data Room & Scoring** | Create an issuer company, open Data Rooms and use project scoring. |
| **Ambassador** | Invite people you can vouch for and earn referral rewards. Setting this path gives you the 30-point starting reputation floor. |
| **Apply for Residency** | Open a Residency application and collect guarantees. The application only opens the process: Resident surfaces stay locked until Residency is completed. |

### The welcome grant

Every new member starts with the same kind of welcome grant:

- **30** starting reputation when you register directly (the Ambassador floor).
- **40** starting reputation plus **1 vouch gift** when you register through a
  member's invitation. The reputation the inviter reserved for the invitation
  is returned to them when it activates.

Reputation can go up and down from there. See
[Reputation economy](05-reputation-economy.md).

### The statuses

| Status | How you get it | What it grants |
|---|---|---|
| **Registered** | Register with your email and a magic link, arrive through a member's invitation, or follow a member's Data Room link | Cabinet, profile and a read-only view of your balances. Everything else comes from the paths below. Cannot see dealflow or place blocks. |
| **Ambassador** | Take the Ambassador path (open to every registered member) | The right to send invitations and earn referral rewards, a reputation view, **read-only** access to the Secondary Market and the Demand Board, and the wallet actions for rewards (move rewards into your payment balance, request a payout). **Does not grant dealflow, placing blocks or deal threads.** |
| **Residency applicant** | Take the Apply for Residency path | The Guarantee Board, where you request guarantees. Becomes **Resident** after two guarantees from KYC-verified members and a completed probation. |
| **Resident** | The guarantee route above, or the waitlist (see below) | Access to dealflow, placing blocks, mediated introductions, deal threads, posting on the Demand Board, and the right to guarantee and vouch others. |

### Two routes to Resident

- **Guarantee route (ordinary Resident).** You apply for Residency and collect
  **two guarantees from KYC-verified members**. Each guarantee starts a
  probation (30 days by default). When it completes in good standing, you
  become a Resident.
- **Waitlist route (full Resident).** You complete KYC, join the waitlist and
  collect **two vouches, at least one from a KYC-verified Resident**; the
  decisive second vouch must come from a KYC-verified Resident. A full Resident
  also gets the Data Room allowances described in
  [Data Rooms, scoring and subscriptions](12-data-rooms-scoring-and-subscriptions.md).

Both routes lead to the same dealflow rights. The wording of how the two routes
relate is still being consolidated, and this page will follow the product.

### Reading the table

- **Ambassador is about community growth** (invites, referral rewards).
  **Resident is about market participation** (dealflow, blocks, vouching).
  Neither implies the other: a member can hold both.
- **Data Room functions are not a status.** They are a silent extension of your
  account, described below.

---

## Axis 2 — Trust Tier

Trust Tier is an **independent axis from Status**. It exists to let members
participate at the level of identity assurance they are comfortable with, from
fully anonymous to KYC-verified.

| Trust Tier | How you reach it | What it unlocks |
|---|---|---|
| **Anonymous** | Default for everyone | View dealflow, act as a buyer (requires one guarantor, any tier). **Cannot create sale blocks.** |
| **Vouched** | At least two active guarantees where **both** guarantors are Verified | Full secondary-market access: create sale blocks, participate in deal threads. |
| **Verified** | Pass KYC | Full access with no guarantor requirement, plus primary-listing eligibility and faster operator service levels. |

Guarantors are **not limited to two people**. Two Verified guarantees is the
minimum threshold for the Vouched path, not a cap — you can collect more.

### Why Trust Tier matters even if you are a Resident

A Resident who is still Anonymous **cannot place sale blocks**. They can browse
dealflow and act as a buyer (with one guarantor), but to become a seller they
must either:

- reach **Vouched** by collecting guarantees from Verified members (two is the
  minimum), or
- reach **Verified** by completing KYC.

This is the most common point of friction. If you are a Resident and the
"create block" action is unavailable, check your Trust Tier first.

### KYC and anonymity

KYC is performed at an external provider. Your documents never leave the
provider, and GBlock never sees or stores them. Completing KYC upgrades you to
the **Verified** trust tier and is the cleanest path to full market access,
including:

- No guarantor requirement for sale blocks.
- A 72-hour block freshness window (vs. 24 hours for Vouched).
- The ability to serve as a guarantor on the Vouched path.
- The ability to give vouches on the Resident path (see below).
- A 1.2x reputation accrual rate (1.3x with 2FA enabled).
- The faster 24-hour operator review SLA.
- Payouts above $150 within 30 days (see [Payouts and rewards](10-payouts-and-rewards.md)).

You are never forced to reveal your identity to the network. Anonymous members
can accumulate Volume and act as buyers indefinitely.

One identity can be verified only once: if the same person is already an
active verified member, a new KYC attempt with that identity is declined
rather than merged. See
[Trust and safety - KYC and identity](07-trust-and-safety.md#kyc-and-identity).

---

## The full access matrix

This is the single most important table in the wiki. It shows what each Trust
Tier permits, and the conditions that apply.

| Action | Anonymous | Vouched | Verified |
|---|---|---|---|
| View dealflow | Yes | Yes | Yes |
| Express buyer interest | Yes (needs 1 guarantor, any tier) | Yes | Yes |
| Create a sale block | **No** | Yes (2 Verified guarantors, 24h freshness) | Yes (0 guarantors, 72h freshness) |
| Act as guarantor (Vouched path) | No | No | **Yes, exclusively** |
| Give a vouch (Resident path) | No | First vouch only (KYC-approved members) | First vouch, plus the decisive vouch if you are a Resident |
| Primary-market listing | No | No | Yes (requires KYB + project KYC) |
| Maximum simultaneous blocks | 0 | 1 | 3 |
| Operator review SLA | 72h | 48h | 24h |
| Reputation accrual rate | 1.0x | 1.0x | **1.2x** |
| Reputation accrual with 2FA | 1.1x | 1.1x | **1.3x** |

Notes:

- The matrix applies to members who already hold the Resident status; the
  Ambassador and Data Room paths do not give dealflow rights by themselves.
- "Freshness" is how long a block stays visible before it must be renewed or it
  goes stale. Verified sellers get a longer window because their identity is
  already proven.
- "Operator review SLA" is the target time for the GBlock operator to review
  your submission (a block, an access request, a complaint). Higher trust buys
  you a faster queue.
- On the Resident path, **any KYC-approved member can give a first vouch**, but
  the decisive second vouch — the one that completes a waitlist candidate's
  Resident status — must come from a **KYC-verified Resident**.
- How many vouches you can give is derived from your Volume capacity, not from a
  fixed per-tier cap: your limit is your Volume capacity divided by ten
  (rounded down). See [Reputation economy](05-reputation-economy.md#vouches).
- 2FA is voluntary at every tier and adds a 0.1x accrual bonus on top of your
  base rate. See [Trust and safety](07-trust-and-safety.md#two-factor-authentication).

---

## Axis 3 — Reputation Tier

Reputation Tier is derived from your **Volume** (long-term reputation). It
determines your reward rate and how much capacity you have to back others.
Volume is a ledger of reputation events: good conduct grows it, while stakes,
penalties and clawbacks reduce it. It cannot be bought.

The canonical tier catalog (`tier-catalog-2026-07-v1`):

| Tier | Volume range | Reward rate | Recovery window |
|---|---|---|---|
| **Member** | 0 - 49 | 10% | 168 hours |
| **Core** | 50 - 149 | 13% | 120 hours |
| **Principal** | 150 - 349 | 17% | 72 hours |
| **Partner** | 350 - 749 | 20% | 24 hours |
| **Vanguard** | 750+ | 25% | 12 hours |

The Vanguard tier has **no Volume ceiling**: the ladder keeps climbing, and
25% is the maximum direct reward rate.

How to read this:

- **Reward rate** is the share of confirmed non-transactional TECH HY revenue
  allocated to the member when a rewardable event occurs (for example, a
  successful referral). Higher tiers earn a larger share. The rate you see in
  the cabinet is locked once a week from a snapshot of your Volume — see
  [Reputation economy](05-reputation-economy.md#two-views-of-volume).
- **Recovery window** is the catalog's waiting time after a penalty or a
  reworked vouch, by tier. _Rolling out._
- The lowest Reputation Tier (0-49 Volume) is called **Member**. It was
  previously named Verified, and the app may still show the old name until it is
  updated. **Verified** now means only the KYC Trust Tier.

For the mechanics behind Volume, see
[Reputation economy](05-reputation-economy.md).

---

## Special admission: the founding grant

There is a further admission path alongside invitation and self-registration:
the **founding operator grant**. It exists to bootstrap the network with a first
cohort of trusted Residents who can then guarantee others.

- Granted by the operator with a recorded reason and evidence.
- **Quota:** 50 founding grants, or until 100 active Residents exist.
- Founding Residents **must pass KYC**, so they enter as Verified Trust Tier.
- They serve a **14-day probation** during which they cannot issue guarantees.
- After probation they form the initial pool of Verified guarantors who can
  vouch others into Vouched status.

This path is not openly requestable. It is an operator decision tied to the
early growth phase of the club.

---

## Data Room functions (the "founder" extension)

"Founder" is **not a role you apply for** and not a badge you wear. It is a
silent extension of your account — internally the mark of an _activated Data
Room_ — that unlocks the selling side of the platform: a payment account
(top-ups and scoring purchases) and the paid Data Room functions.

How it works:

- **Anyone onboarded can open a Data Room.** Any member in good standing who has
  chosen a path may create one, including investors who hold a stake in a
  company. The first Data Room is free. See
  [Data Rooms, scoring and subscriptions](12-data-rooms-scoring-and-subscriptions.md).
- **Activation is automatic and silent.** The functions switch on when **you,
  as the room owner, upload the first document** to a Data Room of your own
  company. An empty room, and the scoring form on its own, do not activate
  anything. There is no application and no waiting period.
- **It is lifelong.** Nothing — archiving or deleting a room, KYC changes or
  account sleep — removes it.
- **It is invisible.** You will not see the word "Founder" anywhere in the
  cabinet. The functions simply appear.
- **It only unlocks the input side.** You can top up your payment balance and
  purchase project scoring. It does not by itself unlock withdrawals — payouts
  follow the model in [Payouts and rewards](10-payouts-and-rewards.md).
- **It does not change your reputation.**

In the cabinet, the wallet's payment block is visible to everyone; if the
functions are not active yet, the top-up button explains what activates them
(upload a first document to your Data Room).

---

## Probation

Probation is a supervised observation period that starts when a guarantee is
activated. It exists so that a guarantor's reputation is genuinely on the line
for the person they vouched for.

| Probation type | Duration | When it applies |
|---|---|---|
| Standard | 30 days | Default for a normal guarantee. |
| Founding | 14 days | For founding-grant Residents. |
| Extended | 60 days | Applied in response to conduct concerns. |

During probation:

- The ward is under supervised observation. Accepting a guarantee does **not**
  lock any of your reputation up front.
- If the ward commits a trust violation, the ward is penalized, the guarantor
  carries **50%** of the ward's negative reputation events while the guarantee
  is active, and the probation is extended by another 30 days.
- Three violations by a ward lead to revocation of the guarantee and a
  reputation impact for the guarantor.
- If the ward completes probation in good standing, the guarantee is recorded as
  completed. For a Residency applicant this is the step that makes them a
  Resident.

Probation is one of the reasons GBlock can stay sponsorship-based without a
centralized gatekeeper on every action: the network polices itself through
shared accountability.

---

## Identity: one person, one account

GBlock enforces a single canonical identity per real person.

- One real person maps to one member account, which can hold several paths.
- Buyer and Seller are **modes inside a single account**, not separate
  accounts. You do not register twice to do both.
- GBlock is rolling out a record that ties sanctions to the **person** rather
  than the account, so that opening a new account does not clear a ban or an
  open sanction. _Rolling out._

This is what makes shared accountability enforceable. If a member misbehaves,
the reputation cost attaches to the real person, not a throwaway handle.

---

## Putting it together: a worked example

Suppose you register with your email, click the magic link and complete your
profile. At that moment:

- **Status:** Registered. After you pick the Ambassador path you hold the
  30-point reputation floor (a registration through a member's invitation would
  start at 40 plus 1 vouch gift).
- **Trust Tier:** Anonymous (no KYC, no guarantees).
- **Reputation Tier:** Member (0-49 Volume).

What can you do? Browse dealflow, no (that needs Resident). Place a sale block,
no. Send invitations, yes — each one reserves 10 of your reputation points until
it activates or expires.

To unlock more, you would pursue one or more of:

1. **Become a Resident** through the guarantee route (two guarantees from
   KYC-verified members, then probation) or the waitlist route (KYC, then two
   vouches). Your invitation vouch gift, if you have one, counts as a real
   vouch. This opens dealflow rights, block placement, and vouching.
2. **Reach Vouched** by collecting guarantees from Verified members (two is the
   minimum). This lets you place sale blocks.
3. **Reach Verified** by completing KYC. This removes the guarantor requirement
   for blocks, lets you vouch others, raises your accrual rate to 1.2x, and
   puts you in the 24-hour operator SLA queue.
4. **Activate the Data Room functions** by uploading the first document to your
   own Data Room. This switches on top-ups and scoring purchases.

Each of these is independent. You can sequence them in whatever order matches
your goals.

---

## Where to go next

- **How to actually get in:** [Getting access](03-getting-access.md)
- **The end-to-end flows:** [User journeys](04-user-journeys.md)
- **The numbers behind Volume:** [Reputation economy](05-reputation-economy.md)
- **Data Rooms, scoring and subscriptions:** [Data Rooms, scoring and subscriptions](12-data-rooms-scoring-and-subscriptions.md)
- **Every term used on this page, defined:** [Glossary](08-glossary.md)
