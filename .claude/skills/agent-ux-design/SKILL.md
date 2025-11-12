---
name: agent-ux-design
description: Guide for creating effective UX design for AI agents. Use this skill when designing conversational agents for financial services, crypto/blockchain, or other domains. Applies Microsoft's agent UX principles. Helps plan, design, and evaluate agent behavior, interfaces, conversational flows, intent patterns, interaction models, and handoff patterns.
---

# Agent UX Design

This skill provides comprehensive guidance for designing user experiences for AI agents, with specialization in financial services and crypto/blockchain domains.

## Overview

Agent UX design requires balancing multiple concerns: making AI capabilities accessible while maintaining user control, providing automation while preserving agency, and creating conversational interfaces that feel natural while remaining efficient. This skill applies Microsoft's research-backed agent UX principles and provides practical patterns for designing agent experiences across conversational AI, autonomous task agents, and multi-agent systems.

## When to Use This Skill

Apply this skill when:
- Designing conversational agents for financial services or investment applications
- Creating agent interfaces for crypto, DeFi, or blockchain applications
- Planning agent behavior and conversation flows
- Evaluating agent UX for usability issues
- Developing intent patterns and interaction models
- Designing handoff patterns between agents or agents and humans
- Conducting design reviews of agent experiences
- Creating documentation for agent conversation flows

## Core Capabilities

This skill enables:

### 1. Design Planning
Plan agent experiences using Microsoft's proven UX principles, ensuring designs support human agency, build trust through transparency, and enhance rather than replace human capabilities.

### 2. Conversation Flow Design
Create natural, efficient conversation flows that handle complex multi-turn interactions, manage context effectively, and gracefully handle errors and edge cases.

### 3. Domain-Specific Pattern Application
Apply specialized patterns for financial services (risk communication, compliance, transaction flows) and crypto/blockchain (security, gas fees, multi-chain complexity).

### 4. Usability Evaluation
Systematically evaluate agent designs across key dimensions: effectiveness, efficiency, learnability, trust, control, transparency, error handling, personalization, accessibility, and emotional intelligence.

### 5. Intent & Interaction Modeling
Design intent hierarchies, disambiguation strategies, and interaction models (progressive disclosure, guided discovery, proactive notification, collaborative analysis).

### 6. Handoff Pattern Design
Create seamless transitions between agents, from agents to humans, and back, maintaining context and user trust throughout.

## Design Workflow

### Step 1: Understand the Agent Context

Begin by clearly defining:

**Agent Purpose**:
- What user needs does this agent address?
- What tasks should it handle?
- What is explicitly out of scope?

**Target Users**:
- Who are the primary users?
- What is their expertise level?
- What are their goals and pain points?
- What devices/platforms will they use?

**Domain Requirements**:
- What domain knowledge is essential?
- What compliance or regulatory requirements apply?
- What security considerations are critical?
- What data is needed and how sensitive is it?

**Success Criteria**:
- How will success be measured?
- What are the key performance indicators?
- What user satisfaction targets apply?

### Step 2: Apply Core UX Principles

Reference `references/microsoft-agent-ux-principles.md` for complete principles. Key principles to apply:

**Agent (Space) Principles**:
- **Connecting, Not Collapsing**: Design agents that facilitate human connections rather than replace them
- **Easily Accessible Yet Occasionally Invisible**: Enable background operation with contextual surfacing

**Agent (Time) Principles**:
- **Past**: Leverage historical context and memory
- **Now**: Deliver dynamic, contextual information
- **Future**: Design for adaptive evolution

**Agent (Core) Principles**:
- **Embrace Uncertainty, Establish Trust**: Build trust through transparency about capabilities and limitations

**Implementation Guidelines**:
- **Transparency**: Disclose AI involvement, explain functionality, show past actions
- **Control**: Enable customization, preferences, and user override
- **Consistency**: Maintain coherent multimodal experiences

### Step 3: Design Conversation Flows

Use `assets/agent-flow-template.md` as a starting point.

**Key Considerations**:

1. **Entry Points**: Define how users reach each flow (direct request, proactive suggestion, handoff)

2. **Intent Recognition**:
   - Identify primary intents
   - Plan disambiguation strategies (see `references/conversational-design-patterns.md`)
   - Handle multi-intent requests
   - Set confidence thresholds

3. **Flow Structure**: Choose appropriate pattern:
   - **Linear**: Simple sequential tasks
   - **Branching**: Multiple paths based on choices
   - **Hub-and-Spoke**: Central menu with independent actions
   - **Conversational**: Natural back-and-forth
   - **Proactive**: Agent-initiated based on triggers

4. **Context Management**:
   - Maintain session context (current state)
   - Leverage user context (preferences, history)
   - Use domain context (data, market state)
   - Track task context (goal, progress)

5. **Turn Design**:
   - Keep agent messages concise but complete
   - Use progressive disclosure for details
   - Provide clear next steps
   - Enable easy interruption/redirection

6. **Confirmation Strategy**:
   - Implicit for low-risk actions
   - Explicit for medium-risk actions
   - Staged for high-risk actions

### Step 4: Apply Domain-Specific Patterns

**For Financial Services** (see `references/financial-services-patterns.md`):

Apply specialized patterns for:
- **Portfolio Management**: Review, analysis, rebalancing
- **Investment Advice**: Research, recommendations, risk assessment
- **Transactions**: Trade execution, transfers, confirmations
- **Risk Communication**: Clear, contextualized risk disclosure
- **Regulatory Compliance**: Required disclaimers, documentation, suitability

Key considerations:
- Always include appropriate risk disclaimers
- Distinguish between information and advice
- Require confirmation for transactions
- Communicate uncertainty and confidence levels
- Provide clear reasoning and data sources
- Enable human advisor handoff for complex decisions

**For Crypto/Blockchain** (see `references/crypto-blockchain-patterns.md`):

Apply specialized patterns for:
- **Wallet Management**: Balances, multi-chain support, security
- **DeFi Operations**: Swaps, liquidity provision, yield farming
- **NFT Interactions**: Viewing, buying, selling collections
- **Transaction Lifecycle**: Gas fees, confirmations, failures
- **Security**: Contract verification, scam prevention, approval management

Key considerations:
- Always display gas costs upfront
- Show transaction costs transparently (gas + protocol fees)
- Explain slippage and price impact
- Warn about security risks (unverified contracts, unlimited approvals)
- Clarify custody (self-custody vs protocol vs exchange)
- Support multi-chain complexity
- Handle transaction failures gracefully

### Step 5: Design Handoffs

Use `assets/handoff-pattern-template.md` to document handoff patterns.

**Identify Handoff Triggers**:
- Complexity exceeds agent capability
- Legal/regulatory requirement
- User explicit request
- High-value/high-risk decision
- Emotional/sensitive situation
- Low confidence in response

**Design Handoff Flow**:

1. **Pre-Handoff**: Gather necessary context
2. **Initiation**: Explain why handoff is occurring
3. **Context Transfer**: Package and transfer all relevant information
4. **Execution**: Smooth transition with clear status
5. **Post-Handoff**: Target acknowledges context and continues

**Key Principles**:
- Set clear expectations (why, who, when)
- Transfer complete context (no repeated information)
- Maintain conversation continuity
- Position as progression, not failure
- Enable return path when appropriate

### Step 6: Evaluate Design

Use `assets/evaluation-checklist.md` for comprehensive evaluation.

Reference `references/evaluation-framework.md` for detailed methodology.

**Key Evaluation Dimensions**:

1. **Effectiveness**: Can users accomplish goals?
2. **Efficiency**: How quickly can goals be achieved?
3. **Learnability**: Is the agent easy to learn?
4. **Trust**: Do users trust recommendations?
5. **Control**: Do users feel in control?
6. **Transparency**: Is agent behavior clear?
7. **Error Handling**: Are errors prevented and recoverable?
8. **Personalization**: Does agent adapt to users?
9. **Accessibility**: Can all users access effectively?
10. **Emotional Intelligence**: Appropriate emotional responses?

**Evaluation Methods**:
- **Heuristic Evaluation**: Expert review against principles (fast, early stage)
- **User Testing**: Observe real users completing tasks (mid-late stage)
- **Analytics Review**: Measure usage patterns and outcomes (live product)
- **Conversation Analysis**: Review transcripts for patterns (ongoing)

### Step 7: Document & Iterate

**Create Design Documentation**:
- Use `assets/agent-flow-template.md` for conversation flows
- Use `assets/handoff-pattern-template.md` for handoff patterns
- Use `assets/design-critique-template.md` for design reviews

**Iterate Based on Findings**:
- Test with real users early and often
- Analyze conversation patterns
- Monitor key metrics (completion rate, satisfaction, error rate)
- Refine based on feedback
- Continuously improve

## Working with This Skill

### Starting a New Design

When starting a new agent design:

1. **Clarify the Brief**: Ask questions to understand:
   - What specific problem is being solved?
   - Who are the users and what do they need?
   - What are the constraints (technical, regulatory, business)?

2. **Load Relevant References**: Based on domain, review:
   - `references/microsoft-agent-ux-principles.md` (always)
   - `references/financial-services-patterns.md` (for financial agents)
   - `references/crypto-blockchain-patterns.md` (for crypto agents)
   - `references/conversational-design-patterns.md` (for conversation design)

3. **Use Templates**: Start with appropriate templates from `assets/`

4. **Apply Principles Systematically**: Work through each principle checking alignment

### Reviewing an Existing Design

When reviewing an existing agent:

1. **Use Design Critique Template**: `assets/design-critique-template.md`

2. **Evaluate Against Principles**: Check alignment with Microsoft agent UX principles

3. **Review Domain Patterns**: Ensure domain-specific patterns are correctly applied

4. **Consider All Dimensions**: Use evaluation framework to assess comprehensively

5. **Provide Specific, Actionable Feedback**:
   - Identify both strengths and issues
   - Explain impact of issues
   - Suggest specific improvements
   - Prioritize recommendations

### Planning Conversation Flows

When designing conversation flows:

1. **Start with User Goals**: What is the user trying to accomplish?

2. **Map Intent to Outcome**: Define success clearly

3. **Identify Decision Points**: Where does the conversation branch?

4. **Plan Error Handling**: What can go wrong and how to recover?

5. **Design for Context**: What information must be maintained?

6. **Include Variations**: Account for different scenarios and user types

7. **Document Thoroughly**: Use flow template to capture complete design

### Evaluating Usability

When conducting usability evaluation:

1. **Choose Appropriate Method**: Heuristic review, user testing, or analytics

2. **Use Evaluation Checklist**: `assets/evaluation-checklist.md`

3. **Test Key Scenarios**: Focus on common and critical tasks

4. **Look for Patterns**: Identify recurring issues

5. **Prioritize Findings**: Classify by severity (critical, high, medium, low)

6. **Provide Clear Recommendations**: Specific, actionable, prioritized

## Best Practices

### Conversation Design
- Lead with key information, use progressive disclosure for details
- Confirm understanding, especially for high-stakes actions
- Provide clear next steps and enable easy exits
- Handle interruptions and topic changes gracefully
- Maintain context across conversational turns
- Use familiar language adapted to user expertise

### Building Trust
- Always disclose AI involvement
- Explain reasoning and show data sources
- Acknowledge uncertainty and limitations
- Provide confidence levels for recommendations
- Enable verification of information
- Be consistent and reliable

### Managing Risk
- Require explicit confirmation for significant actions
- Communicate risk clearly and contextually
- Provide appropriate disclaimers
- Enable human override and handoff
- Document decisions and rationale
- Implement appropriate security measures

### Accessibility
- Support screen readers and keyboard navigation
- Provide text alternatives for visual information
- Use sufficient color contrast
- Enable adjustable text size
- Avoid time pressures
- Support multiple input modalities

### Personalization
- Remember user preferences and patterns
- Adapt communication style appropriately
- Provide relevant, contextualized suggestions
- Respect privacy while personalizing
- Enable user control over personalization
- Learn from interactions

## Common Patterns Quick Reference

### Intent Patterns
- **Informational**: Query, Status, Help
- **Transactional**: Create, Update, Delete, Execute
- **Navigational**: Go to, Back, Reset

### Interaction Models
- **Progressive Disclosure**: Start simple, reveal complexity as needed
- **Guided Discovery**: Step-by-step guidance through complex decisions
- **Proactive Notification**: Surface relevant information without request
- **Collaborative Analysis**: Work together with user to analyze

### Confirmation Patterns
- **Implicit**: Low-risk, acknowledge post-action
- **Explicit**: Medium-risk, preview and confirm
- **Staged**: High-risk, multiple confirmations with full details

### Error Recovery
- **Prevention**: Validate input, require confirmation, provide defaults
- **Clear Communication**: Explain what went wrong simply
- **Recovery Path**: Make it obvious how to fix
- **Context Preservation**: Don't lose user's work

### Handoff Types
- **Agent-to-Human**: Complexity, regulation, explicit request
- **Agent-to-Agent**: Specialization, cross-domain
- **Human-to-Agent**: Routine follow-up, ongoing monitoring

## Resources

This skill includes comprehensive reference materials and templates:

### References (Domain Knowledge)

**`references/microsoft-agent-ux-principles.md`**
Complete Microsoft agent UX design principles covering Agent (Space), Agent (Time), and Agent (Core) with implementation guidelines for Transparency, Control, and Consistency.

**`references/financial-services-patterns.md`**
Specialized patterns for financial services including portfolio management, investment advice, transaction flows, risk communication, regulatory compliance, and trust-building approaches.

**`references/crypto-blockchain-patterns.md`**
Specialized patterns for crypto/blockchain including wallet management, DeFi operations, NFT interactions, gas fee management, multi-chain navigation, security, and scam prevention.

**`references/conversational-design-patterns.md`**
Universal conversation design patterns covering intent recognition, interaction flows, dialogue management, context maintenance, error recovery, confirmations, and multimodal interaction.

**`references/evaluation-framework.md`**
Comprehensive framework for evaluating agent UX across 10 dimensions with multiple evaluation methods, domain-specific criteria, metrics, and continuous improvement processes.

### Assets (Templates for Output)

**`assets/agent-flow-template.md`**
Complete template for documenting agent conversation flows including entry points, detailed turns, variations, error handling, context management, handoffs, proactive behaviors, and examples.

**`assets/evaluation-checklist.md`**
Comprehensive checklist for evaluating agent UX covering all dimensions with severity tracking, recommendations prioritization, and reporting structure.

**`assets/design-critique-template.md`**
Structured template for reviewing agent designs against principles, with sections for strengths, issues, recommendations, and prioritization.

**`assets/handoff-pattern-template.md`**
Detailed template for documenting handoff patterns including trigger conditions, interaction models, context transfer, outcome patterns, variations, and anti-patterns.

## Tips for Success

1. **Start with Principles**: Always ground designs in Microsoft's agent UX principles
2. **Think Conversationally**: Design for natural dialogue, not just command-response
3. **Plan for Failure**: Error handling and recovery are as important as happy paths
4. **Test Early, Test Often**: Get real user feedback as early as possible
5. **Document Thoroughly**: Use templates to capture complete design rationale
6. **Iterate Based on Data**: Let metrics and user feedback drive improvements
7. **Balance Automation and Control**: Empower users, don't override them
8. **Build Trust Through Transparency**: Always explain reasoning and acknowledge limits
9. **Respect Domain Context**: Apply financial or crypto patterns appropriately
10. **Design for Accessibility**: Consider all users from the start

## Anti-Patterns to Avoid

- **Overconfidence**: Never present uncertain information as certain
- **Loss of Control**: Don't force automation or remove user agency
- **Opacity**: Never hide AI involvement or reasoning
- **Collapsing Connections**: Don't replace human interaction unnecessarily
- **Over-Intrusion**: Respect user focus and attention
- **Inconsistency**: Maintain predictable behavior and terminology
- **Poor Error Handling**: Don't leave users stuck or confused
- **Ignoring Context**: Remember and use conversation history
- **One-Size-Fits-All**: Adapt to user expertise and preferences
- **Security Neglect**: Never compromise on security, especially in financial/crypto domains

## Getting Help

When uncertain about design decisions:
- Review relevant reference materials for specific guidance
- Apply evaluation framework to identify potential issues
- Consider creating a design critique using the template
- Test assumptions with users early
- Document decision rationale for future reference
