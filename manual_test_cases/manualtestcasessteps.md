# Manual Test Cases — ASDFBET Client Bugs

Step-by-step manual testing guide for client-reported issues. Open this doc, pick a test case, follow the steps, mark pass/fail, then automate later.

**Source:** `manual_test_cases/ASDFBET - ASDFBET Issues (barb's view) 2026-07-21_15-20.json`

---

## How to use

1. Find the test case by section or bug ID
2. Check **Status** — prioritize **Ready to Retest** and **New**
3. Complete **Precondition** steps first
4. Follow the numbered steps in order
5. Compare result against **Expected**
6. Check off each step as you go
7. When finished, check **Manual test complete**
8. After writing automation, check **Automation written**
9. Record: Pass / Fail / Blocked + notes

### Status key

| Status | Action |
|--------|--------|
| Ready to Retest | Run now |
| New | Run now |
| In Progress | Run when fix is deployed |
| Under Review | Run to confirm expected behavior with team |
| Needs Info | Gather extra data while testing |
| Added to Roadmap | Skip — not fixed yet |
| Completed | Skip — already closed |

---

## Progress tracker

| ID | Test case | Manual | Automation |
|---|-----------|--------|------------|
| BUG-01 | Agent Pay Message Template Not Sent | [ ] | [ ] |
| BUG-02 | Deposit Completion Notification Missing | [ ] | [ ] |
| BUG-04 | Balance Update Delay After Deposit | [ ] | [ ] |
| BUG-07 | Deposit Request from Deposit Money Screen Fails | [ ] | [ ] |
| BUG-14 | View Instructions Shows Duplicated Page | [ ] | [ ] |
| BUG-37 | Deposit Requests Cannot Be Cancelled | [ ] | [ ] |
| BUG-49 | Incorrect Korean Translation on Deposit Page | [ ] | [ ] |
| BUG-29 | KRW Transactions Displayed as USD Without Conversion | [ ] | [ ] |
| BUG-03 | Notification Sound Missing | [ ] | [ ] |
| BUG-17 | Deposit Bonus Notification Shows Incorrect Amount | [ ] | [ ] |
| BUG-45 | Notification Messages Only in English | [ ] | [ ] |
| BUG-53 | Notification Badge Missing on Mobile | [ ] | [ ] |
| BUG-05 | First Deposit Bonus — Full Amount Registered as Bonus | [ ] | [ ] |
| BUG-06 | Balance History Wrong After Bonus Application | [ ] | [ ] |
| BUG-16 | Cannot Add Games When Editing Bonus | [ ] | [ ] |
| BUG-19 | Wagering Progress Does Not Update After Spins | [ ] | [ ] |
| BUG-18 | Bonus Cancellation Restores Original Deposit | [ ] | [ ] |
| BUG-41 | Incorrect Balance After Cancelling Bonus Mid-Play | [ ] | [ ] |
| BUG-40 | Cash Prize Calculated From First Bet Not Deposit | [ ] | [ ] |
| BUG-32 | Category/Games Visible in Bonus Details | [ ] | [ ] |
| BUG-33 | View Bonus Details from Player Bonuses in Backoffice | [ ] | [ ] |
| BUG-34 | Bonus Expired Status Column and Tag | [ ] | [ ] |
| BUG-20 | Main Wallet and Pragmatic Game Balance Not Synced | [ ] | [ ] |
| BUG-21 | Blackjack Losses Reversed / Wagering Not Counted | [ ] | [ ] |
| BUG-22 | Roulette INSUFFICIENT BALANCE Error | [ ] | [ ] |
| BUG-35 | No Games After Selecting Provider in Slots | [ ] | [ ] |
| BUG-38 | Game Language Does Not Match Platform Language | [ ] | [ ] |
| BUG-48 | Real-Time Game Provider Balance in USD for KRW Account | [ ] | [ ] |
| BUG-39 | Transactions Page Infinite Loading After Withdrawal | [ ] | [ ] |
| BUG-51 | Completed Withdrawal Shown as Pending | [ ] | [ ] |
| BUG-52 | Bank Account Number Shown in Withdrawal View Instructions | [ ] | [ ] |
| BUG-10 | Sports Betting Login Loop | [ ] | [ ] |
| BUG-15 | New Admin Account Cannot Log In | [ ] | [ ] |
| BUG-43 | Player Session Does Not Expire | [ ] | [ ] |
| BUG-44 | Password Reset Email Field Shows @ and Rejects Email | [ ] | [ ] |
| BUG-47 | Login ID Remains After Closing Popup | [ ] | [ ] |
| BUG-12 | Duplicate Language Options (Kanuri / 한국어) | [ ] | [ ] |
| BUG-46 | Promotion Popup Only Shows in English | [ ] | [ ] |
| BUG-26 | Published Promotions Not on User Page | [ ] | [ ] |
| BUG-27 | Published Blog Posts Not on User Page | [ ] | [ ] |
| BUG-13 | Blog Banner Flag Removed (Legacy) | [ ] | [ ] |
| BUG-08 | Total Deposits Not Displayed in All Players | [ ] | [ ] |
| BUG-11 | Currency Display — USD Only in Backend | [ ] | [ ] |
| BUG-36 | Incorrect Currency Labels on Player Wallet | [ ] | [ ] |
| BUG-28 | Deposit and Bonus Balance Incorrect in Player KPI | [ ] | [ ] |
| BUG-23 | Decimal Cashback/Rakeback Rates Cannot Be Saved | [ ] | [ ] |
| BUG-24 | Player Logs Not Sorted Chronologically | [ ] | [ ] |
| BUG-42 | Bonus Bet Amounts Not Displayed in Player Logs | [ ] | [ ] |
| BUG-50 | Usernames Overlap in Sportsbook Backoffice | [ ] | [ ] |
| MTC-01 | Bonus Balance After Losing Money in Game | [ ] | [ ] |

---

## Payments & Deposits

<details>
<summary><strong>Agent Pay Message Template Not Sent [BUG-01]</strong></summary>

**Status:** Ready to Retest · **Component:** AgentPay / Payment Flow  
**Precondition:** Agent created in AgentPay with a saved message template assigned under Template setting.  
**Expected:** After bank account is assigned to customer, the template message is sent automatically and visible in transactions (and notifications when feature is live).

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | In AgentPay back office, confirm agent exists with a saved message template selected |
| 2 | [ ] | As player, submit a bank deposit request |
| 3 | [ ] | As cashier, claim the transaction and assign bank account details to the customer |
| 4 | [ ] | Check AgentPay transaction details for the template message |
| 5 | [ ] | On player side, check notifications for the template message |
| 6 | [ ] | Validate template content matches what was configured |

</details>

<details>
<summary><strong>Deposit Completion Notification Missing [BUG-02]</strong></summary>

**Status:** Ready to Retest · **Component:** Frontend  
**Precondition:** Player logged in. Deposit request submitted and cashier completes it.  
**Expected:** Notification appears on player side confirming deposit is complete.

**Progress**
- [+] Manual test complete
- [+] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | Log in as player |
| 2 | [ ] | Submit a bank deposit |
| 3 | [ ] | Cashier completes deposit |
| 4 | [ ] | Without refreshing, observe player UI immediately after completion |
| 5 | [ ] | Click notification icon |
| 6 | [ ] | Validate deposit completion notification appears |
| 7 | [ ] | Validate notification shows correct status (e.g. Flat Deposit Confirmed) |

</details>

<details>
<summary><strong>Balance Update Delay After Deposit [BUG-04]</strong></summary>

**Status:** Ready to Retest · **Component:** Frontend  
**Precondition:** Player logged in with known balance. Deposit about to be completed by cashier.  
**Expected:** Balance updates immediately without page refresh.

**Progress**
- [+] Manual test complete
- [+] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | Log in as player — note current balance in wallet header |
| 2 | [ ] | Submit deposit request |
| 3 | [ ] | Cashier completes deposit |
| 4 | [ ] | **Do not refresh** — watch wallet balance in header |
| 5 | [ ] | Validate balance updates within a few seconds without refresh |
| 6 | [ ] | Expand wallet details — validate Real/Bonus balances are correct |
| 7 | [ ] | If balance did not update, refresh page and note the delay |

</details>

<details>
<summary><strong>Deposit Request from Deposit Money Screen Fails [BUG-07]</strong></summary>

**Status:** Ready to Retest · **Component:** Frontend  
**Precondition:** Player logged in.  
**Expected:** Deposit works from both Wallet menu AND Deposit Money screen.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | Log in as player |
| 2 | [ ] | Navigate to **Deposit Money** screen (not via Wallet menu) |
| 3 | [ ] | Select deposit method, enter amount, bank, account number |
| 4 | [ ] | Click **Submit** |
| 5 | [ ] | Validate deposit request is submitted successfully |
| 6 | [ ] | Repeat same deposit via **Wallet → Deposit** for comparison |
| 7 | [ ] | Validate both paths produce the same result |

</details>

<details>
<summary><strong>View Instructions Shows Duplicated Page [BUG-14]</strong></summary>

**Status:** Ready to Retest · **Component:** Frontend  
**Precondition:** Player has a pending deposit in Transaction History.  
**Expected:** Clicking "View Instructions" shows deposit instructions, not a duplicate of the current page.

**Progress**
- [+] Manual test complete
- [+] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | Log in as player with a pending deposit |
| 2 | [ ] | Open **Wallet → Transactions** (or Transaction History) |
| 3 | [ ] | Find the pending deposit entry |
| 4 | [ ] | Click **View Instructions** |
| 5 | [ ] | Validate deposit instructions are displayed (bank details, amount, steps) |
| 6 | [ ] | Validate the page is NOT a duplicate of the transaction list |

</details>

<details>
<summary><strong>Deposit Requests Cannot Be Cancelled [BUG-37]</strong></summary>

**Status:** Ready to Retest · **Component:** Frontend  
**Precondition:** Player has a pending deposit (bank or crypto).  
**Expected:** Player or backoffice operator can cancel a pending deposit request.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | Log in as player — submit a deposit request (bank or crypto) |
| 2 | [ ] | Look for **Cancel** option on the pending deposit |
| 3 | [ ] | Validate player can cancel the request |
| 4 | [ ] | After cancel, validate player can submit a new deposit |
| 5 | [ ] | For crypto: validate player can reopen deposit window to see wallet address |
| 6 | [ ] | In backoffice, find the same pending deposit |
| 7 | [ ] | Validate operator can cancel from backoffice |

</details>

<details>
<summary><strong>Incorrect Korean Translation on Deposit Page [BUG-49]</strong></summary>

**Status:** New · **Component:** Frontend  
**Precondition:** Player logged in. Language set to Korean.  
**Expected:** All deposit page text is correctly translated to Korean.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | Log in as player |
| 2 | [ ] | Switch language to **한국어** |
| 3 | [ ] | Open **Wallet → Deposit** |
| 4 | [ ] | Review all labels, buttons, placeholders, error messages |
| 5 | [ ] | Validate Korean translations are correct and natural |
| 6 | [ ] | Compare against English version for mismatches |

</details>

<details>
<summary><strong>KRW Transactions Displayed as USD Without Conversion [BUG-29]</strong></summary>

**Status:** Ready to Retest · **Component:** Backend  
**Precondition:** Player with KRW wallet. At least one KRW deposit completed.  
**Expected:** KRW amounts show as KRW (or correctly converted USD), not raw number labeled USD.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | Log in as KRW player — deposit KRW 50,000 |
| 2 | [ ] | Cashier completes deposit |
| 3 | [ ] | In backoffice, open player **Transaction History** |
| 4 | [ ] | Validate amount shows KRW 50,000 (or correct USD conversion), NOT USD 50,000 |
| 5 | [ ] | Check Player KPI, wallet, and balance history for same issue |

</details>

---

## Notifications

<details>
<summary><strong>Notification Sound Missing [BUG-03]</strong></summary>

**Status:** Ready to Retest · **Component:** Frontend  
**Precondition:** Player logged in. Browser/system sound enabled.  
**Expected:** Notification sound plays when a notification arrives.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | Log in as player — ensure device volume is on |
| 2 | [ ] | Trigger a notification (e.g. complete a deposit) |
| 3 | [ ] | Validate notification appears visually |
| 4 | [ ] | Validate notification sound plays |
| 5 | [ ] | Test on desktop and mobile if possible |

</details>

<details>
<summary><strong>Deposit Bonus Notification Shows Incorrect Amount [BUG-17]</strong></summary>

**Status:** Ready to Retest · **Component:** Frontend  
**Precondition:** Player deposits with a deposit bonus selected.  
**Expected:** Notification shows the actual deposited amount, not an unknown/incorrect number.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | Log in as player |
| 2 | [ ] | Submit deposit with a bonus selected (e.g. 1,000 KRW + bonus) |
| 3 | [ ] | Cashier completes deposit |
| 4 | [ ] | Open notifications |
| 5 | [ ] | Find deposit/bonus notification |
| 6 | [ ] | Validate displayed amount matches actual deposit amount (e.g. 1,000 KRW) |

</details>

<details>
<summary><strong>Notification Messages Only in English [BUG-45]</strong></summary>

**Status:** In Progress · **Component:** Frontend  
**Precondition:** Player logged in.  
**Expected:** Notifications display in the player's selected language (Korean, Chinese, etc.).

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | Log in as player — set language to **한국어** |
| 2 | [ ] | Trigger notifications (deposit, bonus, etc.) |
| 3 | [ ] | Validate notification text is in Korean |
| 4 | [ ] | Switch to **中文** — repeat |
| 5 | [ ] | Validate notification text is in Chinese |
| 6 | [ ] | Switch to English — validate English notifications |

</details>

<details>
<summary><strong>Notification Badge Missing on Mobile [BUG-53]</strong></summary>

**Status:** New · **Component:** Frontend  
**Precondition:** Mobile device. Player logged in.  
**Expected:** Red badge appears on notification bell when unread notifications exist.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | Open player webapp on mobile |
| 2 | [ ] | Trigger a notification (e.g. deposit completion) |
| 3 | [ ] | Validate notification sound plays |
| 4 | [ ] | Validate red badge appears on bell icon |
| 5 | [ ] | Open notifications — validate badge clears or updates |

</details>

---

## Bonuses

<details>
<summary><strong>First Deposit Bonus — Full Amount Registered as Bonus [BUG-05]</strong></summary>

**Status:** Ready to Retest · **Component:** Frontend / Backend  
**Precondition:** Daily 10% First Deposit Bonus is active.  
**Expected:** Deposit KRW 100,000 + 10% bonus → Real Money: 100,000 / Bonus Money: 10,000.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | Log in as player eligible for first deposit bonus |
| 2 | [ ] | Select **Daily 10% First Deposit Bonus** on deposit |
| 3 | [ ] | Deposit KRW 100,000 |
| 4 | [ ] | Cashier completes deposit |
| 5 | [ ] | Open **Wallet** — check Real Balance and Bonus Balance |
| 6 | [ ] | Validate Real Balance = KRW 100,000 |
| 7 | [ ] | Validate Bonus Balance = KRW 10,000 (NOT 110,000 all in bonus) |

</details>

<details>
<summary><strong>Balance History Wrong After Bonus Application [BUG-06]</strong></summary>

**Status:** Ready to Retest · **Component:** Backend  
**Precondition:** Player deposited KRW 100,000 with KRW 10,000 bonus.  
**Expected:** Balance history shows correct Before/After. Second deposit adds to real balance correctly.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | Complete deposit with bonus (BUG-05 setup) |
| 2 | [ ] | In backoffice, open player **Balance History** |
| 3 | [ ] | Validate Balance Before/After are correct (NOT -100,000 / 0) |
| 4 | [ ] | Player deposits KRW 50,000 more (no bonus) |
| 5 | [ ] | Validate balance goes from 100,000 → 150,000 (real money) |
| 6 | [ ] | Validate balance history reflects correct progression |

</details>

<details>
<summary><strong>Cannot Add Games When Editing Bonus [BUG-16]</strong></summary>

**Status:** Ready to Retest · **Component:** Backend  
**Precondition:** Existing bonus with game include/exclude list.  
**Expected:** Newly added games are saved after submitting changes.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | In backoffice, open **Bonuses** → edit an existing bonus |
| 2 | [ ] | Go to **Games** section |
| 3 | [ ] | Add a new game to included or excluded list |
| 4 | [ ] | Click **Save Bonus** |
| 5 | [ ] | Re-open the same bonus for editing |
| 6 | [ ] | Validate the newly added game is still in the list |
| 7 | [ ] | Also test removing a game — validate removal persists |

</details>

<details>
<summary><strong>Wagering Progress Does Not Update After Spins [BUG-19]</strong></summary>

**Status:** Ready to Retest · **Component:** Backend  
**Precondition:** Player in bonus mode with active wagering requirement.  
**Expected:** Wagering progress bar increases after each qualifying spin/bet.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | Log in as player with active bonus and wagering requirement |
| 2 | [ ] | Note current Wagering Progress % |
| 3 | [ ] | Enter bonus mode — play several spins on an eligible slot |
| 4 | [ ] | Return to lobby — check Wagering Progress |
| 5 | [ ] | Validate progress increased |
| 6 | [ ] | Repeat for 5+ spins — validate progress continues to update |

</details>

<details>
<summary><strong>Bonus Cancellation Restores Original Deposit [BUG-18]</strong></summary>

**Status:** Under Review · **Component:** Backend  
**Precondition:** Player deposited KRW 1,000,000 + KRW 100,000 bonus. Played games — balance now KRW 900,000.  
**Expected:** Cancelling bonus returns remaining balance (900,000), not original deposit (1,000,000).

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | Set up: deposit 1,000,000 KRW with 10% bonus |
| 2 | [ ] | Play games until balance drops (e.g. to 900,000) |
| 3 | [ ] | Note Real Balance, Bonus Balance, total |
| 4 | [ ] | Cancel the bonus |
| 5 | [ ] | Validate Real Money = remaining balance (~900,000), NOT 1,000,000 |
| 6 | [ ] | Validate Bonus Balance = 0 |

</details>



<details>
<summary><strong>Cash Prize Calculated From First Bet Not Deposit [BUG-40]</strong></summary>

**Status:** Under Review · **Component:** Backend  
**Precondition:** Cash Prize bonus configured: 1x wagering, 10% reward.  
**Expected:** Wagering based on deposit amount. Prize = 10% of deposit after 1x wagering complete.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | Configure Cash Prize bonus (1x wagering, 10%) |
| 2 | [ ] | Player deposits eligible amount |
| 3 | [ ] | Player places first bet |
| 4 | [ ] | Validate wagering is NOT immediately marked complete after one bet |
| 5 | [ ] | Complete full 1x wagering on deposit amount |
| 6 | [ ] | Validate Cash Prize = 10% of deposit amount |

</details>

<details>
<summary><strong>Category/Games Visible in Bonus Details [BUG-32]</strong></summary>

**Status:** Ready to Retest · **Component:** Frontend  
**Precondition:** Bonus with included/excluded games configured.  
**Expected:** Player can see which categories/games apply in bonus details.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | In backoffice, configure bonus with specific game include/exclude rules |
| 2 | [ ] | On player side, open bonus details (marketplace or bonus page) |
| 3 | [ ] | Validate included/excluded categories and games are displayed |
| 4 | [ ] | Validate list matches backoffice configuration |

</details>

<details>
<summary><strong>View Bonus Details from Player Bonuses in Backoffice [BUG-33]</strong></summary>

**Status:** Ready to Retest · **Component:** Backend  
**Precondition:** Player has active/expired bonuses.  
**Expected:** Backoffice player bonuses page shows full bonus details.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | In backoffice, go to **Players** → select player with bonuses |
| 2 | [ ] | Open **Bonuses** tab |
| 3 | [ ] | Click to view bonus details |
| 4 | [ ] | Validate bonus name, type, wagering, status, expiry are shown |
| 5 | [ ] | Validate game restrictions are visible |

</details>

<details>
<summary><strong>Bonus Expired Status Column and Tag [BUG-34]</strong></summary>

**Status:** Ready to Retest · **Component:** Backend  
**Precondition:** Player with at least one expired bonus.  
**Expected:** Expired bonuses have clear column/tag indicating expiry.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | In backoffice, go to player **Bonuses** tab |
| 2 | [ ] | Find an expired bonus |
| 3 | [ ] | Validate there is a dedicated column or tag showing **Expired** |
| 4 | [ ] | Validate it is visually distinct from active bonuses |

</details>

---

## Casino & Gaming



<details>
<summary><strong>Main Wallet and Pragmatic Game Balance Not Synced [BUG-20]</strong></summary>

**Status:** Ready to Retest · **Component:** Backend  
**Precondition:** Player with bonus balance. Pragmatic game available.  
**Expected:** In-game balance matches platform wallet balance.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | Log in as player — note wallet balance (e.g. bonus ₩45.27) |
| 2 | [ ] | Launch a Pragmatic slot game |
| 3 | [ ] | Compare in-game balance (bottom of game screen) with platform wallet |
| 4 | [ ] | Validate amounts match |
| 5 | [ ] | Refresh page, return to lobby — validate balances still match |

</details>

<details>
<summary><strong>Blackjack Losses Reversed / Wagering Not Counted [BUG-21]</strong></summary>

**Status:** Ready to Retest · **Component:** Backend  
**Precondition:** Player in bonus mode with wagering requirement. Blackjack included in bonus games.  
**Expected:** Losses are permanent. Wagering progress increases after blackjack bets.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | Enter bonus mode with active wagering |
| 2 | [ ] | Note balance and wagering progress |
| 3 | [ ] | Play Blackjack — intentionally lose several hands |
| 4 | [ ] | Return to lobby |
| 5 | [ ] | Validate lost money is NOT returned to balance |
| 6 | [ ] | Validate wagering progress increased |

</details>

<details>
<summary><strong>Roulette INSUFFICIENT BALANCE Error [BUG-22]</strong></summary>

**Status:** Needs Info · **Component:** Backend  
**Precondition:** Player with sufficient balance. Roulette included in bonus (if testing bonus play).  
**Expected:** Bet is placed successfully without error.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | Log in as player with sufficient real or bonus balance |
| 2 | [ ] | Launch Roulette (note exact game name) |
| 3 | [ ] | Attempt to place a bet from real balance |
| 4 | [ ] | Validate bet succeeds — no "INSUFFICIENT BALANCE" error |
| 5 | [ ] | If in bonus mode, repeat from bonus balance on eligible roulette |
| 6 | [ ] | Document game name, balance type, and bonus inclusion if issue reproduces |

</details>

<details>
<summary><strong>No Games After Selecting Provider in Slots [BUG-35]</strong></summary>

**Status:** Ready to Retest · **Component:** Frontend  
**Precondition:** Player logged in. Multiple providers configured.  
**Expected:** Selecting a provider in a matching category shows games. Mismatched category+provider shows empty (by design).

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | Go to **Slot Games → View All** |
| 2 | [ ] | Select a slot provider that provides slot games |
| 3 | [ ] | Validate games are displayed |
| 4 | [ ] | Select **Instant Games** category → choose a table games provider |
| 5 | [ ] | Validate no games shown (expected — provider mismatch) |
| 6 | [ ] | Document which provider+category combos work vs empty |

</details>

<details>
<summary><strong>Game Language Does Not Match Platform Language [BUG-38]</strong></summary>

**Status:** Ready to Retest · **Component:** Frontend  
**Precondition:** Player language set to Korean. Game provider supports Korean.  
**Expected:** Game opens in Korean when platform is set to Korean.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | Set platform language to **한국어** |
| 2 | [ ] | Launch a game from a provider known to support Korean |
| 3 | [ ] | Validate in-game UI language is Korean |
| 4 | [ ] | Repeat with **中文** |
| 5 | [ ] | Validate in-game UI language is Chinese |
| 6 | [ ] | Document any games that default to English despite platform language |

</details>

<details>
<summary><strong>Real-Time Game Provider Balance in USD for KRW Account [BUG-48]</strong></summary>

**Status:** New · **Component:** Backend  
**Precondition:** KRW player account (e.g. henry@asdfop.com).  
**Expected:** Provider balance shows in KRW (or correct currency), visible without extra clicks.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | Log in to backoffice |
| 2 | [ ] | Open KRW player profile |
| 3 | [ ] | Find **Real-Time Game Provider Balance** section |
| 4 | [ ] | Validate balance is visible on load (not hidden until click) |
| 5 | [ ] | Validate amount is displayed in KRW, not USD |

</details>

---

## Withdrawals & Transactions

<details>
<summary><strong>Transactions Page Infinite Loading After Withdrawal [BUG-39]</strong></summary>

**Status:** Ready to Retest · **Component:** Frontend  
**Precondition:** Test player (altest). Player logged in.  
**Expected:** Transactions page loads normally after withdrawal. No auto-logout.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | Log in as test player **altest** |
| 2 | [ ] | Submit a withdrawal request |
| 3 | [ ] | Open **Wallet → Transactions** |
| 4 | [ ] | Validate page loads within reasonable time |
| 5 | [ ] | Validate transaction list displays |
| 6 | [ ] | Validate player is NOT logged out |

</details>

<details>
<summary><strong>Completed Withdrawal Shown as Pending [BUG-51]</strong></summary>

**Status:** New · **Component:** Frontend  
**Precondition:** Player has a completed withdrawal.  
**Expected:** Transaction History status matches actual status everywhere.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | Log in as player with a completed withdrawal |
| 2 | [ ] | Open **Transaction History** |
| 3 | [ ] | Find the withdrawal entry — note status shown in list |
| 4 | [ ] | Click **View Instructions** for the same withdrawal |
| 5 | [ ] | Validate status in list matches View Instructions (both should show **Completed**) |
| 6 | [ ] | Validate status is NOT "Pending" if withdrawal is completed |

</details>

<details>
<summary><strong>Bank Account Number Shown in Withdrawal View Instructions [BUG-52]</strong></summary>

**Status:** New · **Component:** Frontend  
**Precondition:** Player has a withdrawal in progress.  
**Expected:** Bank account number is NOT displayed in withdrawal View Instructions.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | Log in as player — submit withdrawal request |
| 2 | [ ] | Open **Transaction History** |
| 3 | [ ] | Click **View Instructions** on the pending withdrawal |
| 4 | [ ] | Validate bank account number is NOT visible |
| 5 | [ ] | Validate only necessary withdrawal info is shown |

</details>

---

## Authentication & Session

<details>
<summary><strong>Sports Betting Login Loop [BUG-10]</strong></summary>

**Status:** Ready to Retest · **Component:** Frontend  
**Precondition:** Player already logged in on main platform.  
**Expected:** Sports page loads without asking to log in again.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | Log in as player on main casino site |
| 2 | [ ] | Navigate to **Sports** section |
| 3 | [ ] | Validate sports page loads with player session |
| 4 | [ ] | Validate no repeated login prompts |
| 5 | [ ] | Attempt to place a bet — validate session persists |

</details>

<details>
<summary><strong>New Admin Account Cannot Log In [BUG-15]</strong></summary>

**Status:** In Progress · **Component:** Backend  
**Precondition:** New admin account created in backoffice.  
**Expected:** New admin can log in with registered email and password.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | In backoffice, create a new admin account with email and password |
| 2 | [ ] | Log out |
| 3 | [ ] | Attempt to log in with the new admin credentials |
| 4 | [ ] | Validate login succeeds |
| 5 | [ ] | Validate admin has expected permissions |

</details>

<details>
<summary><strong>Player Session Does Not Expire [BUG-43]</strong></summary>

**Status:** In Progress · **Component:** Backend  
**Precondition:** Player logged in more than 24 hours ago (or session timeout configured).  
**Expected:** Session expires and player must log in again.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | Log in as test player |
| 2 | [ ] | Leave session idle beyond configured timeout (24h+) |
| 3 | [ ] | Attempt to navigate or perform an action |
| 4 | [ ] | Validate player is logged out and redirected to login |
| 5 | [ ] | Validate fresh login is required |

</details>

<details>
<summary><strong>Password Reset Email Field Shows @ and Rejects Email [BUG-44]</strong></summary>

**Status:** In Progress · **Component:** Frontend  
**Precondition:** Registered player email exists.  
**Expected:** Email field is empty/normal. Registered email accepted for reset.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | Go to login page → click **Forgot Password** |
| 2 | [ ] | Validate email field is empty (no pre-filled "@") |
| 3 | [ ] | Enter a registered email address |
| 4 | [ ] | Submit password reset request |
| 5 | [ ] | Validate no error popup appears |
| 6 | [ ] | Validate reset confirmation modal/email is sent |

</details>

<details>
<summary><strong>Login ID Remains After Closing Popup [BUG-47]</strong></summary>

**Status:** In Progress · **Component:** Frontend  
**Precondition:** Not logged in.  
**Expected:** Login field is cleared when popup is closed and reopened.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | Open login popup |
| 2 | [ ] | Enter a username/email — do NOT log in |
| 3 | [ ] | Close the login popup |
| 4 | [ ] | Re-open login popup |
| 5 | [ ] | Validate username/email field is empty |

</details>

---

## Localization & UI

<details>
<summary><strong>Duplicate Language Options (Kanuri / 한국어) [BUG-12]</strong></summary>

**Status:** Ready to Retest · **Component:** Frontend  
**Precondition:** Player on language settings page.  
**Expected:** Single Korean option (한국어). No duplicate "Kanuri".

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | Log in as player |
| 2 | [ ] | Open language selector (header or settings) |
| 3 | [ ] | Review all language options |
| 4 | [ ] | Validate only one Korean option exists (**한국어**) |
| 5 | [ ] | Validate "Kanuri" is not listed |

</details>

<details>
<summary><strong>Promotion Popup Only Shows in English [BUG-46]</strong></summary>

**Status:** In Progress · **Component:** Frontend  
**Precondition:** Active promotion with popup configured.  
**Expected:** Promotion popup displays in all supported languages.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | Set language to **English** — validate promotion popup appears |
| 2 | [ ] | Set language to **한국어** — validate promotion popup appears |
| 3 | [ ] | Set language to **中文** — validate promotion popup appears |
| 4 | [ ] | Validate popup content is translated per language |

</details>

<details>
<summary><strong>Published Promotions Not on User Page [BUG-26]</strong></summary>

**Status:** Ready to Retest · **Component:** Frontend  
**Precondition:** Promotion created and published in backoffice.  
**Expected:** Promotion visible on player-facing promotions page.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | In backoffice, create and **publish** a promotion |
| 2 | [ ] | On player site, navigate to **Promotions** page |
| 3 | [ ] | Validate the published promotion appears |
| 4 | [ ] | Validate title, description, and CTA are correct |

</details>

<details>
<summary><strong>Published Blog Posts Not on User Page [BUG-27]</strong></summary>

**Status:** Ready to Retest · **Component:** Frontend  
**Precondition:** Blog post created and published in backoffice.  
**Expected:** Blog post visible on player-facing blog page.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | In backoffice, create and **publish** a blog post |
| 2 | [ ] | On player site, navigate to **Blog** page |
| 3 | [ ] | Validate the published post appears |
| 4 | [ ] | Open the post — validate content renders correctly |

</details>

<details>
<summary><strong>Blog Banner Flag Removed (Legacy) [BUG-13]</strong></summary>

**Status:** Ready to Retest · **Component:** Backend  
**Precondition:** Access to blog management in backoffice.  
**Expected:** "Is banner" flag is removed. Banner/promotion links set on banner itself.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | In backoffice, open blog post editor |
| 2 | [ ] | Validate **Is banner** flag is no longer present |
| 3 | [ ] | Validate redirect/promotion links are configured on the banner directly |
| 4 | [ ] | Publish blog post with banner — validate it displays correctly on player site |

</details>

---

## Back Office

<details>
<summary><strong>Total Deposits Not Displayed in All Players [BUG-08]</strong></summary>

**Status:** Ready to Retest · **Component:** Backend  
**Precondition:** Players with completed deposits exist.  
**Expected:** Total Deposits column shows correct value per player.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | In backoffice, go to **All Players** |
| 2 | [ ] | Find a player with known deposit history |
| 3 | [ ] | Validate **Total Deposits** column is populated |
| 4 | [ ] | Compare value against player's actual deposit total in transaction history |

</details>

<details>
<summary><strong>Currency Display — USD Only in Backend [BUG-11]</strong></summary>

**Status:** Ready to Retest · **Component:** Backend  
**Precondition:** Player's Wallet column activated in backoffice settings. KRW player with deposits.  
**Expected:** Amounts show both system currency (USD) and player currency (KRW).

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | In backoffice settings, activate **Player's Wallet** column |
| 2 | [ ] | Open a KRW player's profile |
| 3 | [ ] | Check wallet, transactions, KPI sections |
| 4 | [ ] | Validate KRW amounts display in KRW (alongside USD where applicable) |
| 5 | [ ] | Validate amounts are NOT all shown as USD only |

</details>

<details>
<summary><strong>Incorrect Currency Labels on Player Wallet [BUG-36]</strong></summary>

**Status:** Ready to Retest · **Component:** Backend  
**Precondition:** KRW player with balance.  
**Expected:** Unconverted amounts show player's actual currency, not USD label.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | In backoffice, open KRW player profile |
| 2 | [ ] | Review wallet balance fields |
| 3 | [ ] | Validate currency label matches player's currency (KRW) |
| 4 | [ ] | Check related fields: transactions, balance history, KPI |
| 5 | [ ] | Validate no KRW amounts are incorrectly labeled as USD |

</details>

<details>
<summary><strong>Deposit and Bonus Balance Incorrect in Player KPI [BUG-28]</strong></summary>

**Status:** Ready to Retest · **Component:** Backend  
**Precondition:** Player with known deposit and bonus amounts.  
**Expected:** KPI deposit and bonus values match actual player balances.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | Note player's actual deposit total and bonus balance (player side or transactions) |
| 2 | [ ] | In backoffice, open player **KPI** tab |
| 3 | [ ] | Compare **Deposit** amount in KPI vs actual |
| 4 | [ ] | Compare **Bonus Balance** in KPI vs actual |
| 5 | [ ] | Validate both match |

</details>

<details>
<summary><strong>Decimal Cashback/Rakeback Rates Cannot Be Saved [BUG-23]</strong></summary>

**Status:** Ready to Retest · **Component:** Backend  
**Precondition:** Access to rank settings in backoffice.  
**Expected:** Decimal values (e.g. 1.5%) save successfully in Cashback and Rakeback fields.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | In backoffice, go to **Rank Settings** |
| 2 | [ ] | Edit a rank — enter decimal cashback (e.g. 1.5%) |
| 3 | [ ] | Enter decimal rakeback (e.g. 0.5%) |
| 4 | [ ] | Click **Save** |
| 5 | [ ] | Validate no "must be an integer" error |
| 6 | [ ] | Re-open rank — validate decimal values persisted |

</details>

<details>
<summary><strong>Player Logs Not Sorted Chronologically [BUG-24]</strong></summary>

**Status:** Ready to Retest · **Component:** Backend  
**Precondition:** Player with multiple log entries across different dates/times.  
**Expected:** Logs sorted newest-first (or consistent chronological order).

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | In backoffice, open player **Logs** tab |
| 2 | [ ] | Review timestamp order of entries |
| 3 | [ ] | Validate entries are sorted chronologically |
| 4 | [ ] | Apply a date filter — validate sort remains consistent |

</details>

<details>
<summary><strong>Bonus Bet Amounts Not Displayed in Player Logs [BUG-42]</strong></summary>

**Status:** Under Review · **Component:** Backend  
**Precondition:** Player played games in bonus mode.  
**Expected:** Each bonus bet log entry shows the wager amount.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | Player enters bonus mode and places several bets |
| 2 | [ ] | In backoffice, open player **Logs** |
| 3 | [ ] | Filter or find bonus-related log entries |
| 4 | [ ] | Validate each bonus bet entry shows the **wager amount** |
| 5 | [ ] | Validate amounts are sufficient to audit wagering and cancellation |

</details>

<details>
<summary><strong>Usernames Overlap in Sportsbook Backoffice [BUG-50]</strong></summary>

**Status:** New · **Component:** Frontend  
**Precondition:** Access to Sportsbook backoffice Players page.  
**Expected:** Usernames display without overlapping.

**Progress**
- [ ] Manual test complete
- [ ] Automation written

| # | Done | Step |
|---|------|------|
| 1 | [ ] | Log in to Sportsbook backoffice |
| 2 | [ ] | Navigate to **Players** page |
| 3 | [ ] | Review username column in the player list |
| 4 | [ ] | Validate usernames do not overlap each other |
| 5 | [ ] | Test at different screen widths / zoom levels |

</details>

---

## Skipped (Roadmap / Completed)

| Bug | Title | Status | Reason |
|-----|-------|--------|--------|
| — | Crypto deposit limits | Completed | Closed — refer to NOWPayments docs |
| BUG-25 | Log export includes only current page | Added to Roadmap | Not fixed yet |
| BUG-31 | Deposit bonus order/priority in modal | Added to Roadmap | Not fixed yet |
