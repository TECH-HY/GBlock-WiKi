# 6. Platform tour

A page-by-page walk-through of what you see as a GBlock member. This tour
covers the public surfaces and the member cabinet. Screenshots are included
where the live UI is available; for surfaces still in pre-market validation,
the description is based on the platform specification.

---

## Public surfaces

These pages are visible to anyone, including guests who are not yet members.

### Landing

The front door of GBlock. It introduces the product, the three principles, the
compliance boundaries, and the paths to access.

<p align="center">
  <img src="../images/landing-full.jpeg" alt="GBlock landing page, full view" width="720" />
</p>

The landing page offers these calls to action:

- **One GBlock registration** (enter your email and accept the terms; you
  receive a secure link to complete setup — there is no role to pick at entry).
- **Request access from the community** (Telegram route for applicants without
  an invitation).
- **Become a GBlock ambassador** (the Ambassador program section, with a link
  to the Ambassador Terms).
- **FAQ** (the accordion of the most common questions).

<p align="center">
  <img src="../images/faq.jpeg" alt="GBlock FAQ section" width="560" />
</p>

### Magic link authentication

The login surface. You enter your email, receive a signed single-use link, and
click it to authenticate. The system gives the same response whether or not the
email is known, to prevent enumeration.

<p align="center">
  <img src="../images/auth-desktop.png" alt="Magic link authentication — desktop" width="560" />
</p>

<p align="center">
  <img src="../images/auth-mobile.png" alt="Magic link authentication — mobile" width="280" />
</p>

### Ambassador Terms

A standalone page describing the rights, obligations, and reward model for the
Ambassador path. Ambassador entry is the public registration form; there is no
separate application.

---

## Member cabinet

Everything below requires authentication. The cabinet is the daily home of an
active member.

### Cabinet home

The dashboard you land on after onboarding. It surfaces the things you need at
a glance:

- **Reputation hero:** your Volume, current Reputation Tier, reward rate, and
  progress toward the next tier.
- **Trust Tier badge:** Anonymous, Vouched, or Verified, so you always know
  which market actions you can take.
- **Tier Catalog:** your position in the canonical tier ladder and what the
  next tier requires.
- **Standing:** whether you are in good standing, on probation, or under any
  restriction.
- **Quick actions:** invite, dealflow, referrals, report.

<p align="center">
  <img src="../images/cabinet-mobile.png" alt="GBlock cabinet — mobile view" width="320" />
</p>

The cabinet navigation shows only the tabs your paths and status allow. The
full set is: Overview, Dealflow, Demand Board, Secondary Market, Threads,
Reputation, Invites, Referrals, Vouches, Balances, Subscriptions,
Notifications, Report, KYC, CRM Profile, Support, and Settings. A member who is
restricted and cannot reach Settings still reaches the **My data** page.

### Profile and interests

- **Profile complete / edit:** the onboarding profile (identity details the
  operator needs to run the club). Required before you can act in the network.
- **Interests:** the asset classes you care about (for Residents). Options
  include pre-IPO, private equity, OTC, secondary market, investment
  opportunities, and other. These personalize discovery but never bypass access
  gates.

### Reputation

The detailed reputation dashboard:

- Your **Volume** total and your **grade** in the tier catalog.
- Your **reward rate**, locked weekly from a snapshot, and progress toward the
  next tier.
- **V_capacity** (your operational capacity, which drives your tier and how many
  vouches you can give) and **V_rate** (the part of your Volume that counts
  toward your locked weekly reward rate).
- The grade ladder with every tier's Volume range and rate.
- Your recent reputation events.

This is where you inspect the numbers behind the [reputation economy](05-reputation-economy.md).

### Send Invite

The invitation surface. You enter an email, the system reserves 10 reputation
points, and the recipient receives a magic link. You should only invite people
whose conduct you can stand behind, because their behavior affects your
reputation.

### Vouches

Where you see the vouches you have given, their status and the reputation
events they caused, and the vouch capacity you have left (your Volume capacity
divided by ten). You vouch from a deal thread. See
[Reputation economy - Vouches](05-reputation-economy.md#vouches).

### Demand Board and Secondary Market

The **Demand Board** shows aggregated, anonymous demand per asset. Demands are
signals only — there is no "respond" button — and a member can hold a limited
number of active demands for a limited term. Residents can post and manage
demands; Ambassadors can read the board.

The **Secondary Market** page lists anonymous positions from Residents.
"Interested" opens a private thread; introduction and settlement stay between
the parties, and GBlock records the confirmed outcome. Listings run for 90
days. Ambassadors have read-only access.

### Referrals

Referral reward candidates, each in one of these states:

- **Pending** (under review)
- **Locked** (held pending resolution)
- **Approved** (cleared for release)
- **Released** (paid out)
- **Suppressed** (held back due to a conduct or policy issue)

Rewards are paid only from confirmed non-transactional TECH HY revenue, and
credited to your reward balance monthly on the 1st.

Members who registered after clicking a link to one of your Data Rooms appear
here as **silent referrals** — attributed to you like any other referral, with
no obligations on either side. See
[Silent Data Room referrals](11-silent-dr-referral.md).

### Guarantee Board

Where you request, accept, or cancel guarantees. This is the hub for the shared
accountability system. Accepting a guarantee starts a probation period for the
ward, and while it is active a share of the ward's negative reputation events
lands on you.

### Dealflow

The dealflow overview lists active sale blocks. Each card shows a safe preview.
Clicking a card opens the block detail page.

### Block detail

A safe, gated view of a single block. You see the preview and any terms the
seller has exposed. Two actions live here:

- **Request access:** ask the seller and operator to let you see more.
- **Express interest:** signal that you want a mediated introduction.

### Deal threads

Your mediated introduction channels, found under **Deals** and **Threads**.
Each deal has its own detail page with the message thread between you and the
counterparty. This is the governed channel for buyer-seller communication.

### Seller Dashboard

Your view as a seller. It lists your blocks across every lifecycle state and
gives you a path to create a new one.

- **Create Block:** the drafting form for a new sale block.
- **Seller block detail:** manage your own block. Renew (extend freshness) or
  close the block. Both actions require re-authentication.

### Data Room

The Virtual Data Room for a project you are representing or backing. From here
you:

- Upload diligence documents.
- Grant access (direct; unlisted tokens are switched off at launch).
- Toggle download permissions.
- Revoke access.
- Invite teammates to the room (Owner, Editor or Member).
- View the project's scoring report (Potential 0-150 + Readiness 0-150).
- Publish to the public catalog (requires a valid scoring and a completed
  company profile).
- Offer the room to another member, who must accept the transfer.
- Close the room — **delete permanently** (documents removed, grants revoked)
  or **archive** (investors keep read access, and a room subscription is paused
  while it is archived).

The room belongs to its creator. Pricing and allowances are described in
[Data Rooms, scoring and subscriptions](12-data-rooms-scoring-and-subscriptions.md).

Room documents carry a layered watermark (a visible layer plus a forensic
layer) so leaked material can be traced. _Rolling out._

<p align="center">
  <img src="../images/dataroom.png" alt="Data room interface" width="720" />
</p>

### Project catalog

The public catalog of published projects. A room appears here only with a
**valid scoring and a completed company profile**. If the scoring stops being
valid, the room leaves the catalog and its report placeholder is marked until
renewed — the room itself keeps working for investors who already have access.

### Wallet

Your balances and money movements:

- **Reward balance:** referral rewards land here in a monthly batch on the
  1st of the month. You can move rewards into your payment balance; the
  transfer **adds a 3% bonus** on top of the amount you move.
- **Payment balance:** funds for platform purchases such as project scoring and
  Data Room subscriptions, topped up by card. A top-up above $150 earns a +5%
  bonus, and a top-up of $500 or more earns +10%. You can also set up an
  automatic top-up.
- **Payout requests:** withdrawals are requested from the wallet and reviewed
  by the operator — there is no self-service withdrawal. Minimum $50, USDT
  BEP-20, one request per calendar month, and without KYC up to $150 within
  30 days. The operator pays approved requests
  within 20 business days. See [Payouts and rewards](10-payouts-and-rewards.md).

If your Data Room functions are not active yet, the payment block is visible
but the top-up button is locked, with a hint that uploading the first document
to your Data Room activates it. _Rolling out._

### Subscriptions

Where you manage what you pay for: your Data Room subscriptions, scoring
vouchers, and unfreezing a Data Room whose subscription lapsed. Cancelling is
done only here, in at most three screens, and every screen has a "cancel now"
option. You are offered a 50% retention discount once per Data Room, and members
who have been inactive receive a warning email three days before a charge. See
[Data Rooms, scoring and subscriptions](12-data-rooms-scoring-and-subscriptions.md).

### Support

The contact-operator surface. You open a ticket with a subject and a
description; the operator responds within one business day. Payout requests
are handled through the same reviewed pipeline, with their own payout SLA
(response in 1 business day, payout within 20 business days, transaction hash
in the completion notification).

### Scoring report

A deterministic, two-axis evaluation of a project: **Potential** (0-150) and
**Readiness** (0-150). The report gives members a consistent way to compare
opportunities on the same dimensions.

### Notifications

Your activity feed. Expect alerts for:

- Probation start, end, and violation.
- Reputation updates and tier changes.
- Weekly reputation snapshots.
- Block freshness warnings.

### Report (complaints)

The safe reporting surface. You pick a category (KYB / KYC, Misrepresentation,
Off-platform, Harassment, Privacy, Fraud, Other) and write to the operator at
the address shown on the page, quoting the category. Evidence and operator
notes stay internal; your identity is not exposed to the subject of the
complaint. A deal thread has its own complaint and dispute actions.

### Settings, My data and 2FA

- **Settings:** account preferences, including the account deletion request.
- **My data:** export a copy of your data and request account deletion. It is
  also reachable by members who are restricted and cannot open Settings.
- **2FA:** TOTP two-factor authentication. Enabling it adds a 0.1x reputation
  accrual bonus and strengthens account security. Enabling, verifying, and
  disabling 2FA all require re-authentication. All members are expected to
  keep 2FA enabled — see
  [Trust and safety](07-trust-and-safety.md#two-factor-authentication).

---

## Mobile experience

GBlock is built mobile-first. The cabinet and the public surfaces adapt to
small screens, so you can review dealflow, accept guarantees, and respond in
deal threads from a phone. Sensitive actions still require re-authentication
regardless of device.

<p align="center">
  <img src="../images/landing-mobile.png" alt="GBlock landing — mobile" width="320" />
</p>

---

## API (v1)

For members who want to integrate GBlock data into their own tools, a limited
API is available. It uses your signed-in session — there are no API keys.

- **Read:** session, profile, dashboard, blocks, block detail, your deals and
  deal detail, and your wallet.
- **Write:** wallet transfers, wallet payments, and the intro-compensation
  action on a deal.

The API cannot place blocks, send invitations, or modify reputation.

> The API surface is intended for monitoring and personal tooling. Anything
> else that changes state goes through the cabinet, where re-authentication and
> operator review can apply.

---

## Where to go next

- **The rules behind what you see:** [User roles and statuses](02-user-roles-and-statuses.md)
- **Step-by-step flows on every page above:** [User journeys](04-user-journeys.md)
- **Balances, payouts, and rewards:** [Payouts and rewards](10-payouts-and-rewards.md)
- **The security model behind the cabinet:** [Trust and safety](07-trust-and-safety.md)
