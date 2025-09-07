# Feature Planning Guide

## Pre-Implementation Planning Requirements

**CRITICAL: Always start in planning mode before any implementation work**

### 1. Gather Context & Research
- Examine current codebase structure and patterns
- Review existing similar features
- Identify integration points and constraints
- **Research external dependencies**: Use Task tool to research any packages, APIs, or technologies needed
- Get latest knowledge on unfamiliar libraries or concepts

### 2. Create Detailed Implementation Plan
- **User Stories**: Define clear goals with acceptance criteria
- **Technical Approach**: Design with architecture decisions and reasoning
- **Task Breakdown**: Sequential, implementable tasks with specific file paths
- **Dependencies**: List all packages, APIs, or external resources needed
- **Testing Strategy**: Plan validation and quality gates
- **Risk Assessment**: Identify risks and mitigation strategies

### 3. Document Complete Plan
- **Write to**: `.claude/tasks/TASK_NAME.md` (use descriptive task name)
- Include detailed reasoning behind technical decisions
- Provide specific file paths for each implementation task
- Set clear success metrics and validation criteria

### 4. MANDATORY: Get Approval Before Implementation
- Present plan for review and feedback
- **Do not start implementation until explicit approval received**
- Refine plan based on feedback if needed
- Only proceed after user approves the approach

## Planning Template

**Save to**: `.claude/tasks/TASK_NAME.md`

```markdown
# Task: [Descriptive Name]

## User Stories & Value
- **As a user, I want** [goal] **so that** [value]
- **Acceptance criteria**: [testable requirements]
- **Success metrics**: [how to measure success]

## Research & Dependencies
- **External packages/APIs needed**: [list with versions if known]
- **Knowledge gaps researched**: [what was researched using Task tool]
- **Key findings**: [important insights from research]

## Technical Approach & Reasoning
- **Architecture decision**: How it fits with existing code and WHY
- **Data flow**: Input → processing → output
- **Integration points**: What systems it connects to and HOW
- **Implementation reasoning**: Why this approach over alternatives

## Detailed Implementation Tasks
1. **[Task 1]**: [specific actions] - Files: `path/to/file.ext`
2. **[Task 2]**: [clear deliverables] - Files: `path/to/file.ext` 
3. **[Task 3]**: [testing requirements] - Files: `test/path.test.ext`

## Testing Strategy
- **Unit tests**: Core functionality validation
- **Integration tests**: System interactions
- **User acceptance**: Feature validation criteria

## Risks & Mitigations
- **Technical risks**: Potential blockers and solutions
- **Business risks**: Impact assessment and mitigation
- **Rollback plan**: How to undo changes if needed

---
## Implementation Progress (Updated During Work)
- [ ] Task 1: [Status and details will be added during implementation]
- [ ] Task 2: [Status and details will be added during implementation]  
- [ ] Task 3: [Status and details will be added during implementation]

## Implementation Notes (Added During Work)
[Detailed descriptions of changes, file paths, discovered issues, and decisions will be appended here as work progresses]
```

## MVP Mindset - Don't Overplan
- Focus on core value delivery first
- Avoid over-engineering and gold-plating
- Plan enough detail to start, refine as you learn
- Get feedback early and often
- **Think minimum viable implementation**