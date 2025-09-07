# Implementation Guide

## Live Task Implementation & Plan Updates

**CRITICAL: Update the plan as you work - keep `.claude/tasks/TASK_NAME.md` current**

### 1. Load Task Context
- Review the approved plan in `.claude/tasks/TASK_NAME.md`
- Understand current task scope and acceptance criteria
- Identify specific files that need modification or creation

### 2. Analyze Implementation Approach
- Follow existing code patterns and conventions
- Plan focused implementation strategy
- Consider error handling and edge cases

### 3. Execute Implementation
- Implement ONLY the specified task scope
- Add appropriate error handling and validation
- Follow project coding standards
- Include comments for complex logic only

### 4. MANDATORY: Update Plan During Work
- **Update task status**: Mark tasks in progress/completed in the plan
- **Document all changes**: Append detailed descriptions to "Implementation Notes"
- **Record decisions**: Add reasoning for implementation choices made
- **Note discoveries**: Document any issues found or scope changes needed
- **Include file paths**: Specify exactly what files were modified/created
- **Handoff context**: Provide clear information for subsequent tasks

## Implementation Best Practices

### Code Quality
- Follow existing patterns in the codebase
- Use proper TypeScript typing (if applicable)
- Write clear, maintainable code
- Add error handling for edge cases

### Scope Management
- Stay focused on single task at a time
- Resist urge to "improve" unrelated code
- Avoid scope creep during implementation
- Save separate improvements as new tasks

### Documentation
- Update task progress in real-time
- Record implementation decisions
- Note technical debt discovered
- Provide clear context handoffs

## Implementation Workflow with Live Plan Updates

1. **Start Task**: Load context from `.claude/tasks/TASK_NAME.md`
2. **Update Plan**: Mark current task as "in progress" 
3. **Implement**: Write focused, quality code
4. **Document Changes**: Append detailed changes to Implementation Notes section
5. **Complete Task**: Mark as done and add file paths/decisions made
6. **Validate**: Test basic functionality works
7. **Update & Handoff**: Prepare context for next task or engineer

## Plan Update Examples

**Task Status Updates:**
```markdown
## Implementation Progress (Updated During Work)
- [x] Task 1: Set up database models - COMPLETED 
  - Created `models/User.js` and `models/Product.js`
  - Added validation schemas and relationships
- [🔄] Task 2: Implement API endpoints - IN PROGRESS
  - Working on user authentication routes
```

**Implementation Notes Additions:**
```markdown
## Implementation Notes (Added During Work)

### 2024-01-15: Database Model Setup (Task 1)
- **Files modified**: `models/User.js`, `models/Product.js`, `config/database.js`
- **Key decisions**: Used Mongoose over Sequelize due to existing MongoDB setup
- **Issues discovered**: User schema needed additional email validation field
- **Next steps**: API endpoints can now reference these models safely

### 2024-01-15: API Authentication (Task 2 - Partial)
- **Files modified**: `routes/auth.js`, `middleware/authenticate.js`
- **Current status**: Login/signup endpoints working, password reset pending
- **Blocker**: Need to research best JWT refresh token patterns (suggest using Task tool)
- **Files ready for next engineer**: Routes structure in place, just needs token logic
```

## Quality Checks
- Code follows project conventions
- Acceptance criteria are met
- Basic functionality tested
- No unintended side effects