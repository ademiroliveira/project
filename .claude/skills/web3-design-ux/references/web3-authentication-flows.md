# Web3 Authentication Flows

Comprehensive guide to designing wallet connection and authentication experiences.

## Core Principles

1. **Progressive access** - Browse before connecting
2. **Multiple wallet support** - Don't force one wallet
3. **Clear permissions** - Explain what access is granted
4. **Persistent sessions** - Remember connections
5. **Easy disconnect** - Always provide logout

## Connection Patterns

### Initial Connection

```
Connect Wallet

Choose your wallet:

[MetaMask] Most popular
[WalletConnect] Mobile wallets
[Coinbase Wallet] Coinbase users
[Show 12 more options ▾]

Don't have a wallet?
[Get Started with Web3]

Why connect?
• Trade tokens
• Manage your portfolio
• Participate in governance
```

### First-Time User Flow

```
Step 1: Choose wallet
Step 2: Install if needed → [Install MetaMask]
Step 3: Create wallet in extension
Step 4: Return to dApp
Step 5: Approve connection
Step 6: Connected! ✓
```

### Returning User Flow

```
Welcome back!

Last connected: MetaMask
Address: 0x742d...8f3a

[Reconnect] [Use Different Wallet]
```

## Permission Patterns

### Connection Request

```
MetaMask wants to connect

[DApp Name] is requesting:
✓ View your wallet address
✓ View your token balances
✗ Cannot move your funds
✗ Cannot see private keys

[Cancel] [Connect]
```

### Signature Request

```
Sign Message

[DApp] requests your signature to:
• Prove wallet ownership
• Log you in securely

No gas fee • No transaction

Message preview:
"Sign in to [DApp]
Nonce: 12345
Timestamp: 2024-01-15"

[Cancel] [Sign]
```

### Transaction Approval

```
Confirm Transaction

Action: Swap 500 USDC for ETH

Spending: 500 USDC from your wallet
Receiving: ~0.27 ETH to your wallet
Network fee: $12.50

[Reject] [Confirm]
```

## Session Management

### Active Session Indicator

```
Header:
🟢 Connected: 0x742d...8f3a
[5.2 ETH] [Disconnect ▾]

Dropdown:
• Switch Account
• Disconnect
• View on Explorer
```

### Auto-Reconnection

```
Welcome Back!

Reconnecting to MetaMask...
✓ Connected

Your balances:
ETH: 5.2
USDC: 1,000
```

### Session Timeout

```
Session Expired

For security, your session timed out
after 7 days of inactivity.

[Reconnect Wallet]
```

## Multi-Account Support

### Account Switching

```
Switch Account

Currently: 0x742d...8f3a (5.2 ETH)

Your other accounts:
○ 0x891f...2c1b (2.1 ETH)
○ 0x123a...9d8f (0.3 ETH)

[Select] [Add Account]
```

### Multi-Signature Wallets

```
Multi-Sig Wallet Detected

Wallet: Treasury.eth
Signers: 3 of 5 required

Pending approvals:
• Withdraw $10K (2/3 signatures)
• Update settings (1/3 signatures)

[View All Pending]
```

## Mobile-Specific Patterns

### WalletConnect Flow

```
Connect Mobile Wallet

1. Open your wallet app
2. Scan this QR code
   [QR CODE IMAGE]
3. Approve connection in app

Or paste connection link:
wc:a281567bb3e4...

[Copy Link]
```

### In-App Browser

```
You're in MetaMask Browser

Connected automatically
Address: 0x742d...8f3a

[Switch Account] [Go to Website]
```

### Deep Linking

```
[Opens wallet app automatically]
↓
[User approves in wallet]
↓
[Returns to dApp]
Connected! ✓
```

## Error States

### Wallet Not Installed

```
MetaMask Not Found

You need MetaMask to use this dApp

[Install MetaMask] (recommended)
[Use Different Wallet]
[Learn About Wallets]
```

### Wrong Network

```
⚠️ Wrong Network

You're on: Ethereum Mainnet
Need: Polygon

[Switch to Polygon]
[Stay on Ethereum]

Why: This feature only available on Polygon
```

### Connection Failed

```
Connection Failed

Possible reasons:
• Wallet extension locked
• Connection rejected
• Network issue

[Try Again]
[Use Different Wallet]
[Get Help]
```

### Insufficient Permissions

```
⚠️ Additional Permission Needed

This action requires permission to:
• Spend your USDC tokens

Current permission: View only

[Grant Permission] [Cancel]
```

## Security Patterns

### Network Verification

```
✓ Secure Connection

• Official website: app.example.com
• SSL certificate valid
• Smart contracts verified

[View Security Details]
```

### Phishing Warning

```
🚨 Phishing Warning

This site (app-examp1e.com) is NOT
the official site (app.example.com)

DO NOT connect your wallet!

[Close Tab] [Report Phishing]
```

### Permission Review

```
Your Active Connections

example.com
• Connected 2 hours ago
• Can view address & balances
• Last activity: 5 minutes ago
[Disconnect]

other-dapp.com
• Connected 30 days ago
• Can spend USDC (unlimited)
• Last activity: 28 days ago
⚠️ [Review] [Disconnect]
```

## Hardware Wallet Support

### Ledger Connection

```
Connect Ledger

1. Connect Ledger to computer
2. Open Ethereum app on device
3. Confirm connection

Waiting for Ledger...

[Cancel] [Troubleshoot]
```

### Transaction Signing (Hardware)

```
Confirm on Ledger

Check your Ledger device:
• Review transaction details
• Press both buttons to confirm

⏳ Waiting for confirmation...
```

## ENS Integration

```
Connected: alice.eth
(0x742d...8f3a)

[View Profile] [Disconnect]
```

## Best Practices

1. **Never ask to connect immediately** - Let users browse first
2. **Support multiple wallets** - Don't lock into one
3. **Explain permissions clearly** - What access means
4. **Remember connections** - Auto-reconnect on return
5. **Show connection status always** - Persistent indicator
6. **Enable easy disconnect** - One-click logout
7. **Handle errors gracefully** - Clear recovery steps
8. **Support mobile wallets** - WalletConnect + deep links
9. **Verify network** - Prompt switch if wrong
10. **Security warnings** - Detect phishing attempts

## Anti-Patterns

❌ Force connection to view anything
❌ Only support one wallet
❌ Unclear what permissions mean
❌ Lose connection on refresh
❌ Hard to disconnect
❌ No mobile wallet support
❌ Silent failure on wrong network
❌ Expose to phishing without warning
