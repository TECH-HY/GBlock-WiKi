# 10. Payouts and rewards

Your account has two balances, and this page explains how money-shaped value
moves through them: how rewards reach you, how you can move value between
balances, and how a withdrawal actually works.

The short version: **there is no self-service withdrawal.** Every payout is a
reviewed request to the operator. This is deliberate — it is part of the same
reviewed-by-design model that governs access and introductions.

---

## The two balances

| Balance | What it holds | What it is for |
|---|---|---|
| **Reward balance** | Referral rewards and other reputation-linked rewards | Accumulation and withdrawal via payout request |
| **Payment balance** | Funds you top up by card | Platform purchases, such as project scoring and Data Room subscriptions |

Balances are **not interchangeable in both directions**:

- **Reward → payment** is self-service. Moving rewards into your payment
  balance **adds a 3% bonus**: you receive the amount you move plus 3% of it.
  Without verified KYC, no more than $150 of rewards can be moved within 30
  days.
- **Payment → reward** is not self-service. If you need to move value the
  other way, it goes through an operator-reviewed request.

---

## How rewards reach you

Rewards are earned through the referral economy — your tier's direct rate
(10-25% by Reputation Tier), multi-level overrides (6% / 3% / 1%), and pool
distributions. See [Reputation economy](05-reputation-economy.md).

Three scheduling facts to calibrate expectations:

- A reward becomes releasable **30 days after the revenue** it comes from. If
  the payment is refunded inside that window, the reward is cancelled; after the
  window, a refund is recovered from you as a debt against future rewards.
- Approved rewards are released to your reward balance by the operator after
  the hold. Releases are **manual at launch** and are not tied to a fixed
  calendar date.
- Reward balances are **reconciled daily** against the reward ledger: the sum
  of balances can never exceed accrued-minus-withdrawn rewards. A
  discrepancy halts payouts and alerts the operator — this protects the
  integrity of everyone's balances.

There is no condition like "rewards unlock after your first deal": rewards
accumulate on the reward balance as they are approved. Rewards come from
scoring purchases, Data Room subscriptions and voucher purchases — not from fees
on deals between members. Reward accrual stops while your account is sleeping
(see [Trust and safety](07-trust-and-safety.md#inactivity-deletion-and-your-data)).

---

## Requesting a payout

**Step 1. Check your eligibility.**

- Your reward balance must be at least the **$50 minimum**. Below that, the
  payout request is not available.
- Without verified KYC, payouts are limited to **$150 within any 30 days**,
  counted together for the same payout address and any linked accounts. A
  request above that needs KYC.
- With verified KYC, a request can be up to **$1,500**. Because only one request
  is allowed per calendar month, this is also your monthly limit _(rolling
  out)_.
- One payout request is allowed per calendar month; a rejected request does
  not count.
- The first payout to a new address is held for 72 hours _(rolling out)_.
- If your KYC was revoked, or your account carries a sanction, you cannot open a
  payout request until the situation is resolved.

**Step 2. Submit the request.**

From the wallet, submit a payout request with:

- the amount (at least $50, within your cap),
- a destination address in **USDT (BEP-20)**.

Double-check the destination address. Crypto transfers cannot be recalled.

**Step 3. Operator review.**

Your request enters the operator's payout queue:

- **First response within 1 business day.**
- **Approved payouts are sent within 20 business days.**

"Business day" means a working day, not a clock-hour or calendar-day count —
a request filed late on Friday gets its first response on the next working
day.

**Step 4. Completion and the transaction hash.**

When the payout is sent, you receive a notification containing the
**transaction hash (tx-hash)** — the on-chain identifier you can use to verify
the transfer yourself.

---

## If a request is rejected

A rejected request does not touch your balance: the funds stay where they
were, and you can see the reason. Common reasons include a payout address that
does not match the required network (USDT BEP-20), a flagged referral chain
under review, or an account restriction. You can fix the issue and request
again.

---

## Topping up the payment balance

You top up the payment balance by card. A single top-up is at least $10 and at
most $10,000 _(the maximum is rolling out)_.

**Top-up bonus _(rolling out)_.** A top-up of **$500 or more** gives you **three
bonus scoring vouchers**. They are valid for 3 months, work for scoring only
and cannot be transferred or withdrawn. They replace the cash bonus tiers of
earlier versions (+5% above $150 and +10% from $500), which are being retired.
An automatic top-up keeps its 1% bonus. Until the change goes live, the app may
still credit the earlier cash bonus tiers.

---

## Refunds of topped-up funds

Payment-balance funds are not refunded to your card after you have completed
your first scoring purchase. Before that point, the standard refund window
applies, the card amount is returned and the matching share of the top-up bonus
is taken back with it. After it, remaining payment-balance funds can only leave
through an operator-reviewed request.

_Rolling out:_ a refund of topped-up funds, of any amount, keeps 15% of the
refunded amount and deducts the price of each bonus voucher you have already
used. Unused bonus vouchers are cancelled.

**Bonus funds cannot be withdrawn.** The top-up bonus (the cash bonus today,
bonus vouchers when they replace it) and the 3% bonus on a reward transfer can
only be spent on platform services. They cannot be paid out, refunded to a card
or moved back to the reward balance.

---

## What GBlock is and is not here

The payout rails exist so members can receive their earned rewards. To be
explicit about the boundaries:

- Payouts move **GBlock's own reward obligations** to members. They are not a
  settlement service for deals between members, and they never move deal
  funds. See [What GBlock is not](01-what-is-gblock.md#what-gblock-is-not).
- A payout notification with a tx-hash is the only "payment confirmation"
  GBlock sends. Any message claiming a payout needs a fee, a deposit, or your
  seed phrase is **not** from GBlock.

---

## Where to go next

- **How rewards are earned:** [Reputation economy](05-reputation-economy.md)
- **The payout request journey:** [User journeys - Request a payout](04-user-journeys.md#request-a-payout)
- **The wallet page:** [Platform tour - Wallet](06-platform-tour.md#wallet)
- **Accounts, verification, and restrictions:** [Trust and safety](07-trust-and-safety.md)
