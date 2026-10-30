# 10. Payouts and rewards

Your account has two balances. This page explains how rewards reach you, how
value moves between balances, and how a withdrawal will work once it opens.

In short: **USDT withdrawal opens later.** At launch your rewards accumulate in
the reward balance and can be moved into the payment balance with a 3% bonus.
When withdrawal opens, **there is no self-service withdrawal:** every payout is a
reviewed request to the operator. This is deliberate and part of the same
reviewed-by-design model that governs access and introductions.

---

## The two balances

| Balance | What it holds | What it is for |
|---|---|---|
| **Reward balance** | Referral rewards | Accumulating, then transfer to the payment balance; payout requests once withdrawal opens |
| **Payment balance** | Funds you top up by card | Platform purchases: scoring and Data Room subscriptions |

- **Reward to payment** is self-service and **adds a 3% bonus**. Without verified
  KYC you can move up to $150 of rewards within 30 days. With KYC the amount is
  not limited, but the bonus is paid only on the first $1,500 you move in any 30
  days, at most $45 _(rolling out)_.
- **Payment to reward** is not self-service; it goes through an operator-reviewed
  request.

---

## How rewards reach you

Rewards come from the referral economy: your tier's direct rate (10-25%),
overrides (6% / 3% / 1%) and the top-ambassador pool. See
[Reputation economy](05-reputation-economy.md#rewards).

- A reward becomes releasable **30 days after the revenue** it comes from. If the
  payment is refunded in that window, the reward is cancelled; after it, a
  refund is recovered against your future rewards.
- The operator releases approved rewards to your reward balance after the hold.
  Releases are manual at launch and not tied to a calendar date.
- Rewards come from scoring purchases, Data Room subscriptions and voucher
  purchases, not from fees on deals between members.
- Reward accrual stops while your account is sleeping; see
  [Trust and safety](07-trust-and-safety.md#inactivity-deletion-and-your-data).

---

## Requesting a payout

**Withdrawal opens later.** At launch the wallet shows "Withdrawal opens later"
instead of a request form, and payout requests are not accepted until it opens.
Rewards you earn are not cancelled: they stay in your reward balance and can be
moved into the payment balance. The rules below apply from the day withdrawal
opens.

**1. Check eligibility.**

- Your reward balance is at least the **$50 minimum**.
- **Without KYC:** up to **$150 within any 30 days** for the same payout address.
- **With KYC:** up to **$1,500** per request. As one request is allowed per
  calendar month, this is also your monthly limit _(rolling out)_.
- **One request per calendar month**; a rejected request does not count.
- The first payout to a new address is held for 72 hours _(rolling out)_.
- If your KYC was revoked or your account carries a sanction, you cannot open a
  request until that is resolved.

**2. Submit.** From the wallet, enter the amount and a **USDT (BEP-20)**
destination address. Check the address carefully; crypto transfers cannot be
recalled.

**3. Operator review.** First response within **1 business day**. Approved
payouts are sent within **20 business days**. A business day is a working day,
so a request filed late on Friday gets its first response on the next working
day.

**4. Completion.** You receive a notification with the **transaction hash**, the
on-chain identifier you can use to verify the transfer.

**If a request is rejected,** your balance is untouched and you see the reason,
for example an address on the wrong network, an account restriction or a referral
chain under review. Fix it and request again.

---

## Topping up the payment balance

You top up by card. A single top-up is **$10 to $100,000**.

**Top-up bonus _(rolling out)_.** A top-up of **$500 or more** gives you **three
bonus scoring vouchers**. They are valid for 90 days, work for scoring only, and
cannot be transferred or withdrawn. They replace the earlier cash bonus tiers
(+5% above $150 and +10% from $500). An automatic top-up keeps a 1% bonus and
also earns the vouchers. Until the change is live, the app may still credit the
earlier cash bonus.

**Refunds of topped-up funds.** A refund of topped-up funds, of any amount,
carries a **15% refund fee** on the refunded amount, and the price of each bonus
voucher you already used is deducted once, at the first refund of that top-up. A
refund is never below zero. No fee is charged where the law requires a full refund
or where the error is GBlock's. Unused bonus vouchers are cancelled _(rolling
out)_. An approved refund is processed within 10 business days; your bank may need
longer to show it.

**Bonus funds cannot be withdrawn.** The top-up bonus and the 3% bonus on a reward
transfer can only be spent on platform services. They cannot be paid out,
refunded to a card or moved back to the reward balance.

---

## What GBlock is and is not here

Once withdrawal is open, payouts move **GBlock's own reward obligations** to
members. They are not a settlement service for deals between members and never
move deal funds. A payout notification with a transaction hash is the only
payment confirmation GBlock sends. Any message claiming a payout needs a fee, a deposit or your seed phrase
is **not** from GBlock.

---

## Where to go next

- **How rewards are earned:** [Reputation economy](05-reputation-economy.md)
- **The payout flow in context:** [User journeys](04-user-journeys.md#request-a-payout)
- **Accounts and restrictions:** [Trust and safety](07-trust-and-safety.md)
