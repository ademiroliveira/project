# Agent Conversation Flow Template

**Agent Name**: [Agent Name]
**Version**: [1.0]
**Date**: [YYYY-MM-DD]
**Author**: [Name]
**Domain**: [Financial Services / Crypto / Other]

## Overview

**Purpose**: [What this agent does in 1-2 sentences]

**Key Capabilities**:
- [Capability 1]
- [Capability 2]
- [Capability 3]

**Target Users**: [Primary user personas]

## Entry Points

### Entry Point 1: [Name]
**Trigger**: [How user reaches this flow]
**Example Utterances**:
- "[Example user input 1]"
- "[Example user input 2]"
- "[Example user input 3]"

**Initial Context Needed**:
- [Data point 1]
- [Data point 2]

### Entry Point 2: [Name]
[Repeat structure above]

## Main Conversation Flow

### Flow 1: [Primary Task Name]

#### Intent: [Intent Name]
**User Goal**: [What the user wants to accomplish]

**Success Criteria**: [How we know the task succeeded]

**Flow Diagram**:
```
Start
  ↓
[Agent greeting/acknowledge]
  ↓
[Gather information - Step 1]
  ↓
[User provides info]
  ↓
[Agent confirms understanding]
  ↓
[Gather information - Step 2]
  ↓
[User provides info]
  ↓
[Agent presents analysis/preview]
  ↓
[Request confirmation]
  ↓
[User confirms] → [Execute action] → [Success outcome]
  ↓                                        ↓
[User declines]                    [Provide confirmation]
  ↓                                        ↓
[Handle cancellation]               [Suggest next steps]
  ↓                                        ↓
End                                      End
```

#### Detailed Conversation

**Turn 1 - Agent**: [Opening message]
```
"[Exact agent message or template]"
```

**Turn 2 - User**: [Expected user response]
```
Examples: "[User response 1]", "[User response 2]"
```

**Turn 3 - Agent**: [Agent response]
```
"[Agent message]"

[Any UI elements shown]
```

[Continue for all turns...]

#### Variations

**Variation A: [Scenario Name]**
**Trigger**: [What causes this variation]
**Difference**: [How flow differs from main path]

**Variation B: [Scenario Name]**
[Repeat structure]

#### Error Handling

**Error Case 1: [Error Name]**
**Trigger**: [What causes this error]
**Agent Response**:
```
"[Error message]"

[Recovery options]
```

**Error Case 2: [Error Name]**
[Repeat structure]

### Flow 2: [Secondary Task Name]
[Repeat structure from Flow 1]

## Context Management

### Data Requirements

**Required Data**:
- [Data field 1]: [Source, format]
- [Data field 2]: [Source, format]

**Optional Data**:
- [Data field 1]: [Enhances experience how?]

### Context Persistence

**Session Context** (cleared after session):
- Current conversation state
- Temporary selections
- Draft actions

**User Context** (persists across sessions):
- User preferences
- Historical patterns
- Saved preferences

### Context Sharing

**Data Shared with Other Agents**:
- [Data type 1]: [Shared with which agents]
- [Data type 2]: [Shared with which agents]

## Handoff Scenarios

### Handoff to Human

**Trigger Conditions**:
- [Condition 1]
- [Condition 2]
- [Condition 3]

**Handoff Message**:
```
"[Message to user explaining handoff]"
```

**Context Transferred**:
- Conversation history
- [Specific data point 1]
- [Specific data point 2]

### Handoff to Specialist Agent

**Trigger**: [When specialist needed]

**Target Agent**: [Specialist agent name]

**Context Transferred**: [What information is passed]

## Proactive Behaviors

### Trigger 1: [Trigger Name]
**Condition**: [When agent proactively engages]
**Message**:
```
"[Proactive message template]"
```
**Frequency Limit**: [How often this can trigger]

### Trigger 2: [Trigger Name]
[Repeat structure]

## Personalization

**Adapts Based On**:
- User expertise level (beginner, intermediate, expert)
- Usage patterns
- Stated preferences
- Historical behavior

**Adaptation Examples**:

**For Beginners**:
```
"[More explanatory version of message]"
```

**For Experts**:
```
"[Concise version with shortcuts]"
```

## Key Decision Points

### Decision 1: [Decision Name]
**When**: [Point in conversation]
**Options**:
- Option A: [Description] → [Leads to flow X]
- Option B: [Description] → [Leads to flow Y]

**Decision Logic**: [How agent decides or presents choice]

### Decision 2: [Decision Name]
[Repeat structure]

## Success Outcomes

### Outcome 1: [Outcome Name]
**Achieved When**: [Conditions]

**Confirmation Message**:
```
"[Success message with details]"

[UI elements]

[Next action suggestions]
```

**Metrics Logged**:
- [Metric 1]
- [Metric 2]

### Outcome 2: [Outcome Name]
[Repeat structure]

## Failure Outcomes

### Failure 1: [Failure Type]
**Occurs When**: [Conditions]

**Message**:
```
"[Failure explanation]

[Why it failed]

[What user can do]

[Recovery options]"
```

**Metrics Logged**: [Failure tracking]

## Conversation Examples

### Example 1: Happy Path

**Scenario**: [Description of scenario]

**Full Conversation**:
```
User: "[Initial request]"

Agent: "[Response]"

User: "[Follow-up]"

Agent: "[Response]"

[Continue full conversation...]

Outcome: [What happened]
```

### Example 2: Error Recovery

**Scenario**: [Description of scenario with error]

**Full Conversation**:
[Same format as Example 1]

### Example 3: Complex Scenario

**Scenario**: [Multi-turn, complex interaction]

**Full Conversation**:
[Same format as Example 1]

## Design Notes

### Tone & Voice
- [Personality trait 1]
- [Personality trait 2]
- [Language preferences]

### Confirmation Strategy
- [When explicit confirmation needed]
- [When implicit confirmation acceptable]
- [High-risk action protocols]

### Response Time Expectations
- Simple queries: [Target time]
- Complex analysis: [Target time]
- Transactions: [Target time]

## Compliance & Safety

### Required Disclaimers
- [Disclaimer 1]
- [Disclaimer 2]

### Security Considerations
- [Security measure 1]
- [Security measure 2]

### Privacy Protections
- [Privacy measure 1]
- [Privacy measure 2]

## Testing Checklist

**Functional Testing**:
- [ ] Happy path works end-to-end
- [ ] All variations handled
- [ ] Error cases graceful
- [ ] Handoffs successful
- [ ] Data validation correct

**UX Testing**:
- [ ] Tone appropriate
- [ ] Language clear
- [ ] Flow feels natural
- [ ] Time to completion acceptable
- [ ] User satisfaction high

**Edge Cases**:
- [ ] [Specific edge case 1]
- [ ] [Specific edge case 2]
- [ ] [Specific edge case 3]

## Metrics & KPIs

**Success Metrics**:
- Task completion rate: [Target %]
- Time to completion: [Target time]
- User satisfaction: [Target score]

**Performance Metrics**:
- Response time: [Target]
- Intent accuracy: [Target %]
- Error rate: [Target %]

**Engagement Metrics**:
- Return usage rate: [Target %]
- Feature discovery: [Target %]

## Revision History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | [Date] | [Name] | Initial version |
| | | | |
