# Plan - Structured Feature Planning

Create comprehensive implementation plan for a new feature with systematic approach and approval gate.

## Instructions

1. **Gather Context**
   - Examine current codebase structure and patterns
   - Review existing similar features
   - Identify integration points and constraints

2. **Create Structured Plan**
   - Define clear user stories with acceptance criteria
   - Design technical approach with architecture decisions
   - Break down into sequential, implementable tasks
   - Plan testing strategy and quality gates
   - Assess risks and mitigation strategies

3. **Document Plan**
   - Write comprehensive plan to tasks/[feature-name].md
   - Include file paths and specific implementation details
   - Set clear success metrics and validation criteria

4. **Request Approval**
   - Present plan for review and feedback
   - Suggest refinements if needed
   - Get explicit approval before implementation

**Feature to plan**: $ARGUMENTS

**🎯 Starting systematic planning process...**

## Step 1: Context Analysis

**Current codebase structure:**
!`echo "📁 Project structure:"
ls -la src/ 2>/dev/null || echo "  No src/ directory found"
ls -la components/ 2>/dev/null || echo "  No components/ directory found"  
ls -la pages/ 2>/dev/null || echo "  No pages/ directory found"
echo -e "\n📋 Existing tasks:"
find ./tasks -name "*.md" -not -name "_*" 2>/dev/null | head -5 || echo "  No existing feature tasks found"`

**Existing patterns to follow:**
!`echo "🔍 Code patterns analysis:"
find . -name "*.js" -o -name "*.ts" -o -name "*.tsx" -o -name "*.jsx" 2>/dev/null | head -5 | while read file; do
  echo "  📄 Found: $file"
done
echo "📦 Package setup:"
[ -f "package.json" ] && echo "  ✅ Node.js project detected" || echo "  ⚠️  No package.json found"`

## Step 2: Feature Planning

I'll now create a comprehensive plan for **$ARGUMENTS** that includes:

### 🎯 User Stories & Value
- **As a user, I want** [clear goal] **so that** [business value]
- **Acceptance criteria**: Specific, testable requirements
- **Success metrics**: How we measure success

### 🏗️ Technical Approach  
- **Architecture decisions**: How it fits with existing code
- **Data flow**: Input → processing → output
- **Integration points**: What existing systems it connects to
- **Dependencies**: What needs to be built or installed

### 📋 Implementation Tasks
I'll break this into specific, sequential tasks:
1. [Task 1 with file paths and specifics]
2. [Task 2 with clear deliverables]
3. [Task 3 with testing requirements]

### 🧪 Testing Strategy
- **Unit tests**: For core functionality
- **Integration tests**: For system interactions  
- **User acceptance**: For feature validation
- **Quality gates**: What must pass before deployment

### ⚠️ Risks & Mitigations
- **Technical risks**: Potential blockers and solutions
- **Business risks**: Impact and mitigation strategies
- **Rollback plan**: How to undo if needed

## Step 3: Plan Documentation

Writing comprehensive plan to **`tasks/$ARGUMENTS.md`**...

## Step 4: Approval Gate

**📋 Plan Summary:** [I'll provide a concise summary of the plan]

**🔄 Next Action**: Please review the plan above. When you approve, I'll suggest `/do 1` to start implementing the first task.

**💡 Coaching Tip**: Taking time to plan systematically prevents over-building and reduces rework. This upfront investment saves significant time during implementation!