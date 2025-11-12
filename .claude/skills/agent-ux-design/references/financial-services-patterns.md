# Financial Services Agent Design Patterns

Design patterns and best practices for conversational agents in financial services and investment domains.

## Intent Patterns for Financial Services

### Portfolio Management Intents

#### Intent: Portfolio Review
**User Utterances**:
- "How is my portfolio performing?"
- "Show me my investment returns"
- "What's my portfolio allocation?"

**Agent Response Pattern**:
1. Acknowledge request
2. Retrieve current portfolio state
3. Present key metrics (returns, allocation, risk)
4. Offer contextual insights or recommendations
5. Provide next action options

**Design Considerations**:
- Show both absolute and relative performance (vs benchmarks)
- Include time-period context (day, month, year, all-time)
- Visualize allocation when possible
- Highlight significant changes or alerts

#### Intent: Investment Advice
**User Utterances**:
- "Should I buy Tesla stock?"
- "What do you think about bonds right now?"
- "Where should I invest $10,000?"

**Agent Response Pattern**:
1. Acknowledge request and set expectations
2. Gather user context (risk tolerance, timeline, goals)
3. Provide analysis based on available data
4. Frame advice with confidence levels and caveats
5. Recommend consulting financial advisor for major decisions

**Compliance Considerations**:
- Always include risk disclaimers
- Clarify agent is not a licensed financial advisor
- Document reasoning and data sources
- Avoid guarantees or predictions
- Suggest professional consultation for significant decisions

### Transaction Intents

#### Intent: Execute Trade
**User Utterances**:
- "Buy 100 shares of AAPL"
- "Sell my Tesla holdings"
- "Transfer $5000 to my savings account"

**Agent Response Pattern**:
1. Parse transaction details
2. Confirm understanding with user
3. Show transaction preview (costs, fees, impact)
4. Request explicit confirmation
5. Execute and provide confirmation
6. Offer receipt/documentation

**Security Considerations**:
- Require explicit confirmation for all transactions
- Show complete transaction details before execution
- Implement appropriate authentication
- Provide immediate confirmation with transaction ID
- Offer transaction reversal window when possible

#### Intent: Transaction History
**User Utterances**:
- "Show my recent trades"
- "What did I buy last month?"
- "Find transactions over $1000"

**Agent Response Pattern**:
1. Clarify time range and filters
2. Present transactions in digestible format
3. Offer filtering and sorting options
4. Provide summary statistics
5. Enable drill-down into specific transactions

### Research & Analysis Intents

#### Intent: Market Research
**User Utterances**:
- "Tell me about the semiconductor industry"
- "What's happening with interest rates?"
- "Explain how REITs work"

**Agent Response Pattern**:
1. Provide overview appropriate to user knowledge level
2. Offer current market context
3. Present key metrics and trends
4. Link to relevant portfolio impact (if applicable)
5. Suggest related topics or deeper dives

#### Intent: Company Analysis
**User Utterances**:
- "Analyze Apple's financials"
- "What are the risks of investing in startup XYZ?"
- "Compare Microsoft and Google"

**Agent Response Pattern**:
1. Present key company metrics
2. Highlight strengths and risks
3. Provide industry context
4. Show competitive positioning
5. Offer investment thesis perspectives

## Interaction Models

### Progressive Disclosure Model

**Pattern**: Start simple, reveal complexity as needed.

**Application in Financial Services**:
1. **L1 - Quick Summary**: "Your portfolio is up 2.3% this month"
2. **L2 - Key Details**: "Your tech stocks drove gains (+8%), while bonds were flat"
3. **L3 - Full Analysis**: Detailed breakdown by position, sector analysis, risk metrics

**Benefits**:
- Reduces cognitive load
- Serves both quick checks and deep dives
- Adapts to user expertise level

### Guided Discovery Model

**Pattern**: Agent guides user through complex decisions step-by-step.

**Application Example - Investment Planning**:
```
Agent: "Let's build an investment plan together. First, what are your primary financial goals?"
User: "Retirement and saving for a house"
Agent: "Great. When are you planning to retire?"
User: "In about 20 years"
Agent: "And when do you hope to buy a house?"
User: "Within 5 years"
Agent: "Since you need money for the house soon, we should consider a mix of short-term and long-term strategies. What's your risk tolerance?"
```

**Benefits**:
- Breaks complex decisions into manageable steps
- Educates user during process
- Gathers necessary context naturally

### Proactive Notification Model

**Pattern**: Agent surfaces relevant information without user request.

**Appropriate Triggers**:
- Significant portfolio changes (>5% daily movement)
- Market events affecting user holdings
- Approaching investment goals or deadlines
- Risk threshold breaches
- Opportunities matching user preferences

**Design Guidelines**:
- Respect notification preferences
- Provide immediate context
- Offer clear next actions
- Allow easy dismissal
- Never create urgency for sales purposes

### Collaborative Analysis Model

**Pattern**: Agent and user work together to analyze information.

**Application Example - Portfolio Rebalancing**:
```
Agent: "Your portfolio has drifted from target allocation. Tech is now 45% vs target of 35%."
User: "Should I rebalance?"
Agent: "Let's look at the factors. Your tech holdings are up 30% this year. Selling now would create tax implications. What's your priority - maintaining allocation or tax efficiency?"
User: "Tax efficiency"
Agent: "We could rebalance gradually through new contributions instead of selling. Would you like to see that plan?"
```

**Benefits**:
- Positions agent as collaborator, not decision-maker
- Educates through dialogue
- Respects user agency
- Builds trust through transparency

## Outcome Patterns

### Success Outcomes

#### Outcome: Transaction Completed
**Elements**:
- Confirmation message with transaction details
- Transaction ID for reference
- Receipt/documentation offer
- Portfolio impact summary
- Related action suggestions

**Example**:
```
✓ Trade executed successfully
- Bought 100 shares of AAPL at $185.32
- Total: $18,532.00 + $4.95 fee
- Transaction ID: TXN-2024-001234
- New portfolio allocation: Tech 38% (+2%)

[Download Receipt] [View Updated Portfolio]
```

#### Outcome: Insight Provided
**Elements**:
- Clear, actionable insight
- Supporting data/reasoning
- Confidence level indication
- Related resources
- Next steps

**Example**:
```
💡 Portfolio Insight
Your dividend income has increased 15% this year, now generating $285/month in passive income.

Why this matters: You're on track to reach your $400/month dividend goal 8 months ahead of schedule.

Consider: Reinvesting dividends could accelerate growth by an estimated additional 3-4% annually.

[Learn More] [Adjust Settings] [Dismiss]
```

### Partial Success Outcomes

#### Outcome: Clarification Needed
**Pattern**: Agent needs more information to proceed.

**Example**:
```
I can help with that trade, but I need a few more details:
• Which account? (Checking, Savings, Investment)
• Limit order or market order?
• Time in force? (Day, GTC)

[Provide Details] [Market Order with Defaults]
```

### Failure Outcomes

#### Outcome: Cannot Process Request
**Elements**:
- Clear explanation of why
- Alternative suggestions
- Path to resolution
- Human escalation option

**Example**:
```
❌ Unable to execute trade

Reason: Insufficient funds in account
- Trade requires: $5,000
- Available balance: $3,250
- Shortfall: $1,750

Options:
1. Transfer funds from another account
2. Reduce order size to 65 shares
3. Speak with a financial advisor

[Transfer Funds] [Adjust Order] [Contact Advisor]
```

#### Outcome: Outside Agent Capability
**Pattern**: Request requires human expertise.

**Example**:
```
This question involves complex tax implications that require professional advice.

What I can tell you:
- General information about capital gains taxation
- Where to find IRS resources
- Your transaction history for reference

What you need:
A certified tax professional or financial advisor can provide personalized guidance for your situation.

[Find Advisor] [View Tax Resources] [Download Transaction History]
```

## Handoff Patterns

### Agent-to-Human Handoff

**Triggers**:
- User explicitly requests human
- Regulatory requirement for human review
- Agent confidence below threshold
- Complex emotional or personal situation
- High-value transaction beyond threshold

**Handoff Protocol**:
1. Acknowledge handoff trigger
2. Summarize context gathered
3. Set expectations for timing
4. Maintain conversation history
5. Provide human with full context

**Example**:
```
I understand you'd like to discuss estate planning. This requires specialized expertise, so I'm connecting you with a financial advisor.

Summary for advisor:
- User goals: Estate planning for 3 beneficiaries
- Portfolio value: $2.5M
- Age: 58, retiring in 7 years
- Current estate plan: Last updated 2015

Estimated wait time: 2-3 minutes

[Cancel] [Continue Waiting]
```

### Human-to-Agent Handoff

**Triggers**:
- Human advisor completes consultation
- Routine follow-up tasks
- Ongoing monitoring requested
- User prefers agent for simple tasks

**Handoff Protocol**:
1. Human provides context to agent
2. Agent confirms understanding
3. Set clear scope of agent responsibility
4. Establish escalation criteria
5. Provide human contact option

### Agent-to-Agent Handoff

**Triggers**:
- Specialized domain expertise needed
- Cross-platform continuation
- Multi-agent workflow

**Example - Investment Agent to Tax Agent**:
```
Investment Agent: "You're considering selling NVDA shares purchased in 2020. This could have significant tax implications. Let me connect you with our tax planning agent."

Tax Agent: "I can see you're evaluating a sale of 500 NVDA shares purchased in 2020. Based on your cost basis of $25/share and current price of $485/share, this would generate approximately $230,000 in long-term capital gains..."
```

## Financial Domain-Specific Patterns

### Risk Communication Pattern

**Principle**: Always communicate risk clearly and contextually.

**Elements**:
- Visual risk indicators (color, icons)
- Plain language risk descriptions
- Quantified risk metrics when possible
- Comparison to user's risk profile
- Historical context

**Example**:
```
⚠️ High Risk
This investment carries above-average risk for your profile.

Risk factors:
• High volatility (30% annualized)
• Concentration risk (single sector)
• Limited trading history (2 years)

Your risk tolerance: Moderate
Recommendation: Consider limiting to <5% of portfolio

[Proceed Anyway] [View Alternatives] [Learn More]
```

### Regulatory Compliance Pattern

**Principle**: Build compliance into every interaction.

**Required Elements**:
- Appropriate disclaimers
- Risk disclosures
- Suitability considerations
- Documentation and audit trails
- Clear distinction between advice and information

**Standard Disclaimer Template**:
```
This information is for educational purposes only and does not constitute financial advice. Investment decisions should be made based on your individual circumstances and in consultation with a qualified financial advisor. Past performance does not guarantee future results.
```

### Trust-Building Pattern

**Principle**: Establish and maintain user trust through consistency and transparency.

**Tactics**:
- Show sources for all data
- Explain reasoning clearly
- Acknowledge uncertainty
- Admit mistakes promptly
- Provide verification mechanisms
- Enable user control

**Example**:
```
Based on analysis of 247 analyst ratings (via Bloomberg, updated 2 hours ago), AAPL has a consensus rating of "Buy" with average price target of $195 (+5% from current).

However, keep in mind:
• Analyst accuracy varies significantly
• Price targets frequently miss
• This represents average opinion, not prediction

[View Analyst Details] [See Historical Accuracy] [Alternative Analyses]
```

## Conversation Design Best Practices

### 1. Speak the User's Language
- Adapt complexity to user sophistication
- Define jargon when first used
- Offer glossary or explanations
- Use analogies for complex concepts

### 2. Be Concise But Complete
- Lead with key information
- Use progressive disclosure for details
- Provide "Learn More" options
- Avoid overwhelming with data

### 3. Set Clear Expectations
- Explain what agent can/cannot do
- Provide timing estimates
- Indicate confidence levels
- Clarify when human expertise needed

### 4. Respect User Emotions
- Acknowledge financial stress or anxiety
- Use empathetic language
- Avoid dismissive responses
- Recognize emotional aspects of money decisions

### 5. Enable Easy Exits
- Allow conversation interruption
- Provide "start over" options
- Enable topic switching
- Offer save/resume functionality

## Mobile-Specific Considerations

### Quick Action Patterns
- One-tap portfolio check
- Voice-activated balance inquiry
- Biometric transaction approval
- Quick trade templates

### Notification Design
- Rich notifications with key metrics
- Actionable notification buttons
- Grouped related updates
- Respect quiet hours

### Input Optimization
- Smart defaults for common actions
- Recent/frequent items prioritized
- Voice input for searches
- Minimal typing required

## Accessibility Requirements

- Screen reader compatibility
- High contrast modes for financial data
- Text resizing support
- Alternative text for charts/graphs
- Voice navigation support
- Color-blind friendly visualizations
