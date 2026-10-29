# 9. Roadmap and stage

GBlock is a staged product. This page describes the current stage, the
roadmap, what is live today, what is planned, and what is explicitly out of
scope. It exists so members and applicants can calibrate their expectations.

---

## Current stage: PRE_MARKET_INTERNAL_UAT

GBlock is in **PRE_MARKET_INTERNAL_UAT** (pre-market internal user acceptance
testing). This is a controlled, pre-market phase.

What this means in practice:

- Anyone can register with an email address, but market access (the Resident
  status and the dealflow) is sponsorship-based. There is no open entry into the
  market surfaces.
- The product is being validated against its specification with a controlled
  group of members.
- Some functionality described in this wiki is live; some is planned and
  marked as such.
- Deployment to this stage does **not** imply market release or live commercial
  traffic.

If you are reading about GBlock from outside, treat the live experience as
real but evolving. Features marked as _planned_ or _roadmap_ in this wiki are
not yet available to members.

---

## Roadmap phases

The GBlock roadmap is organized into five phases.

| Phase | Focus |
|---|---|
| **P0 - Core Platform** | The foundation: identity, magic-link auth, member cabinet, reputation, statuses, guarantees, complaints, 2FA. |
| **P1 - Primary Market Readiness** | KYC/KYB flows, project scoring, data room, primary-market listing eligibility. |
| **P2 - Dealflow and Market Operations** | Sale blocks, dealflow, access requests, deal threads, operator review tooling. |
| **P3 - Growth and Trust Economy** | Referral rewards, tier catalog maturity, ambassador growth, reputation economy tuning, Data Room subscriptions. |
| **P4 - Regulated Integrations** | Integrations with regulated counterparties where applicable, subject to jurisdictional limits. |

Phases are sequential in intent but overlapping in execution. P0, P1, and P2
are largely in place today; P3 is maturing; P4 is future work contingent on
external partnerships and regulatory positioning.

---

## What is live

The following are part of the current product for members:

- Registration by email with a magic link, and invitation-based onboarding,
  with the welcome grant (30 starting reputation; 40 plus a vouch gift via
  invitation). After the first login the member chooses their paths: Data Room
  & Scoring, Ambassador, Apply for Residency.
- Member cabinet: home, profile, reputation, vouches, notifications,
  subscriptions, and the My data page (export and deletion request).
- Statuses and paths: Registered, Ambassador, Residency applicant, Resident.
  Two routes to Resident: guarantees plus probation, or the waitlist with
  vouches.
- Trust Tiers: Anonymous, Vouched, Verified (via KYC).
- Canonical Tier Catalog and the reputation economy: Volume split into
  V_capacity and V_rate, a weekly locked reward rate, and the tier ladder
  Member → Core → Principal → Partner → Vanguard at rates 10 / 13 / 17 / 20 /
  25%.
- Invitations that reserve reputation, vouches that stake Volume, and guarantees
  with probation, including the Trust Gate for sale blocks.
- Sale blocks: draft, submit, review, active, stale, expired, removed,
  rejected, archived.
- Dealflow browsing, access requests, buyer interest, the Demand Board and the
  Secondary Market.
- Mediated deal threads with automated contact checks on messages, plus
  complaints and disputes from inside a deal.
- Data Room: owner-controlled document storage, access grants, team members,
  ownership transfer, scoring report, and the public project catalog.
- **Data Room pricing.** First room free; free secondary-market rooms for full
  Residents by tier; monthly subscriptions for all other rooms with one scoring
  voucher per month; freeze (not deletion) when a subscription lapses; the
  cancellation flow with a retention offer. See
  [Data Rooms, scoring and subscriptions](12-data-rooms-scoring-and-subscriptions.md).
- **Scoring that does not expire.** A scoring stays valid while it matches the
  current engine version and the company has an active Data Room; the scoring
  starts from the company's Data Room.
- Wallet: reward and payment balances, card top-ups with bonuses, reward-to-payment
  transfers with a 3% bonus, monthly reward crediting on the 1st, and daily
  balance reconciliation against the reward ledger.
- **Payouts through operator-reviewed requests.** Self-service withdrawal has
  been removed: payout requests go through the support pipeline (minimum $50,
  USDT BEP-20, one request per calendar month, $150 within 30 days without KYC) with transaction-hash
  notifications.
- Support tickets to the operator.
- Reporting through the Report page and the operator.
- 2FA (TOTP, with accrual bonus).
- Device alerts for unrecognized logins.
- API (v1) for personal tooling, on your signed-in session.
- **Data Room functions as a silent flag.** Automatic activation when the room
  owner uploads the first document to a room of their own, lifelong, no badge —
  unlocking top-ups and scoring purchases, with the locked-wallet hint for
  everyone else.
- **KYC deduplication and revocation handling.** A duplicate identity is
  declined at verification. A revoked verification blocks new grants, new Data
  Rooms and payouts, while existing rooms and grants stay live.
- **Account lifecycle.** The inactivity warning, sleeping and deactivation
  stages, and deletion only on the member's own request.
- **Silent Data Room referral engine.** Last-click attribution across Data Room
  links, invitation links and ambassador links, the ambassador-ladder
  economics, and founder-facing link metrics in the cabinet.
- **Contact-check quarantine and covers.** Quarantine ends at contract
  signing; recipients see neutral covers, senders see status, the operator
  sees everything.

---

## Rolling out

These are confirmed parts of the product model that are being switched on in
stages. Some members may already see them; not everyone does yet. They are
described throughout this wiki with a _rolling out_ marker.

- **Payout SLA clocks.** The 1-business-day response / 20-business-day payout
  targets as enforced queue metrics.
- **2FA enforcement for all members.**
- **Contact-check extensions.** Broader language matching in the detector
  (transliteration, mixed scripts, slang, obfuscations).
- **Layered document watermarking** (visible + forensic) in Data Rooms.
- **Referral tree and reward history** in the cabinet (the tree itself is
  live; history views are being expanded).
- **Recovery window** after a penalty or reworked vouch, by tier.
- **Sanctions tied to the person** rather than the account.

---

## What is planned

The following are in active development or design and are **not** yet live.
They are described here so members know what is coming, but they should not be
relied on today.

- **Following a Data Room and public ambassador codes.** Ambassadors would be
  able to follow published Data Rooms (cabinet feed, weekly digest), and share
  them under a public AMB-XXXX code. See
  [Silent Data Room referrals](11-silent-dr-referral.md#planned-following-a-data-room-and-ambassador-codes).
- **Silent Data Room referral analytics.** The engine is live (see
  [Silent Data Room referrals](11-silent-dr-referral.md)); deeper analytics
  and reporting continue to expand.
- **Self-service Data Room to Primary Market listing.** A flow where a member
  creates a data room from the cabinet, the project is scored automatically,
  and it is listed as a primary-market draft that enters operator eligibility
  review. Investors would then view the public room, express interest, and
  request access.
- **API expansion.** The current API covers a small set of read and wallet
  actions. Broader surface area is under consideration, with
  re-authentication and operator review applied to any mutating action.
- **Reputation economy tuning.** As the network grows, accrual events, reward
  rates, and recovery windows may be adjusted. Changes follow operator policy
  and are versioned (the current catalog is `tier-catalog-2026-07-v1`).
- **Changes from the next product specification edition.** The internal product
  specification is being revised and its current edition is awaiting final
  acceptance. Where it changes limits, prices or rules described in this wiki,
  this wiki will be updated after the edition is accepted.

Anything in this section is directional, not committed. Do not make decisions
that depend on these features being available by a specific date.

---

## What is out of scope

These are things GBlock explicitly does not do and does not plan to do. They
are listed to remove ambiguity.

- **On-platform transactional settlement.** GBlock arranges introductions; it
  does not move money or assets.
- **Custody.** GBlock does not hold assets, funds, or securities.
- **Investment advice.** GBlock does not advise on the merits of any
  opportunity. Members do their own diligence.
- **Public marketplace.** Market surfaces such as the dealflow, blocks and deal
  threads are for Residents, who are admitted by sponsorship. There is no plan
  for an open public marketplace.
- **Crypto or token products.** A _block_ is a private package of assets or an
  opportunity, nothing more.
- **Guaranteed returns.** No promise of profit, ever. Any communication
  claiming otherwise is not from GBlock.

---

## Stage-aware reading of this wiki

Because GBlock is in a pre-market stage, treat this wiki as a description of
the member experience at the current stage, not a fixed product contract. When
a feature is described as live, it reflects the current behavior. When a
feature is described as planned, it reflects the direction of travel.

The authoritative product specification is internal to TECH HY. This wiki is the
public-facing companion, not the internal system of record.

---

## Where to go next

- **Start from the top:** [What is GBlock](01-what-is-gblock.md)
- **Who can do what, today:** [User roles and statuses](02-user-roles-and-statuses.md)
- **The definitions behind every term above:** [Glossary](08-glossary.md)
- **Balances and payouts:** [Payouts and rewards](10-payouts-and-rewards.md)
- **Data Rooms, scoring and subscriptions:** [Data Rooms, scoring and subscriptions](12-data-rooms-scoring-and-subscriptions.md)
