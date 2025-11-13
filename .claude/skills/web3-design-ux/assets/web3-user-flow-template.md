# Web3 User Flow: [Flow Name]

**dApp**: [Name]
**Flow**: [e.g., "First Swap", "Add Liquidity", "Stake Tokens"]
**User**: [Persona - e.g., "First-time DeFi user", "Experienced trader"]
**Date**: [YYYY-MM-DD]

## Flow Overview

**Goal**: [What user wants to accomplish]
**Success Criteria**: [How we know they succeeded]
**Entry Point**: [Where flow begins]

## Pre-Conditions

**User has**:
- [ ] Web3 wallet installed
- [ ] Wallet connected to dApp
- [ ] On correct network
- [ ] Sufficient balance for action
- [ ] Sufficient ETH for gas
- [ ] [Other requirements]

## Flow Steps

### Step 1: [Step Name]

**Screen**: [Screen/page name]

**User Action**: [What user does]

**System Response**: [What happens]

**UI Elements**:
- [Element 1]
- [Element 2]

**Success**: [How to know this step succeeded]
**Error Cases**: [What could go wrong]

**Screenshot/Wireframe**: [Link or embed]

---

### Step 2: [Step Name]

[Repeat structure]

---

## Transaction Details

**Transactions Required**: [Number]

**For each transaction**:
1. **Purpose**: [What it does]
2. **Gas Cost**: [Estimate]
3. **User Approval**: [What they confirm]
4. **Wait Time**: [Expected duration]

## Happy Path Example

```
User: New DeFi user wants to swap 100 USDC for ETH

1. Opens swap interface
2. Selects USDC and enters 100
3. Selects ETH as output token
4. Reviews: ~0.054 ETH, $12 gas, 1% slippage
5. Clicks "Swap"
6. Wallet popup: Reviews and confirms
7. Transaction submitted
8. Waits ~2 minutes
9. ✓ Receives 0.054 ETH
10. Views updated balance

Total time: 3 minutes
Total cost: 100 USDC + $12 gas
Result: SUCCESS ✓
```

## Error Scenarios

### Error 1: Insufficient Balance

**Trigger**: User doesn't have enough tokens

**Flow**:
1. User enters amount
2. System detects insufficient balance
3. Shows error: "Insufficient USDC balance"
4. Suggests: "You have 50 USDC, need 100"
5. Options: [Reduce amount] [Buy USDC]

**Recovery**: User adjusts amount or buys tokens

---

### Error 2: Transaction Failed

**Trigger**: Slippage exceeded

**Flow**:
1. Transaction submitted
2. Price moves >1%
3. Transaction reverts
4. Shows: "Transaction failed: Slippage exceeded"
5. Explains: "Price moved more than 1% limit"
6. Gas charged: $8.23
7. Options: [Retry with 2% slippage] [Cancel]

**Recovery**: User retries with higher slippage

---

## Mobile Considerations

**Differences on mobile**:
- [Difference 1]
- [Difference 2]

**WalletConnect flow**: [If applicable]

## Time & Cost Analysis

**Estimated Duration**:
- First-time user: [X] minutes
- Experienced user: [Y] minutes

**Costs**:
- Gas: $[X] (Ethereum) / $[Y] (L2)
- Protocol fees: [X]%
- Total: $[Total]

## Success Metrics

**Quantitative**:
- Completion rate: [Target %]
- Time to complete: [Target time]
- Error rate: [Target %]

**Qualitative**:
- User understands what happened
- User feels confident
- User would do it again

## Pain Points Identified

1. [Pain point]
   - Impact: [High/Medium/Low]
   - Fix: [Proposed solution]

2. [Pain point]
   - Impact: [High/Medium/Low]
   - Fix: [Proposed solution]

## Recommendations

1. [Recommendation]
2. [Recommendation]
3. [Recommendation]

## Related Flows

- [Related flow 1]
- [Related flow 2]

## Notes

[Additional observations, questions, or context]
