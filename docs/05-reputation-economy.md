# 5. Reputation economy

Reputation is the backbone of GBlock. It replaces money as the thing that
unlocks access, and it is the mechanism that keeps the network honest. This
page explains how reputation is measured, how it grows, and what it unlocks.

---

## Volume: your reputation

**Volume is your long-term reputation.** It is a ledger of reputation events:

- Positive events grow it: good conduct, vouches you receive, and referral
  outcomes.
- Negative events reduce it: stakes you put up, penalties, clawbacks, and a share
  of the negative events of members you back.
- Volume determines your **Reputation Tier**, which sets your reward rate and
  how much you can back others.
- The single most important rule: **you cannot buy Volume.** It is only earned.

Earlier versions of this guide described a second unit called _Power_. It is
not part of the member experience: invitations and vouches are paid for in
reputation points directly, as described below.

### Two views of Volume

Your **Reputation** page in the cabinet shows your Volume in two views:

| View | What it is | What it drives |
|---|---|---|
| **V_capacity** | Your operational capacity: all reputation events | Your Reputation Tier, your access, and how many vouches you can give |
| **V_rate** | The part of your Volume that counts toward rewards (it excludes deal-outcome events) | Your reward rate |

Your **reward rate is locked once a week**, from a snapshot of your V_rate taken
at the start of the week. Events that arrive mid-week change your tier and
access at once, but never the rate you have already locked. The next snapshot
date is shown on the page.

Think of it this way: Volume is your track record, V_capacity is the budget that
track record lets you deploy, and V_rate is the part of it that pays.

---

## The Canonical Tier Catalog

Reputation Tier is derived from Volume. The canonical catalog
(`tier-catalog-2026-07-v1`) is:

| Tier | Volume range | Reward rate | Recovery window |
|---|---|---|---|
| **Member** | 0 - 49 | 10% | 168 hours |
| **Core** | 50 - 149 | 13% | 120 hours |
| **Principal** | 150 - 349 | 17% | 72 hours |
| **Partner** | 350 - 749 | 20% | 24 hours |
| **Vanguard** | 750+ | 25% | 12 hours |

The ladder has no ceiling: Vanguard starts at 750 Volume and 25% is the
maximum direct reward rate. The recovery window is the catalog's waiting time
after a penalty or a reworked vouch (168/120/72/24/12 hours by tier). It is
defined in the catalog and is being switched on in stages. _Rolling out._

### How to read the catalog

- **Reward rate** is the share of confirmed non-transactional TECH HY revenue
  allocated to the member when a rewardable event occurs. Higher tiers earn a
  larger share. Rewards are never paid from transaction volume, because GBlock
  does not settle transactions.
- **Free Data Room allowance.** A full Resident gets more free secondary-market
  Data Rooms at higher tiers (1 / 2 / 3 / 5 / 8 by reward-rate tier). See
  [Data Rooms, scoring and subscriptions](12-data-rooms-scoring-and-subscriptions.md).

### Verified and Member

The word _Verified_ means one thing: the **Verified Trust Tier**, reached by
passing KYC (identity assurance). The lowest **Reputation Tier** (0-49 Volume,
the start of your reputation journey) is called **Member**. It was previously
named Verified, and the app may still show the old name until it is updated.

The two axes are independent. A KYC-verified member with little activity is
Verified trust tier and Member reputation tier. A long-tenured anonymous member
could be Vanguard reputation tier while still Anonymous trust tier. Always check
the context.

---

## What backing someone costs

Three actions put your own reputation behind another person.

### Invitations

- Sending an invitation **reserves 10 reputation points** from you.
- The points return when the invitation **activates** (the recipient onboards)
  or **expires** (30 days, with no penalty).
- The person you invite starts with a welcome grant: 30 points, plus 10 on top
  when they come through an invitation (40 in total), and 1 vouch gift.
- If the invitee misbehaves, you may face a reputation impact beyond the
  reserve. This is why you should only invite people you can stand behind.

An Ambassador starts with the 30-point floor, so a new Ambassador can have 3
invitations open at once.

### Guarantees

- Accepting a guarantee request does **not** lock any reputation up front.
- While the guarantee is active, **50% of the ward's negative reputation events
  also land on you.**
- If the ward violates trust during probation, the probation is extended; three
  violations lead to revocation of the guarantee. See
  [User roles and statuses - Probation](02-user-roles-and-statuses.md#probation).

### Vouches

Vouches are the second backing instrument. They are how waitlist candidates
reach **Resident** status, and they move real reputation.

- Vouching for a member credits **+10 reputation to them** and **+5 to you**.
- Creating a vouch stakes **10 of your Volume capacity**. Net of your +5
  reward, a vouch costs you 5 net capacity — vouches are never free.
- Your vouch limit is derived from your Volume: **your Volume capacity divided
  by ten, rounded down**. There are no separate per-tier caps. When your
  capacity is low, you have fewer vouches to give.
- The first vouch of a waitlist candidate can come from **any KYC-approved
  member**; the decisive second vouch — the one that completes Resident
  status — must come from a **KYC-verified Resident**.

**If a vouch goes wrong.** A vouch can be revoked (withdrawn because the
vouched member violated trust):

- The staked Volume is **not** returned, and revoking costs a further **5
  Volume**, also never returned.
- The reputation granted to both sides is clawed back, plus an extra 1-point
  penalty for the voucher.
- Negative reputation events of the member you vouched for propagate to you at
  **50%** while your vouch is active.
- Two or more revocations in a rolling 30 days put your vouching on hold and
  queue the case for operator review.

The rules are deliberately asymmetric: vouching earns modestly, but backing
the wrong person costs you real reputation.

---

## Reward rates and the referral ladder

The reward rate from the tier catalog is the **direct** (first-level) share of
confirmed non-transactional TECH HY revenue allocated to you when a
rewardable event occurs — a scoring purchase, a Data Room subscription, a
voucher purchase, or another sale attributable to your referral. Fees on deals
between members are not part of it.

On top of the direct ladder:

- **Multi-level overrides:** 6% for second-level referrals, 3% for third-level,
  1% for fourth-level (for members with KYC).
- **Top-leaders pool:** 5% of rewardable revenue is pooled and distributed
  monthly among the top ambassadors.
- **Top-ambassador bonus:** the leading ambassador of each month receives an
  additional bonus.

Rewards are never paid from transaction volume, because GBlock does not settle
transactions. A 5% reserve is held back for refunds and compensations; this is
an internal accounting figure, not a member-facing number.

### How rewards reach you

- Rewards become releasable **30 days after the revenue** they come from. If the
  payment is refunded inside that window, the reward is cancelled; after the
  window a refund is recovered from you as a debt against future rewards.
- Reward accruals are credited to your **reward balance** in a monthly batch
  on the **1st of the month**.
- There is no self-service withdrawal: moving rewards off-platform happens
  through a reviewed **payout request** (minimum $50, USDT BEP-20; one request per
  calendar month; without KYC up to $150 within 30 days). See
  [Payouts and rewards](10-payouts-and-rewards.md).
- You can move rewards into your payment balance yourself: the transfer **adds a
  3% bonus** on top of the amount you move. Moving payment balance back into
  rewards is an operator-reviewed request.
- Balances are reconciled daily against the reward ledger; any discrepancy
  alerts the operator before anything is paid out.

---

## How Volume grows

Volume is a ledger. The exact accrual events are governed by operator policy,
but the categories are stable:

- **Vouches you receive and give**, within the rules above.
- **Well-maintained blocks.** Active, fresh, accurately described blocks
  contribute to seller reputation.
- **Referral outcomes.** When an invitee contributes positively to the network,
  the inviter's referral attribution can translate into Volume.
- **Sustained good conduct.** Long-term participation without violations is
  recognized.

Your accrual rate is multiplied by your Trust Tier and 2FA status:

| Trust Tier | Base rate | With 2FA |
|---|---|---|
| Anonymous | 1.0x | 1.1x |
| Vouched | 1.0x | 1.1x |
| Verified | 1.2x | **1.3x** |

This is why KYC matters even for reputation growth. A Verified member earns
reputation 20% faster than an Anonymous member at the same level of activity,
and 30% faster with 2FA enabled.

---

## What reputation unlocks

Reputation is not a vanity score. It translates directly into capability.

| Capability | Driver |
|---|---|
| Higher reward rate on non-transactional revenue | Reputation Tier (weekly snapshot) |
| More vouches you can give (capacity divided by ten) | Volume capacity (V_capacity) |
| More free secondary-market Data Rooms (full Residents) | Reward-rate tier |
| Shorter operator review SLA | Trust Tier (Verified at 24h, Vouched at 48h, Anonymous at 72h) |
| Higher reputation accrual rate | Trust Tier + 2FA |
| Eligibility to act as guarantor on the Vouched path | Trust Tier (Verified only) |
| Ability to place sale blocks without a guarantor | Trust Tier (Verified only) |
| Primary-market listing eligibility | Trust Tier (Verified) + KYB + project KYC |
| Higher simultaneous active block limit | Trust Tier (0 / 1 / 3) |

Notice that some capabilities are driven by **Trust Tier** (identity assurance)
and others by **Reputation Tier** (accumulated conduct). They work together.
A Verified member with Vanguard-tier Volume has the best of both: full market
access, the highest reward rate, and the shortest SLA.

---

## Common misconceptions

**"I can pay to skip tiers."**
No. Volume cannot be purchased. The only way to climb tiers is to accumulate
reputation through conduct over time.

**"Volume only ever goes up."**
No. Stakes, penalties, clawbacks and the liability for people you back all
reduce it. Sanctions follow the person, not the account, so a new account does
not wipe the slate.

**"A higher Reputation Tier lets me place blocks."**
Not by itself. Block placement is gated by **Trust Tier** (Vouched or
Verified), not Reputation Tier. A Vanguard-tier Anonymous member still cannot
place a block.

**"Rewards come from deal volume."**
No. GBlock does not settle transactions. Rewards are paid only from confirmed
non-transactional TECH HY revenue.

**"I can withdraw my rewards whenever I want."**
No. There is no self-service withdrawal. Rewards are paid out through a
reviewed payout request with a $50 minimum (and, without KYC, a limit of $150
within 30 days). See [Payouts and rewards](10-payouts-and-rewards.md).

**"Vouching is free reputation."**
No. A vouch stakes your Volume capacity, is limited by that capacity, and a
revoked vouch costs you the stake plus a penalty.

---

## Where to go next

- **How the tiers interact with access:** [User roles and statuses](02-user-roles-and-statuses.md)
- **What the cabinet shows you about your reputation:** [Platform tour - Reputation](06-platform-tour.md#reputation)
- **How rewards turn into payouts:** [Payouts and rewards](10-payouts-and-rewards.md)
- **KYC, 2FA, and the security behind all of this:** [Trust and safety](07-trust-and-safety.md)
