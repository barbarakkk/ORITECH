## Deposits

<details>
<summary><strong>First Deposit — Bank Transfer after Registration [ORBT-BK-01]</strong></summary>

New player completes registration with phone verification, then makes their first bank transfer deposit. Covers the full flow: sign-up → welcome modal → wallet → deposit method → submit.

| # | Step |
|---|------|
| 1 | Go to the registration page and open the sign-up form |
| 2 | Fill in ID (username), email, and password fields |
| 3 | Select country code (+995) and enter phone number |
| 4 | Click **VERIFY** to request the SMS code |
| 5 | Enter the 4-digit verification code and click **VERIFY** |
| 6 | Validate "Phone number verified" confirmation appears in green |
| 7 | Check the marketing promotions checkbox |
| 8 | Check the Terms and Conditions checkbox |
| 9 | Click **Create Account** and validate the button is enabled only after ToS is accepted |
| 10 | Validate the "Welcome to [Brand]!" modal appears confirming account creation |
| 11 | Click the **Wallet** button in the header |
| 12 | Validate the wallet panel slides open with Deposit / Withdraw / Transactions tabs |
| 13 | Click **Deposit** tab |
| 14 | Select **Bank** (Bank transfer · KRW) as the deposit method |
| 15 | Enter a valid amount (e.g. 10000 KRW) in the Amount field |
| 16 | Select sender bank from the dropdown (e.g. Bank 1) |
| 17 | Enter account number in the "Your account" field |
| 18 | Click **Submit** |
| 19 | Validate "Request submitted" confirmation message appears, stating a cashier will process the request shortly |

</details>

<details>
<summary><strong>Deposit Completion Notification [TC-02]</strong></summary>

**Component:** Frontend · **Priority:** High  
**Precondition:** Player is logged in with an active session on the webapp.  
**Expected result:** A notification appears on the player side confirming the deposit is complete.

| # | Step |
|---|------|
| 1 | Log in as a player and go to the home page |
| 2 | Click the **Wallet** button in the header |
| 3 | Expand wallet details and note the current balance (e.g. ₩12,500) |
| 4 | Click the **Deposit** tab in the wallet panel |
| 5 | Select **Bank** (Bank transfer · KRW) as the deposit method |
| 6 | Enter deposit amount (e.g. 1,000 KRW) |
| 7 | Select sender bank from the dropdown (e.g. Bank 1) |
| 8 | Enter account number in the "Your account" field |
| 9 | Click **Submit** |
| 10 | Validate "Request submitted" confirmation modal appears |
| 11 | *(Cashier completes the deposit in AgentPay — see ORBT-BK-02)* |
| 12 | On the player webapp, observe the UI immediately after deposit completion |
| 13 | Click the **notification** icon in the header |
| 14 | Validate a deposit-related notification appears (e.g. "Your transaction instructions have been received 💰") |
| 15 | Open the notification and validate it shows deposit status updates (e.g. Flat Deposit Pending → Flat Deposit Confirmed) |
| 16 | Click **Wallet** and expand balance details |
| 17 | Validate the balance reflects the deposited amount (e.g. balance increases from ₩12,500 to ₩14,500) |
| 18 | Re-open the notification panel and confirm the deposit completion notification is still visible |

</details>

<details>
<summary><strong>Deposit Process Walkthrough with No Bonus [TC-03]</strong></summary>

Precondition: Player is logged in with an active session.  
Expected: Deposit completes without claiming a deposit bonus — funds go to Real Balance, Bonus Balance is unchanged, and wagering progress stays at 0%.

| # | Step |
|---|------|
| 1 | Log in as a player and go to the casino/home page |
| 2 | Click the **Wallet** button in the header |
| 3 | Expand wallet details and note Real Balance, Bonus Balance, and Wagering Progress |
| 4 | Click the **Deposit** tab |
| 5 | Select **No bonus** (do not select any deposit bonus offer) |
| 6 | Select **Bank** (Bank transfer · KRW) as the deposit method |
| 7 | Enter deposit amount (e.g. 1,000 KRW) |
| 8 | Select sender bank from the dropdown (e.g. Bank 1) |
| 9 | Enter account number in the "Your account" field |
| 10 | Click **Submit** |
| 11 | If validation error appears (e.g. "The source account choice field is required"), fill the missing required field and submit again |
| 12 | Validate "Request submitted" / transaction instructions confirmation appears |
| 13 | *(Cashier completes the deposit in AgentPay — see ORBT-BK-02)* |
| 14 | Observe player-side notifications — validate Flat Deposit Pending then Flat Deposit Confirmed |
| 15 | Click **Wallet** and expand balance details |
| 16 | Validate **Real Balance** increased by the deposited amount (e.g. ₩0 → ₩1,000) |
| 17 | Validate **Bonus Balance** is unchanged (no bonus awarded for this deposit) |
| 18 | Validate **Wagering Progress** remains at 0% |

</details>



## Casino & Gaming

<details>
<summary><strong>Bonus Balance After Losing Money in Game [MTC-01]</strong></summary>

Precondition: Player logged in with active bonus balance and an eligible bonus to wager.  
Expected: After losing bets in bonus mode, Bonus Balance decreases correctly. Lost funds are not restored. Real Balance and wagering progress reflect gameplay accurately.

| # | Step |
|---|------|
| 1 | Log in as player with active bonus balance |
| 2 | Open **Wallet** — note Real Balance, Bonus Balance, and Wagering Progress |
| 3 | Click the **Bonus Money** badge in the header |
| 4 | Open the **Bonus Money** tab |
| 5 | Click **Play to wager** |
| 6 | Validate **Bonus Mode Active** screen appears with eligible games |
| 7 | Select a bonus game (e.g. Duck River) and wait for game to load |
| 8 | Place bets and play at least one round — intentionally lose money |
| 9 | During play, note the in-game balance updates after bets settle |
| 10 | Click **Exit Bonus Play** |
| 11 | Open **Wallet** again — expand balance details |
| 12 | Validate **Bonus Balance** decreased by the amount lost |
| 13 | Validate lost funds were **not** returned to balance |
| 14 | Validate **Real Balance** is unchanged (if playing from bonus money) |
| 15 | Validate **Wagering Progress** updated if bets counted toward wagering |
| 16 | Validate header wallet amount matches updated Bonus Balance |

</details>

<details>
<summary><strong>Bonus Balance Correct After Exiting Game Mid-Play [MTC-02]</strong></summary>

Precondition: Player logged in with active bonus balance and an eligible bonus to wager.  
Expected: Exiting bonus play mid-game (before round completes) leaves balances correct — no funds restored incorrectly, no unexpected balance changes from the incomplete session.

| # | Step |
|---|------|
| 1 | Log in as player with active bonus balance |
| 2 | Open **Wallet** — note Real Balance, Bonus Balance, and Wagering Progress |
| 3 | Click the **Bonus Money** badge in the header |
| 4 | Open the **Bonus Money** tab |
| 5 | Click **Play to wager** on an active bonus |
| 6 | Select a bonus game (e.g. Gates of Olympus Roulette) and wait for game to load |
| 7 | Optionally place a bet or observe a round in progress — do not wait for round to finish |
| 8 | If an error modal appears (e.g. Invalid bet), dismiss it and continue |
| 9 | Click **Exit Bonus Play** while still in the game (mid-round or mid-session) |
| 10 | Validate player returns to the home page |
| 11 | Open **Wallet** — expand balance details |
| 12 | Validate **Bonus Balance** reflects only completed bets (no incorrect restore from mid-exit) |
| 13 | Validate **Real Balance** is unchanged unless a completed bet affected it |
| 14 | Validate **Wagering Progress** only reflects bets that actually settled |
| 15 | Validate header wallet total matches Real + Bonus balances in dropdown (e.g. ₩19,471.69) |

</details>

<details>
<summary><strong>Balance After Cancelling Bonus Mid-Play </strong></summary>

**Component:** Backend ·  
Precondition: Player has active bonus balance (e.g. deposit KRW 50,000 + 5% bonus = ₩52,500 total). Player enters bonus mode and plays until balance decreases (client report: ~₩26,500 remaining).  
Expected: Cancelling bonus mid-play transfers the correct remaining real money to Real Balance (~₩24,000 after deducting bonus portion). Amount must match remaining balance, not original deposit.

| # | Step |
|---|------|
| 1 | Log in as player with active **KRW Bonus Balance** bonus |
| 2 | Go to **My Gifts & Bonuses** → **Bonus Money** tab |
| 3 | Validate **Active Bonus** is shown (e.g. KRW Bonus Balance) |
| 4 | Note starting balances: Real Balance, Bonus Balance, Wagering Progress (e.g. Real ₩1,000 · Bonus ₩15,471.69 · Wagering 17%) |
| 5 | Click **Play to wager** on the active bonus |
| 6 | Validate **Bonus Mode Active** screen shows Real Balance, Bonus Balance, Required Wagering |
| 7 | Select an eligible bonus game (e.g. **Survivor**) → click **Bonus Play** |
| 8 | Place bets during gameplay (e.g. ₩1.5k, ₩5k) — play until balance drops from starting amount |
| 9 | Note in-game balance and wagering progress during play |
| 10 | Click **Exit Bonus Play** mid-session (before finishing all wagering) |
| 11 | Open **Wallet** — note updated Bonus Balance and Wagering Progress (e.g. Bonus ₩18,971.69 · Wagering 20%) |
| 12 | Return to **My Gifts & Bonuses** → **Bonus Money** tab |
| 13 | Click **Cancel** on the active bonus |
| 14 | Confirm bonus cancellation in the dialog |
| 15 | Open **Wallet** — note Real Balance and Bonus Balance after cancel |
| 16 | Validate **Bonus Balance** is ₩0 (or bonus removed from active list) |
| 17 | Validate **Real Money** credited matches expected remaining amount (not original deposit, not full pre-play bonus total) |
| 18 | Compare actual Real Balance after cancel vs expected calculation — document if mismatch (client report: expected ~₩24,000, received ₩25,238.10) |

</details>



## Withdrawals & Transactions

<details>
<summary><strong>Transactions Page Infinite Loading After Withdrawal [BUG-39]</strong></summary>

**Component:** Frontend · **Status:** Ready to Retest  
**Precondition:** Test player **altest** logged in. Player has submitted a withdrawal request.  
**Expected:** Transactions page loads normally after withdrawal. No infinite loading. Player is not logged out.

| # | Step |
|---|------|
| 1 | Log in as test player **altest** |
| 2 | Submit a withdrawal request via **Wallet → Withdraw** |
| 3 | Open **Wallet** from the header or account menu |
| 4 | Click the **Transactions** tab |
| 5 | Validate transaction history loads within a reasonable time (no infinite spinner) |
| 6 | Validate transaction list displays with date/time, type, name, amount, and result |
| 7 | Validate filters are visible: **Activity Type**, **Status**, **From**, **To** |
| 8 | Validate the recent withdrawal appears in the list |
| 9 | Click **page 2** in pagination — validate second page loads |
| 10 | Click **page 1** — validate first page loads again |
| 11 | Validate player session is still active (not auto-logged out) |
| 12 | Navigate away and return to **Wallet → Transactions** — validate page still loads correctly |

</details>



## Sports Betting

<details>
<summary><strong>Sports Betting — Place Single Bet [MTC-04]</strong></summary>

Precondition: Player logged in with sufficient Real Balance to place a bet.  
Expected: Player can access Sports, select odds, place a bet, and view it in My Bets — no login loop or session loss.

| # | Step |
|---|------|
| 1 | Log in as player and go to the home page |
| 2 | Validate player is logged in (no login prompt on homepage) |
| 3 | Click **Sports** in the top navigation |
| 4 | Validate Sports page loads with events and odds (no repeated login prompt) |
| 5 | Navigate to a competition (e.g. **UEFA Champions League Qualification**) |
| 6 | Find a match (e.g. **Omonia Nicosia vs FC Kairat Almaty**) |
| 7 | Click an odds option (e.g. **Draw @ 1.92**) |
| 8 | Validate selection appears in the **My bets** bet slip on the right |
| 9 | Enter a **Stake** amount (e.g. 2) |
| 10 | Validate **Total odds** and potential return update in the bet slip |
| 11 | Click **Place bet** |
| 12 | Validate **Bet placed** confirmation appears |
| 13 | Click **OK** to dismiss confirmation |
| 14 | Validate bet slip clears (shows no odds selected) |
| 15 | Click **My bets** in the top navigation |
| 16 | Validate **My Bets** page loads with the placed bet |
| 17 | Validate bet details: match, type (**Single**), odds (e.g. 1.92), stake, and potential return |
| 18 | Validate player session remains active throughout (no auto-logout) |

</details>



## Authentication & Session

<details>
<summary><strong>Player Session Does Not Expire After More Than One Day [BUG-43]</strong></summary>

**Component:** Backend · **Status:** In Progress  
**Precondition:** Test player account available. Session timeout is configured in the platform (client report: session should expire after 24 hours).  
**Expected:** After the configured session period with no activity, the player is automatically logged out and must sign in again to access protected pages.

| # | Step |
|---|------|
| 1 | Log in as test player on the player webapp |
| 2 | Validate login succeeded — profile menu / wallet is visible in the header |
| 3 | Note the login timestamp (date and time) for reference |
| 4 | Open **Wallet** — validate balance and account details load while session is active |
| 5 | Navigate to a protected page (e.g. **My Gifts & Bonuses**, **Wallet → Transactions**, or **My bets**) |
| 6 | Validate protected content loads without login prompt |
| 7 | Leave the session **idle** — do not interact with the site beyond the configured timeout period (24h+ per client report) |
| 8 | After timeout period has passed, return to the same browser tab (or reopen the site in the same browser without clearing cookies) |
| 9 | Attempt to navigate to the **home page** |
| 10 | Validate player is **logged out** or prompted to log in again |
| 11 | Attempt to open **Wallet** |
| 12 | Validate wallet is **not** accessible without authentication (redirect to login or login modal appears) |
| 13 | Attempt to open a protected route directly (e.g. account/wallet, my-bets) |
| 14 | Validate access is blocked and login is required |
| 15 | Log in again with the same test player credentials |
| 16 | Validate fresh login succeeds and protected pages load normally |
| 17 | Document result: Pass if session expired and re-login was required · Fail if player remained logged in after 24h+ idle |

</details>



## Admin / Back Office

<details>
<summary><strong>Cashier — Review and Process Player Bank Deposit [ORBT-BK-02]</strong></summary>

Precondition: Player has submitted a bank transfer deposit request (see ORBT-BK-01). Cashier logs into the AgentPay back office, locates the pending transaction, claims it, assigns a bank agent account, confirms payment receipt, and releases funds to the player. Transaction status must progress through each stage: Pending → Claimed → Account Assigned → Payment Confirmed → Completed.

| # | Step |
|---|------|
| 1 | Log in to the AgentPay cashier back office with cashier credentials |
| 2 | Navigate to **Transactions** in the left sidebar |
| 3 | Locate the player's pending deposit transaction (status: **Open/Pending**) |
| 4 | Click **Open** on the transaction to view its details |
| 5 | Review the transaction details — verify amount, player, and payment method match the submitted request |
| 6 | Click **Claim** to take ownership of the transaction |
| 7 | Confirm the claim in the confirmation dialog — validate status changes to **Claimed** |
| 8 | Click **Approve & assign account** |
| 9 | Select the appropriate agent bank account from the dropdown (e.g. Bank 1) |
| 10 | Click **Submit** — validate status changes to **Account Assigned** |
| 11 | Wait for player to complete the bank transfer to the assigned account |
| 12 | Click **Confirm payment received** |
| 13 | Verify the deposited amount is pre-filled correctly (e.g. 10,000 KRW) |
| 14 | Add a confirmation note (e.g. "Confirmed via Telegram") |
| 15 | Click **Submit** — validate status changes to **Payment Confirmed** |
| 16 | Click **Deposit funds to player** |
| 17 | Click **Submit** in the deposit modal |
| 18 | Validate transaction status changes to **Completed** |
| 19 | Verify on the player account side that the balance reflects the deposited amount |

</details>

<details>
<summary><strong>Cashier — Reject Player Deposit Request [ORBT-BK-03]</strong></summary>

Precondition: Player has submitted a bank transfer deposit request (see ORBT-BK-01).  
Expected: Cashier rejects the deposit with a valid reason and note — transaction status changes to **Rejected** and appears in the Rejected transactions list. Player balance is not credited.

| # | Step |
|---|------|
| 1 | Log in to the AgentPay cashier back office with cashier credentials |
| 2 | Navigate to **Transactions** in the left sidebar |
| 3 | Open the **Pending** tab and locate the player's deposit transaction |
| 4 | Click **Open** on the transaction to view its details |
| 5 | Review the transaction details — verify amount, player, and payment method |
| 6 | Click **Reject** |
| 7 | In the rejection modal, select rejection reason (e.g. **Player KYC pending**) |
| 8 | Enter a note explaining the rejection (e.g. "KYC") |
| 9 | Click **Confirm** |
| 10 | Validate transaction status changes to **Rejected** |
| 11 | Navigate to the **Rejected** tab in Transactions |
| 12 | Validate the rejected deposit appears in the Rejected list |
| 13 | On the player webapp, verify the deposit was not credited — balance remains unchanged |
| 14 | Validate the player receives a notification about the rejected deposit (if applicable) |

</details>


