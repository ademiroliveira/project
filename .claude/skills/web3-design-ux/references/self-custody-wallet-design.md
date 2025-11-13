# Self-Custody Wallet Design

Designing wallet experiences that balance security with usability for self-custodial asset management.

## Core Challenge

Self-custody means users are fully responsible for:
- Private key/seed phrase security
- Transaction approval
- Asset recovery
- No customer support to reset password

One mistake = permanent loss

## Wallet Creation

### Seed Phrase Backup

```
Secure Your Wallet

Your recovery phrase is the ONLY way
to recover your wallet if:
• You lose your device
• Your device breaks
• You forget your password

⚠️ CRITICAL:
• Write on paper (don't screenshot)
• Store in safe place
• Never share with anyone
• We cannot recover it for you

[I Understand] [Learn More]
```

**Manual Backup Flow**:
```
Step 1: Write Down Your Recovery Phrase

Word 1: abandon
Word 2: ability
Word 3: able
...
Word 12: absorb

☐ I've written all 12 words
☐ I've stored them safely
☐ I understand this is my only backup

[Continue]

Step 2: Verify Your Backup

Enter word 3: [____]
Enter word 7: [____]
Enter word 11: [____]

[Verify]
```

### Cloud Backup Option

```
Encrypted Cloud Backup

Your recovery phrase, encrypted with
your password, stored in iCloud/Google Drive

Security:
✓ Encrypted with your password
✓ We never see your password or phrase
✓ You can disable anytime

Convenience:
✓ Automatic backup
✓ Restore on new device
✓ No paper needed

⚠️ Trade-off: Cloud provider has encrypted data

[Enable Cloud Backup]
[Manual Backup Instead]
```

## Security Levels

### Progressive Security

**Basic (Default)**:
```
Security: Good ⭐⭐⭐

✓ Password protected
✓ Recovery phrase backed up
○ No biometric auth
○ No hardware wallet
○ No multi-sig

[Enhance Security]
```

**Enhanced**:
```
Security: Better ⭐⭐⭐⭐

✓ Password + biometric
✓ Recovery phrase + cloud backup
✓ Transaction confirmations
○ No hardware wallet
○ No multi-sig

[Maximum Security]
```

**Maximum**:
```
Security: Best ⭐⭐⭐⭐⭐

✓ Hardware wallet
✓ Multi-signature (2-of-3)
✓ Social recovery
✓ Time delays on large withdrawals

[Current Setup]
```

## Transaction Security

### Biometric Confirmation

```
Confirm Transaction

[Face ID icon]

Scan face to approve:
Send 0.5 ETH ($925)
To: Alice (0x742d...8f3a)

[Use Password Instead]
```

### Transaction Limits

```
Daily Limits

Standard transactions: Instant
Amount: Up to $1,000/day

Large transactions: 24-hour delay
Amount: $1,000 - $10,000

Very large: Multi-sig required
Amount: Over $10,000

[Customize Limits]
```

### Address Whitelisting

```
Whitelist Address

Add alice.eth as trusted contact?

Benefits:
• Skip extra confirmations
• No transaction delays
• Quick send option

[Add to Whitelist] [Send Once]
```

## Recovery Mechanisms

### Social Recovery

```
Social Recovery Setup

Choose 3-5 guardians who can help
recover your wallet if you lose access

Guardians (3 of 5 needed):
1. alice@email.com ✓
2. +1-555-0123 ✓
3. bob.eth ✓
4. Hardware Wallet ✓
5. backup@email.com ✓

How it works:
• You lose access
• 3+ guardians approve
• New wallet access granted

[Set Up Guardians]
```

### Account Abstraction

```
Smart Contract Wallet

Advanced recovery options:
• Social recovery (3-of-5 guardians)
• Time-locked recovery
• Spending limits
• Session keys for dApps

Trade-offs:
+ Better security & recovery
+ More flexible permissions
- Slightly higher gas costs

[Upgrade to Smart Wallet]
```

## Permission Management

### dApp Permissions

```
Active Connections

uniswap.org
• View balances ✓
• Spend USDC: Unlimited ⚠️
Connected: 2 days ago
[Revoke] [Edit Limit]

aave.com
• View balances ✓
• Spend DAI: 5,000 remaining
Connected: 1 week ago
[Revoke] [Add More]

[Revoke All]
```

### Token Approvals

```
⚠️ Unlimited Approval Warning

Uniswap can spend unlimited USDC

Risks:
• If Uniswap is hacked, all USDC at risk
• Approval persists forever until revoked

Safer option:
Approve only 500 USDC (this transaction)

[Approve 500] [Approve Unlimited] [Cancel]
```

## Multi-Signature Wallets

### Setup

```
Create Multi-Sig Wallet

Signers: [3 total]

1. Your main wallet (you)
2. Partner wallet
3. Hardware wallet (backup)

Threshold: [2 of 3] required

Use for:
• Joint accounts
• Business treasuries
• Added security

[Create Multi-Sig]
```

### Transaction Flow

```
Multi-Sig Transaction

Proposal: Withdraw $5,000
To: 0x742d...8f3a

Approvals: 2 of 3 needed

✓ Your signature (just now)
⏳ Partner signature (pending)
○ Hardware wallet (not needed if 2 approve)

[View Details] [Revoke Your Signature]
```

## Hardware Wallet Integration

### Connection

```
Connect Hardware Wallet

1. Connect Ledger via USB
2. Enter PIN on device
3. Open Ethereum app
4. Confirm connection

Benefits:
• Private keys never leave device
• Immune to computer viruses
• Physical confirmation required

[Connect] [Buy Ledger]
```

### Transaction Signing

```
⚠️ Confirm on Ledger

Check Ledger screen:

To: 0x742d35Cc...
Amount: 0.5 ETH
Gas: $12.50

Press both buttons if correct

⏳ Waiting for Ledger...

[Cancel]
```

## Mobile Wallet Patterns

### Biometric + Passcode

```
Unlock Wallet

[Face ID icon]
or
Enter 6-digit passcode
[● ● ● ● ● ●]

Forgot passcode?
[Recover with Seed Phrase]
```

### Quick Actions

```
Wallet Home

Your balance: $8,234

Quick Actions:
[Send] [Receive] [Buy] [Swap]

Recent:
→ Sent to Alice ($100)
← Received from Bob ($50)

[View All Activity]
```

## Security Education

### First Transaction

```
Important: Verify Address

You're sending to:
0x742d35Cc6634C0532925a3b844Bc9e7595f8f3a

✓ Double-check first few and last few characters
✓ Verify with recipient if large amount
✓ Send small test transaction first

⚠️ Transactions are irreversible
Wrong address = permanent loss

☐ I've verified the address

[Continue]
```

### Phishing Protection

```
🚨 Phishing Alert

This site is asking for your seed phrase

NEVER share your seed phrase!
• Not with support
• Not with "wallet verification"
• Not to "claim rewards"

Legitimate uses:
✓ Restoring wallet on new device (type it yourself)

[Report Phishing] [Close]
```

## Best Practices

1. **Make backup mandatory** - Don't let users skip
2. **Verify backup** - Test they wrote it correctly
3. **Enable biometrics** - Convenient security
4. **Progressive security** - Start simple, offer more
5. **Social recovery** - Modern alternative to seed phrases
6. **Transaction limits** - Protect against mistakes
7. **Address whitelisting** - Reduce confirmation friction
8. **Revocable permissions** - Easy approval management
9. **Hardware wallet support** - For serious users
10. **Continuous education** - In-context security tips

## Anti-Patterns

❌ Allow skipping seed phrase backup
❌ Screenshot seed phrases
❌ No verification of backup
❌ Unclear permission implications
❌ Unlimited approvals as default
❌ No recovery options
❌ No biometric support
❌ Make security too complex
❌ No phishing warnings
❌ Hiding security controls
