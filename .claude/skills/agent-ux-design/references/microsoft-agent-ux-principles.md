# Microsoft Agent UX Design Principles

This document contains Microsoft's core principles and guidelines for designing agent experiences, synthesized from designers and user researchers across Microsoft.

## Core Design Principles

### Agent (Space): Environment & Context

The environment where agents operate across physical and digital worlds.

#### Connecting, Not Collapsing
- **Principle**: Help connect people to other people, events, and actionable knowledge
- **Goal**: Enable collaboration and connection rather than replacing human interaction
- **Application**: Design agents that facilitate relationships and enhance social connections
- **Anti-pattern**: Agents that isolate users or replace meaningful human contact

#### Easily Accessible Yet Occasionally Invisible
- **Principle**: Agent operates in the background, surfacing only when contextually relevant
- **Goal**: Reduce intrusion while maintaining availability
- **Application**:
  - Support multimodal inputs/outputs across devices
  - Use subtle notifications rather than interruptive alerts
  - Allow users to invoke the agent when needed
- **Anti-pattern**: Constantly visible agents that demand attention

### Agent (Time): Temporal Dynamics

How agents function across past, present, and future.

#### Past: Historical Context & Memory
- **Principle**: Analyze beyond isolated events to create connections from past interactions
- **Goal**: Enable agents to actively reflect on memory and learn from history
- **Application**:
  - Track user preferences and patterns over time
  - Reference previous conversations and decisions
  - Build contextual understanding from historical data
- **Example**: "Based on your previous investments in tech stocks..."

#### Now: Dynamic Contextual Information
- **Principle**: Deliver information through dynamic cues rather than static notifications
- **Goal**: Gradually increase interaction complexity as context develops
- **Application**:
  - Provide real-time contextual assistance
  - Adapt responses based on current user state
  - Start simple, add complexity as needed
- **Example**: Showing relevant market data when user is reviewing portfolio

#### Future: Adaptive Evolution
- **Principle**: Adapt to new devices, platforms, user behaviors continuously
- **Goal**: Evolve through continuous interaction and learning
- **Application**:
  - Design for platform flexibility
  - Plan for behavioral changes
  - Build learning mechanisms into agent systems
- **Example**: Agent adapts to new crypto exchanges as user explores them

### Agent (Core): Foundational Elements

#### Embrace Uncertainty, Establish Trust
- **Principle**: Uncertainty is inherent; transparency and user control are essential
- **Goal**: Build trust through honesty about capabilities and limitations
- **Application**:
  - Humans control when agent is on/off
  - Agent status is clearly visible
  - Acknowledge when uncertain or when human judgment is needed
  - Provide confidence levels for recommendations
- **Example**: "I'm 85% confident in this investment analysis, but market volatility is high. Consider consulting your financial advisor."

## Implementation Guidelines

Three pillars govern how principles are executed in practice.

### 1. Transparency

**Core Requirement**: Users must understand what the agent is doing and why.

#### Required Elements:
- **AI Disclosure**: Clearly indicate when AI is involved
- **Functionality Explanation**: Explain how the agent works
- **Past Actions**: Show history of agent decisions and recommendations
- **Feedback Mechanisms**: Enable users to provide input on agent performance
- **Modification Access**: Allow users to adjust system behavior

#### Financial Services Applications:
- Display reasoning behind investment recommendations
- Show data sources used for analysis
- Provide audit trails for transactions
- Explain risk calculations transparently
- Document compliance with regulations

#### Crypto/Blockchain Applications:
- Show on-chain verification steps
- Explain smart contract interactions
- Display gas fee calculations
- Provide transaction history and traceability
- Clarify custody and security mechanisms

### 2. Control

**Core Requirement**: Users must have agency over the agent's behavior.

#### Required Capabilities:
- **Customization**: Allow users to tailor agent behavior
- **Preferences**: Enable detailed preference specification
- **Personalization**: Support individual user needs
- **Data Management**: Provide file/data deletion and modification
- **Intervention**: Allow users to override agent decisions

#### Financial Services Applications:
- Set risk tolerance levels
- Define investment criteria and constraints
- Control notification frequency
- Manage data sharing permissions
- Override automated trading decisions

#### Crypto/Blockchain Applications:
- Set transaction approval workflows
- Define security thresholds
- Control wallet interactions
- Manage protocol preferences
- Configure gas price limits

### 3. Consistency

**Core Requirement**: Maintain coherent experiences across contexts.

#### Required Elements:
- **Multimodal Experiences**: Consistent across devices and platforms
- **Familiar UI Patterns**: Use standard interface elements
- **Cognitive Load Reduction**: Keep responses concise and clear
- **Visual Consistency**: Maintain consistent icons, colors, terminology
- **Behavioral Consistency**: Predictable agent responses

#### Implementation Examples:
- Standard icons (paperclip for files, image icon for graphics)
- Consistent terminology across platforms (e.g., "portfolio" not "holdings" in one place and "assets" in another)
- Uniform interaction patterns (similar swipe/tap/voice commands)
- Coherent brand voice and personality

## Core Agent Purposes

Agents should serve these fundamental goals:

### 1. Broaden Human Capacities
- Support brainstorming and ideation
- Enable problem-solving at scale
- Provide automation for repetitive tasks
- Amplify human decision-making capabilities

### 2. Fill Knowledge Gaps
- Help users get up-to-speed on complex domains
- Provide translation between technical and plain language
- Offer context-specific expertise
- Bridge understanding gaps

### 3. Facilitate Collaboration
- Support individual working preferences
- Enable team coordination
- Connect people with relevant experts
- Enhance communication flows

### 4. Make Users Better Versions of Themselves
- Provide coaching and guidance
- Support skill development and upskilling
- Assist with emotional regulation
- Help achieve personal and professional goals

## Anti-Patterns to Avoid

### Diminishing Human Value
- Don't position agent as replacement for human judgment
- Avoid creating dependency on agent recommendations
- Don't remove human agency from critical decisions

### Collapsing Connections
- Don't isolate users from other people
- Avoid replacing social interactions unnecessarily
- Don't eliminate collaborative opportunities

### Over-Intrusion
- Avoid constant notifications
- Don't demand attention when not needed
- Respect user's focus and flow states

### Opacity
- Never hide agent involvement
- Don't obscure reasoning or data sources
- Avoid unexplained recommendations or actions

### Loss of Control
- Don't force agent interactions
- Avoid locking users into agent-determined paths
- Never make irreversible actions without confirmation
