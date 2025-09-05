---
allowed-tools: Read, Bash(git:*), Write, Grep, Glob, TodoWrite
description: Comprehensive code quality analysis with systematic checklist
model: claude-3-opus-20241115
---

# Comprehensive Code Quality Review

I'm now switching to **Opus model** for thorough analysis and systematic quality assessment.

## Step 1: Review Scope Analysis

Let me examine what changes need to be reviewed:

### Current Git Status
!`if git rev-parse --git-dir > /dev/null 2>&1; then
  echo "📊 Git Status:"
  git status --porcelain
  
  echo -e "\n📝 Staged Changes:"  
  git diff --cached --stat 2>/dev/null || echo "No staged changes found"
  
  echo -e "\n📋 Changed Files:"
  git diff --cached --name-only 2>/dev/null || echo "No files in staging area"
  
  echo -e "\n🔍 Recent Commits for Context:"
  git log --oneline -3 2>/dev/null || echo "No recent commits"
else
  echo "⚠️  No git repository found. I'll review the current codebase structure instead."
  echo "📁 Project structure:"
  find . -type f -name "*.js" -o -name "*.ts" -o -name "*.tsx" -o -name "*.jsx" | head -10
fi`

### Lines of Code Impact
!`if git rev-parse --git-dir > /dev/null 2>&1; then
  LINES_CHANGED=$(git diff --cached --stat 2>/dev/null | tail -1 | grep -oE '[0-9]+' | head -1 || echo "0")
  FILES_CHANGED=$(git diff --cached --name-only 2>/dev/null | wc -l || echo "0")
  echo "📊 Review Scope: $FILES_CHANGED files, ${LINES_CHANGED:-0} lines changed"
  
  if [ "${LINES_CHANGED:-0}" -gt 500 ]; then
    echo "⚠️  Large changeset detected. Consider reviewing in smaller chunks."
  fi
fi`

## Step 2: Systematic Quality Analysis

Now I'll conduct a comprehensive review using my systematic checklist:

### Code Structure & Quality Assessment
Let me analyze the code structure, naming, and organization:

!`if git diff --cached --name-only 2>/dev/null | head -1 > /dev/null; then
  echo "🔍 Analyzing code changes..."
  git diff --cached 2>/dev/null | head -50 || echo "No staged changes to review"
else
  echo "ℹ️  No specific changes to review. I'll provide general codebase feedback."
fi`

### Detailed Quality Checklist

I'm now performing a systematic analysis of:

#### ✅ **Code Quality Standards**
- Function size and single responsibility principle
- Clear, descriptive naming conventions
- Code duplication and DRY principles
- Proper error handling and edge cases
- Meaningful comments for complex logic

#### ✅ **Testing & Reliability**
- Unit test presence and coverage
- Edge case and error condition testing
- Integration point validation
- Test maintainability and clarity

#### ✅ **Security & Safety**
- No exposed secrets or credentials
- Input validation and sanitization
- Authentication and authorization checks
- Protection against common vulnerabilities

#### ✅ **Performance & Maintainability**
- Efficient algorithms and data structures
- Database query optimization (if applicable)
- Memory usage and resource management
- Adherence to project conventions

#### ✅ **Accessibility & UX** (when applicable)
- Semantic HTML and ARIA labels
- Keyboard navigation support
- Color contrast and responsive design
- User-friendly error handling

## Step 3: Review Results & Recommendations

Based on my systematic analysis, here are my findings:

### 🎯 **Overall Assessment**
[I'll provide specific feedback based on the actual code being reviewed]

### 📝 **Specific Recommendations**
[Detailed, actionable suggestions with file/line references]

### 🏆 **What's Working Well**
[Positive observations and good practices to highlight]

### ⚠️ **Areas for Improvement**
[Prioritized list of issues to address]

---

**🔄 Next Action Based on Review Results**:

- **✅ Review Approved**: Ready to `/commit [message]` these high-quality changes
- **⚠️ Minor Issues**: Address the suggestions above, then `/commit` when ready
- **❌ Major Issues**: Fix critical problems first, then `/review` again for validation
- **🧪 Uncertain Areas**: Use `/experiment [hypothesis]` to test risky approaches

**💡 Coaching Tip**: Systematic code review catches issues early and builds quality habits. Even small improvements compound over time to create better codebases!