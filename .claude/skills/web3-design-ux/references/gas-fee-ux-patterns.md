# Gas Fee UX Patterns

Comprehensive patterns for designing gas fee experiences in Web3 applications. Gas fees are one of the biggest UX pain points—these patterns make them manageable.

## The Gas Fee Challenge

Gas fees create unique UX problems:
- **Variable costs**: Change by the minute
- **High costs**: Sometimes $50-100+ per transaction
- **Paid even on failure**: Users pay for failed transactions
- **Complex concepts**: Gwei, gas limits, base fees, priority fees
- **User frustration**: "Why am I paying to use my own money?"

Good gas UX is essential for adoption.

---

## Display Patterns

### Pattern: Fiat-First Gas Display

**Always show gas in user's currency first, crypto amount secondary.**

```
Gas fee: $12.50
(0.0067 ETH at 45 gwei)
```

**Not**:
```
Gas: 0.0067 ETH
(274,892 gas × 45 gwei)
```

---

### Pattern: Contextual Gas Display

**Show gas cost where users make decisions, not just at confirmation.**

```
Swap 500 USDC for ETH

You'll receive: ~0.27 ETH
Gas cost: $12.50

Net value: $487.50 worth of ETH
(after gas)

[Review Swap]
```

**Shows total cost of operation upfront.**

---

### Pattern: Gas Price Indicators

**Visual indicators for current gas prices.**

```
Current gas: 45 gwei

🟢 Low (< 30 gwei)
🟡 Normal (30-60 gwei) ← You are here
🟠 High (60-100 gwei)
🔴 Very High (> 100 gwei)

[Refresh]
```

---

## Selection Patterns

### Pattern: Three-Tier Gas Selection

**Offer three clearly differentiated options.**

```
Select Speed

🐢 Slow
$8 • ~10 minutes
30 gwei

🚶 Normal (Recommended)
$12 • ~3 minutes
45 gwei

🚀 Fast
$25 • ~30 seconds
90 gwei

[Select] [Custom]
```

**Benefits**:
- Clear time/cost tradeoff
- Most users choose middle option
- Advanced users can customize

---

### Pattern: Smart Gas Defaults

**Set defaults based on transaction urgency and user history.**

```
Recommended: Normal ($12)

Based on:
✓ Not time-sensitive (swap)
✓ Your usual choice (90% select Normal)
✓ Current network conditions (moderate)

[Use Recommended] [Change]
```

---

### Pattern: Gas Scheduler

**Allow users to schedule transactions for lower gas.**

```
Current gas: $18 (High)

Schedule options:

Now: $18
In 2 hours: ~$10 (estimated)
Tonight (11 PM): ~$6 (estimated)

Set alert when gas drops below: [$10]

[Schedule] [Send Now]
```

---

## Optimization Patterns

### Pattern: Gas Savings Calculator

**Show savings from optimization options.**

```
Gas Optimization

Current approach: 3 transactions
Approve + Swap + Stake
Total gas: ~$36

Optimized: 1 transaction
Approve + Swap + Stake (batched)
Total gas: ~$15

💰 Save $21 (58%)

[Use Optimized] [Keep Separate]
```

---

### Pattern: Layer 2 Recommendation

**Suggest L2s when gas is high.**

```
⚠️ High Gas Alert

Ethereum: $45 gas for this swap

Save 99% on Layer 2:
• Polygon: $0.02
• Arbitrum: $0.20
• Optimism: $0.25

Note: Requires bridging assets first

[Bridge to L2] [Continue on Ethereum]
```

---

### Pattern: Batch Operation Suggestions

**Identify batchable operations.**

```
💡 Save on Gas

You have 3 pending actions:
• Claim rewards from Pool A
• Claim rewards from Pool B
• Compound earnings

Do separately: 3 tx × $12 = $36
Do together: 1 tx = $15

[Batch All] [Do Separately]
```

---

## Timing Patterns

### Pattern: Gas Price History

**Show historical context for current prices.**

```
Current gas: 65 gwei (High)

24-hour range:
|-------|----X----|
20      45    65    90 gwei

Typical this time of day: 45 gwei
You're paying 44% more than average

[Wait for Lower Gas] [Continue Anyway]
```

---

### Pattern: Gas Price Alerts

**Notify when gas drops to target.**

```
⏰ Set Gas Alert

Notify me when gas drops below:
[30 gwei] ($8 for this transaction)

Current: 65 gwei ($18)

How to notify:
☑ Browser notification
☑ Email
☐ SMS

[Set Alert] [Cancel]
```

---

### Pattern: Weekend Discount Indicator

**Educate about gas patterns.**

```
💡 Gas Tip

Gas is typically 30-40% cheaper on weekends

Current (Friday 5 PM): $18
Typical Sunday morning: ~$11

Can this wait until weekend?

[Remind Me Sunday] [Continue Now]
```

---

## Explanation Patterns

### Pattern: Gas Fee Breakdown

**Explain where gas money goes.**

```
Gas fee: $12.50 (?)

Breakdown:
• Base fee: $9 → Burned (destroyed)
• Priority fee: $3.50 → Miners/validators

Why charged:
Gas pays network validators to process
your transaction. This keeps Ethereum
secure and decentralized.

We don't receive any gas fees.

[Learn More] [Got It]
```

---

### Pattern: Failed Transaction Explanation

**Explain why gas is charged even on failure.**

```
❌ Transaction Failed

Gas charged: $8.23

Why you were charged:
Even though your transaction failed,
validators still used computing power
to attempt it. Gas pays for that work.

Think of it like:
Paying for postage even if mail is
returned to sender—delivery was attempted.

[Retry with Fix] [Learn More]
```

---

### Pattern: Gas Limit Explanation

**Help users understand gas limits.**

```
Gas Limit: 200,000 (?)

What this means:
Maximum gas this transaction can use

Actual use will likely be less (~150,000)
You're charged only for actual use

Why set higher:
Safety buffer to prevent transaction failure

[Use Recommended] [Customize]
```

---

## Mitigation Patterns

### Pattern: Gas Refund Program

**Compensate for failed transactions.**

```
We're sorry your transaction failed

Gas paid: $8.23

Our commitment:
✓ We'll credit you $8 in platform tokens
✓ Next transaction fee: 50% off
✓ Priority support to resolve issue

[Claim Credit] [Retry Transaction]
```

---

### Pattern: Gasless Transactions

**Use meta-transactions where possible.**

```
✨ No Gas Required

This transaction is sponsored!

You pay: $0 gas
Sponsor: [Protocol] Treasury
Why: Growing user adoption

[Continue Free] [Learn More]
```

---

### Pattern: Gas Token Incentives

**Offer platform tokens to offset gas.**

```
Expensive transaction? We'll help!

Gas cost: $45
Reward: 450 $PLATFORM tokens

Estimated value: $40-50
Offsets ~90% of gas cost

[Continue] [Learn About Rewards]
```

---

## Emergency Patterns

### Pattern: Stuck Transaction Recovery

**Help users unstick transactions.**

```
Transaction Stuck (10+ minutes)

Your transaction is delayed due to
gas price increase after submission.

Options:

1. Wait longer (may still confirm)
   Cost: $0
   Risk: May fail eventually

2. Speed Up (+50% gas)
   Cost: Additional $6
   95% likely to confirm soon

3. Cancel transaction
   Cost: $3 to cancel
   Frees up your wallet

[Speed Up] [Cancel] [Keep Waiting]
```

---

### Pattern: Gas Price Spike Warning

**Alert before user submits during spike.**

```
⚠️ Unusual Gas Prices

Current gas: 350 gwei ($95 for this tx)

This is 4.5× normal prices!

What's happening:
Major NFT drop causing network congestion

Recommendation:
Wait 1-2 hours for prices to normalize

[Wait] [Set Alert] [Continue Anyway]
```

---

## Advanced Patterns

### Pattern: MEV Protection Toggle

**Offer front-running protection with gas tradeoff.**

```
MEV Protection (?)

Protect against front-running:
☑ Enable Flashbots RPC

Tradeoff:
+ Protected from sandwich attacks
- Slightly slower (~10 sec more)
- May need 5-10% higher gas

Recommended for large trades (>$10k)

[Enable] [Disable]
```

---

### Pattern: EIP-1559 Visualization

**Show base fee vs priority fee for advanced users.**

```
Advanced Gas Settings

Base Fee: 35 gwei (auto)
Cannot be changed, burned by network

Priority Fee: 2 gwei
[1] [2] [3] [5] gwei

Lower = cheaper but slower
Higher = faster but more expensive

Total: 37 gwei ($12.15)

[Confirm] [Reset to Auto]
```

---

### Pattern: Custom Gas Expert Mode

**Allow full customization for experts.**

```
⚠️ Expert Mode

Gas Limit: [200,000]
Max Fee: [50 gwei]
Priority Fee: [2 gwei]

Total max cost: $18.50
Likely cost: ~$12.30

Only change if you understand these
parameters. Incorrect settings may
cause transaction failure.

[Save Custom Settings] [Use Auto]
```

---

## Mobile-Specific Patterns

### Pattern: Simplified Mobile Gas

**Minimize decisions on mobile.**

```
Transaction Fee: $12

[Confirm] [Change Speed]

(Tap "Change Speed" for options)

Reduces cognitive load
One-tap for 80% case
Options available but not overwhelming
```

---

### Pattern: Mobile Gas Notification

**Push notification for scheduled transactions.**

```
[Phone notification]

⛽ Low Gas Alert!

Gas dropped to $8 (your target)

Your scheduled swap is ready:
500 USDC → ETH

[Execute Now] [Wait Longer]
```

---

## Best Practices Summary

1. **Always show fiat value first**
2. **Provide 3 tiers: slow/normal/fast**
3. **Set smart defaults** (normal speed)
4. **Show total operation cost** (not just gas)
5. **Explain where gas goes** (not to the dApp)
6. **Offer optimization suggestions** (batch, L2, timing)
7. **Alert on unusual prices** (4x+ normal)
8. **Help recover stuck transactions**
9. **Show historical context** (is this high or normal?)
10. **Enable gas price alerts** (notify when low)

---

## Anti-Patterns to Avoid

❌ **Showing gwei only** - Meaningless to most users
❌ **No price context** - Is 45 gwei high or low?
❌ **Hidden at confirmation** - Surprise gas costs
❌ **No optimization help** - Missing savings opportunities
❌ **Complex by default** - Exposing base/priority fees upfront
❌ **No failure explanation** - "Why was I charged?"
❌ **Ignoring L2s** - Not suggesting cheaper alternatives
❌ **Static estimates** - Not updating as network changes

---

## Implementation Checklist

Essential features:
- [ ] Fiat-first gas display
- [ ] Three-tier speed selection (slow/normal/fast)
- [ ] Time estimates for each tier
- [ ] Real-time gas price updates
- [ ] Gas price indicator (low/normal/high/very high)
- [ ] Total operation cost (including gas)
- [ ] Failed transaction gas explanation
- [ ] Gas fee breakdown ("where does it go?")

Recommended features:
- [ ] Gas price history/context
- [ ] L2 recommendations when gas is high
- [ ] Batch operation suggestions
- [ ] Gas price alerts
- [ ] Transaction scheduling
- [ ] Stuck transaction recovery
- [ ] Gas optimization calculator

Advanced features:
- [ ] Gasless transaction options
- [ ] Gas token rewards/offsets
- [ ] MEV protection toggle
- [ ] Custom gas for experts
- [ ] Weekend timing suggestions

Good gas UX can significantly improve user satisfaction and reduce support burden. Prioritize these patterns based on your users' needs and sophistication level.
