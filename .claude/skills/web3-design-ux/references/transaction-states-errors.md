# Transaction States & Error Handling

Comprehensive guide to designing transaction state communication and error handling in Web3 applications.

## Transaction Lifecycle

Web3 transactions go through multiple states. Users need to understand each stage.

### Standard Transaction States

```
1. Initiated → User clicks "confirm"
2. Wallet Review → User reviews in wallet
3. Signed → User approved in wallet
4. Submitted → Sent to mempool
5. Pending → Waiting for inclusion in block
6. Confirming → In block, awaiting confirmations
7. Confirmed → Finalized
8. Failed → Transaction reverted or rejected
```

---

## State Display Patterns

### Pattern: Visual State Indicators

**Use consistent icons and colors for each state.**

```
States:

⏸️  Not Started (gray)
👁️  Review in Wallet (blue)
✍️  Signed (blue)
⏳  Pending (yellow)
⏱️  Confirming (yellow)
✓  Confirmed (green)
❌  Failed (red)
```

---

### Pattern: Progressive Status Updates

**Show users exactly where transaction is in the process.**

```
Transaction Status

✓ Signed in wallet
✓ Submitted to network
⏳ Waiting for confirmation... (45 seconds)
○ Confirming (0/12 blocks)
○ Complete

Estimated time remaining: ~2 minutes

[View on Etherscan] [Cancel]
```

---

### Pattern: Block Confirmation Counter

**Show accumulating confirmations for security-critical transactions.**

```
Transaction Confirming

●●●●●○○○○○○○ 5/12 confirmations

Why wait for confirmations:
More confirmations = more secure
12 confirmations = virtually irreversible

[View Details]
```

---

## Pre-Transaction States

### Pattern: Transaction Preview

**Always show comprehensive preview before wallet popup.**

```
Review Transaction

Action: Swap USDC for ETH

Details:
You pay: 500 USDC
You receive: ≈0.27 ETH
Rate: 1 ETH = 1,851 USDC
Price impact: 0.12%
Minimum received: 0.268 ETH (1% slippage)

Network: Ethereum
Gas fee: ~$12.50

Total cost: 500 USDC + $12.50 gas

⚠️ This transaction cannot be undone

[Back] [Continue to Wallet]
```

---

### Pattern: Wallet Signature Request

**Clear communication while waiting for user action in wallet.**

```
Waiting for Confirmation

Please check your wallet to approve
this transaction

If you don't see a popup:
• Check your wallet app/extension
• Look for pending requests
• Wallet might be locked

[I Don't See It] [Cancel]
```

---

## Active Transaction States

### Pattern: Submission Confirmation

**Immediate feedback when transaction is submitted.**

```
✓ Transaction Submitted!

Transaction hash:
0x742d35Cc6634C0532925a3b844Bc9e7595f8f3a

Status: Pending
Estimated time: 2-3 minutes

[View on Etherscan] [Track Progress]
```

---

### Pattern: Real-Time Status Updates

**Live updates as transaction progresses.**

```
Swap in Progress

⏳ Processing... (1 minute elapsed)

Status: Pending in mempool
Current network gas: 48 gwei
Your gas: 45 gwei

Likely to confirm in ~2 minutes

[Refresh] [Speed Up] [Details]
```

---

### Pattern: Multi-Step Transaction Tracking

**Track progress through multi-transaction operations.**

```
Adding Liquidity

Step 1: Approve USDC ✓
Completed 2 minutes ago

Step 2: Approve ETH ✓
Completed 1 minute ago

Step 3: Deposit to Pool ⏳
Pending... (~1 minute remaining)

[View All Transactions] [Cancel Remaining]
```

---

## Success States

### Pattern: Success Confirmation

**Clear, celebratory confirmation with details.**

```
✓ Swap Complete!

Swapped: 500 USDC
Received: 0.272 ETH

Details:
Rate: 1 ETH = 1,838 USDC
Gas paid: $11.89
Time: 2 min 15 sec

Transaction: 0x742d...8f3a
[View on Etherscan]

Your new balance: 5.472 ETH

[Done] [Swap Again]
```

---

### Pattern: Updated Balance Display

**Immediately reflect new balances.**

```
Before transaction:
ETH: 5.2
USDC: 1,000

After transaction:
ETH: 5.472 (+0.272) ✨
USDC: 500 (-500)

[View Full History]
```

---

## Failure States

### Pattern: Failed Transaction Explanation

**Clear explanation of what went wrong and why.**

```
❌ Transaction Failed

Reason: Slippage tolerance exceeded

What happened:
The price moved more than your 1%
tolerance while the transaction was
being processed.

Gas charged: $8.23
(Gas is always charged, even for
failed transactions, as network work
was performed)

What to do:
• Increase slippage to 2%
• Wait for price to stabilize
• Try smaller amount

[Retry with 2% Slippage]
[Adjust Manually]
[Contact Support]
```

---

### Pattern: Common Error Messages

**User-friendly explanations for technical errors.**

```
Error Categories:

❌ Slippage Exceeded
→ "Price moved too much"

❌ Insufficient Gas
→ "Transaction ran out of gas"

❌ Insufficient Balance
→ "Not enough tokens in wallet"

❌ Reverted
→ "Smart contract rejected transaction"

❌ User Rejected
→ "Cancelled in wallet"

❌ Nonce Too Low
→ "Transaction order issue"

Each with specific recovery steps
```

---

### Pattern: Error Recovery Guidance

**Actionable steps to fix the problem.**

```
❌ Insufficient Gas

Your transaction failed because it
ran out of gas.

What this means:
The gas limit was too low for this
complex operation.

Solution:
We've increased the gas limit from
200,000 to 250,000 for you.

New estimated cost: $13.50 (was $12.00)

[Retry with Higher Gas] [Learn More]
```

---

## Stuck Transaction States

### Pattern: Stuck Transaction Detection

**Proactively detect and alert about stuck transactions.**

```
⚠️ Transaction Delayed

Your transaction has been pending
for 15 minutes (longer than expected)

Likely cause:
Gas price increased after you submitted.
Your 45 gwei is now below average (60 gwei).

Options:
1. Wait longer (may still confirm)
2. Speed up (pay +$6 more gas)
3. Cancel (pay $3 cancellation fee)

[Speed Up] [Cancel] [Wait]
```

---

### Pattern: Speed Up Transaction

**Allow users to increase gas to speed up stuck transactions.**

```
Speed Up Transaction

Current gas: 45 gwei
Network average: 65 gwei

Increase to: [65 gwei] ▲▼

Additional cost: +$5.50
Total gas: $18.00 (was $12.50)

Likelihood of confirmation:
95% within 2 minutes

[Speed Up] [Cancel]
```

---

### Pattern: Cancel Transaction

**Enable transaction cancellation (with caveats).**

```
Cancel Transaction

⚠️ Cancellation is not guaranteed

How it works:
We submit a new transaction with the
same nonce but 0 value to yourself.
If it confirms first, original is cancelled.

Cost: $3.00 gas
Success rate: ~85%

If cancellation fails:
Original transaction will still execute
and you'll pay both gas fees.

[Attempt Cancel] [Keep Waiting]
```

---

## Partial Success States

### Pattern: Partial Execution

**Handle cases where only part of transaction succeeded.**

```
⚠️ Partially Executed

Goal: Swap 500 USDC for ETH
Executed: 350 USDC for ETH

What happened:
Liquidity pool couldn't fulfill full amount
at your price limit.

Result:
✓ Swapped 350 USDC → 0.190 ETH
× Remaining 150 USDC not swapped

Gas charged: Full amount ($12.50)

Options:
• Swap remaining 150 USDC
• Keep as USDC
• Set limit order for better price

[Swap Remaining] [Keep USDC]
```

---

## Notification Patterns

### Pattern: Transaction Notifications

**Notify users of important transaction events.**

```
Browser Notification:
"✓ Swap complete! Received 0.272 ETH"

Email Notification:
"Your swap of 500 USDC for ETH has
been confirmed. View transaction →"

SMS (optional, high-value):
"$10,000 withdrawal confirmed"

In-app bell icon (3):
• Swap complete
• Reward claim ready
• New governance proposal
```

---

### Pattern: Transaction History

**Maintain searchable transaction history.**

```
Transaction History

Filters:
[All Types ▾] [All Status ▾] [Last 30 Days ▾]

Today
✓ Swap USDC → ETH        -500 USDC
  2:15 PM • $11.89 gas    +0.272 ETH

Yesterday
✓ Claim Rewards          +$127.50
  3:42 PM • $8.23 gas

✓ Add Liquidity          -1,000 USDC
  10:22 AM • $15.67 gas   -0.5 ETH

[Export CSV] [Load More]
```

---

## Time-Sensitive Patterns

### Pattern: Expiration Warnings

**Warn about time-sensitive transactions.**

```
⚠️ Transaction Expires Soon

Time remaining: 3 minutes

If not confirmed by 3:45 PM:
Transaction will fail automatically

Current status: Pending
Estimated confirmation: 2 minutes

[Speed Up] [Details]
```

---

### Pattern: Deadline Display

**Show deadline clearly for limit orders, etc.**

```
Limit Order Active

Buy ETH at $1,800 or lower

Expires: Dec 31, 2024 11:59 PM
Time remaining: 2 days 14 hours

[Modify] [Cancel] [Extend]
```

---

## Error Prevention Patterns

### Pattern: Pre-Flight Checks

**Validate before submitting transaction.**

```
Pre-Transaction Validation

Running checks...

✓ Sufficient balance
✓ Valid recipient address
✓ Reasonable gas price
✓ Network connection stable
⚠️ High price impact (3.2%)

Warning:
Price impact is higher than normal.
Consider smaller amount or adding liquidity.

[Adjust Amount] [Continue Anyway]
```

---

### Pattern: Simulation Results

**Show simulation before execution.**

```
Transaction Simulation

We simulated this transaction:

✓ Would succeed
✓ Gas usage: 147,892
✓ No errors detected

Estimated outcome:
You'd receive: 0.272 ETH
Gas cost: $12.15

Safe to proceed

[Confirm] [Cancel]
```

---

## Monitoring Patterns

### Pattern: Transaction Dashboard

**Central view of all transaction activity.**

```
Active Transactions (2)

⏳ Swap pending (45s)
   500 USDC → ETH
   [Details]

⏳ Approval pending (20s)
   Compound permission
   [Details]

Recent (5)
✓ Claim rewards (2m ago)
✓ Add liquidity (1h ago)

[View All History]
```

---

### Pattern: Persistent Status Bar

**Always-visible status indicator.**

```
[Header bar]
⏳ (2) transactions pending

Hover/click shows:
• Swap (est. 1 min)
• Approval (est. 30 sec)

[View Details]
```

---

## Best Practices Summary

**Essential Elements**:
1. **Preview before execution** - Show everything upfront
2. **Immediate submission feedback** - Confirm it was sent
3. **Real-time updates** - Don't make users refresh
4. **Clear success/failure states** - No ambiguity
5. **Explain failures simply** - "Price moved too much"
6. **Provide recovery steps** - Always offer next action
7. **Show transaction history** - Let users track everything
8. **Handle stuck transactions** - Speed up/cancel options

**Communication Principles**:
- Use plain language, not error codes
- Explain why gas was charged on failure
- Show time estimates for each state
- Provide transaction hash and explorer link
- Update in real-time, don't require refresh
- Notify for significant events
- Maintain history permanently

**Error Handling**:
- Categorize errors clearly
- Explain what happened in simple terms
- Show what user can do to fix it
- Offer automatic fixes when possible
- Link to support for complex issues

---

## Anti-Patterns to Avoid

❌ **Silent failures** - No explanation what went wrong
❌ **Technical error messages** - "Error: 0x1234"
❌ **Lost transactions** - No way to track after leaving page
❌ **No recovery guidance** - Dead end after failure
❌ **Binary states** - Only "pending" or "complete"
❌ **No stuck transaction help** - Users can't unstick
❌ **Hidden transaction hash** - Can't verify on explorer
❌ **No notification options** - Users must constantly check

Proper transaction state management and error handling are critical for Web3 UX. Users are dealing with real money and irreversible actions—they need constant, clear communication about what's happening.
