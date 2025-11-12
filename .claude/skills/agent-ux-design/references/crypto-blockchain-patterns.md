# Crypto & Blockchain Agent Design Patterns

Design patterns for conversational agents in cryptocurrency, DeFi, NFT, and blockchain domains.

## Crypto-Specific Intent Patterns

### Wallet Management Intents

#### Intent: Check Balance
**User Utterances**:
- "What's my ETH balance?"
- "Show my wallet"
- "How much USDC do I have?"

**Agent Response Pattern**:
1. Display primary balance with USD equivalent
2. Show significant token holdings
3. Provide network context (which chain)
4. Display recent activity summary
5. Offer related actions

**Design Considerations**:
- Support multi-chain wallets
- Show gas tokens prominently
- Update in real-time or indicate last refresh
- Display both token amount and fiat value
- Consider showing unrealized gains/losses

#### Intent: Send Crypto
**User Utterances**:
- "Send 0.5 ETH to Alice"
- "Transfer 100 USDC to 0x..."
- "Pay Bob 50 DAI"

**Agent Response Pattern**:
1. Parse: amount, token, recipient
2. Resolve recipient (ENS, address book, address)
3. Estimate gas fees
4. Show complete transaction preview
5. Request explicit confirmation
6. Execute and track transaction
7. Provide transaction hash and explorer link

**Security Considerations**:
- Verify recipient address display (full address, not truncated)
- Highlight new/unknown recipients
- Flag suspiciously large amounts
- Show clear gas cost
- Require confirmation for every transaction
- Display expected confirmation time

### DeFi Intents

#### Intent: Swap Tokens
**User Utterances**:
- "Swap 1 ETH for USDC"
- "Convert my DAI to USDT"
- "Trade 1000 USDC for BTC"

**Agent Response Pattern**:
1. Parse swap parameters
2. Get best route (DEX aggregation)
3. Show estimated output and price impact
4. Display slippage tolerance
5. Show all fees (gas + protocol)
6. Request confirmation
7. Execute and track

**Unique Considerations**:
- Show price impact prominently
- Display slippage tolerance clearly
- Indicate expected vs. minimum output
- Show route (which DEXs involved)
- Warn about high slippage or price impact
- Offer MEV protection options

#### Intent: Provide Liquidity
**User Utterances**:
- "Add liquidity to ETH/USDC pool"
- "Stake in curve"
- "Farm with my tokens"

**Agent Response Pattern**:
1. Explain pool/strategy briefly
2. Show required token ratios
3. Display expected APY/APR
4. Clarify risks (IL, smart contract, market)
5. Estimate transaction costs
6. Guide through approval + deposit
7. Provide tracking for position

**Risk Communication**:
- Explain impermanent loss clearly
- Highlight smart contract risks
- Show historical APY variance
- Indicate lock-up periods if any
- Warn about experimental protocols

#### Intent: Check Yield Opportunities
**User Utterances**:
- "What are the best yields for stablecoins?"
- "Where can I earn on my ETH?"
- "Show me farming opportunities"

**Agent Response Pattern**:
1. Filter by user holdings/preferences
2. Sort by relevant metric (APY, TVL, risk)
3. Show key metrics per opportunity
4. Highlight risks and requirements
5. Provide easy entry path

### NFT Intents

#### Intent: View NFT Collection
**User Utterances**:
- "Show my NFTs"
- "What NFTs do I own?"
- "Display my collection"

**Agent Response Pattern**:
1. Group by collection
2. Display with images/thumbnails
3. Show floor prices
4. Indicate collection stats
5. Offer filtering and sorting

#### Intent: NFT Transaction
**User Utterances**:
- "List my Bored Ape for sale"
- "Buy CryptoPunk #1234"
- "Make an offer on that NFT"

**Agent Response Pattern**:
1. Display NFT with full metadata
2. Show current market context (floor, sales)
3. Present transaction parameters
4. Show marketplace fees clearly
5. Estimate total costs
6. Request confirmation
7. Track listing/sale

### Security & Safety Intents

#### Intent: Contract Verification
**User Utterances**:
- "Is this token contract safe?"
- "Verify this address"
- "Check this transaction"

**Agent Response Pattern**:
1. Analyze contract if available
2. Show verification status
3. Check against known scams
4. Display audit status
5. Show community trust signals
6. Highlight risk factors
7. Provide recommendation

**Critical Safety Features**:
- Flag unverified contracts
- Warn about suspicious patterns
- Show audit status prominently
- Indicate age of contract
- Display transaction permissions
- Highlight unlimited approvals

## Blockchain-Specific Interaction Models

### Gas Fee Management Model

**Pattern**: Help users navigate gas fee complexity.

**Features**:
1. **Real-time Gas Price Display**
   - Show current network conditions
   - Display slow/standard/fast options
   - Indicate expected wait times
   - Show USD equivalent

2. **Gas Optimization Suggestions**
   - Recommend timing for transactions
   - Suggest batch operations
   - Identify gas-efficient alternatives
   - Warn about expensive operations

3. **Transaction Prioritization**
   ```
   Current network gas: 45 gwei (Medium)

   Your transaction cost estimates:
   • Slow (10 min): $12
   • Standard (3 min): $18
   • Fast (30 sec): $35

   Recommendation: Wait 2 hours for estimated $8 gas

   [Proceed Now] [Schedule for Low Gas] [Set Alert]
   ```

### Multi-Chain Navigation Model

**Pattern**: Simplify cross-chain complexity.

**Features**:
1. **Chain Context Always Visible**
   - Current chain indicator
   - Available chains for asset
   - Quick chain switching
   - Balance per chain

2. **Intelligent Chain Suggestions**
   ```
   User: "Swap ETH for USDC"
   Agent: "I notice you have ETH on both Ethereum and Arbitrum.

   Ethereum: 0.5 ETH (gas ~$15)
   Arbitrum: 2.1 ETH (gas ~$0.50)

   Recommend using Arbitrum for 97% lower fees.

   [Use Arbitrum] [Use Ethereum] [Compare]
   ```

3. **Bridge Guidance**
   - Detect when bridging needed
   - Explain bridge process
   - Show bridge options and costs
   - Estimate total time
   - Provide tracking

### Transaction Lifecycle Model

**Pattern**: Guide users through blockchain transaction lifecycle.

**Stages**:

1. **Pre-Transaction**
   ```
   Preparing your swap...
   ✓ Route found: Uniswap V3
   ✓ Price impact: 0.12% (good)
   ✓ Gas estimated: $12
   → Awaiting your confirmation in wallet
   ```

2. **Submitted**
   ```
   Transaction submitted
   TX: 0xabc...def
   Status: Pending
   Expected confirmation: ~30 seconds

   [View on Etherscan] [Speed Up] [Cancel]
   ```

3. **Confirming**
   ```
   Confirming... ⏳
   Block: 18,234,567
   Confirmations: 2/12

   Your transaction is being secured by the network.
   ```

4. **Confirmed**
   ```
   ✓ Swap complete!
   Received: 1,847.23 USDC
   Gas used: $11.43
   TX: 0xabc...def

   [View Receipt] [Share] [Done]
   ```

5. **Failed**
   ```
   ❌ Transaction failed

   Reason: Slippage tolerance exceeded
   Gas charged: $8.23 (network fee for failed tx)

   The price moved while your transaction was pending.

   [Try Again with Higher Slippage] [Cancel] [Learn More]
   ```

### Approval Management Model

**Pattern**: Make token approvals transparent and safe.

**Features**:

1. **Clear Approval Explanation**
   ```
   This action requires token approval.

   What this means:
   You're giving Uniswap permission to access your USDC tokens.

   Approval type: Limited (1000 USDC)
   Alternative: Unlimited (saves gas on future swaps)

   Gas cost: ~$8

   [Approve Limited] [Approve Unlimited] [Learn More]
   ```

2. **Approval Tracking**
   ```
   Your active token approvals:

   USDC → Uniswap V3: Unlimited
   DAI → Curve Finance: 5,000 remaining
   WETH → 1inch: Expired

   [Manage Approvals] [Revoke Selected]
   ```

3. **Security Warnings**
   ```
   ⚠️ Warning: Unlimited Approval

   This gives the smart contract unlimited access to your tokens.

   Recommended only for:
   • Trusted, audited protocols
   • Tokens you frequently trade

   Risk: If contract is compromised, all tokens could be at risk.

   [Continue Anyway] [Use Limited Approval]
   ```

## Outcome Patterns for Crypto

### Success Outcomes

#### Outcome: Transaction Successful
**Elements**:
- Confirmation with transaction hash
- Block explorer link
- Before/after balances
- Total costs breakdown
- Related actions

**Example**:
```
✓ Swap successful!

Swapped: 1.0 ETH
Received: 1,847.23 USDC
Rate: 1 ETH = 1,847.23 USDC
Price impact: 0.12%
Gas paid: 0.0042 ETH ($7.76)

TX: 0xabc...def
Block: 18,234,567

[View on Etherscan] [Share] [Swap More] [Done]
```

#### Outcome: Position Opened
**Example for DeFi**:
```
✓ Liquidity added successfully

Pool: ETH/USDC (0.3% fee)
Your position:
• 0.5 ETH
• 923.62 USDC
• LP tokens: 21.43

Value: $1,847.24
Expected APR: 24.5%
Your share: 0.08% of pool

[View Position] [Add More] [Track Performance]
```

### Warning Outcomes

#### Outcome: High Slippage Warning
**Example**:
```
⚠️ High slippage detected

Your trade will have 5.8% price impact.

What this means:
You'll receive significantly less than expected due to low liquidity.

Expected: 1,847 USDC
Actual: 1,740 USDC
Difference: -107 USDC (-5.8%)

Consider:
• Trading smaller amount
• Using different DEX
• Waiting for better liquidity

[Proceed Anyway] [Reduce Amount] [Cancel]
```

#### Outcome: High Gas Warning
**Example**:
```
⚠️ Extremely high gas cost

Current gas: 285 gwei
Transaction cost: $186

This is 4.2x normal gas prices.

Recommendation: Wait for lower gas
Average gas: 65 gwei (~$43)
Historical low: 15 gwei (~$10)

[Set Gas Alert] [Proceed Anyway] [Schedule Transaction]
```

### Failure Outcomes

#### Outcome: Transaction Reverted
**Example**:
```
❌ Transaction failed

Reason: Insufficient output amount
What happened: Price moved unfavorably during transaction

Gas charged: $12.43
(Network still charges gas for failed transactions)

Solutions:
• Increase slippage tolerance (currently 0.5%)
• Try again when price stabilizes
• Use smaller trade size

[Retry with 1% Slippage] [Wait and Retry] [Cancel]
```

## Crypto-Specific Handoff Patterns

### Agent-to-Wallet Handoff

**Trigger**: Transaction requires wallet signature

**Pattern**:
```
Agent: "I've prepared your transaction. Please review and confirm in your wallet."

[Wallet UI Opens]
• Displays transaction details
• User reviews and signs
• Signature returned to agent

Agent: "Transaction signed. Submitting to network..."
```

**Design Considerations**:
- Clear context transfer
- Keep agent UI visible
- Indicate when waiting for wallet
- Handle wallet rejection gracefully

### Agent-to-Block Explorer Handoff

**Trigger**: User needs detailed transaction info

**Pattern**:
```
Agent provides:
• Transaction hash
• Direct link to explorer
• Key metrics summary
• Context for what to look for

Opens: Etherscan/Arbiscan with transaction highlighted
```

### Cross-Protocol Handoff

**Example - Lending to Farming**:
```
Lending Agent: "You've supplied 10,000 USDC to Aave. You received aUSDC tokens that can be used in yield farming."

Farming Agent: "I see you have aUSDC. You can deposit these in Harvest Finance for an additional 8% APY while maintaining your Aave position."
```

## Crypto Domain-Specific Patterns

### Risk Communication for DeFi

**Pattern**: Layered risk explanation.

**L1 - Risk Level**:
```
Risk: MEDIUM ⚠️
```

**L2 - Risk Factors**:
```
• Smart contract risk: Audited (Certik, 2023)
• Impermanent loss: Possible with volatile pairs
• Platform risk: Established (2+ years, $500M TVL)
```

**L3 - Detailed Explanation**:
```
Smart Contract Risk:
This protocol's contracts were audited by Certik in March 2023 with no critical issues. However, audits don't guarantee safety. Even audited contracts can have vulnerabilities.

Impermanent Loss:
If ETH and USDC prices diverge significantly, you may have less value than if you held tokens separately. This is common in liquidity provision.

Platform Risk:
Protocol has operated for 2+ years without major incident, but all DeFi carries risk of exploits or economic attacks.

Historical context: [Link to incident reports]
```

### Scam Prevention Pattern

**Principle**: Protect users from common crypto scams.

**Red Flags to Detect**:
- Unverified contracts
- Unusual token permissions
- Suspicious URLs/domains
- Too-good-to-be-true yields
- Pressure tactics
- Requests for private keys/seed phrases

**Warning Example**:
```
🚨 SCAM WARNING

This token contract shows multiple red flags:
✗ Unverified source code
✗ Created less than 24 hours ago
✗ Developer holds 85% of supply
✗ Has "hidden" transfer restrictions

DO NOT PROCEED

This matches common "rug pull" patterns.

[Report Scam] [Block Contract] [Learn More]
```

### Privacy Pattern

**Principle**: Respect blockchain transparency implications.

**Considerations**:
- Addresses are pseudonymous but public
- All transactions visible on-chain
- Privacy tools available (Tornado Cash, etc.)
- Different privacy models per chain

**Communication Example**:
```
Privacy note:
This transaction will be publicly visible on the Ethereum blockchain. Anyone can see:
• The amount transferred
• Your wallet addresses
• Token types involved

Not visible:
• Your identity (unless address is linked to you elsewhere)
• The reason for transfer

Consider: Using a fresh address for sensitive transactions.

[Continue] [Learn About Privacy] [Use Privacy Tool]
```

### Custody Clarity Pattern

**Principle**: Always clarify where assets are held.

**States to Communicate**:

1. **Self-Custody**
```
✓ You control these assets
Your keys, your crypto.
Assets in your wallet: 0x12...34
```

2. **Protocol Custody** (DeFi)
```
⚠️ Assets deposited in smart contract
Protocol: Aave
Contract: 0xab...cd (verified)
You can withdraw anytime
Risk: Smart contract vulnerability
```

3. **Exchange Custody**
```
⚠️ Exchange controls these assets
Held by: Coinbase
Protection: FDIC insured (USD only)
Crypto not insured
Can withdraw to self-custody anytime
```

## Conversation Design for Crypto

### Onboarding New Users

**Progressive Complexity**:

**Day 1**:
- Simple wallet operations
- Basic send/receive
- Clear gas explanations
- Limited jargon

**Week 1**:
- Introduce swaps
- Explain DEXs vs CEXs
- Basic risk concepts

**Month 1**:
- DeFi opportunities
- Yield strategies
- Advanced features

### Education Integration

**Pattern**: Teach while doing.

**Example**:
```
User: "What's gas?"

Agent: "Gas is the fee paid to process your transaction on Ethereum. Think of it like a postage stamp for blockchain transactions.

Current gas: 45 gwei
Your swap would cost: ~$12

Gas varies based on network demand. Right now it's medium.

[Proceed] [Wait for Lower Gas] [Learn More About Gas]"
```

### Building Trust in Uncertain Environment

**Tactics**:
- Always verify information on-chain
- Link to block explorers
- Show source of price data
- Acknowledge when information is uncertain
- Provide multiple data sources

**Example**:
```
Token price: $1.85
Sources:
• CoinGecko: $1.85
• CoinMarketCap: $1.84
• DEX price: $1.86

Last updated: 2 seconds ago

Note: Prices vary slightly across sources due to different exchange data and timing.

[Refresh] [View Chart] [More Details]
```

## Mobile Considerations for Crypto

### Quick Actions
- Portfolio balance check
- Gas price monitoring
- Price alerts
- Quick swaps with presets

### Security Enhancements
- Biometric confirmation for transactions
- Whitelist trusted addresses
- Transaction limits
- Geographic restrictions

### Notifications
- Transaction confirmations
- Price alerts
- Gas price drops
- Portfolio milestones
- Security alerts

## Web3-Specific Accessibility

- Wallet connection indicators
- Chain network indicators
- Transaction state always visible
- Clear error messages
- Alternative for Web3-required features
- Progressive enhancement for non-Web3 users
