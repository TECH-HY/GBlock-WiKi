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
| **Payment balance** | Funds you top up by card | Platform purchases, such as project scoring |

Balances are **not interchangeable in both directions**:

- **Reward → payment** is self-service. Moving rewards into your payment
  balance costs a **3% fee**.
- **Payment → reward** is not self-service. If you need to move value the
  other way, it goes through an operator-reviewed request.

---

## How rewards reach you

Rewards are earned through the referral economy — your tier's direct rate
(10-25% by Reputation Tier), multi-level overrides (6% / 3% / 1%), and pool
distributions. See [Reputation economy](05-reputation-economy.md).

Two scheduling facts to calibrate expectations:

- Rewards are credited to your reward balance in a **monthly batch on the
  1st of the month**. Activity during a month is paid out in the following
  batch.
- Reward balances are **reconciled daily** against the reward ledger: the sum
  of balances can never exceed accrued-minus-withdrawn rewards. A
  discrepancy halts payouts and alerts the operator — this protects the
  integrity of everyone's balances.

There is no condition like "rewards unlock after your first deal": rewards
accumulate on the reward balance as they are approved.

---

## Requesting a payout

**Step 1. Check your eligibility.**

- Your reward balance must be at least the **$50 minimum**. Below that, the
  payout request is not available.
- Without verified KYC, a single request is capped at **$150**. With KYC,
  there is no cap on a request.

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

## Refunds of topped-up funds

Payment-balance funds are not refunded to your card after you have completed
your first scoring purchase. Before that point, the standard refund window
applies. After it, remaining payment-balance funds can only leave through an
operator-reviewed request.

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
