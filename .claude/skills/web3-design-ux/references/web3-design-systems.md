# Web3 Design Systems

Resources and patterns for Web3 design systems and component libraries.

## Leading Web3 Design Systems

### Ethereum.org Design System
- Open source
- Figma community files
- Comprehensive components
- Accessibility-focused

### Rainbow Design System
- Mobile-first approach
- iOS/Android patterns
- Wallet-specific components
- Modern, colorful aesthetic

### Uniswap Design System
- DeFi-focused
- Clean, minimal
- Trading interface patterns
- Dark mode native

### Aave Design System
- Finance-oriented
- Trust-building elements
- Data visualization
- Professional aesthetic

## Core Components

### Wallet Connection Button
```
States:
- Not connected: [Connect Wallet]
- Connecting: [Connecting... ⏳]
- Connected: [0x742d...8f3a ▾]
- Wrong network: [⚠️ Switch Network]

Variants:
- Primary (prominent)
- Secondary (subtle)
- Compact (mobile)
```

### Network Selector
```
[🟣 Ethereum ▾]

Dropdown shows:
- Network name
- Balance
- Network icon/color
- Switch action
```

### Token Input
```
[Amount input] [MAX]
[Token selector ▾]

Balance: 1,000 USDC
≈ $1,000 USD
```

### Transaction Button
```
States:
- Enabled: [Swap]
- Disabled: [Enter amount]
- Loading: [Swapping... ⏳]
- Success: [✓ Swap complete]
- Error: [❌ Swap failed]
```

### Gas Fee Display
```
Gas: $12.50
[⚙️ Settings]

Tiers: Slow | Normal | Fast
```

### Status Indicator
```
⏳ Pending
✓ Confirmed
❌ Failed
⚠️ Warning
```

## Design Tokens

### Colors

**Network Colors:**
- Ethereum: #627EEA (purple)
- Polygon: #8247E5 (purple)
- Arbitrum: #28A0F0 (blue)
- Optimism: #FF0420 (red)

**Status Colors:**
- Success: #10B981 (green)
- Warning: #F59E0B (yellow)
- Error: #EF4444 (red)
- Info: #3B82F6 (blue)
- Pending: #6B7280 (gray)

### Typography

**Font Families:**
- Interface: Inter, SF Pro, system-ui
- Mono: JetBrains Mono, Courier
- Numbers: Tabular nums for alignment

**Scale:**
- xs: 12px (labels)
- sm: 14px (body)
- base: 16px (default)
- lg: 18px (emphasis)
- xl: 20px (headings)
- 2xl: 24px (large headings)

### Spacing

8px base unit
- xs: 4px
- sm: 8px
- md: 16px
- lg: 24px
- xl: 32px
- 2xl: 48px

## Component Patterns

### Card Component
```
<Card>
  <CardHeader>
    <Title>Pool</Title>
    <Badge>Active</Badge>
  </CardHeader>
  <CardBody>
    <Stat label="APY" value="42.5%" />
    <Stat label="TVL" value="$125M" />
  </CardBody>
  <CardFooter>
    <Button>Add Liquidity</Button>
  </CardFooter>
</Card>
```

### Modal Pattern
```
<Modal>
  <ModalHeader>
    <Title>Swap</Title>
    <CloseButton />
  </ModalHeader>
  <ModalBody>
    [Content]
  </ModalBody>
  <ModalFooter>
    <Button variant="secondary">Cancel</Button>
    <Button variant="primary">Confirm</Button>
  </ModalFooter>
</Modal>
```

## Accessibility Standards

- WCAG 2.1 AA minimum
- Color contrast 4.5:1 text
- Keyboard navigation
- Screen reader support
- Focus indicators
- Skip links
- ARIA labels

## Resources

**Figma Files:**
- ethereum.org/assets
- rainbow.me/design
- uniswap.org/design

**Component Libraries:**
- wagmi.sh (React hooks)
- web3-react (React)
- web3modal (Multi-framework)
- RainbowKit (React)

**Icon Sets:**
- Cryptocurrency Icons
- Network Logos
- Web3 Icons
- Social Icons

## Best Practices

1. Use established design systems
2. Maintain consistency across platforms
3. Accessibility from the start
4. Mobile-responsive components
5. Dark mode support
6. Network color coding
7. Status icon standards
8. Component documentation
9. Design tokens for scalability
10. Community contribution friendly
