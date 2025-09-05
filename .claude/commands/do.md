# Do - Focused Task Implementation

Implement specific task from feature plan with focused execution and progress tracking.

## Instructions

1. **Load Task Context**
   - Find current feature plan in tasks/ directory
   - Load specific task by ID number
   - Display task requirements and scope

2. **Analyze Implementation Approach**
   - Understand task scope and acceptance criteria
   - Identify files that need modification or creation
   - Consider existing code patterns to follow
   - Plan focused implementation strategy

3. **Execute Implementation**
   - Implement ONLY the specified task scope
   - Follow existing code patterns and conventions
   - Add appropriate error handling and validation
   - Include proper comments for complex logic

4. **Update Progress**
   - Mark task as completed in the feature plan
   - Document decisions made during implementation
   - Note any issues discovered
   - Suggest next logical task or action

**Task to implement**: Task #$ARGUMENTS

**🎯 Starting focused implementation...**

## Step 1: Task Context Loading

**Finding current feature plans:**
!`echo "📋 Available feature plans:"
find ./tasks -name "*.md" -not -name "_*" 2>/dev/null | while read task; do
  echo "  📄 $(basename "$task" .md): $(head -1 "$task" 2>/dev/null | sed 's/^# //')"
done || echo "  ⚠️  No feature tasks found"

echo -e "\n🔍 Looking for task #$ARGUMENTS..."`

## Step 2: Task Analysis

**Understanding the implementation requirements:**

I'll analyze the specific requirements for task #$ARGUMENTS:
- **Scope**: What exactly needs to be implemented
- **Files**: Which files need to be modified or created  
- **Patterns**: Existing code patterns to follow
- **Dependencies**: What other code this interacts with

## Step 3: Focused Implementation

**Implementing task #$ARGUMENTS with:**
- Clear, maintainable code following project conventions
- Appropriate error handling for edge cases
- Proper TypeScript typing (if applicable)
- Comments explaining non-obvious business logic
- Single responsibility and focused scope

## Step 4: Implementation Validation

**After implementation, I'll:**
- Verify code follows existing patterns
- Check that acceptance criteria are met
- Test basic functionality works as expected
- Update task progress in the feature plan

## Step 5: Progress Update & Next Actions

**Documenting completion:**
- Mark task #$ARGUMENTS as completed
- Record implementation decisions made
- Note any issues or technical debt discovered
- Provide clear context for next tasks

---

**🔄 Next Action Recommendations:**

- **Task completed successfully**: Use `/test` to validate implementation works correctly
- **Multiple tasks remaining**: Continue with `/do [next-task-id]` for sequential implementation
- **Significant changes made**: Consider `/commit [message]` to save progress before continuing
- **Implementation challenges**: Try `/experiment [hypothesis]` to explore alternative approaches
- **Ready for review**: Use `/review` to get comprehensive code quality feedback

**💡 Coaching Tip**: Staying focused on one task at a time prevents scope creep and ensures each piece is thoroughly implemented. Resist the urge to "improve" unrelated code - that can be a separate task!