# DEX Design Best Practices

Best practices for designing decentralized exchange (DEX) interfaces.

## Core DEX UX Principles

### 1. Price Transparency

Always show complete pricing information upfront:
- Current exchange rate
- Price impact of trade size
- Slippage tolerance
- All fees (protocol + gas)
- Expected vs minimum output

```
Swap Preview

500 USDC → 0.27 ETH

Rate: 1 ETH = 1,851 USDC
Price impact: 0.12% (excellent)
Min. received: 0.268 ETH (with 1% slippage)

Fees:
• Protocol: 0.3% ($1.50)
• Gas: $12.50
Total cost: $514

[Confirm Swap]
```

### 2. Slippage Management

**Default to reasonable slippage**: 0.5-1% for most trades
**Auto-adjust for volatility**: Higher for volatile pairs
**Warn on high slippage**: Alert when >3%

```
⚠️ High Slippage (5.2%)

This trade will significantly move the price.

Your 500 USDC trade in a pool with $10K liquidity

Consider:
• Splitting into smaller trades
• Using a different pool
• Waiting for more liquidity

[Proceed Anyway] [Split Trade]
```

### 3. Route Optimization

Show best route and explain routing:

```
Best Route Found

500 USDC → 0.272 ETH (best price)

Route: USDC → WETH → ETH
Via: Uniswap V3 (0.3% pool)

Alternative routes:
• Direct USDC/ETH: 0.269 ETH ❌
• Via DAI: 0.270 ETH ❌

Automatically using best route
```

### 4. Liquidity Depth Visualization

Help users understand market depth:

```
Liquidity Analysis

Pool: ETH/USDC
Total Liquidity: $125M

Your trade: $500 (0.0004% of pool)
Impact: Minimal ✓

Large trade warning threshold: $50K+
```

## Trading Features

### Limit Orders

```
Limit Order

Buy ETH when price reaches: [$1,800]
Current price: $1,851

Amount: 500 USDC
Will receive: ~0.277 ETH

Expires: [24 hours ▾]

[Place Order] [Market Order Instead]
```

### Token Selection

Searchable with safety indicators:

```
Select Token

[Search token name or paste address]

Popular:
✓ ETH - Ethereum
✓ USDC - USD Coin (verified)
✓ DAI - Dai Stablecoin (verified)

Your Tokens (3)
Custom Tokens (1)
⚠️ Unverified Tokens (show?)

[Import Custom Token]
```

### Price Alerts

```
Set Price Alert

Notify when ETH reaches: [$1,750]
Current: $1,851

Alert via:
☑ Browser notification
☑ Email
☐ SMS

[Create Alert]
```

## Liquidity Provision

### Add Liquidity Interface

```
Add Liquidity

Pool: ETH/USDC (0.3% fee)

Deposit amounts (balanced automatically):
ETH:  [0.5] ($925)
USDC: [925]

Pool share: 0.08%
Current APY: 24.5%

Estimated earnings:
• Trading fees: 18% APY
• Rewards: 6.5% APY

⚠️ Impermanent Loss Risk

[Preview] [Add Liquidity]
```

### Impermanent Loss Calculator

```
Impermanent Loss Calculator

If ETH price changes by:
-50%: -5.7% IL
-25%: -1.5% IL
  0%:  0% IL ← Current
+25%: -1.5% IL
+50%: -5.7% IL

Note: Trading fees may offset IL
Historical IL for this pool: -2.1% (offset by +18% fees)

[Learn More]
```

### Position Management

```
Your Liquidity Position

Pool: ETH/USDC
Value: $1,850 (↑ +$124 / +7%)

Breakdown:
• Initial: $1,000
• IL: -$42 (-4.2%)
• Fees earned: +$166 (+16.6%)

Net gain: +$124 (+12.4%)

[Add More] [Remove] [Claim Fees]
```

## Safety Features

### Token Verification

```
⚠️ Unverified Token

TOKEN ($TOKEN)
Contract: 0x1234...5678

Red flags:
❌ Not verified on Etherscan
❌ Created 2 days ago
❌ No liquidity history
⚠️ Possible scam token

[Cancel] [I Understand Risk]
```

### Honeypot Detection

```
🚨 Honeypot Detected

This token cannot be sold!

Contract analysis:
• Buy: Allowed ✓
• Sell: Blocked ❌
• High tax: 99% ⚠️

DO NOT TRADE THIS TOKEN

[Report] [Go Back]
```

### MEV Protection

```
MEV Protection

☑ Enable Flashbots RPC

Protection from:
• Front-running
• Sandwich attacks
• Transaction copying

Trade-off: ~10 sec slower

Recommended for trades >$10K

[Enable] [Learn More]
```

## Best Practices

1. **Show total cost** - Amount + all fees + gas
2. **Visualize price impact** - Use color coding
3. **Default safe settings** - Reasonable slippage
4. **Warn about risks** - High slippage, unverified tokens
5. **Explain routing** - Why this path was chosen
6. **Auto-refresh prices** - Keep rates current
7. **Enable limit orders** - For patient traders
8. **Calculate IL** - Help LP providers understand risk
9. **Verify tokens** - Protect against scams
10. **Offer MEV protection** - For large trades

## Mobile DEX Patterns

- Large swap button (thumb-friendly)
- Simplified settings by default
- Quick token favorites
- One-tap amount presets (25%, 50%, 75%, 100%)
- Swipe to confirm large trades

## Anti-Patterns

❌ Hidden fees revealed at confirmation
❌ No slippage control
❌ Can't see price impact
❌ No token verification
❌ Auto-executing expired prices
❌ No MEV protection option
❌ Unclear LP position value
