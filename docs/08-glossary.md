# 8. Glossary

Plain-language definitions of the terms used across GBlock. Terms are grouped
by theme to make them easier to scan.

---

## Membership and identity

**Registered**
The base status of anyone who registers with an email, arrives via invitation,
or follows a member's Data Room link. Starts with the welcome grant (30
reputation, or 40 plus a vouch gift via invitation). Cannot see dealflow or
place blocks on its own.

**Paths**
What you choose in the cabinet after your first login: Data Room & Scoring,
Ambassador, and Apply for Residency. They are not mutually exclusive.

**Welcome Grant**
The starting reputation every new member receives: 30, or 40 plus one vouch
gift when the registration came through an invitation. The inviter's reserved
reputation is returned on activation.

**Ambassador**
The baseline path, open to every registered member. Grants the right to send
invitations and earn referral rewards, read-only access to the Secondary Market
and Demand Board, and the wallet actions for rewards. Does **not** grant
dealflow access.

**Residency Applicant**
A member who took the Apply for Residency path and is collecting guarantees.
Resident surfaces stay locked until Residency is completed.

**Resident**
A status for market participants. Reached by the guarantee route (two
guarantees from KYC-verified members, then probation) or by the waitlist route
(KYC, then two vouches, the decisive one from a KYC-verified Resident). Grants
dealflow access, the right to place blocks, mediated introductions, deal
threads, and the right to guarantee and vouch others.

**Full Resident**
A Resident who came through the waitlist route: KYC approved, two active
vouches and an approved waitlist request. Gets free secondary-market Data Rooms
by tier. See [Data Rooms, scoring and subscriptions](12-data-rooms-scoring-and-subscriptions.md).

**Data Room Functions**
A silent, lifelong extension of your account — payment account (top-ups,
scoring purchases) and the paid Data Room functions. Activated automatically
when you, as room owner, upload the first document to a Data Room of your own
company. No badge, no application. Internally called an _activated Data Room_.
_Rolling out._

**Waitlist**
The route to full Resident status, open to every registered member who has
completed KYC, including Ambassadors.

**Founding Grant**
An operator-granted path to Resident status, used to bootstrap the network.
Limited to 50 grants or until 100 active Residents exist. Founding Residents
must pass KYC and serve a 14-day probation.

**Canonical Identity**
The rule that one real person maps to one `person_id`, one member account, and
one GBlock profile. Buyer and Seller are modes inside the same account, not
separate registrations.

---

## Trust Tier

**Trust Tier**
An independent axis from Status and Reputation Tier. Determines market access
based on identity assurance. Values: Anonymous, Vouched, Verified.

**Anonymous**
The default Trust Tier. Can view dealflow and act as a buyer (with one
guarantor, any tier). **Cannot create sale blocks.**

**Vouched**
A Trust Tier reached by collecting at least two active guarantees from Verified
members (a minimum threshold, not a cap — guarantors are unlimited). Grants
full secondary-market access, including sale block creation.

**Verified**
A Trust Tier reached by completing KYC. Grants full access with no guarantor
requirement, primary-listing eligibility, faster operator SLA, and a 1.2x
reputation accrual rate (1.3x with 2FA).

> Note: _Verified_ means only the Trust Tier reached by KYC. The lowest
> Reputation Tier (0-49 Volume) is called _Member_; it was previously named
> Verified, and the app may still show the old name until it is updated.

---

## Reputation

**Volume**
Long-term reputation. A ledger of reputation events: good conduct grows it;
stakes, penalties and clawbacks reduce it. Determines Reputation Tier. Cannot
be bought.

**V_capacity**
The view of Volume that counts every reputation event. It is your operational
capacity: it drives your Reputation Tier and how many vouches you can give.

**V_rate**
The view of Volume that counts toward rewards (it excludes deal-outcome
events). A snapshot of it, taken weekly, locks your reward rate for the week.

**Reputation Tier**
A tier derived from Volume. Canonical catalog (`tier-catalog-2026-07-v1`):
Member, Core, Principal, Partner, Vanguard (750+, no ceiling). Determines
reward rate and the free Data Room allowance of full Residents.

**Canonical Tier Catalog**
The authoritative mapping of Volume ranges to tiers, reward rates, and
recovery windows. See [Reputation economy](05-reputation-economy.md).

**Recovery Window**
The catalog's waiting time (168 / 120 / 72 / 24 / 12 hours by tier) after a
penalty or a reworked vouch. _Rolling out._

**Reward Rate**
The share of confirmed non-transactional TECH HY revenue allocated to a member
when a rewardable event occurs. Higher Reputation Tiers earn a higher rate.
Never paid from transaction volume.

**Accrual Rate**
The multiplier applied to reputation earned from activity. Set by Trust Tier
(1.0x / 1.0x / 1.2x) and raised by 0.1x when 2FA is enabled.

---

## Guarantees, vouches, and probation

**Guarantee**
An act where a Verified member backs another member on the Vouched trust path
and on the guarantee route to Resident. Locks no reputation up front, but the
guarantor carries 50% of the ward's negative reputation events while it is
active. Starts a probation period.

**Guarantor**
The member who issues a guarantee. Shares accountability for the ward's
conduct during probation.

**Ward**
The member who receives a guarantee and enters probation.

**Vouch**
A backing on the Resident path, delivered through the waitlist. Credits +10
reputation to the candidate and +5 to the voucher, and stakes 10 of the
voucher's Volume capacity. The first vouch of a candidate can come from any
KYC-approved member; the decisive second vouch must come from a KYC-verified
Resident. A member's vouch limit is their Volume capacity divided by ten
(rounded down).

**Rework**
The withdrawal (revocation) of a vouch or guarantee because the backed member
violated trust. The staked capacity is not returned and revoking a vouch costs
a further 5 Volume; reputation is clawed back with an additional penalty; two
revocations within 30 days put vouching on hold for operator review.

**Probation**
The supervised observation period after a guarantee activates. Standard 30
days, Founding 14 days, Extended 60 days. Each violation extends it by 30 days;
three violations revoke the guarantee.

**Trust Gate**
The check that determines whether a member can place a sale block based on
their Trust Tier. Anonymous is blocked; Vouched is allowed with two Verified
guarantors and 24-hour freshness; Verified is allowed with no guarantors and
72-hour freshness.

---

## Market and dealflow

**Block (Sale Block)**
A private package of assets or an opportunity placed by a member. Explicitly
**not** a blockchain or crypto concept.

**Dealflow**
The set of active sale blocks visible to members who have dealflow rights.

**Buyer**
A mode inside a member account. Browses dealflow, requests access, expresses
interest, enters deal threads.

**Seller**
A mode inside a member account. Places and manages sale blocks.

**Mediated Introduction**
The governed connection between a buyer and a seller after access is approved.
GBlock never hands out direct seller contact.

**Deal Thread**
The private in-platform channel between a buyer and a seller in a mediated
introduction. Where the conversation happens. Not a transaction channel.

**Freshness**
The window during which an active block is current before it must be renewed.
Verified sellers get 72 hours; Vouched sellers get 24 hours. After the window,
the block moves through `stale_warning` to `expired`.

**Data Room (VDR)**
A member-controlled Virtual Data Room for a project. The owner uploads
diligence documents, grants and revokes access, toggles download, invites
teammates, and views the scoring report. A Data Room belongs to **its
creator**; the company record behind it is shared, so several creators can have
rooms for the same company. A room can be transferred only if the recipient
accepts.

**Archive (Data Room)**
A soft close. Investors keep read access, and a room subscription is paused
while the room is archived. Only "delete permanently" removes documents and
revokes grants.

**Listing State**
A Data Room's publication status in the public project catalog. Listed only
with a valid scoring, a completed company profile and a Pro room; if the
scoring stops being valid or the room goes back to Free, the room leaves the
catalog (with a placeholder) while it keeps working for existing grantees.

**Scoring Report**
A deterministic evaluation of a project on two axes: Potential (0-150) and
Readiness (0-150). It does not expire with time; it stays valid while it was
made by the current scoring engine version, and it is shown publicly while the
room is Pro.

**Data Room Subscription**
The monthly charge for a Data Room that is not covered by a free allowance. It
includes one scoring voucher per month. If it lapses, the room is frozen, not
deleted.

**Free Room / Pro Room**
Every Data Room is Free or Pro. Pro (a paid subscription, an operator promotion
or a 30-day voucher window) is needed to order a scoring, to appear in the
public catalog and to list a primary-market block. _Rolling out._ See
[Data Rooms, scoring and subscriptions](12-data-rooms-scoring-and-subscriptions.md#free-and-pro-rooms-rolling-out).

**Scoring Voucher**
A prepaid scoring. Vouchers are valid for 3 months. Applying one to a Free room
opens a 30-day Pro window with one scoring. See
[Data Rooms, scoring and subscriptions](12-data-rooms-scoring-and-subscriptions.md).

**Primary Market**
The surface for primary raises. Listing requires Verified Trust Tier, KYB, and
project-level KYC.

**Secondary Market**
The surface for blocks of existing assets (secondary blocks, pre-IPO, OTC,
M&A). Access depends on Trust Tier.

---

## Security

**Magic Link**
A signed, single-use authentication link sent to your email. Expires after 30
minutes. The login response is generic to prevent email enumeration.

**Re-authentication**
A fresh magic-link confirmation within the last 10 minutes, required for
sensitive actions (managing blocks, accepting guarantees, Data Room uploads and
access grants, exporting your data, managing 2FA). See
[Trust and safety](07-trust-and-safety.md#re-authentication) for the list.

**KYC**
Know Your Customer. Identity verification performed by an external provider.
Documents never leave the provider. Grants the Verified Trust Tier. One
identity verifies exactly one active account; a duplicate identity is
declined, not merged. If KYC is revoked, existing rooms and grants stay live,
but new grants, new Data Rooms and payouts are paused.

**KYB**
Know Your Business. Business-level verification required for primary-market
listings.

**2FA (TOTP)**
Voluntary two-factor authentication using a Time-based One-Time Password app.
Adds a 0.1x reputation accrual bonus and strengthens account security.

**Device Alert**
An email sent when GBlock detects a login from an unrecognized device.

**Standing**
A member's current good-standing or restricted status, visible on the cabinet
home. GBlock is rolling out a record that ties sanctions to the person rather
than the account.

**Sleeping / Deactivated**
Stages of the inactivity lifecycle: a warning after 14 days without a login,
sleeping after 30 days (accrual stops, payments and new Data Rooms are frozen),
and deactivation after 180 days of sleeping (public listings unpublished,
nothing deleted, re-entry through full KYC).

**My data**
The cabinet page where you export your data and request account deletion.

---

## Balances and payouts

**Reward Balance**
The balance where referral rewards land, credited in a monthly batch on the
1st of the month. Withdrawals happen through payout requests only.

**Payment Balance**
The balance used for platform purchases (such as project scoring and Data Room
subscriptions), funded by card top-ups. Rewards can be moved into it and the
transfer adds a 3% bonus; moving it back to rewards is an operator-reviewed
request.

**Payout Request**
The only way to withdraw rewards: a reviewed request to the operator.
Minimum $50, USDT (BEP-20) destination, one request per calendar month, without KYC up to $150 within 30 days, with KYC up to $1,500 per month (_rolling out_).
See [Payouts and rewards](10-payouts-and-rewards.md).

**Business-Day SLA**
Payout clocks measured in working days: the operator responds to a payout
request within 1 business day, and approved payouts are sent within 20
business days.

**Transaction Hash (tx-hash)**
The on-chain identifier of a sent payout, delivered to you in the completion
notification so you can verify the transfer.

**Reconcile**
The daily automated check that reward balances on accounts never exceed
accrued-minus-withdrawn rewards. A discrepancy alerts the operator before any
payout moves.

---

## Deal communication

**Contact Verification Check**
The automated check on deal-thread messages for direct contact data (emails,
phones, messenger handles, external messenger links).

**Quarantine**
The state of a message held by the contact verification check: the recipient
sees a neutral cover, the sender sees their own text and its status, and the
operator can review everything. Quarantine applies until the deal contract is
signed; afterwards, exchanging contacts is legitimate. _Rolling out._

**Silent Referral**
A member who registered after clicking a link to your Data Room. Attributed
to you like any other referral (last click wins, all channels), with no
reputation, vouch, or accountability obligations for either side. See
[Silent Data Room referrals](11-silent-dr-referral.md).

---

## Operator and governance

**Operator**
The internal role that runs GBlock: reviewing blocks, moderating complaints,
running eligibility checks, and granting founding status.

**Complaint**
A member-submitted report of misconduct or quality issues. Evidence and
operator notes stay internal; reporter identity is not exposed to the subject.

**SLA (Operator Review)**
The target time for the operator to review a submission. Set by Trust Tier:
Verified 24h, Vouched 48h, Anonymous 72h. Payout requests use a separate
business-day SLA (see above).

---

## Where to go next

- **The full role and access model:** [User roles and statuses](02-user-roles-and-statuses.md)
- **Every flow that uses these terms:** [User journeys](04-user-journeys.md)
- **The numbers behind Volume and the tier catalog:** [Reputation economy](05-reputation-economy.md)
- **Balances and payouts in detail:** [Payouts and rewards](10-payouts-and-rewards.md)
