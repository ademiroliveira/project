# Smart Contract Interaction Design Guide

Guidelines for designing user experiences around smart contract interactions.

## Approval Flows

### Token Approval

**When**: Before contract can spend user's tokens

**Design Pattern**:
```
Permission Required

[Protocol] needs permission to use your USDC

Amount options:
○ Exact (500 USDC) - Recommended
  Only for this transaction
  More secure, costs gas each time

○ Unlimited (∞ USDC)
  Saves gas on future transactions
  Less secure if contract hacked

Why needed: Smart contracts can't access
your tokens without permission

[Approve Limited] [Approve Unlimited] [Cancel]
```

**Best Practices**:
- Explain why approval needed
- Default to limited approval
- Show security trade-offs
- Estimate gas savings of unlimited
- Make revocation easy

### Approval + Action (Permit)

**Better UX**: Combine approval with action using Permit/Permit2

```
One Transaction Instead of Two

Old way:
1. Approve tokens ($12 gas)
2. Wait for confirmation
3. Execute swap ($12 gas)
Total: $24 gas, 4 minutes

New way (Permit):
1. Sign approval + execute swap ($12 gas)
Total: $12 gas, 2 minutes

[Use Permit] [Traditional Approval]
```

## Multi-Step Transactions

### Sequential Operations

**Pattern**: Clear progress indicator

```
Step 2 of 3: Deposit Tokens

✓ Approve USDC (completed)
⏳ Deposit to pool (confirming...)
○ Stake LP tokens (waiting)

Estimated remaining: 2 minutes
Gas spent so far: $12
Remaining gas: ~$12

[View Details] [Cancel Remaining]
```

### Batched Operations

**Pattern**: Combine when possible

```
Add Liquidity (Optimized)

Instead of 3 separate transactions:
✓ Approve Token A
✓ Approve Token B
✓ Deposit both

We'll batch into 1 transaction:
✓ Approve + Approve + Deposit

Save: $24 gas, 4 minutes

[Use Batch] [Separate Transactions]
```

## Read vs Write Operations

### Read Operations (Free)

- Check balance
- View pool info
- Get exchange rate
- See history

**Design**: Instant, no wallet popup

### Write Operations (Cost Gas)

- Transfer tokens
- Swap
- Stake
- Vote

**Design**: Preview → Wallet confirmation → Status tracking

## Transaction Preview

```
Review Before Signing

Action: Add Liquidity to ETH/USDC

You'll deposit:
• 0.5 ETH ($925)
• 925 USDC

You'll receive:
• 21.43 LP tokens

Contract interaction:
• Call: addLiquidity()
• Contract: 0x742d...8f3a (verified ✓)
• Network: Ethereum

Costs:
• Gas: ~$15 (normal speed)
• Protocol fee: 0%

Risks:
⚠️ Impermanent loss possible
⚠️ Smart contract risk

[Back] [Sign Transaction]
```

## Contract Safety Indicators

```
Contract Information

✓ Verified on Etherscan
✓ Audited by Trail of Bits (2023)
✓ $500M TVL (high confidence)
✓ 2 years operational
✓ Open source

[View Contract] [View Audit Report]
```

```
⚠️ Unverified Contract Warning

This contract is NOT verified

Risks:
✗ Source code not public
✗ No audit available
✗ Created 3 days ago
✗ Unknown developer

DO NOT INTERACT unless you trust source

[Go Back] [View Contract] [I Accept Risk]
```

## Transaction Simulation

```
Simulating Transaction...

✓ Simulation successful
✓ No errors detected
✓ Estimated gas: 147,892
✓ Will receive: 0.272 ETH

Safe to proceed

[Confirm] [Cancel]
```

```
❌ Simulation Failed

Reason: Insufficient output amount

This transaction would fail if executed.

Suggested fixes:
• Increase slippage tolerance
• Check token balances
• Try smaller amount

[Adjust Settings] [Cancel]
```

## Gas Estimation

```
Estimated Gas Usage

Complex operation: 285,000 gas units

At current price (45 gwei):
• Total cost: $12.83
• Base fee: $9.50 (burned)
• Priority: $3.33 (to validators)

This is [normal] for this operation

[Adjust Gas] [Continue]
```

## Signature Requests

### Personal Sign

```
Signature Request

[Protocol] requests your signature

Purpose: Prove wallet ownership

Message:
"Sign in to Protocol
Nonce: 12345
Timestamp: 2024-01-15"

No gas fee • No transaction

[Cancel] [Sign]
```

### Typed Data (EIP-712)

```
Sign Order

Readable format:

Sell: 100 USDC
Buy: 0.054 ETH minimum
Expires: 2024-01-16 3:00 PM
Fee: 0.5%

This signature allows order execution

[Reject] [Sign]
```

## Best Practices

1. **Always preview before wallet**: Show everything that will happen
2. **Verify contracts**: Display verification status
3. **Simulate transactions**: Catch failures before execution
4. **Explain approvals**: Why needed, what it means
5. **Batch when possible**: Reduce transaction count
6. **Show contract info**: Build trust through transparency
7. **Clear error messages**: Technical errors → Plain English
8. **Recovery paths**: Always offer next steps
9. **Gas estimates**: Before user commits
10. **Progress tracking**: Multi-step visibility

## Anti-Patterns

❌ No transaction preview
❌ Unlimited approvals by default
❌ Unverified contract interactions without warning
❌ No simulation before execution
❌ Technical error messages only
❌ Lost context between steps
❌ No gas estimates
❌ Can't cancel multi-step flows
❌ No contract verification indicators
❌ Unclear what signature does
