# Agent Handoff Pattern Template

**Pattern Name**: [Descriptive name for this handoff pattern]
**Pattern Type**: [ ] Agent-to-Human [ ] Agent-to-Agent [ ] Human-to-Agent
**Domain**: [Financial Services / Crypto / General / Other]
**Version**: [1.0]
**Author**: [Name]
**Date**: [YYYY-MM-DD]

## Overview

**Purpose**: [What this handoff accomplishes in 1-2 sentences]

**When to Use**: [Situations where this pattern applies]

**Key Benefit**: [Primary advantage of this handoff approach]

---

## Pattern Components

### Trigger Conditions

List specific conditions that initiate this handoff:

1. **[Trigger 1 Name]**
   - **Condition**: [Specific criteria that must be met]
   - **Frequency**: [How often this typically occurs]
   - **Example**: [Concrete example of this trigger]

2. **[Trigger 2 Name]**
   - **Condition**: [Specific criteria]
   - **Frequency**: [How often]
   - **Example**: [Concrete example]

3. **[Trigger 3 Name]**
   - **Condition**: [Specific criteria]
   - **Frequency**: [How often]
   - **Example**: [Concrete example]

### Intent Context

**Primary Intent Being Handled**: [The user's main goal]

**Intent Complexity Level**: [ ] Simple [ ] Moderate [ ] Complex [ ] Very Complex

**Why Handoff Needed**: [Explain why this intent requires handoff]

---

## Interaction Model

### Pre-Handoff Phase

**Initial Agent**: [Which agent/system starts]

**User State**: [What is the user trying to accomplish?]

**Agent Responsibilities Before Handoff**:
1. [Responsibility 1]
2. [Responsibility 2]
3. [Responsibility 3]

**Information to Gather**:
- [Required data point 1]
- [Required data point 2]
- [Required data point 3]
- [Optional data point 1]
- [Optional data point 2]

**Pre-Handoff Conversation Example**:
```
User: "[Initial request]"

Agent: "[Acknowledge and begin gathering context]"

User: "[Provide information]"

Agent: "[Confirm understanding and indicate handoff coming]"
```

### Handoff Initiation

**Decision Logic**:
```
IF [condition 1] AND [condition 2]
THEN initiate handoff
ELSE [alternative action]
```

**Handoff Message to User**:
```
"[Template message explaining why handoff is occurring]

[Set expectations for what happens next]

[Estimated timing if applicable]

[User options: proceed, cancel, modify]"
```

**Example**:
```
Agent: "This requires specialized expertise that I don't have. I'm connecting you with [human expert / specialist agent] who can better assist with [specific need].

They'll have all the context from our conversation and should be available in approximately [time estimate].

[Continue] [Cancel] [Modify Request]"
```

### Context Transfer

**Data Transferred**:

| Data Category | Specific Fields | Format | Required? |
|---------------|----------------|--------|-----------|
| User Identity | [Fields] | [Format] | Yes/No |
| Conversation History | [What's included] | [Format] | Yes/No |
| Intent Details | [Specific data] | [Format] | Yes/No |
| User Preferences | [Preferences] | [Format] | Yes/No |
| Session State | [State info] | [Format] | Yes/No |

**Context Package Example**:
```json
{
  "handoff_id": "unique-id",
  "timestamp": "ISO-8601",
  "from_agent": "agent-name",
  "to_agent": "target-agent-name",
  "user": {
    "id": "user-id",
    "name": "User Name",
    "tier": "premium",
    "preferences": {}
  },
  "conversation": {
    "summary": "Brief summary of conversation",
    "full_transcript": [...],
    "key_points": [...]
  },
  "intent": {
    "primary": "intent-name",
    "confidence": 0.95,
    "entities": {...}
  },
  "context": {
    "relevant_data": {...}
  }
}
```

### Handoff Execution

**Target System/Agent**: [Who receives the handoff]

**Transfer Protocol**: [How the handoff technically occurs]

**Wait State Management**:
- **Expected Wait Time**: [Time estimate]
- **User Communication During Wait**: [What user sees/hears]
- **Timeout Handling**: [What happens if handoff takes too long]

**Execution Example**:
```
[Original Agent]
"Connecting you now..."

[Brief transition period]
[Loading indicator / hold music / status message]

[Target Agent/Human]
"Hello! I'm [name/system], and I can help with [specific capability].
I can see you were discussing [context]. Let's continue from there..."
```

### Post-Handoff Phase

**Target Agent/Human Responsibilities**:
1. [Acknowledge context received]
2. [Confirm understanding]
3. [Continue assistance]

**Opening Message from Target**:
```
"[Greeting acknowledging context]

[Confirm understanding of need]

[Indicate how they'll help]

[First action or question]"
```

**Example**:
```
Financial Advisor: "Hi [User Name], I'm Sarah, a senior financial advisor.
I can see you're interested in estate planning for your three beneficiaries
and your portfolio is currently valued at $2.5M.

Let me start by understanding your primary goals for your estate plan.
What's most important to you - minimizing taxes, ensuring equal distribution,
or something else?"
```

---

## Outcome Patterns

### Successful Handoff Outcomes

**Outcome 1: [Name]**
- **Description**: [What success looks like]
- **User Experience**: [How user perceives success]
- **Metrics**: [How to measure]

**Example**:
```
User receives help from target agent/human, completes their goal,
and reports high satisfaction with seamless transition.

Metrics:
- Handoff completion rate: 95%
- User satisfaction: 4.5/5
- Time to resolution: Acceptable range
```

**Outcome 2: [Name]**
[Repeat structure]

### Partial Success Outcomes

**Outcome: [Name]**
- **Description**: [What partial success means]
- **Recovery Path**: [How to improve situation]

**Example**:
```
Context transferred successfully but user had to repeat some information.

Recovery: Apologize for duplication, quickly gather missing info, proceed.
```

### Failure Outcomes

**Failure 1: [Name]**
- **Description**: [What failure looks like]
- **Cause**: [Why it failed]
- **User Impact**: [How this affects user]
- **Recovery Strategy**: [How to handle]

**Example**:
```
Failure: Target agent/human unavailable

Cause: System overload or off-hours

Impact: User unable to complete high-priority task

Recovery Strategy:
1. Apologize and explain situation
2. Offer callback/message option
3. Provide estimated availability
4. Offer alternative if available
5. Save state for later resumption
```

---

## Return/Continuation Patterns

### Return to Original Agent

**When This Occurs**: [Situations where user returns]

**Context Brought Back**:
- [Data/decisions from handoff]
- [Outcomes achieved]
- [Next steps identified]

**Continuation Message**:
```
"[Welcome back]

[Acknowledge what was accomplished]

[Offer next steps]"
```

**Example**:
```
Agent: "Welcome back! I can see you spoke with Sarah about estate planning
and she's sent you a detailed proposal to review.

I can help you:
• Review the key recommendations
• Schedule a follow-up meeting
• Answer general questions
• Implement any simple changes

What would be helpful?"
```

### No Return (Handoff Completes Task)

**Final State**:
- [Task completed by target]
- [User satisfied]
- [Session ended cleanly]

**Completion Message from Target**:
```
"[Summary of what was accomplished]

[Next steps if any]

[How to get further help]

[Closure]"
```

---

## Design Considerations

### User Experience Principles

**Transparency**:
- [ ] User understands why handoff occurring
- [ ] Clear about what to expect
- [ ] Knows who/what they're being connected to

**Control**:
- [ ] User can cancel handoff
- [ ] User can modify request
- [ ] User can return to original agent if possible

**Continuity**:
- [ ] Context is preserved
- [ ] User doesn't repeat information
- [ ] Conversation feels continuous

**Trust**:
- [ ] Handoff feels smooth, not like failure
- [ ] Target is introduced properly
- [ ] Expertise is communicated

### Technical Requirements

**Data Security**:
- [Security measures for data transfer]
- [Compliance requirements]
- [Privacy protections]

**Performance**:
- **Target Response Time**: [Expected time]
- **Timeout Threshold**: [When to fail]
- **Fallback Options**: [What happens if target unavailable]

**Reliability**:
- **Handoff Success Rate Target**: [Percentage]
- **Retry Logic**: [How retries are handled]
- **Error Handling**: [How errors are managed]

---

## Variations

### Variation 1: [Name]

**Difference**: [How this varies from main pattern]

**When to Use**: [Specific circumstances]

**Modified Flow**: [How the flow changes]

**Example**:
[Concrete example of this variation]

### Variation 2: [Name]
[Repeat structure]

---

## Anti-Patterns to Avoid

### Anti-Pattern 1: [Name]

**Description**: [What not to do]

**Why It's Bad**: [Negative consequences]

**Instead Do**: [Correct approach]

**Example of Anti-Pattern**:
```
[Bad example showing the anti-pattern]
```

**Better Approach**:
```
[Good example showing correct way]
```

### Anti-Pattern 2: [Name]
[Repeat structure]

---

## Metrics & Evaluation

### Success Metrics

**Primary Metrics**:
- **Handoff Completion Rate**: [Target %]
- **Time to Handoff**: [Target time]
- **Context Transfer Accuracy**: [Target %]
- **User Satisfaction Post-Handoff**: [Target score]

**Secondary Metrics**:
- **Repeat Information Rate**: [Target %]
- **Handoff Cancellation Rate**: [Target %]
- **Return to Original Agent Rate**: [Target %]

### Evaluation Questions

1. Is the handoff trigger appropriate? (Not too early, not too late)
2. Is the handoff smooth and seamless?
3. Do users understand why the handoff is occurring?
4. Is context adequately preserved?
5. Does the target agent/human have sufficient information?
6. Is the overall user experience positive?

---

## Implementation Checklist

**Design Phase**:
- [ ] Trigger conditions clearly defined
- [ ] Context transfer requirements identified
- [ ] User messaging crafted
- [ ] Failure scenarios planned
- [ ] Return paths designed

**Development Phase**:
- [ ] Handoff API/protocol implemented
- [ ] Context packaging developed
- [ ] Timeout handling coded
- [ ] Error recovery built
- [ ] Logging/monitoring added

**Testing Phase**:
- [ ] Happy path tested
- [ ] Failure scenarios tested
- [ ] Context transfer validated
- [ ] User experience reviewed
- [ ] Performance measured

**Launch Phase**:
- [ ] Monitoring dashboards active
- [ ] Alerts configured
- [ ] Documentation complete
- [ ] Training completed (if human handoff)
- [ ] Rollback plan ready

---

## Examples

### Example 1: Complete Scenario

**Scenario**: [Description of situation]

**Full Conversation with Handoff**:
```
User: "[Initial request]"

Agent A: "[Response and context gathering]"

User: "[Provides information]"

Agent A: "[Determines handoff needed]"

Agent A: "[Handoff message]"

[Transition]

Agent B/Human: "[Greeting with context]"

User: "[Continues conversation]"

Agent B/Human: "[Assistance provided]"

...

[Resolution reached]

Agent B/Human: "[Closure]"
```

**Outcome**: [What happened]

**Time to Resolution**: [Total time]

**User Satisfaction**: [Rating]

### Example 2: Handoff with Complication
[Similar structure showing a more complex scenario]

### Example 3: Failed Handoff Recovery
[Structure showing failure and successful recovery]

---

## Related Patterns

**Similar Patterns**:
- [Related pattern 1]: [How it relates]
- [Related pattern 2]: [How it relates]

**Alternative Approaches**:
- [Alternative 1]: [When to use instead]
- [Alternative 2]: [When to use instead]

---

## References

**Design Guidelines**:
- [Reference document 1]
- [Reference document 2]

**Implementation Docs**:
- [Technical spec 1]
- [API documentation]

**Related Work**:
- [Research paper or article]
- [Industry best practice]

---

## Revision History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | [Date] | [Name] | Initial pattern documentation |
| | | | |

---

## Notes

[Any additional notes, considerations, or context that doesn't fit elsewhere]
