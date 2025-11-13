# Web3 Design Patterns

Common design patterns for Web3 applications including dApp interfaces, wallet integration, onboarding flows, and interaction models.

## Overview

Web3 applications share common UX challenges and solutions. This document catalogs proven design patterns that work across different dApps, enabling consistent, predictable user experiences.

---

## Wallet Connection Patterns

### Pattern: Progressive Connection

**Problem**: Users shouldn't need to connect wallet to browse and learn about the application.

**Solution**: Show full interface, enable wallet connection only when needed for transactions.

**Implementation**:
```
Landing view (no wallet):
✓ Browse available pools
✓ View current rates
✓ Read documentation
✗ Cannot interact or transact

[Connect Wallet to Get Started]

After connection:
✓ All features unlocked
✓ Show user's balances
✓ Enable transactions
```

**Benefits**:
- Lower barrier to entry
- Users can evaluate before committing
- Reduces wallet prompt fatigue

---

### Pattern: Multi-Wallet Support

**Problem**: Users use different wallets (MetaMask, WalletConnect, Coinbase Wallet, etc.)

**Solution**: Support multiple wallet options with clear discovery.

**Implementation**:
```
Connect Wallet

Popular:
[MetaMask] [Coinbase Wallet] [WalletConnect]

More options:
[Rainbow] [Trust] [Ledger] [Show All]

New to Web3? [Get a Wallet]
```

**Best Practices**:
- Show 3-4 most popular options first
- "Show all" for comprehensive list
- Link to wallet education for newcomers
- Remember user's choice for next time

---

### Pattern: Connection Persistence

**Problem**: Users annoyed by repeated connection requests.

**Solution**: Remember connection across sessions, with clear disconnect option.

**Implementation**:
```
Header (connected):
🟢 0x742d...8f3a | 5.2 ETH
[Disconnect]

Auto-reconnects on return
Clear visual indicator of connection status
Easy disconnect for security
```

---

## Transaction Flow Patterns

### Pattern: Three-Stage Transaction

**Problem**: Users need to understand what's happening during blockchain transactions.

**Solution**: Clear three-stage flow: Preview → Execute → Confirm

**Implementation**:

**Stage 1: Preview**
```
Review Swap

You pay: 500 USDC
You receive: ≈0.27 ETH

Rate: 1 ETH = 1,851 USDC
Price impact: 0.12%
Gas fee: ~$12

[Back] [Confirm]
```

**Stage 2: Execute**
```
Confirm in Wallet

Please approve this transaction in your wallet

⏳ Waiting for confirmation...
[Cancel]
```

**Stage 3: Confirm**
```
✓ Swap Complete!

Received: 0.272 ETH
Gas paid: $11.89

[View Transaction] [Done]
```

---

### Pattern: Batch Transaction Indicator

**Problem**: Multi-step operations confuse users about progress.

**Solution**: Clear step indicator showing progress through multi-transaction flows.

**Implementation**:
```
Step 2 of 3

✓ Approve USDC
⏳ Swap USDC for ETH ← You are here
⏸️ Add to liquidity pool

Estimated remaining time: 2 minutes
[Cancel Remaining Steps]
```

---

### Pattern: Failed Transaction Recovery

**Problem**: Failed transactions are frustrating and users don't know what to do.

**Solution**: Clear explanation with actionable recovery steps.

**Implementation**:
```
❌ Transaction Failed

Reason: Slippage exceeded
Gas charged: $8.23 (unavoidable)

What this means:
Price moved more than your 1% tolerance
while transaction was being processed.

Fix it:
[Retry with 2% Slippage]
[Wait for Stable Price]
[Try Smaller Amount]
[Contact Support]
```

---

## Onboarding Patterns

### Pattern: Layered Onboarding

**Problem**: New users overwhelmed by Web3 complexity.

**Solution**: Progressive education across first several interactions.

**Implementation**:

**First Visit**:
```
Welcome to [DApp]

What we do: Swap tokens and earn yield

Quick start:
1. Connect wallet
2. Choose tokens to swap
3. Confirm transaction

[Get Started] [Learn More]
```

**First Transaction**:
```
Your First Swap

You're swapping USDC for ETH

What happens:
• You approve the swap in your wallet
• Transaction processes on blockchain (~2 min)
• ETH appears in your wallet

[Continue]
```

**After 5 Transactions**:
```
Ready for more?

You've mastered swapping!

Try next:
• Provide liquidity to earn fees
• Stake tokens for rewards
• Vote in governance

[Explore Features]
```

---

### Pattern: Testnet First

**Problem**: Users nervous about using real money to learn.

**Solution**: Offer testnet mode for practice.

**Implementation**:
```
🧪 Practice Mode

You're on Goerli Testnet

• All features work normally
• Use fake ETH (no value)
• Learn without risk
• Switch to mainnet when ready

Balance: 10 test ETH
[Get More Test ETH] [Switch to Mainnet]
```

---

### Pattern: Contextual Help

**Problem**: Users need education at point of confusion, not upfront.

**Solution**: Inline help exactly when and where needed.

**Implementation**:
```
Slippage Tolerance (?)
[1%]

Hover/tap shows:
"Maximum price change you'll accept.
Higher = more likely to execute
Lower = better price protection
Most users use 0.5-1%"

[Learn More]
```

---

## Information Display Patterns

### Pattern: Fiat-First Display

**Problem**: Users think in dollars, not ETH/token amounts.

**Solution**: Show fiat value prominently, crypto amount secondary.

**Implementation**:
```
Your Balance

$8,234
5.2 ETH

Recent change: +$127 (+1.5%) today
```

---

### Pattern: Progressive Disclosure

**Problem**: Too much information overwhelms users.

**Solution**: Show essential info first, details on demand.

**Implementation**:

**Level 1 - Glance**:
```
ETH/USDC Pool
42.5% APY
```

**Level 2 - Details** (expand):
```
42.5% APY total
• Trading fees: 18.2% APY
• Token rewards: 24.3% APY

TVL: $125M
Risk: Medium
```

**Level 3 - Deep dive** (click through):
```
[Full details page with charts, history, composition, risks, etc.]
```

---

### Pattern: Real-Time Updates

**Problem**: Stale data leads to bad decisions.

**Solution**: Show data freshness and update automatically.

**Implementation**:
```
ETH Price: $1,851

Updated: 3 seconds ago ⟳

[Auto-updating every 10 seconds]
```

---

## Error Prevention Patterns

### Pattern: Address Book

**Problem**: Typos in addresses cause permanent loss.

**Solution**: Saved address book with verification.

**Implementation**:
```
Send USDC

To:
○ Alice (0x742d...8f3a) [Edit]
○ Treasury (0x891f...2c1b) [Edit]
○ New address [Enter]

First time sending to address?
[Verify on Etherscan]
```

---

### Pattern: Warning Thresholds

**Problem**: Users accidentally make mistakes with large amounts.

**Solution**: Warn when transaction exceeds typical patterns.

**Implementation**:
```
⚠️ Large Transaction

Swapping: 50 ETH ($92,500)

This is:
• 10x your typical swap size
• 95% of your total balance

Are you sure?
[Go Back] [Yes, Continue]
```

---

### Pattern: Confirmation Inputs

**Problem**: High-risk actions need extra confirmation.

**Solution**: Require typing or selecting confirmation for critical actions.

**Implementation**:
```
⚠️ Remove All Liquidity

This will withdraw your entire position
Value: $15,234

To confirm, type: REMOVE ALL
[_______________]

[Cancel] [Confirm]
```

---

## Status Communication Patterns

### Pattern: Transaction Toast

**Problem**: Users lose track of transaction status.

**Solution**: Persistent toast notification in corner.

**Implementation**:
```
┌─ Bottom right ────────┐
│ ⏳ Swapping...        │
│ Est. 2 minutes        │
│ [View] [Dismiss]      │
└───────────────────────┘

Stays visible across navigation
Updates in real-time
Dismissible but not intrusive
```

---

### Pattern: Notification Center

**Problem**: Multiple transactions or activities to track.

**Solution**: Central notification hub.

**Implementation**:
```
🔔 (3)

Notifications:
✓ Swap complete (2 min ago)
⏳ Approval pending (30 sec)
✓ Rewards claimed (1 hour ago)

[Clear All] [Settings]
```

---

### Pattern: Network Status Bar

**Problem**: Users unaware of network issues.

**Solution**: Visible status indicator.

**Implementation**:
```
⚠️ Ethereum network congestion
Gas prices: Very High (150 gwei)
Consider waiting or using L2

[More Info] [Dismiss]
```

---

## Permission Patterns

### Pattern: Explicit Approvals

**Problem**: Token approvals are confusing and risky.

**Solution**: Clear explanation with recommended limits.

**Implementation**:
```
Permission Required

[DApp] needs permission to use your USDC

Options:
○ Limited: 500 USDC (recommended)
  Only for this transaction
  More secure

○ Unlimited: ∞ USDC
  Save gas on future transactions
  Less secure

Why needed: Smart contracts can't access
your tokens without permission

[Approve] [Cancel]
```

---

### Pattern: Approval Management

**Problem**: Users forget what approvals they've granted.

**Solution**: Dashboard of active permissions.

**Implementation**:
```
Active Approvals

Uniswap
• USDC: Unlimited ⚠️ [Revoke]
• ETH: 1,000 remaining [Revoke]

Aave
• DAI: Unlimited ⚠️ [Revoke]

[Revoke All Unlimited]
```

---

## Mobile-Specific Patterns

### Pattern: Mobile Wallet Deep Links

**Problem**: Mobile Web3 requires wallet app switching.

**Solution**: Deep link to wallet app for signing.

**Implementation**:
```
[Opens in-app browser of mobile wallet]
or
[Deep links to wallet app for signature]
then
[Returns to dApp]

Seamless flow
```

---

### Pattern: Mobile-Optimized Actions

**Problem**: Limited mobile screen space.

**Solution**: Bottom sheet actions, thumb-friendly buttons.

**Implementation**:
```
[Bottom sheet slides up]

Swap USDC for ETH

[Large button: Confirm Swap]

Critical actions in thumb reach
Large touch targets
Swipe to dismiss
```

---

## Cross-Chain Patterns

### Pattern: Network Recommendations

**Problem**: Users confused which network to use.

**Solution**: Recommend optimal network for action.

**Implementation**:
```
Available on 3 networks:

✓ Polygon (Recommended)
  Gas: $0.02
  Time: 10 sec
  Reason: Best value for this amount

Ethereum
  Gas: $12
  Time: 2 min

Arbitrum
  Gas: $0.15
  Time: 15 sec

[Use Polygon] [Compare]
```

---

### Pattern: Unified Balance View

**Problem**: Assets spread across multiple chains.

**Solution**: Aggregate view with per-chain breakdown.

**Implementation**:
```
Total USDC: $5,850

By chain:
Ethereum: $3,200 [View]
Polygon: $1,800 [View]
Arbitrum: $850 [View]

[Bridge Between Chains]
```

---

## Summary

These patterns provide proven solutions to common Web3 UX challenges. Apply them consistently to create familiar, predictable experiences across different dApps and protocols.

**Next Steps**:
- Review patterns relevant to your application
- Adapt patterns to your specific context
- Test with users to validate effectiveness
- Iterate based on feedback

For implementation details and domain-specific patterns, see companion documents:
- Gas Fee UX Patterns
- Transaction States & Errors
- Web3 Authentication Flows
- Self-Custody Wallet Design
