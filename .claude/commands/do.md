---
allowed-tools: [Read, Edit, Write, Bash, TodoWrite, Glob, Grep]
argument-hint: [task-id]
description: Implement specific task from feature plan with focused execution
model: claude-3-5-sonnet-20241022
---

# Task Implementation - Focused Execution

I'm now switching to **Sonnet model** for efficient, focused implementation.

**Task to implement**: Task #$ARGUMENTS

## Step 1: Load Task Context
Let me find the current feature plan and load the specific task:

!`find ./tasks -name "*.md" -not -name "_*" | head -3`

Let me examine the available tasks to find task #$ARGUMENTS:

## Step 2: Task Analysis
I'll analyze the specific requirements for this task:
- Understand the scope and acceptance criteria
- Identify files that need to be modified or created
- Consider existing code patterns to follow
- Plan the implementation approach

## Step 3: Focused Implementation
I will now implement ONLY the specified task with:
- Clear, maintainable code following project conventions
- Appropriate error handling and edge case consideration
- Proper TypeScript typing (if applicable)
- Comments for non-obvious logic

## Step 4: Implementation Validation
After implementation, I'll:
- Verify the code follows existing patterns
- Check that requirements are met
- Update the task progress in the plan
- Suggest appropriate next actions

## Step 5: Progress Tracking & Next Actions
I'll update the feature plan with:
- Implementation details and decisions made
- Any issues discovered during implementation
- Clear handoff context for next tasks

---

**🔄 Next Action Options**:
- **Task complete**: Use `/test` to validate implementation
- **Multiple tasks remaining**: Continue with `/do [next-task-id]`
- **Large changes**: Consider `/commit [message]` to save progress
- **Implementation issues**: Try `/experiment [hypothesis]` to explore solutions

**💡 Coaching Tip**: Stay focused on just this one task. Resist the urge to implement extra features or "improve" unrelated code!