---
allowed-tools: Read, Write, Glob, Grep, TodoWrite
argument-hint: [feature-name]
description: Create structured feature plan with systematic approach
model: claude-3-opus-20241115
---

# Feature Planning - Systematic Approach

I'm now switching to **Opus model** for deep planning and reasoning.

**Feature to plan**: $ARGUMENTS

Let me create a comprehensive implementation plan for this feature following our systematic approach.

## Step 1: Context Gathering
First, let me understand the current codebase structure and existing patterns:

!`ls -la src/ 2>/dev/null || echo "No src directory found"`

!`find . -name "*.md" -path "./tasks/*" | head -5`

## Step 2: Feature Planning

I'll now create a structured plan that includes:

### User Stories & Acceptance Criteria
- Clear user value proposition
- Specific, testable requirements
- Success metrics

### Technical Approach
- Architecture decisions and rationale  
- Integration with existing systems
- Dependencies and constraints

### Implementation Tasks
- Sequential, implementable steps
- File paths and specific changes
- Estimated complexity

### Testing Strategy
- Unit test requirements
- Integration testing needs
- Quality gates and validation

### Risk Assessment
- Technical risks and mitigation
- Rollback procedures
- Experimental areas

## Step 3: Plan Documentation

I'll write this comprehensive plan to `tasks/$ARGUMENTS.md` for tracking and reference.

## Step 4: Next Action Guidance

Once the plan is complete, I'll provide specific guidance on next steps.

---

**🔄 Next Action**: After reviewing this plan, use `/do 1` to start implementing the first task, or ask for plan refinements if needed.

**💡 Coaching Tip**: This systematic approach prevents over-building and reduces rework. Take time to review and approve before implementation!