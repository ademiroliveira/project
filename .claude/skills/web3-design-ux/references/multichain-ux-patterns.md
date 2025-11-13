# Multi-Chain UX Patterns

Design patterns for applications operating across multiple blockchain networks.

## Core Challenges

- Users confused which network they're on
- Assets fragmented across chains
- Different gas costs and speeds per chain
- Complex bridging between networks
- Inconsistent wallet support

## Network Display

### Persistent Network Indicator

```
Header: [🟣 Ethereum ▾]

Always visible
Color-coded by network
Clickable to switch
```

### Network Switcher

```
Switch Network

Your balances:
● Ethereum    5.2 ETH ($9,620)
○ Polygon     1,245 MATIC ($1,120)
○ Arbitrum    0.8 ETH ($1,480)
○ Optimism    2.1 ETH ($3,885)

[Select Network]
```

## Unified Balance View

```
Total Portfolio: $16,105

By Network:
Ethereum  $9,620 [→]
Polygon   $1,120 [→]
Arbitrum  $1,480 [→]
Optimism  $3,885 [→]

[Aggregate View] [Per-Chain View]
```

## Network Recommendation

```
Best Network for This Action

✓ Polygon (Recommended)
  Gas: $0.02
  Time: 10 seconds
  Best for: Small transactions

Ethereum
  Gas: $12.50
  Time: 2 minutes
  Best for: Large amounts, maximum security

[Use Polygon] [Compare All]
```

## Cross-Chain Actions

### Asset Location

```
You want to swap USDC on Arbitrum
Your USDC is on: Ethereum

Options:
1. Switch to Ethereum (use your USDC there)
   Gas: $12, Time: 2 min

2. Bridge to Arbitrum first
   Bridge cost: $15, Time: 10 min
   Then swap: $0.20, Time: 30 sec

Recommended: Option 1 (faster & cheaper)

[Switch to Ethereum] [Bridge First]
```

## Chain-Specific Properties

Display key differences:

| Network | Gas | Speed | Security |
|---------|-----|-------|----------|
| Ethereum | $10-50 | 2 min | Highest |
| Polygon | $0.01-0.05 | 10 sec | High |
| Arbitrum | $0.10-0.50 | 30 sec | High |
| Optimism | $0.10-0.50 | 30 sec | High |

## Testnet Handling

```
🧪 You're on Goerli Testnet

This is practice mode with fake ETH

[Switch to Mainnet] [Stay on Testnet]
```

## Best Practices

1. Always show active network prominently
2. Color-code networks consistently
3. Aggregate balances across chains
4. Recommend optimal network for action
5. Handle asset location intelligently
6. Enable one-click network switching
7. Show network-specific costs upfront
8. Warn about testnet usage
9. Support all major L2s
10. Maintain state during network switch
