# Cash Prize Bonus — Oritech

How **Cash Prize** works on the Oritech platform: config, player flow, instance fields, and expected payout.

> Create path in backoffice: **Bonuses → Create New Bonus → Cash Prize Bonus**

---

## What it is

Cash Prize is a **wager-to-release** reward.

- The prize stays **pending** until wagering is complete.
- The player bets with **their own real money** (not a locked bonus wallet).
- When the wager requirement is met, the prize is paid into **real balance**.

**Cost profile:** operator pays only on completion.  
**Best for:** retention, reloads, milestones (not first-deposit acquisition).

### Cash Prize vs Bonus Money vs Free Spins

| | Cash Prize | Bonus Money | Free Spins |
|---|---|---|---|
| Play funds | Player’s **real cash** | **Bonus balance** | Free rounds |
| Prize timing | Pending → release after wager | Match locked upfront | Spins granted |
| Payout | Credit **prize amount** to real balance | Unlock / convert bonus (with caps) | Wins → cash or bonus (per config) |
| Operator risk | Low (pay only if completed) | Higher (match credited early) | Bounded per spin |

---

## End-to-end flow

```text
1. Trigger fires (e.g. qualifying deposit)
2. System creates player_bonus instance
3. Sets init_amount  = prize (fixed or % of deposit)
4. Sets wager_amount = init_amount × wagering_coefficient
5. Player places qualifying bets with real money
6. wagered_amount increases until ≥ wager_amount
7. is_wagered = true
8. Transfer: wallet += prize (init_amount, or per-split share)
9. is_transfered = true, is_active = false
```

### Example (10% · 1× · split 1 · KRW)

| Step | Value |
|---|---|
| Deposit | ₩10,000 |
| Prize (`init_amount`) | ₩10,000 × 10% = **₩1,000** |
| Wager required (`wager_amount`) | ₩1,000 × 1 = **₩1,000** |
| On complete, wallet credit | **+₩1,000** |

Player may wager more than ₩1,000; that must **not** increase the payout.

---

## Backoffice configuration

### General

| Field | Role |
|---|---|
| **Type** | Cash Prize |
| **Name / Description** | Player-facing labels |
| **Status** | Active / inactive |
| **Trigger** | e.g. Deposit |
| **Deposit Order** | Any / First / Second / … |
| **Recurrence** | Once / Daily / Weekly / Monthly / None |

### Configuration

| Field | Role |
|---|---|
| **Bonus Expiry** | How long the player has to finish after claim |
| **Campaign Expiry** | How long the offer stays available |
| **Wagering** | Coefficient (e.g. `1×`) applied to the **prize amount** |
| **Max Claim** | Cap multiplier on claimable prize (`0` = no max / disabled per product rules) |
| **Amount Type** | Fixed amount or **Percent (%)** of deposit |
| **Win with Wagering** | Whether wins during the wager period affect routing / eligibility (product-specific) |
| **Split Count** | Number of release stages for the prize |

### Per-currency (`currency_config`)

Each currency used in production must be configured before launch.

| Field | Role |
|---|---|
| **Amount** | Prize value, or **percent** if Amount Type = % |
| **Min Deposit** | Minimum deposit to qualify |
| **Min Bet / Max Bet** | Bet size limits that count toward wagering |
| **Max Amount** | Ceiling on prize size |

#### KRW example (from live “cash prize test”)

| Amount | Max Bet | Min Bet | Max Amount | Min Deposit |
|---|---|---|---|---|
| 10 (%) | 0 | 1000 | 500000 | 10000 |

→ Deposit ₩10,000 qualifies; prize = **₩1,000**.

### Delivery channels

Cash Prize can be delivered via:

- Deposit trigger  
- CRM segment  
- Promo code  
- Bonus Wheel  
- Leaderboard prize  

(Not via Marketplace — Marketplace is Bonus Money packs only.)

---

## Player bonus instance fields

Important fields on the claimed instance (backoffice Entity Details / Bonuses tab):

| Field | Meaning |
|---|---|
| `bonus_id` | Template ID |
| `init_amount` | Prize that should be paid |
| `wager_amount` | Total wagering required |
| `wagered_amount` | Qualifying wager counted so far |
| `amount` | Current / residual value on the record |
| `split_number` | Configured release stages |
| `split_wagered` | Split stages with wager progress |
| `split_claimed` | Split stages already claimed / paid |
| `is_wagered` | Wager requirement met |
| `is_transfered` | Prize credited to wallet |
| `is_active` | Still active for the player |
| `take_on` | e.g. `deposit` |
| `min_bet` / `max_bet` | Copied from currency config |
| `currency` / `wallet_id` | Wallet used for credit |

### Correct completion state (`split_number = 1`)

```text
init_amount      = 1000
wager_amount     = 1000
wagered_amount   ≥ 1000
split_number     = 1
split_claimed    = 1          // must not exceed split_number
split_wagered    ≤ 1
is_wagered       = true
is_transfered    = true
wallet credit    = init_amount   // 1000
```

---

## Wagering rules (Cash Prize)

1. **Base for wagering is the prize**, not the full deposit.  
   `wager_amount = init_amount × coefficient`
2. Only **qualifying bets** count (min/max bet, included/excluded games & providers).
3. Player uses **real balance** the whole time.
4. Extra wager beyond `wager_amount` does **not** increase the prize.
5. With **Split Count = N**, the prize is released in up to **N** stages; total paid across stages must still equal `init_amount` (unless product docs say otherwise).

---

## Expected vs incorrect payout

| Situation | Expected credit | Incorrect |
|---|---|---|
| 10% of ₩10,000, 1×, split 1 | **₩1,000** | Crediting `wagered_amount` |
| Same, player wagered ₩4,000 | Still **₩1,000** | Crediting `init_amount × split_claimed` when splits inflated |

### Known failure pattern (investigate / regression)

If `split_number = 1` but `split_claimed` / `split_wagered` rise with wager chunks (e.g. per `min_bet`), payout can become:

```text
credit = init_amount × split_claimed   // e.g. 1000 × 4 = 4000  ❌
```

instead of:

```text
credit = init_amount                   // 1000  ✅
```

**Regression check:** deposit ₩10,000 · 10% Cash Prize · 1× · split 1 · wager ≥ ₩4,000 → wallet must receive **+₩1,000** only; `split_claimed` must be **1**.

---

## Quick operator checklist

- [ ] Currency row filled for every live currency  
- [ ] Min deposit matches offer (e.g. KRW 10,000)  
- [ ] Amount Type + Amount = intended prize (fixed or %)  
- [ ] Wagering coefficient understood as **× prize**, not × deposit  
- [ ] Split Count intentional (`1` = single release)  
- [ ] Game include/exclude set if needed  
- [ ] After a test claim: confirm wallet credit equals **`init_amount`**, not wagered total  

---

## References

- Oritech Bonus Strategy: [go.oritech.space/bonus-system](https://go.oritech.space/bonus-system/)  
- Related investigation: player `testkn2` `#1423`, bonus template `#13`, instance `#81` (overpay when `split_claimed` inflated)
