# Agent Design Critique Template

**Project**: [Project Name]
**Agent**: [Agent Name]
**Reviewer**: [Your Name]
**Date**: [YYYY-MM-DD]
**Design Phase**: [ ] Concept [ ] Prototype [ ] Beta [ ] Production

## Quick Summary

**Overall Assessment**: [1-2 sentence overall impression]

**Strengths** (Top 3):
1. [Strength 1]
2. [Strength 2]
3. [Strength 3]

**Areas for Improvement** (Top 3):
1. [Issue 1]
2. [Issue 2]
3. [Issue 3]

**Recommendation**: [ ] Approved [ ] Approved with Changes [ ] Needs Significant Revision [ ] Reject

---

## Design Principles Alignment

### Microsoft Agent UX Principles

#### Agent (Space)

**Connecting, Not Collapsing**:
- [ ] ✓ Facilitates human connections
- [ ] ✓ Enables collaboration
- [ ] ✗ Risks isolating users
- [ ] N/A

**Feedback**:
[How well does this agent connect rather than collapse? Examples?]

**Easily Accessible Yet Occasionally Invisible**:
- [ ] ✓ Operates in background appropriately
- [ ] ✓ Surfaces when relevant
- [ ] ✗ Too intrusive
- [ ] ✗ Too hidden
- [ ] N/A

**Feedback**:
[Balance of visibility? Examples?]

#### Agent (Time)

**Past - Historical Context**:
- [ ] ✓ Analyzes historical context well
- [ ] ✓ Creates connections from past events
- [ ] ✗ Ignores valuable history
- [ ] N/A

**Feedback**:
[How well does the agent use memory and history?]

**Now - Dynamic Contextual Information**:
- [ ] ✓ Delivers timely, contextual information
- [ ] ✓ Uses dynamic cues appropriately
- [ ] ✗ Information feels static or stale
- [ ] N/A

**Feedback**:
[Real-time responsiveness and relevance?]

**Future - Adaptive Evolution**:
- [ ] ✓ Designed for platform flexibility
- [ ] ✓ Can adapt to new behaviors
- [ ] ✗ Seems rigid or limited
- [ ] N/A

**Feedback**:
[How adaptable is this design for future changes?]

#### Agent (Core)

**Embrace Uncertainty, Establish Trust**:
- [ ] ✓ Transparent about limitations
- [ ] ✓ Users control agent on/off
- [ ] ✓ Status clearly visible
- [ ] ✗ Overconfident or misleading
- [ ] ✗ Lacks user control
- [ ] N/A

**Feedback**:
[Trust-building elements? Control mechanisms?]

### Implementation Guidelines

**Transparency**:
- [ ] ✓ AI involvement disclosed
- [ ] ✓ Functionality explained
- [ ] ✓ Past actions visible
- [ ] ✓ Feedback mechanisms present
- [ ] ✗ Lacking transparency

**Rating**: [1-5] ⭐️⭐️⭐️⭐️⭐️

**Feedback**:
[Specific examples of transparency or lack thereof]

**Control**:
- [ ] ✓ Customization available
- [ ] ✓ Preferences adjustable
- [ ] ✓ Personalization supported
- [ ] ✓ Data management enabled
- [ ] ✗ Lacking user control

**Rating**: [1-5] ⭐️⭐️⭐️⭐️⭐️

**Feedback**:
[Specific examples of control or lack thereof]

**Consistency**:
- [ ] ✓ Multimodal consistency
- [ ] ✓ Familiar UI patterns
- [ ] ✓ Low cognitive load
- [ ] ✗ Inconsistent experience
- [ ] ✗ Unfamiliar patterns

**Rating**: [1-5] ⭐️⭐️⭐️⭐️⭐️

**Feedback**:
[Specific examples of consistency or inconsistency]

---

## Conversation Design Review

### Intent Coverage

**Primary Intents Identified**:
1. [Intent 1] - [Well designed / Needs work]
2. [Intent 2] - [Well designed / Needs work]
3. [Intent 3] - [Well designed / Needs work]

**Missing Intents**:
- [Intent that should be covered]
- [Intent that should be covered]

**Feedback**:
[Are all necessary intents covered? Are any unnecessary?]

### Conversation Flows

**Main Flow Quality**:
- [ ] ✓ Natural and intuitive
- [ ] ✓ Efficient (minimal turns)
- [ ] ✓ Clear next steps
- [ ] ✗ Feels awkward or forced
- [ ] ✗ Too many steps
- [ ] ✗ Dead ends

**Rating**: [1-5] ⭐️⭐️⭐️⭐️⭐️

**Feedback**:
[Specific flow issues or strengths]

**Error Handling**:
- [ ] ✓ Graceful error recovery
- [ ] ✓ Clear error messages
- [ ] ✓ Recovery paths obvious
- [ ] ✗ Poor error handling
- [ ] ✗ Confusing errors

**Rating**: [1-5] ⭐️⭐️⭐️⭐️⭐️

**Feedback**:
[Specific examples]

### Confirmation Strategy

**Appropriateness**:
- [ ] ✓ Right level of confirmation for risk
- [ ] ✗ Over-confirming (too cautious)
- [ ] ✗ Under-confirming (too risky)

**Clarity**:
- [ ] ✓ Confirmations are clear and complete
- [ ] ✗ Confirmations lack important details

**Feedback**:
[Assessment of confirmation patterns]

### Tone & Voice

**Consistency**:
- [ ] ✓ Consistent personality throughout
- [ ] ✗ Tone varies inappropriately

**Appropriateness**:
- [ ] ✓ Appropriate for domain/users
- [ ] ✗ Too casual/formal
- [ ] ✗ Doesn't match brand

**Feedback**:
[Examples of tone successes or failures]

---

## User Experience Review

### Usability

**Ease of Use**:
- [ ] ✓ Easy to understand
- [ ] ✓ Easy to complete tasks
- [ ] ✗ Confusing or difficult

**Rating**: [1-5] ⭐️⭐️⭐️⭐️⭐️

**Efficiency**:
- [ ] ✓ Quick task completion
- [ ] ✓ Minimal unnecessary steps
- [ ] ✗ Slow or tedious

**Rating**: [1-5] ⭐️⭐️⭐️⭐️⭐️

**Learnability**:
- [ ] ✓ Easy for new users
- [ ] ✓ Capabilities discoverable
- [ ] ✗ Steep learning curve

**Rating**: [1-5] ⭐️⭐️⭐️⭐️⭐️

**Feedback**:
[Specific usability observations]

### Accessibility

**Screen Reader Support**:
- [ ] ✓ Fully compatible
- [ ] Partial support
- [ ] ✗ Not accessible
- [ ] Not evaluated

**Keyboard Navigation**:
- [ ] ✓ Complete keyboard access
- [ ] Partial support
- [ ] ✗ Requires mouse
- [ ] Not evaluated

**Visual Accessibility**:
- [ ] ✓ Sufficient contrast
- [ ] ✓ Text resizable
- [ ] ✓ No color-only information
- [ ] ✗ Accessibility issues present
- [ ] Not evaluated

**Feedback**:
[Accessibility strengths and issues]

### Emotional Design

**Empathy**:
- [ ] ✓ Shows appropriate empathy
- [ ] ✗ Lacks emotional intelligence
- [ ] ✗ Inappropriate emotional responses

**Trust Building**:
- [ ] ✓ Builds user confidence
- [ ] ✗ Undermines trust

**Feedback**:
[Emotional design observations]

---

## Domain-Specific Review

### Financial Services (if applicable)

**Compliance**:
- [ ] ✓ Appropriate disclaimers
- [ ] ✓ Risk disclosures adequate
- [ ] ✓ Regulatory requirements met
- [ ] ✗ Compliance issues present
- [ ] N/A

**Risk Communication**:
- [ ] ✓ Clear risk communication
- [ ] ✓ Appropriate warnings
- [ ] ✗ Risk not adequately communicated

**Feedback**:
[Financial services specific observations]

### Crypto/Blockchain (if applicable)

**Security**:
- [ ] ✓ Strong security emphasis
- [ ] ✓ Scam prevention measures
- [ ] ✗ Security concerns present
- [ ] N/A

**Transparency**:
- [ ] ✓ Transaction costs upfront
- [ ] ✓ Network status clear
- [ ] ✓ Custody clarified
- [ ] ✗ Lacking transparency

**Feedback**:
[Crypto specific observations]

---

## Visual Design Review

### UI Components

**Clarity**:
- [ ] ✓ Clear, understandable interface
- [ ] ✗ Confusing UI elements

**Consistency**:
- [ ] ✓ Consistent design language
- [ ] ✗ Inconsistent patterns

**Effectiveness**:
- [ ] ✓ UI supports goals well
- [ ] ✗ UI hinders tasks

**Feedback**:
[UI design observations]

### Information Architecture

**Organization**:
- [ ] ✓ Information well organized
- [ ] ✗ Difficult to find information

**Hierarchy**:
- [ ] ✓ Clear information hierarchy
- [ ] ✗ Important info buried

**Feedback**:
[Information architecture observations]

---

## Detailed Feedback

### What's Working Well

**Strength 1**: [Detailed description]

**Example/Evidence**: [Specific example from design]

**Strength 2**: [Detailed description]

**Example/Evidence**: [Specific example]

**Strength 3**: [Detailed description]

**Example/Evidence**: [Specific example]

### Areas for Improvement

**Issue 1**: [Detailed description]

**Impact**: [How this affects users]

**Suggestion**: [Specific recommendation for improvement]

**Priority**: [ ] Critical [ ] High [ ] Medium [ ] Low

**Issue 2**: [Detailed description]

**Impact**: [How this affects users]

**Suggestion**: [Specific recommendation]

**Priority**: [ ] Critical [ ] High [ ] Medium [ ] Low

**Issue 3**: [Detailed description]

**Impact**: [How this affects users]

**Suggestion**: [Specific recommendation]

**Priority**: [ ] Critical [ ] High [ ] Medium [ ] Low

### Questions & Clarifications Needed

1. [Question 1]
2. [Question 2]
3. [Question 3]

---

## Competitive Analysis (optional)

**Similar Agents/Products**:
- [Competitor 1]: [How they handle this]
- [Competitor 2]: [How they handle this]

**How This Design Compares**:
[Competitive positioning - where does this excel or fall short?]

**Opportunities**:
[Gaps in market that this could fill]

---

## Recommendations Summary

### Must Fix (Before Launch)
1. [Critical issue to fix]
2. [Critical issue to fix]

### Should Fix (High Priority)
1. [Important improvement]
2. [Important improvement]
3. [Important improvement]

### Could Improve (Nice to Have)
1. [Enhancement opportunity]
2. [Enhancement opportunity]

### Consider for Future
1. [Long-term opportunity]
2. [Long-term opportunity]

---

## Next Steps

1. **Design Team**: [What they should do next]
2. **Testing**: [What testing is needed]
3. **Review**: [When to review again]

**Follow-up Date**: [When to check progress on recommendations]

---

## Appendix

### Reference Materials
- [Link to prototypes]
- [Link to flow diagrams]
- [Link to requirements]

### Supporting Evidence
- [Screenshots]
- [User quotes]
- [Analytics data]
