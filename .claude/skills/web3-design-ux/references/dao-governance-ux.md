# DAO Governance UX

Design patterns for decentralized autonomous organization interfaces.

## Proposal Display

```
Active Proposals (3)

Proposal #42: Increase Treasury Allocation
Status: Active (3 days left)
Votes: 2.1M / 4M quorum (52%)

For: 1.8M (85%) ████████░
Against: 300K (15%) ██░░░░░░

[Vote] [Details]
```

## Voting Interface

### Vote Casting

```
Proposal #42
Increase Treasury Allocation to Marketing

Your voting power: 10,000 GOV tokens

Vote:
○ For - Support this proposal
○ Against - Reject this proposal
○ Abstain - Don't take a side

Reason (optional):
[Text area for comment]

[Cast Vote] [Delegate Instead]
```

### Delegation

```
Delegate Voting Power

Delegate your 10,000 GOV tokens to:

Suggested delegates:
○ alice.eth (10M delegated, 95% participation)
○ bob.eth (5M delegated, 88% participation)

Or enter address: [________]

You can reclaim anytime

[Delegate] [Keep My Votes]
```

## Proposal Creation

```
Create Proposal

Title: [_________________]

Description:
[Rich text editor]

Actions:
1. Transfer 100K USDC to 0x...
2. Update parameter X to 50

Voting period: [7 days]
Required quorum: [4M votes]

[Submit Proposal]
(Requires 100K tokens to propose)
```

## Governance Token Display

```
Your GOV Tokens

Balance: 10,000 GOV

Status:
• Voting power: 10,000
• Delegated: 0
• Locked in voting: 0

Voting history:
• Proposals voted: 12
• Participation rate: 75%

[Vote] [Delegate] [Get More]
```

## Proposal Details

```
Proposal #42: Increase Treasury Allocation

Proposed by: alice.eth
Created: 7 days ago
Voting ends: 3 days

Description:
[Full proposal text]

On-chain actions:
1. transfer(treasury, 100000 USDC)
2. setParameter(marketingBudget, 50)

Discussion: [Forum link]

[Vote] [Discuss]
```

## Best Practices

1. Clear proposal status
2. Show voting power prominently
3. Easy delegation
4. Proposal templates
5. Discussion integration
6. Vote history tracking
7. Quorum indicators
8. Time-locked vote changes
9. Execution timeline
10. Mobile governance support
