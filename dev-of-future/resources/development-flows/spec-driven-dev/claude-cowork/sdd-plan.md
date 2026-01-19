# Unified Spec-Driven Development (SDD) Workflow

## Overview

Spec-Driven Development represents a fundamental architectural shift in software engineering where **specifications become the permanent source of truth** rather than code. This workflow synthesizes insights from multiple SDD frameworks and approaches to create a unified, practical methodology for AI-assisted development.

## Core Philosophy

### The Inversion Principle
Traditional software development assumes code becomes truth over time. SDD inverts this by ensuring specifications remain authoritative, and runtime systems continuously conform to declared intent.

### Three Implementation Levels

1. **Spec-First**: Write a well-thought-out specification before development
2. **Spec-Anchored**: Maintain the spec after completion for evolution and maintenance
3. **Spec-as-Source**: The spec is the main source; humans edit only the spec, never the code

## The Five-Layer Architecture

SDD operates as an architectural pattern with five distinct layers:

### 1. Specification Layer
- **Purpose**: Authoritative definition of system behavior
- **Format**: Natural language + structured constraints
- **Owner**: Human developers with AI assistance
- **Artifacts**: Requirements, technical specifications, implementation plans

### 2. Generation Layer
- **Purpose**: Transform declarative intent into executable form
- **Mechanism**: AI agents interpret specs and generate code
- **Process**: Pattern-matching with human-approved constraints

### 3. Artifact Layer
- **Purpose**: Contains concrete outputs of generation
- **Contents**: Source code, tests, documentation, configurations
- **Status**: Derived (not authoritative)

### 4. Validation Layer
- **Purpose**: Enforce continuous alignment between intent and execution
- **Methods**: Drift detection, automated testing, spec-to-code verification
- **Importance**: Mandatory architectural capability (not optional)

### 5. Runtime Layer
- **Purpose**: The operational system itself
- **Constraint**: Must continuously conform to specification
- **Feedback**: Informs spec evolution through operational insights

## The Three-Artifact Workflow

Every development run proceeds through three sequential artifacts:

### Artifact 1: Requirements Document
**Purpose**: Capture the "what" and "why"

**Contents**:
- User story or feature description
- Edge cases and constraints
- Success criteria and acceptance tests
- Non-functional requirements

**Process**:
- AI agent drafts initial requirements
- Humans confirm alignment with reality
- Team reviews for completeness

**Key Principle**: Reality check against actual system behavior

### Artifact 2: Technical Specification
**Purpose**: Define the "how" at architectural level

**Contents**:
- Architecture and design patterns
- Data flows and state management
- Impacted files and modules
- API contracts and interfaces
- Dependencies and constraints

**Process**:
- AI agent proposes technical approach
- Reviewers tighten constraints
- Add missing context from system knowledge
- Lock in trade-offs (e.g., "ship fast" vs "refactor first")

**Key Principle**: Prioritization and accountability

### Artifact 3: Implementation Plan
**Purpose**: Define exact execution steps

**Contents**:
- Step-by-step implementation tasks
- Test-driven loops (RED/GREEN/VERIFY)
- File-level change instructions
- Validation checkpoints

**Process**:
- AI agent creates detailed checklist
- Humans approve before execution begins
- Each step references the approved spec

**Key Principle**: Only after plan approval does the agent touch the repository

## Phased Execution Model

### Phase Structure
Work proceeds in controlled phases, not all-at-once execution:

1. **Subset Execution**: Start with tasks 1-2, not entire plan
2. **Progress Marking**: Update implementation plan with completion status
3. **Review Gate**: Review code changes, run tests, confirm correctness
4. **Complexity Handling**: Update task list if unexpected complexity emerges
5. **Pacing Control**: Maintain rhythm and quality over speed

### The RED/GREEN/VERIFY Loop
For each implementation task:

1. **RED**: Write failing test based on spec
2. **GREEN**: Implement minimum code to pass test
3. **VERIFY**: Validate against specification
4. **COMMIT**: Mark task complete only when verified

## Human-AI Collaboration Model

### Why Humans Are Essential

**Reality Anchoring**:
- AI agents excel at pattern matching
- Humans prevent hallucination of non-existent constraints
- Quick human review keeps plans grounded in actual system behavior

**Strategic Decision-Making**:
- Specs are where trade-offs get locked in
- Humans decide priorities (speed vs quality, features vs refactoring)
- AI agents carry decisions through execution

**Contract Enforcement**:
- Reviewed spec becomes a contract
- If output drifts, can diagnose whether issue was plan or execution
- Enables clear accountability

### The Review Gates

**Gate 1 - Requirements Review**:
- Does this match what we actually need?
- Are edge cases comprehensive?
- Are success criteria measurable?

**Gate 2 - Technical Specification Review**:
- Is the architecture sound?
- Are we missing critical context?
- Do trade-offs align with priorities?

**Gate 3 - Implementation Plan Review**:
- Are steps detailed enough?
- Is the testing strategy sufficient?
- Can we execute this incrementally?

**Gate 4 - Execution Review** (per phase):
- Does code match specification?
- Do tests pass and provide coverage?
- Is drift detected and resolved?

## Workflow Integration

### Starting a New Feature

```
1. Capture Intent
   └─> Create requirements.md (user story, constraints, success criteria)
   └─> AI drafts, humans review and refine
   └─> GATE 1: Approve requirements

2. Design Architecture
   └─> Create spec.md (technical approach, architecture, impacted files)
   └─> AI proposes, humans add context and constraints
   └─> GATE 2: Approve technical specification

3. Plan Implementation
   └─> Create tasks.md (step-by-step plan with RED/GREEN/VERIFY)
   └─> AI creates checklist, humans review for completeness
   └─> GATE 3: Approve implementation plan

4. Execute in Phases
   └─> Work on subset (tasks 1-2)
   └─> Mark progress in tasks.md
   └─> Run tests and validation
   └─> GATE 4: Review before next phase
   └─> Repeat until complete

5. Maintain Spec-Anchored State
   └─> Keep all three artifacts updated
   └─> Use for future evolution and maintenance
   └─> Spec remains source of truth
```

### Iterative Refinement

SDD supports iterative development through:

- **Small Work Packages**: Specs can be scoped to small, incremental changes
- **Continuous Validation**: Drift detection ensures alignment at each step
- **Living Documentation**: Specs evolve with the codebase
- **Context Preservation**: "Whys" preserved alongside "whats"

## Anti-Patterns to Avoid

### Over-Specification
**Problem**: Creating illusion of completeness through excessive detail
**Solution**: Focus on intent and constraints, not implementation minutiae

### Skipping Human Review
**Problem**: Without review, you're back to "vibe coding"
**Solution**: Never skip the review gates; they are non-negotiable

### Spec-Code Divergence
**Problem**: Specs become stale and drift from reality
**Solution**: Treat drift detection as mandatory architectural capability

### All-at-Once Execution
**Problem**: Loss of control, difficult debugging, quality issues
**Solution**: Always work in phases with review gates

### Wrong Abstraction Level
**Problem**: Specs at implementation level rather than intent level
**Solution**: Preserve the "why" and constraints, let AI determine "how"

## Context Engineering Integration

SDD is enhanced by context engineering principles:

### Start with Intent
- Begin with clear problem statement and desired outcome
- Let spec capture intent, not just requirements

### Keep Context Current
- Specs should evolve with the codebase
- Operational feedback informs spec refinement
- Documentation and specs stay synchronized

### Preserve the Whys
- Document decision rationale, not just decisions
- Capture trade-offs and constraints
- Explain architectural choices and their context

## Drift Detection Mechanisms

Drift detection is **mandatory**, not optional:

### Continuous Validation
- Automated tests verify spec compliance
- Static analysis checks architectural rules
- Runtime monitoring detects behavioral drift

### Enforcement Points
- Pre-commit hooks validate against spec
- CI/CD pipeline includes spec-compliance checks
- Deployment gates require validation sign-off

### Feedback Loop
- Detected drift triggers spec review
- Either code is corrected or spec is updated
- System remains aligned with declared intent

## Tool-Agnostic Framework

This workflow is intentionally tool-agnostic and can be implemented with:

- **GitHub Spec-Kit**: GitHub-native SDD implementation
- **JetBrains Junie**: IDE-integrated SDD workflow
- **LeanSpec**: Lightweight framework approach
- **OpenSpec**: Open-source spec management
- **Custom Tools**: Any system supporting the three-artifact pattern

## Key Success Factors

### 1. Specification Quality
- Clear, unambiguous language
- Comprehensive but not overly verbose
- Focused on intent and constraints

### 2. Human Engagement
- Active participation in all review gates
- Strategic decision-making on trade-offs
- Continuous oversight and refinement

### 3. Iterative Discipline
- Small, controlled phases
- Regular validation checkpoints
- Continuous alignment verification

### 4. Architectural Enforcement
- Drift detection as infrastructure
- Validation as mandatory capability
- Specs as permanent source of truth

### 5. Context Preservation
- Document the "why" not just the "what"
- Maintain living documentation
- Ensure specs evolve with system

## The SDD Promise

When properly implemented, Spec-Driven Development delivers:

- **Team Alignment**: Single source of truth eliminates translation loss
- **Logic Consistency**: Unified spec prevents divergent implementations
- **Full Traceability**: User story → spec → tests → code → runtime
- **Quality at Speed**: AI velocity with human-governed quality
- **Maintainability**: Specs enable long-term system evolution

## Relationship to Other Methodologies

### SDD and Agile
- Compatible with iterative development
- Specs replace extensive upfront design
- Small work packages align with sprints
- Tests occupy same conceptual space as specs

### SDD and TDD/BDD
- Specs include test-driven loops
- RED/GREEN/VERIFY integrates TDD principles
- Behavior specifications align with BDD
- Specs are design documentation

### SDD and Traditional SDLC
- Modernizes PRD → Design → Implementation flow
- Adds AI-assistance and continuous validation
- Maintains rigor while increasing velocity
- Preserves human oversight and decision-making

## Getting Started

### Minimum Viable SDD

1. **Start Spec-First**: Write simple requirements before coding
2. **Add Human Review**: Review AI-generated specs before execution
3. **Work in Phases**: Execute subset, review, repeat
4. **Track Progress**: Maintain tasks.md with completion status
5. **Validate Continuously**: Run tests after each phase

### Progression Path

1. **Spec-First**: Begin with specifications
2. **Add Gates**: Implement review checkpoints
3. **Spec-Anchored**: Maintain specs post-completion
4. **Add Validation**: Implement drift detection
5. **Spec-as-Source**: Evolve to spec-only editing

## Conclusion

Spec-Driven Development is not a methodology—it's an architectural pattern that inverts the traditional relationship between code and intent. By making specifications authoritative and treating code as derived artifacts, SDD enables AI-assisted development at enterprise scale while maintaining human oversight, quality, and strategic control.

The key insight: **Speed at the code level does not translate to speed across the SDLC unless the system governs its output**. SDD provides that governance through specifications, review gates, phased execution, and continuous validation.

---

*This workflow synthesizes insights from Martin Fowler, InfoQ, Zencoder, JetBrains, and the broader SDD practitioner community.*
