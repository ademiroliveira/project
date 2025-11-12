# Conversational Design Patterns for Agents

Universal patterns for designing conversational agent experiences, applicable across domains.

## Intent Recognition & Design

### Intent Hierarchy

**Pattern**: Organize intents in hierarchical structure for better management and disambiguation.

```
Root
├── Informational
│   ├── Query (search, lookup, explain)
│   ├── Status (check state, get update)
│   └── Help (guidance, tutorials)
├── Transactional
│   ├── Create (new resource)
│   ├── Update (modify existing)
│   ├── Delete (remove)
│   └── Execute (perform action)
└── Navigational
    ├── Go to (page, section)
    ├── Back/Forward (history)
    └── Reset (start over)
```

### Intent Confidence Handling

**High Confidence (>0.8)**:
- Execute immediately
- Confirm action post-execution
- Provide undo option

**Medium Confidence (0.5-0.8)**:
- Present clarifying question
- Offer alternatives
- Allow user to refine

**Low Confidence (<0.5)**:
- Present multiple options
- Ask user to rephrase
- Offer guided menu

**Example**:
```
User: "Show me crypto"

[Low confidence - ambiguous]
Agent: "I can help with several crypto-related things:
• View your crypto portfolio
• Check crypto prices
• Explain how crypto works
• Show news about cryptocurrency

Which would you like?"
```

### Multi-Intent Handling

**Pattern**: Handle requests with multiple intents gracefully.

**Example**:
```
User: "Transfer $500 to savings and show me my balance"

Agent: "I'll help with both:

1. Transferring $500 to savings...
   ✓ Complete. New savings balance: $2,750

2. Your account balances:
   • Checking: $1,245
   • Savings: $2,750
   • Total: $3,995"
```

### Intent Disambiguation

**Pattern**: Ask clarifying questions to resolve ambiguity.

**Disambiguation Framework**:
1. Acknowledge understanding
2. Identify ambiguity
3. Present options clearly
4. Enable quick selection
5. Remember choice for context

**Example**:
```
User: "Buy Apple"

Agent: "I can help you buy Apple stock. To clarify:

• Apple Inc. (AAPL) - $185.32
• Or did you mean: Apple Bonds, Apple Options?

[Apple Stock (AAPL)] [Show All Options]"
```

## Interaction Flow Patterns

### Linear Flow

**Use Case**: Simple, sequential tasks with clear steps.

**Structure**:
```
Step 1 → Step 2 → Step 3 → Completion
```

**Example - Account Setup**:
```
Agent: "Let's set up your investment account. First, what's your investment experience level?"
User: "Beginner"
Agent: "Great. Next, what's your primary investment goal?"
User: "Retirement"
Agent: "Perfect. And approximately how many years until retirement?"
User: "30 years"
Agent: "Excellent. Based on your profile, I'll recommend appropriate investment options..."
```

### Branching Flow

**Use Case**: Tasks with multiple paths based on user choices.

**Structure**:
```
Start
  ├─ Option A → Path A → Outcome A
  ├─ Option B → Path B → Outcome B
  └─ Option C → Path C → Outcome C
```

**Example - Portfolio Action**:
```
Agent: "What would you like to do with your portfolio?"

[Buy] → "What would you like to buy?" → Buy flow
[Sell] → "Which holding do you want to sell?" → Sell flow
[Rebalance] → "Auto-rebalance or custom?" → Rebalance flow
[Analyze] → Portfolio analysis flow
```

### Hub-and-Spoke Flow

**Use Case**: Central menu with independent actions, user can return to hub.

**Structure**:
```
       Hub
    /   |   \
   /    |    \
  A     B     C
  ↓     ↓     ↓
  Hub   Hub   Hub
```

**Example - Dashboard**:
```
Main Menu:
[Portfolio] [Transactions] [Research] [Settings]

User selects → Complete task → Return to Main Menu
```

### Conversational Flow (Mixed Initiative)

**Use Case**: Natural back-and-forth, user and agent both drive conversation.

**Characteristics**:
- Non-linear
- Context-switching allowed
- Interruptions handled
- Agent can ask questions
- User can change direction

**Example**:
```
User: "I want to invest in tech"
Agent: "Great! How much would you like to invest?"
User: "Actually, first tell me about your fees"
Agent: "Of course. We charge 0.5% annually on managed accounts..."
User: "OK, back to tech investing. I want to invest $5000"
Agent: "Perfect. Would you like individual stocks or a tech ETF?"
```

### Proactive Flow

**Use Case**: Agent initiates based on triggers or opportunities.

**Example**:
```
Agent: "Hi! I noticed your portfolio allocation has drifted from your target. Your tech holdings are now 45% vs your target of 35%. Would you like to rebalance?"

User: "Yes"
Agent: "I can rebalance by selling $2,500 in tech stocks. This will incur capital gains tax of approximately $375. Proceed?"
```

## Dialogue Management Patterns

### Context Maintenance

**Pattern**: Maintain conversation context across turns.

**Context Layers**:
1. **Session Context**: Current conversation state
2. **User Context**: Preferences, history, profile
3. **Domain Context**: Financial data, holdings, market state
4. **Task Context**: Current goal, progress

**Example**:
```
Turn 1:
User: "Show me tech stocks"
Agent: "Here are tech stocks: [list]"
Context: {topic: tech_stocks, action: browse}

Turn 2:
User: "What about the top one?"
Agent: "Apple (AAPL) is trading at $185..."
Context: {topic: AAPL, previous_topic: tech_stocks, action: inquire}

Turn 3:
User: "Buy 10 shares"
Agent: "Buying 10 shares of AAPL at $185..."
Context: {topic: AAPL, action: buy, quantity: 10}
```

### Error Recovery

**Pattern**: Handle misunderstandings and errors gracefully.

**Error Types & Responses**:

**1. Misunderstanding**:
```
User: "Transfer money to my other account"
Agent: "I couldn't find another account. You have:
• Checking: $1,245

Did you mean to:
• Open a new account?
• Transfer to an external account?"
```

**2. Invalid Input**:
```
User: "Buy -5 shares of Tesla"
Agent: "I can't process a negative quantity. Did you mean:
• Buy 5 shares of Tesla?
• Sell 5 shares of Tesla?"
```

**3. System Error**:
```
Agent: "I'm having trouble connecting to the market data service. Your account info is still available, but I can't show current prices. Would you like to:
• Retry
• Continue without live prices
• Come back later"
```

### Confirmation Patterns

**Implicit Confirmation** (low-risk actions):
```
User: "Show my balance"
Agent: "Your balance is $1,245. [Action completed, no confirmation needed]"
```

**Explicit Confirmation** (medium-risk):
```
User: "Send $100 to Alice"
Agent: "To confirm:
• Sending $100
• To: Alice Johnson (alice@email.com)
• From: Checking account

[Confirm] [Edit] [Cancel]"
```

**Staged Confirmation** (high-risk):
```
User: "Sell all my stocks"
Agent: "This will sell all your stock holdings:
• Apple: 50 shares (~$9,266)
• Microsoft: 30 shares (~$11,100)
• Tesla: 10 shares (~$2,150)
• Total: ~$22,516

⚠️ This is a significant transaction. Are you sure?"

User: "Yes"
Agent: "Final confirmation required. This action:
• Sells all stocks immediately
• Cannot be undone
• May have tax implications

Type 'CONFIRM SELL ALL' to proceed."
```

### Feedback Patterns

**Immediate Feedback**:
```
User: [Types message]
Agent: [Typing indicator]
Agent: [Response within 1-2 seconds]
```

**Progressive Feedback** (long-running tasks):
```
Agent: "Analyzing your portfolio..."
[2 seconds]
Agent: "Reviewed 15 holdings..."
[3 seconds]
Agent: "Calculating risk metrics..."
[2 seconds]
Agent: "Analysis complete! Here are the results..."
```

**Ambient Feedback** (background tasks):
```
[Top of screen, subtle indicator]
⟳ Syncing portfolio...

[Updates in place without interrupting]

✓ Portfolio synced
```

## Outcome Design Patterns

### Success Communication

**Clear, Positive, Actionable**:
```
✓ Action completed successfully
[What was done]
[Current state]
[Next steps]
```

**Example**:
```
✓ Trade executed

Bought: 50 shares of AAPL
Price: $185.32/share
Total: $9,266.00 + $4.95 fee
Time: 10:32 AM EST

Your new AAPL position: 100 shares ($18,532 value)

[View Portfolio] [View Receipt] [Buy More]
```

### Partial Success Communication

```
⚠️ Partially completed

Executed: 30 of 50 requested shares
Reason: Insufficient funds for full order

Completed:
• Bought 30 shares @ $185.32
• Cost: $5,563.55

Remaining:
• 20 shares not purchased
• Would need additional $3,702.45

[Add Funds] [Cancel Remaining] [Modify Order]
```

### Failure Communication

**Transparent, Helpful, Path Forward**:
```
❌ [Action] failed

[Simple explanation why]
[What this means]
[What to do about it]

[Primary Action] [Alternative] [Get Help]
```

**Example**:
```
❌ Trade cancelled

Your limit order for AAPL at $180 expired without filling.

What happened:
The stock never reached your limit price during the trading day. It stayed between $184-$186.

Options:
• Place new order at current price ($185.32)
• Set higher limit price
• Wait for price to drop

[New Market Order] [Adjust Limit] [Cancel]
```

## Handoff Patterns

### Criteria for Handoffs

**When to Hand Off**:
- Complexity exceeds agent capability
- Legal/regulatory requirement
- User explicitly requests human
- High-value/high-risk decision
- Emotional/sensitive situation
- Agent confidence too low
- Repeated failures

### Smooth Handoff Protocol

**1. Acknowledge Trigger**:
```
Agent: "This requires specialized expertise from our financial advisors."
```

**2. Explain Why**:
```
Agent: "Estate planning involves complex tax and legal considerations that require human expertise."
```

**3. Set Expectations**:
```
Agent: "I'm connecting you with an advisor. Typical wait time: 2-3 minutes."
```

**4. Transfer Context**:
```
[Advisor sees]
Context summary:
• User: Jane Smith (age 58, premium member)
• Topic: Estate planning for 3 beneficiaries
• Portfolio: $2.5M
• Current estate plan: Last updated 2015
• Question: "How do I minimize estate taxes?"

Conversation history: [full transcript]
```

**5. Confirm Handoff**:
```
Agent: "You're now connected with Sarah Johnson, Senior Financial Advisor."
Advisor: "Hi Jane, I've reviewed your question about estate planning..."
```

### Return from Handoff

**When advisor completes**:
```
Advisor: "I've sent detailed estate planning recommendations to your email. The agent can help with any follow-up questions."

Agent: "Thanks for speaking with Sarah! I can help you:
• Review the recommendations
• Schedule a follow-up
• Answer general questions about estate planning
• Connect you with an attorney for implementation

What would be helpful?"
```

### Peer Agent Handoff

**Specialty-to-Specialty**:
```
Investment Agent: "Your question involves tax optimization. Let me connect you with our tax planning agent who specializes in this."

Tax Agent: "Hi! I can see you're considering tax-loss harvesting. I have context from your investment agent about your $5,000 unrealized loss in TSLA. Let's explore this strategy..."
```

## Advanced Conversational Patterns

### Multimodal Interaction

**Pattern**: Support multiple input/output modes seamlessly.

**Input Modes**:
- Text
- Voice
- Touch/tap
- Images/photos
- File upload

**Output Modes**:
- Text
- Voice
- Visual (charts, graphs)
- Documents
- Notifications

**Example**:
```
User: [Voice] "How's my portfolio?"
Agent: [Voice] "Your portfolio is up 2.3% this month"
       [Visual] [Displays chart showing month's performance]
       [Text] "Total value: $52,845 (+$1,187)"

User: [Tap on chart]
Agent: [Visual] [Expands to detailed view]
       [Text] "Top performer: AAPL +8.2%"
```

### Personality & Tone

**Pattern**: Consistent personality that adapts to context.

**Base Personality Traits** (customize per brand):
- Professional but approachable
- Clear and concise
- Supportive, not pushy
- Honest about limitations
- Respectful of user emotions

**Tone Adaptation**:

**Neutral transaction**:
```
"Your trade is complete. You bought 10 shares of AAPL at $185.32."
```

**Success celebration**:
```
"Great news! Your portfolio reached your goal of $50,000. 🎉"
```

**Sensitive situation**:
```
"I understand this is concerning. Let's review your options carefully."
```

**Error situation**:
```
"I'm sorry, that didn't work. Let me help you resolve this."
```

### Brevity vs. Completeness

**Pattern**: Balance detail with conciseness through progressive disclosure.

**Level 1 - Quick Answer**:
```
"Your balance: $1,245"
```

**Level 2 - Useful Context**:
```
"Your checking balance: $1,245
Change today: +$250 (from payroll)"
```

**Level 3 - Complete Information**:
```
"Account Summary:
• Checking: $1,245 (+$250 today)
• Savings: $5,680 (+$0.85 interest)
• Total: $6,925

Recent activity:
• Payroll deposit: +$1,850
• Rent payment: -$1,200
• Groceries: -$127

[View All Transactions] [Transfer Funds]"
```

### Anticipatory Assistance

**Pattern**: Proactively offer relevant help before user asks.

**Triggers**:
- Patterns in behavior
- Upcoming events
- External triggers
- Opportunities

**Example**:
```
[User logs in on payday]

Agent: "Hi! I see your paycheck of $1,850 arrived.

Based on your usual pattern:
• Transfer $500 to savings? [Yes] [No]
• Pay credit card ($347 due tomorrow)? [Yes] [No]

[Dismiss] [Customize Automation]"
```

### Memory & Personalization

**Pattern**: Remember preferences and adapt behavior.

**What to Remember**:
- Explicit preferences
- Implicit patterns
- Communication style preferences
- Common tasks
- Personal context

**Example**:
```
New User:
Agent: "How can I help you today?"

Returning User:
Agent: "Welcome back! Would you like to:
• Check your portfolio (you usually do this first)
• Review your ETH holdings (you were watching this)
• Continue your research on DeFi (from yesterday)"
```

## Conversation Design Best Practices

### Opening Conversations

**Cold Start** (new user):
```
"Hi! I'm here to help with your investments. What brings you here today?"
```

**Warm Start** (returning user):
```
"Welcome back! Your portfolio is up 1.2% today. What would you like to do?"
```

**Contextual Start** (from notification):
```
"I see you tapped the alert about Apple. AAPL dropped 5% today on earnings news. Want to review your position?"
```

### Closing Conversations

**Natural Close**:
```
User: "Thanks, that's all"
Agent: "You're welcome! Let me know if you need anything else."
```

**Suggestive Close**:
```
Agent: "Transaction complete! Anything else I can help with today?"
User: "No thanks"
Agent: "Great. Have a good day!"
```

**Open-Ended Close**:
```
Agent: "Your portfolio analysis is ready in your inbox. I'm here if you have questions!"
```

### Turn-Taking

**Clear turn indicators**:
- Typing indicators while thinking
- "..." for processing
- Quick acknowledgments ("Got it", "One moment")
- Explicit questions end with "?"
- Offers/actions end with clear options

**Allow interruptions**:
```
Agent: "Let me explain how compound interest works. First, the principal amount..."

User: "Skip to how much I'll earn"

Agent: "Sure! Based on your $5,000 investment at 7% for 10 years, you'll earn approximately $4,835 in interest..."
```

### Recovery from Silence

**After 30 seconds of inactivity**:
```
"Still there? Let me know if you need help."
```

**After 2 minutes**:
```
"I'll save our conversation. Come back anytime!"
[Save state]
```

**On return**:
```
"Welcome back! We were discussing [topic]. Want to continue or start fresh?"
```

## Accessibility in Conversation

- Support screen readers
- Provide text alternatives for visual elements
- Allow keyboard navigation
- Support voice input/output
- Clear focus indicators
- Sufficient contrast
- Adjustable text size
- Avoid time pressures
- Provide clear error messages
- Support alternative authentication methods
