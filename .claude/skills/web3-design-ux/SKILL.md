---
name: web3-design-ux
description: Comprehensive guide for designing Web3 and Ethereum dApp user experiences. Use when designing decentralized applications, DEXs, NFT marketplaces, DAOs, DeFi protocols, wallets, or any blockchain-based interfaces. Includes Ethereum.org principles, gas UX, transaction flows, wallet design, multi-chain patterns, and accessibility.
---

# Web3 Design & UX

Comprehensive guidance for designing exceptional user experiences in Web3 applications, based on Ethereum.org documentation, industry best practices, and real-world patterns from successful dApps.

## Overview

Web3 design requires balancing technical blockchain constraints with human needs. This skill provides battle-tested patterns, principles, and practices for creating dApps that are both powerful and usable—from DEXs and NFT marketplaces to DAOs and DeFi protocols.

## When to Use This Skill

Apply this skill when:
- Designing decentralized applications (dApps)
- Creating DEX (decentralized exchange) interfaces
- Building NFT marketplaces or galleries
- Designing DAO governance interfaces
- Creating DeFi (lending, staking, yield) protocols
- Designing self-custody wallets
- Building multi-chain applications
- Evaluating existing Web3 UX
- Creating Web3 design systems
- Optimizing gas fee experiences
- Designing mobile Web3 applications

## Core Capabilities

### 1. Apply Ethereum.org Principles

Use the 7 Web3 Heuristics and blockchain design principles:

**The 7 Heuristics** (see `references/ethereum-web3-heuristics.md`):
1. Feedback Follows Action
2. Security and Trust Are Built In
3. The Most Important Info Is Obvious
4. Clear Terminology
5. Actions Are as Short as Possible
6. Network Connections Are Visible and Flexible
7. Control From the App, Not the Wallet

**10 Blockchain Design Principles** (see `references/blockchain-design-principles.md`):
1. Human-Centered Design Above All
2. Build Trust Through Transparency
3. Design for Global, Distributed Use
4. Provide Constant Feedback
5. Enable Learning Through Practice
6. Design for Confidence and Control
7. Respect User Time and Resources
8. Make Errors Recoverable When Possible
9. Balance Security with Usability
10. Design for Long-Term Relationships

### 2. Design Domain-Specific Interfaces

**DEX (Decentralized Exchange)**:
- Price transparency and slippage management
- Route optimization display
- Liquidity provision (LP) interfaces
- Impermanent loss calculators
- Token verification and safety
- See: `references/dex-design-best-practices.md`

**NFT Applications**:
- Gallery and collection displays
- Minting interfaces
- Trading and listing flows
- Rarity visualization
- Provenance and history
- See: `references/nft-design-patterns.md`

**DAO Governance**:
- Proposal display and voting
- Delegation interfaces
- Governance token management
- Discussion integration
- See: `references/dao-governance-ux.md`

### 3. Optimize Gas Fee UX

Gas fees are the #1 UX pain point. This skill provides comprehensive gas optimization patterns:
- Fiat-first display
- Three-tier selection (slow/normal/fast)
- Gas price indicators and history
- L2 recommendations
- Batch operation suggestions
- Transaction scheduling
- Stuck transaction recovery
- See: `references/gas-fee-ux-patterns.md`

### 4. Handle Transaction States

Clear communication throughout transaction lifecycle:
- Preview before execution
- Wallet signature requests
- Submission confirmation
- Real-time status updates
- Block confirmation tracking
- Success/failure states
- Multi-step transaction tracking
- Error recovery guidance
- See: `references/transaction-states-errors.md`

### 5. Design Wallet Experiences

**Connection & Authentication**:
- Progressive access (browse before connecting)
- Multi-wallet support
- Permission management
- Session persistence
- See: `references/web3-authentication-flows.md`

**Self-Custody Design**:
- Seed phrase backup flows
- Security levels (basic to maximum)
- Biometric authentication
- Social recovery
- Hardware wallet integration
- Permission and approval management
- See: `references/self-custody-wallet-design.md`

### 6. Handle Multi-Chain Complexity

- Network indicators and switching
- Unified balance views
- Network recommendations
- Cross-chain actions
- Asset location handling
- Bridge integration
- See: `references/multichain-ux-patterns.md` and `references/cross-chain-bridge-ux.md`

### 7. Optimize for Mobile

- WalletConnect integration
- Touch-friendly interfaces
- Bottom-sheet actions
- One-handed mode
- Simplified flows
- See: `references/mobile-web3-design.md`

### 8. Ensure Accessibility

- Screen reader compatibility
- Keyboard navigation
- Color contrast standards
- Web3-specific considerations
- See: `references/web3-accessibility.md`

## Quick Start Guide

### For dApp Designers

**1. Start with Core Principles**

Review `references/ethereum-web3-heuristics.md` and `references/blockchain-design-principles.md` to understand Web3-specific UX requirements.

**2. Choose Domain Patterns**

Select relevant patterns for your application:
- DEX? → `references/dex-design-best-practices.md`
- NFTs? → `references/nft-design-patterns.md`
- DAO? → `references/dao-governance-ux.md`

**3. Design Critical Flows**

Use `assets/web3-user-flow-template.md` to document:
- Wallet connection
- First transaction
- Core user actions
- Error scenarios

**4. Optimize Gas UX**

Apply patterns from `references/gas-fee-ux-patterns.md`:
- Show costs upfront
- Offer speed tiers
- Suggest optimizations
- Handle failures gracefully

**5. Evaluate Design**

Use `assets/dapp-design-checklist.md` to audit your design across:
- Wallet connection (10 points)
- Transactions (15 points)
- Gas fees (10 points)
- Security (12 points)
- Mobile (8 points)
- Accessibility (10 points)
- And more...

### For Product Designers

**Understand Web3 First**:
Start with `references/web3-design-patterns.md` for common patterns across all dApps.

**Learn Domain Specifics**:
Deep dive into patterns for your specific use case.

**Apply Templates**:
- User flows: `assets/web3-user-flow-template.md`
- Design evaluation: `assets/dapp-design-checklist.md`
- Smart contract UX: `assets/smart-contract-interaction-guide.md`

**Consider Compliance**:
Review `assets/regulatory-compliance-template.md` for required disclaimers and legal considerations.

### For Developers

**Gas Optimization**:
Use `assets/gas-optimization-checklist.md` to review:
- Transaction batching opportunities
- Permit vs traditional approvals
- L2 integration
- User control options

**Testing Strategy**:
Follow `assets/web3-testing-strategy.md` for comprehensive testing:
- Wallet compatibility
- Transaction scenarios
- Network conditions
- Mobile wallets
- Accessibility

**Smart Contracts**:
Apply patterns from `assets/smart-contract-interaction-guide.md`:
- Approval flows
- Multi-step transactions
- Transaction preview
- Safety indicators
- Simulation

## Working with Specific Scenarios

### Scenario: Designing a Token Swap

**1. Review Patterns**:
- `references/dex-design-best-practices.md` - Core DEX patterns
- `references/web3-design-patterns.md` - Wallet connection, token selection
- `references/gas-fee-ux-patterns.md` - Gas optimization

**2. Design Flow**:
```
1. Connect wallet (if not connected)
2. Select input token + amount
3. Select output token
4. Show preview:
   - Exchange rate
   - Price impact
   - Slippage tolerance
   - Gas cost
   - Total cost
5. User reviews and confirms
6. Approve token (if needed)
7. Execute swap
8. Show real-time status
9. Confirm success with details
```

**3. Apply Heuristics**:
- ✓ Feedback: Show status at every step
- ✓ Security: Display DEX route, warn on high slippage
- ✓ Important info: Rate and total cost prominent
- ✓ Clear terminology: "Price impact" not "slippage percentage"
- ✓ Short actions: Combine approval with swap using Permit
- ✓ Network visible: Show active network, suggest L2 if gas high
- ✓ App control: All info in dApp, not just wallet

**4. Test**:
Use `assets/dapp-design-checklist.md` to evaluate against all criteria.

### Scenario: Designing NFT Minting

**1. Review Patterns**:
- `references/nft-design-patterns.md` - Minting flows
- `references/transaction-states-errors.md` - Handle minting wait times
- `references/gas-fee-ux-patterns.md` - High gas during launches

**2. Key Considerations**:
- Fair launch mechanics
- Quantity limits clear
- Total cost upfront (mint price + gas)
- Progress indicator for supply
- Reveal timing communicated
- Failed mint handling

**3. Apply Security**:
- Contract verification visible
- Team/project transparency
- Audit information
- Risk warnings for new projects

### Scenario: Designing Wallet Onboarding

**1. Review Patterns**:
- `references/self-custody-wallet-design.md` - Complete wallet UX
- `references/web3-authentication-flows.md` - Connection flows
- `references/web3-design-patterns.md` - Onboarding patterns

**2. Critical Flows**:
- Seed phrase backup (mandatory)
- Backup verification
- Security education
- Biometric setup
- First transaction guidance

**3. Balance Security & Usability**:
- Make backup easy (offer cloud option)
- But communicate risks clearly
- Progressive security (start simple, offer more)
- Just-in-time education

### Scenario: Multi-Chain Application

**1. Review Patterns**:
- `references/multichain-ux-patterns.md` - Core multi-chain UX
- `references/cross-chain-bridge-ux.md` - Asset bridging

**2. Key Features**:
- Persistent network indicator
- Unified balance view
- Network recommendations
- Easy switching
- Asset location handling
- Bridge integration

**3. Avoid Confusion**:
- Always show active network
- Use network colors consistently
- Detect assets on wrong network
- Guide users to correct network
- Show costs per network

## Resources Overview

### References (16 files)

**Core Principles**:
1. `ethereum-web3-heuristics.md` - 7 heuristics for Web3 interfaces
2. `blockchain-design-principles.md` - 10 principles from IBM + Web3
3. `web3-design-patterns.md` - Common patterns across dApps

**Financial & Trading**:
4. `dex-design-best-practices.md` - DEX interface patterns
5. `gas-fee-ux-patterns.md` - Complete gas optimization guide
6. `transaction-states-errors.md` - Transaction lifecycle & errors

**Authentication & Wallets**:
7. `web3-authentication-flows.md` - Wallet connection patterns
8. `self-custody-wallet-design.md` - Wallet UX & security

**Multi-Chain**:
9. `multichain-ux-patterns.md` - Multi-network applications
10. `cross-chain-bridge-ux.md` - Asset bridging flows
11. `mobile-web3-design.md` - Mobile-specific patterns

**Specialized Domains**:
12. `nft-design-patterns.md` - NFT marketplaces & galleries
13. `dao-governance-ux.md` - DAO voting & proposals

**Supporting**:
14. `web3-user-research.md` - Research insights
15. `web3-design-systems.md` - Component libraries & tokens
16. `web3-accessibility.md` - Accessibility standards

### Templates (6 files)

1. `dapp-design-checklist.md` - 100-point evaluation checklist
2. `web3-user-flow-template.md` - Document user flows
3. `smart-contract-interaction-guide.md` - Contract UX patterns
4. `web3-testing-strategy.md` - Comprehensive testing checklist
5. `regulatory-compliance-template.md` - Legal disclaimers
6. `gas-optimization-checklist.md` - Gas UX optimization

## Best Practices Summary

**Always**:
1. Show gas costs in fiat currency first
2. Preview transactions before wallet popup
3. Provide real-time transaction status
4. Use plain language, not jargon
5. Make wallet connection optional (browse first)
6. Show active network prominently
7. Handle errors with clear recovery paths
8. Support mobile wallets (WalletConnect)
9. Test accessibility (screen readers, keyboard)
10. Communicate risks transparently

**Never**:
1. Hide costs until final confirmation
2. Use technical error messages only
3. Force wallet connection immediately
4. Leave users wondering about transaction status
5. Ignore mobile users
6. Assume users understand Web3 concepts
7. Use color alone to convey information
8. Skip accessibility considerations
9. Over-promise safety ("completely safe")
10. Forget about gas optimization

## Common Pitfalls

**Gas UX**:
❌ Showing gwei instead of dollars
❌ No indication if gas is high or low
❌ Not suggesting L2 alternatives
✓ Fiat-first, context, alternatives

**Transactions**:
❌ Lost status after leaving page
❌ No explanation of failures
❌ Can't retry or unstick transactions
✓ Persistent tracking, clear errors, recovery options

**Terminology**:
❌ "Slippage tolerance", "MEV", "gas limit"
❌ No explanations or tooltips
✓ "Price change limit", plain language, contextual help

**Network Handling**:
❌ Hidden or unclear active network
❌ Can't switch without leaving dApp
✓ Prominent indicator, one-click switching

**Security**:
❌ Unlimited approvals by default
❌ No contract verification indicators
✓ Limited approvals recommended, show audit status

## Integration with Other Skills

This skill complements:
- **Agent UX Design skill**: For conversational Web3 agents
- **Frontend development**: Implementation of these patterns
- **Smart contract development**: Understanding UX implications

## Getting Help

When designing:
1. Start with relevant heuristics and principles
2. Apply domain-specific patterns
3. Use templates to document and evaluate
4. Test with real users
5. Iterate based on feedback

When stuck:
- Review similar successful dApps
- Check relevant reference documents
- Use evaluation checklists to identify issues
- Test with users unfamiliar with Web3

## Additional Notes

**This skill is based on**:
- Ethereum.org official design documentation
- IBM blockchain design principles
- Real-world patterns from Uniswap, Aave, OpenSea, Safe, and other successful dApps
- Web3 UX research findings
- WCAG 2.1 accessibility standards

**Keep current**: Web3 UX is rapidly evolving. Stay updated on:
- New wallet connection standards
- L2 adoption and UX patterns
- Account abstraction developments
- Mobile wallet innovations
- Accessibility improvements

**Contribute back**: As you discover new patterns or improvements, document them to help the broader Web3 community improve UX for everyone.
