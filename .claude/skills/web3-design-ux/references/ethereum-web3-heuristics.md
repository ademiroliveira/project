# The 7 Heuristics for Web3 Interface Design

These usability heuristics are specifically tailored for Web3 applications and should be used alongside Jakob Nielsen's 10 general interaction design principles. They address unique challenges in blockchain-based applications.

## Overview

Web3 interfaces face unique UX challenges not found in traditional web applications:
- Asynchronous blockchain interactions with variable completion times
- Irreversible transactions with real financial consequences
- Complex technical concepts (gas, blocks, confirmations, keys)
- Multiple network states and wallet connections
- Security-critical user actions

These seven heuristics provide a framework for creating usable, trustworthy Web3 experiences.

---

## Heuristic 1: Feedback Follows Action

**Principle**: "It should be obvious when something has happened, or is happening."

###

 Why This Matters in Web3

Unlike traditional web apps where actions complete instantly, blockchain transactions can take seconds to hours. Users need constant feedback about what's happening to their money and assets.

### Key Requirements

**Immediate Acknowledgment**:
- Confirm button clicks instantly
- Show loading states immediately
- Acknowledge transaction submission before blockchain confirmation

**Progressive Status Updates**:
- Transaction submitted to mempool
- Transaction included in block
- Block confirmations accumulating (1/12, 2/12, etc.)
- Transaction finalized

**Multi-Step Process Visibility**:
For complex interactions (approve + swap, approve + deposit):
- Show each step clearly
- Indicate current step
- Show completion status for each step
- Estimate total time remaining

### Design Patterns

**Transaction Status Display**:
```
⏳ Confirming... (Step 2 of 3)
→ Approve USDC ✓ Complete
→ Swap USDC for ETH ⏳ Pending
→ Add to liquidity pool ⏸️ Waiting

Estimated time: ~2 minutes
```

**Visual States**:
- ⏸️ Waiting - Not yet started
- ⏳ Pending - Submitted, awaiting confirmation
- ⏱️ Confirming - In block, accumulating confirmations
- ✓ Complete - Finalized
- ❌ Failed - Transaction reverted or rejected

**Block Confirmations**:
```
Transaction confirmed
●●●●●●●○○○○○ 7/12 confirmations
Usually final after 12 confirmations
```

### Anti-Patterns

❌ **Silent Transactions**: No indication that something is happening
❌ **Binary States**: Only showing "pending" or "complete" with nothing in between
❌ **No Error Details**: Just showing "failed" without explanation
❌ **Lost Context**: User can't see transaction status after navigation

### Implementation Checklist

- [ ] Immediate visual feedback on all button clicks
- [ ] Transaction submission confirmation before blockchain processing
- [ ] Real-time status updates as transaction progresses
- [ ] Block confirmation counter for finality awareness
- [ ] Persistent status indicator (don't lose on navigation)
- [ ] Estimated completion time
- [ ] Link to block explorer for verification
- [ ] Clear error messages with recovery steps

---

## Heuristic 2: Security and Trust Are Built In

**Principle**: "Security must be prioritized throughout design, not as an afterthought."

### Why This Matters in Web3

Users are interacting with smart contracts that control their funds. One mistake can result in permanent loss. Trust must be earned through transparent security practices.

### Key Requirements

**Security Audit Transparency**:
- Display audit information prominently
- Show which auditing firms and dates
- Link to full audit reports
- Indicate audit scope (what was/wasn't audited)

**Risk Communication**:
- Clearly communicate all risks
- Explain smart contract risks
- Indicate protocol maturity (beta, v1, v2)
- Show Total Value Locked (TVL) as trust signal
- Warn about experimental features

**Team and Governance Transparency**:
- Show who built this
- Indicate if team is anonymous or doxxed
- Show governance model
- Link to documentation and code

**Underlying Integration Risks**:
- Show which protocols are being used
- Indicate risks from dependencies
- Warn about composed risks (using multiple protocols)

### Design Patterns

**Security Badge Display**:
```
🛡️ Security
✓ Audited by Trail of Bits (Dec 2023)
✓ Open source & verified on Etherscan
✓ $2.1B TVL across protocol
⚠️ Smart contract risk remains
```

**Risk Warning Modal** (before first use):
```
⚠️ Understand the Risks

This protocol involves smart contract risk:
• Audits reduce but don't eliminate risk
• Smart contracts can have bugs
• You could lose all deposited funds

Integration risks:
• Uses Aave for lending (audited)
• Uses Chainlink for price feeds (audited)

Only deposit what you can afford to lose.

[ ] I understand the risks
[Cancel] [Continue]
```

**Permission Request Transparency**:
```
This transaction will:
✓ View your wallet address
✓ Spend up to 1000 USDC (you're swapping 500)
✗ Cannot move other tokens
✗ Cannot access your NFTs

[More Details] [Approve] [Reject]
```

### Trust Signals to Display

**Protocol Maturity**:
- Time in operation
- Total Value Locked (TVL)
- Number of users
- Number of transactions

**Code Transparency**:
- Verified contract source code
- Open source repository
- Bug bounty program
- Formal verification status

**Track Record**:
- Incident history (or lack thereof)
- Response to past issues
- Insurance or coverage options

### Anti-Patterns

❌ **Hidden Risks**: Not disclosing smart contract risks
❌ **Audit Washing**: Claiming "audited" without specifics
❌ **False Security**: Overconfident language like "completely safe"
❌ **Buried Information**: Security details hidden in docs
❌ **No Permission Details**: Unclear what user is approving

### Implementation Checklist

- [ ] Prominent security audit information
- [ ] Clear risk disclaimers before critical actions
- [ ] Team and governance transparency
- [ ] Dependency risk communication
- [ ] Permission request details (what exactly is being approved)
- [ ] Track record and incident history
- [ ] Insurance or coverage options if available
- [ ] Link to security documentation

---

## Heuristic 3: The Most Important Info Is Obvious

**Principle**: "Show only relevant data for complex systems with clear prioritization."

### Why This Matters in Web3

Web3 applications can display overwhelming amounts of data: APYs, TVLs, token prices, gas costs, network status, balances across chains, contract addresses, transaction hashes. Users scan rather than read—anchor on key metrics.

### Key Requirements

**Information Hierarchy**:
- Primary info: Large, prominent, high contrast
- Secondary info: Medium size, visible but not dominant
- Tertiary info: Small, lower contrast, expandable

**Context-Specific Relevance**:
- Show what matters for current task
- Hide irrelevant information
- Make additional details available on demand

**Scannable Layout**:
- Key metrics at a glance
- Use size and position to indicate importance
- Group related information

### Design Patterns

**Yield/Lending App Priority**:
```
Primary: APY (36% shown large)
Secondary: TVL, token rewards, risk level
Tertiary: Contract address, pool composition, historical APY
```

**Trading Interface Priority**:
```
Primary: Current price, price change %
Secondary: 24h volume, liquidity, gas cost
Tertiary: Contract address, token supply, holder count
```

**Portfolio View Priority**:
```
Primary: Total value, 24h change
Secondary: Top holdings by value
Tertiary: Small positions, dust, transaction history
```

**Visual Hierarchy Example**:
```
Lending Pool: DAI

         42.5% APY    ← Large, bold, color

TVL: $125M  |  Risk: Low   ← Medium size

○ Audited  ○ 2 years old   ← Small, icons

[View Details ↓]           ← Collapsed details
```

### Progressive Disclosure

**Level 1 - Glance (3 seconds)**:
- Most critical metric only
- Clear enough to make go/no-go decision

**Level 2 - Evaluation (30 seconds)**:
- Key details for informed decision
- Risk indicators
- Cost information

**Level 3 - Deep Dive (3+ minutes)**:
- Full technical details
- Contract addresses
- Historical data
- Advanced parameters

### Anti-Patterns

❌ **Data Overload**: Showing everything at once
❌ **Buried Critical Info**: Important details hidden in details panel
❌ **Equal Weight**: All data same size and prominence
❌ **No Hierarchy**: Users can't quickly find what matters
❌ **Technical by Default**: Contract addresses more prominent than user-relevant data

### Implementation Checklist

- [ ] Clear visual hierarchy (3 distinct levels)
- [ ] Primary metric large and obvious
- [ ] Secondary info visible but subordinate
- [ ] Tertiary details collapsed/expandable
- [ ] Context-appropriate information display
- [ ] Scannable in < 5 seconds for key decision
- [ ] Progressive disclosure for details
- [ ] User-relevant over technically-accurate as default

---

## Heuristic 4: Clear Terminology

**Principle**: "Avoid technical jargon; use simple, universally understood language."

### Why This Matters in Web3

Web3 is already complex enough. Every piece of jargon creates a learning barrier. Terms like "slippage," "gas," "impermanent loss," "MEV," and "nonce" are meaningless to new users.

### Key Requirements

**Use Plain Language**:
- Replace jargon with everyday terms
- Explain unavoidable technical terms
- Use metaphors and analogies
- Consistent terminology across app

**Educate, Don't Assume**:
- Provide contextual help
- Explain concepts in simple terms
- Offer glossary or tooltips
- Progressive education as users advance

**Follow Conventions**:
- Use terms users already know from other apps
- Don't invent project-specific terminology
- Align with ecosystem standards

### Terminology Guidelines

**Replace When Possible**:

| ❌ Technical Term | ✓ Clear Alternative |
|------------------|-------------------|
| "Approve token spending" | "Give permission to use your tokens" |
| "Slippage tolerance" | "Price change limit" or "Maximum price" |
| "Impermanent loss" | "Price change risk" or "Rebalancing loss" |
| "Gas fee" | "Network fee" or "Transaction cost" |
| "Smart contract" | "The program" or just describe what it does |
| "MEV" | "Front-running protection" |
| "Nonce" | "Transaction number" or hide entirely |
| "Wei/Gwei" | Always show in ETH or USD |

**Explain When Necessary**:

If technical term must be used, explain clearly:

```
Slippage (?)
The maximum price change you'll accept.

Your trade might get a slightly different price than shown
due to other trades happening at the same time.

Setting: 1% means you'll accept up to 1% worse price.

[Learn more about slippage]
```

**Contextual Help Icons**:
```
Gas fee: $12.50 (?)

Hover/tap shows:
"Gas fees go to network validators who process your
transaction. We don't receive this fee."
```

### Writing Style

**Use Active Voice**:
- ✓ "You'll receive approximately 1,847 USDC"
- ❌ "1,847 USDC will be received"

**Address the User**:
- ✓ "Your balance: 5.2 ETH"
- ❌ "Account balance: 5.2 ETH"

**Be Specific**:
- ✓ "This will use tokens from your wallet"
- ❌ "Funds will be utilized from address"

**Avoid Jargon Clusters**:
- ❌ "Approve ERC-20 token spending limit via proxy contract"
- ✓ "Give permission to move your USDC tokens"

### Education Patterns

**Inline Glossary**:
Underline or mark technical terms, show definition on hover/tap.

**Progressive Education**:
- First use: Full explanation
- Subsequent uses: Brief reminder
- After mastery: Just the term

**Help Center Integration**:
Link complex concepts to detailed help articles for users who want to learn more.

### Anti-Patterns

❌ **Unexplained Jargon**: Using technical terms without explanation
❌ **Inconsistent Terms**: Calling same thing different names
❌ **Project-Specific Terminology**: Inventing new terms others don't use
❌ **Acronym Soup**: Assuming users know MEV, TVL, APY, LP, DEX
❌ **No Contextual Help**: No way to learn what terms mean

### Implementation Checklist

- [ ] Audit all user-facing text for jargon
- [ ] Replace with plain language where possible
- [ ] Add explanations for necessary technical terms
- [ ] Implement contextual help (tooltips, modals)
- [ ] Create glossary or help section
- [ ] Use consistent terminology throughout
- [ ] Test with non-technical users
- [ ] Progressive education system

---

## Heuristic 5: Actions Are as Short as Possible

**Principle**: "Minimize steps by combining related actions through smart contract or UI optimization."

### Why This Matters in Web3

Every blockchain interaction requires:
- User attention and confirmation
- Gas fees
- Waiting time for confirmation
- Potential for failure

Reducing steps improves UX and saves users money.

### Key Requirements

**Combine Related Actions**:
- Batch approvals with main action when possible
- Use permit signatures instead of separate approve transactions
- Consolidate multi-step flows into single transactions

**Smart Contract Optimization**:
- Use multicall patterns
- Implement batching at contract level
- Support meta-transactions for gasless experiences

**UI Efficiency**:
- Smart defaults based on user behavior
- Quick action shortcuts
- Saved preferences for repeat actions

### Optimization Patterns

**Approve + Action Combined**:

Instead of:
```
Step 1: Approve USDC ⏳
Step 2: Wait for confirmation ⏱️
Step 3: Swap USDC for ETH ⏳
Step 4: Wait for confirmation ⏱️
```

Optimize to:
```
Using permit signature:
Step 1: Sign approval + execute swap ⏳
Step 2: Wait for confirmation ⏱️
```

**Multicall Pattern**:
```
Single transaction that:
✓ Claims rewards
✓ Compounds earnings
✓ Restakes position

Instead of 3 separate transactions
Saves 2x gas fees & 2x waiting time
```

**Permit2 Pattern**:
```
One-time approval for multiple apps:
1. Sign Permit2 approval once
2. All future swaps skip approval step
3. Revoke access anytime

Saves gas on every trade after first
```

### Quick Action Patterns

**Smart Defaults**:
```
Swap Settings:
○ Slippage: Auto (recommended) ← Smart default
○ Transaction speed: Medium ← Usual choice
○ Use Permit: Yes ← Saves gas

[Advanced Settings]
```

**Saved Preferences**:
```
Welcome back!

Your usual settings:
✓ 1% slippage tolerance
✓ Medium transaction speed
✓ Notifications on

[Use These] [Change Settings]
```

**Frequently Used Actions**:
```
Quick Actions:
[Add Liquidity] [Claim Rewards] [Compound]

Based on your typical usage
```

### Batching Opportunities

**Portfolio Management**:
- Claim all rewards across protocols (1 transaction)
- Rebalance multiple positions at once
- Approve multiple tokens simultaneously

**Trading**:
- Place multiple limit orders
- Cancel multiple orders
- Swap multiple tokens in sequence

**DeFi Operations**:
- Deposit to multiple pools
- Claim + compound + restake
- Close multiple positions

### Anti-Patterns

❌ **Unnecessary Steps**: Requiring separate approval when permit would work
❌ **No Batching**: Making users do 10 transactions for what could be 1
❌ **Excessive Confirmations**: Asking to confirm obvious low-risk actions
❌ **No Smart Defaults**: Always making users configure everything
❌ **Ignoring Repeat Users**: Not remembering preferences

### Implementation Checklist

- [ ] Use Permit/Permit2 where possible
- [ ] Implement multicall for related actions
- [ ] Batch similar operations
- [ ] Smart defaults for 80% use case
- [ ] Save user preferences
- [ ] Quick action shortcuts for common tasks
- [ ] Estimate gas savings from optimization
- [ ] Compare step count to competitors
- [ ] Test flow efficiency with real users

---

## Heuristic 6: Network Connections Are Visible and Flexible

**Principle**: "Display current network status with easy switching options."

### Why This Matters in Web3

Multi-chain is the reality. Users interact with Ethereum, Polygon, Arbitrum, Optimism, Base, and more. Network confusion causes failed transactions and lost funds.

### Key Requirements

**Always Show Active Network**:
- Persistent network indicator
- Clear visual distinction between networks
- Update immediately on network change

**Easy Network Switching**:
- Switch networks without leaving app
- Prompt for network change when needed
- Show why network change is required

**Maintain App Visibility**:
- Don't lose context when switching networks
- Show app UI even when disconnected
- Handle network issues gracefully

**Multichain Data Clarity**:
- Indicate which network's data is shown
- Show balances per network
- Aggregate data with per-network breakdown

### Design Patterns

**Persistent Network Indicator**:
```
┌─ Header ────────────────────┐
│ DApp Name    [🟣 Ethereum ▾]│
│                Balance: 5 ETH│
└─────────────────────────────┘

Always visible, clickable to switch
Uses network brand colors
```

**Network Switcher**:
```
Switch Network:

○ Ethereum      5.2 ETH
● Polygon       1,245 MATIC  ← Current
○ Arbitrum      0.8 ETH
○ Optimism      2.1 ETH
○ Base          0.3 ETH

[Select Network]
```

**Required Network Prompt**:
```
⚠️ Switch to Polygon Required

This action requires Polygon network.
You're currently on Ethereum.

Reason: Lower fees for this transaction
Estimated cost: $0.05 (vs $12 on Ethereum)

[Switch to Polygon] [Cancel]
```

**Multichain Balance Display**:
```
Total Portfolio: $12,450

Ethereum        $8,200  [View]
Polygon           $3,100  [View]
Arbitrum          $950    [View]
Optimism          $200    [View]

Tap network to see details
```

**Disconnected State**:
```
⚠️ Wallet Disconnected

You can still:
✓ Browse available pools
✓ View current rates
✓ Learn about the protocol

To interact, please:
[Connect Wallet]
```

###Network-Specific Considerations

**Network Names**:
- Use official brand names
- Show Layer 2 distinction if relevant
- Avoid confusing technical names

**Visual Identity**:
- Use network brand colors
- Show network logos/icons
- Consistent color coding throughout app

**Network Properties to Display**:
- Confirmation time (~12 seconds on Polygon)
- Typical gas cost ($0.02 on Arbitrum)
- Security model (Optimistic vs ZK)
- Mainnet vs testnet distinction

### Multichain UX Patterns

**Chain Recommendation**:
```
Available on 3 networks:

Ethereum       Gas: $12    Time: 2 min
Polygon        Gas: $0.02  Time: 10 sec  ← Recommended
Arbitrum       Gas: $0.15  Time: 15 sec

Based on your action, Polygon offers best value.

[Use Polygon] [Compare Networks]
```

**Cross-Chain Action**:
```
You're swapping USDC on Ethereum
But your USDC is on Polygon

Options:
1. Switch to Polygon (recommended)
   Trade there with $0.02 fee

2. Bridge to Ethereum
   $15 bridge fee + $12 swap fee = $27 total

[Switch to Polygon] [Bridge Assets]
```

### Anti-Patterns

❌ **Hidden Network**: No indication of which network is active
❌ **Locked Network**: Can't switch without leaving app
❌ **Silent Failures**: Transaction fails without explaining wrong network
❌ **Ambiguous Data**: Can't tell which network's data is shown
❌ **Lost Context**: App unusable when wallet disconnected

### Implementation Checklist

- [ ] Persistent network indicator in UI
- [ ] Network brand colors and logos
- [ ] One-click network switching
- [ ] Automatic network switch prompts
- [ ] Show reason for network requirements
- [ ] Multichain balance aggregation
- [ ] Per-network data breakdown
- [ ] Handle disconnected state gracefully
- [ ] Testnet warning (if applicable)
- [ ] Network-specific properties (gas, time)

---

## Heuristic 7: Control From the App, Not the Wallet

**Principle**: "The UI should provide complete information and control for user actions."

### Why This Matters in Web3

Wallet interfaces (MetaMask, Rainbow, etc.) provide minimal context. Users shouldn't need to switch between app and wallet to understand what's happening.

### Key Requirements

**App Communicates Status**:
- Show transaction status in app UI
- Don't rely on wallet notifications
- Provide detailed progress information
- Display clear outcome messages

**Transaction History in App**:
- Show recent transactions
- Filterable/searchable history
- Per-transaction status
- Retry/cancel options

**Block Explorer Integration**:
- Link to block explorer for details
- Deep link to specific transaction
- Show relevant explorer data in-app

**Network Switching in App**:
- Change networks from app UI
- Don't force wallet-only switching
- Explain why switch is needed

**Comprehensive Transaction Preview**:
- Show all details before signing
- Estimate gas cost
- Display expected outcome
- Warning about risks

### Design Patterns

**In-App Transaction Status**:
```
┌─ Recent Transactions ────────┐
│                               │
│ ⏳ Swap 500 USDC → ETH       │
│    Pending... (15 seconds)    │
│    [Cancel] [View Details]    │
│                               │
│ ✓ Add Liquidity               │
│    Confirmed (2 min ago)      │
│    [View on Explorer]         │
│                               │
│ ❌ Claim Rewards               │
│    Failed - Out of gas        │
│    [Try Again] [Details]      │
└───────────────────────────────┘

Always visible, no need to check wallet
```

**Transaction Preview Modal**:
```
Review Transaction

Action: Swap USDC for ETH
You pay: 500 USDC
You receive: ≈ 0.27 ETH

Details:
Route: USDC → ETH (Uniswap V3)
Price impact: 0.12%
Minimum received: 0.268 ETH (if 1% slippage)

Network: Ethereum
Gas fee: ~$12.50 (Medium speed)
Total cost: 500 USDC + $12.50

⚠️ This transaction is irreversible

[Back] [Confirm in Wallet →]
```

**Post-Transaction Feedback**:
```
✓ Swap Complete!

Swapped: 500 USDC
Received: 0.272 ETH
Gas paid: $11.89

Transaction: 0x742d...8f3a
[View on Etherscan]
[Share] [Done]

Your new balance: 5.472 ETH
```

**Transaction Management**:
```
Pending Transaction

Swap 500 USDC → ETH
Submitted 45 seconds ago
Current gas: 45 gwei

Actions:
[Speed Up] - Pay more gas to confirm faster
[Cancel] - Attempt to cancel (costs gas)
[Wait] - Will likely confirm in ~2 minutes

[View on Etherscan]
```

**Failed Transaction Handling**:
```
❌ Transaction Failed

Reason: Slippage tolerance exceeded
Gas charged: $8.23 (network still charged you)

What happened:
Price moved more than your 1% limit while
transaction was pending.

Solutions:
• Increase slippage to 2% and try again
• Wait for price to stabilize
• Try a smaller amount

[Retry with 2% Slippage]
[Cancel]
[Learn More]
```

### Information to Display

**Before Transaction**:
- Exact action being performed
- Assets being moved (from → to)
- Expected outcome with estimates
- All costs (gas + protocol fees)
- Risks and warnings
- Network being used

**During Transaction**:
- Current status (submitted, pending, confirming)
- Time elapsed / estimated remaining
- Block confirmations if relevant
- Options to speed up or cancel
- Link to block explorer

**After Transaction**:
- Final outcome (success/failure)
- Actual amounts received
- Actual gas cost paid
- Transaction hash
- Updated balances
- Next action suggestions

### Block Explorer Integration

**Link Prominently**:
```
[View on Etherscan →]

Deep link to: etherscan.io/tx/0x742d...8f3a
```

**Embed Key Data**:
```
Transaction Details

Status: ✓ Confirmed
Block: 18,234,567
Timestamp: 2 minutes ago
Gas used: 147,852 (paid $11.89)

[Full Details on Etherscan →]
```

### Anti-Patterns

❌ **Wallet-Only Status**: User must check wallet to see transaction status
❌ **No Transaction History**: Can't see past transactions in app
❌ **Minimal Preview**: Wallet shows more info than app
❌ **Lost Transactions**: No way to track after closing browser
❌ **No Error Explanation**: Failed transaction with no helpful info
❌ **Explorer Only**: Must use block explorer for basic info

### Implementation Checklist

- [ ] In-app transaction status display
- [ ] Real-time status updates
- [ ] Transaction history view
- [ ] Comprehensive transaction preview
- [ ] Gas cost estimation before signing
- [ ] Expected outcome clearly shown
- [ ] Failed transaction explanations
- [ ] Retry/cancel functionality
- [ ] Block explorer integration
- [ ] Post-transaction confirmation
- [ ] Updated balances after transaction
- [ ] Persistent status (survives page refresh)

---

## Using These Heuristics

### Evaluation Process

**1. Heuristic Review**:
- Walk through key user flows
- Check each heuristic systematically
- Document violations with screenshots
- Rate severity (critical, major, minor)

**2. Prioritization**:
- Critical: Blocks task completion or causes loss
- Major: Significantly impairs usability
- Minor: Small friction, workarounds exist

**3. Remediation**:
- Address critical issues first
- Batch similar fixes
- Test solutions with users
- Iterate based on feedback

### Integration with Other Principles

These Web3-specific heuristics complement:
- **Jakob Nielsen's 10 Usability Heuristics**: General interaction design
- **IBM Blockchain Design Principles**: Human-centered blockchain design
- **Agent UX Principles**: For conversational Web3 interfaces

Use all frameworks together for comprehensive UX evaluation.

### Continuous Improvement

- Monitor user behavior and feedback
- Track where users get stuck
- Analyze failed transactions
- Iterate on painful interactions
- Stay updated on Web3 UX patterns

---

## Summary: The 7 Heuristics

1. **Feedback Follows Action** - Obvious status of what's happening
2. **Security and Trust Are Built In** - Transparency about risks and audits
3. **The Most Important Info Is Obvious** - Clear visual hierarchy
4. **Clear Terminology** - Plain language over jargon
5. **Actions Are as Short as Possible** - Minimize steps and gas
6. **Network Connections Are Visible and Flexible** - Show network, easy switching
7. **Control From the App, Not the Wallet** - Complete information in app UI

Apply these consistently to create usable, trustworthy Web3 experiences.
