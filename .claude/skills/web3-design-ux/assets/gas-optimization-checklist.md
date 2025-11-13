# Gas Optimization Checklist

Checklist for reviewing and optimizing gas costs in your dApp UX.

## Display Optimization [ /5]

- [ ] Gas shown in fiat currency (not gwei)
- [ ] Gas displayed at decision points (not just confirmation)
- [ ] Current gas price indicator (low/normal/high)
- [ ] Historical context provided (is this high?)
- [ ] Total operation cost shown (gas + fees)

## User Control [ /8]

- [ ] Three-tier gas selection (slow/normal/fast)
- [ ] Custom gas for advanced users
- [ ] Time estimates for each tier
- [ ] Default to reasonable tier (normal)
- [ ] Gas price auto-refresh
- [ ] Ability to update gas mid-flight
- [ ] Transaction scheduling for lower gas
- [ ] Gas price alerts available

## Transaction Optimization [ /10]

- [ ] Batch similar operations
- [ ] Combine approvals with actions (Permit)
- [ ] Avoid unnecessary approvals
- [ ] Minimize transaction count
- [ ] Optimize contract calls
- [ ] Use efficient data encoding
- [ ] Remove redundant operations
- [ ] Gas estimation before execution
- [ ] Simulate transactions to catch failures
- [ ] Suggest gas-efficient alternatives

## Layer 2 Integration [ /5]

- [ ] Support major L2s (Polygon, Arbitrum, Optimism)
- [ ] Recommend L2 when Ethereum gas is high
- [ ] Show L2 cost comparison
- [ ] Easy network switching
- [ ] Bridge integration (if needed)

## Multi-Transaction Flows [ /6]

- [ ] Show total gas for full flow upfront
- [ ] Offer batched vs separate options
- [ ] Explain gas savings from batching
- [ ] Allow partial execution
- [ ] Smart retry logic (don't redo successful steps)
- [ ] Persist state between transactions

## Failed Transaction Handling [ /4]

- [ ] Explain why gas was charged on failure
- [ ] Suggest fixes for common failures
- [ ] Offer gas refund/credit when possible
- [ ] Don't charge twice for retries (reuse approval)

## Timing Strategies [ /5]

- [ ] Show gas price trends (24h chart)
- [ ] Recommend optimal times (weekends cheaper)
- [ ] Queue transactions for low gas
- [ ] Alert when gas drops to target
- [ ] Explain gas price patterns

## Education [ /4]

- [ ] Explain what gas is
- [ ] Show where gas money goes
- [ ] Educate about gas optimization
- [ ] Provide gas-saving tips

## Stuck Transaction Recovery [ /4]

- [ ] Detect stuck transactions
- [ ] Offer speed-up option
- [ ] Offer cancel option
- [ ] Show success probability for each

## Advanced Features [ /3]

- [ ] MEV protection toggle
- [ ] Flashbots RPC integration
- [ ] Gas token support (if available)

---

**Total Score: [ ] / 54**

## Priority Improvements

**High Priority** (biggest impact):
1. [Improvement]
2. [Improvement]
3. [Improvement]

**Medium Priority**:
1. [Improvement]
2. [Improvement]

**Low Priority** (nice-to-have):
1. [Improvement]
2. [Improvement]

## Gas Savings Potential

Current average gas per operation: $[X]

With optimizations:
- Batching: Save $[Y] per multi-step flow
- Permit: Save $[Z] per approval
- L2: Save [%] by suggesting L2 when high gas

**Estimated annual savings for users**: $[Total]

## Implementation Plan

**Phase 1** (Essential - 2 weeks):
- [ ] Fiat gas display
- [ ] Three-tier selection
- [ ] Batch operations

**Phase 2** (Important - 4 weeks):
- [ ] L2 support
- [ ] Gas alerts
- [ ] Transaction scheduling

**Phase 3** (Advanced - 6 weeks):
- [ ] Permit integration
- [ ] MEV protection
- [ ] Advanced analytics

## Testing

- [ ] Test gas estimates accuracy
- [ ] Verify batching works correctly
- [ ] Test stuck transaction recovery
- [ ] Validate L2 recommendations
- [ ] Check gas alert triggers

## Notes

[Additional observations or specific optimizations for your dApp]
