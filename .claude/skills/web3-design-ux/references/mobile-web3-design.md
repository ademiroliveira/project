# Mobile Web3 Design

Patterns for mobile-optimized Web3 experiences.

## Mobile Challenges

- Smaller screen space
- Wallet app switching required
- Touch-based interaction
- Limited connectivity
- One-handed use

## Wallet Integration

### WalletConnect

```
Connect Wallet (Mobile)

[QR Code for desktop]

Or tap to connect mobile wallet:
[Open in Trust Wallet]
[Open in MetaMask]
[Open in Rainbow]
[More Wallets]
```

### In-App Browsers

Automatically connected when user opens dApp in wallet browser.

### Deep Linking

```
wc:a281567bb3e4...

[Automatically opens wallet app]
→ User approves
→ Returns to dApp
```

## Mobile-First Layouts

### Bottom Sheet Actions

```
[Main content area]

[Bottom sheet slides up from bottom]
Swap USDC for ETH
[Large Confirm Button]

Thumb-reach zone for primary actions
```

### Large Touch Targets

Minimum 44x44pt for tap targets
Spacing between interactive elements

### One-Handed Mode

Key actions in lower third of screen
Navigation at bottom
Avoid top-only controls

## Simplified Flows

Less information density
Progressive disclosure more important
Smart defaults reduce decisions

## Mobile Gas UX

```
Transaction Fee: $12

[Confirm] or [⚙️]

Tap gear for speed options
Default = one-tap confirmation
```

## Notifications

```
Push Notifications:
✓ Transaction confirmed
✓ Price alerts hit
✓ Gas dropped to target
✓ Governance vote ending
```

## Offline Handling

```
📡 No Connection

You can still:
• View your balance (last synced)
• Browse available pools
• Prepare transactions

Cannot:
• Execute transactions
• See live prices

[Retry Connection]
```

## Best Practices

1. Bottom-sheet primary actions
2. Large, thumb-friendly buttons
3. Simplified information hierarchy
4. WalletConnect + deep links
5. Push notifications
6. Offline mode support
7. Reduce typing (paste, QR scan)
8. Fast load times
9. Persistent important info
10. Test on various screen sizes
