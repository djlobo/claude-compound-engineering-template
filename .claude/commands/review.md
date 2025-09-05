# Review - Comprehensive Code Quality Analysis

Perform systematic code quality assessment with detailed checklist and actionable feedback.

## Instructions

1. **Analyze Review Scope**
   - Examine current git changes and staged files
   - Assess size and complexity of changes
   - Provide context on what's being reviewed

2. **Systematic Quality Assessment** 
   - Run comprehensive quality checklist covering all critical areas
   - Check code structure, testing, security, performance, accessibility
   - Provide specific findings with file/line references

3. **Generate Actionable Feedback**
   - Categorize issues by severity (critical, important, nice-to-have)
   - Provide specific improvement suggestions
   - Highlight what's working well

4. **Recommend Next Actions**
   - Give clear approval/rejection status
   - Suggest specific steps to address issues
   - Provide guidance on when to re-review

**🔍 Starting comprehensive code quality review...**

## Step 1: Review Scope Analysis

**Examining changes to review:**
!`echo "📊 Review Scope Analysis:"

if git rev-parse --git-dir > /dev/null 2>&1; then
  echo "✅ Git repository detected"
  
  echo -e "\n📝 Current Status:"
  git status --porcelain
  
  echo -e "\n📋 Staged Changes:"  
  git diff --cached --stat 2>/dev/null || echo "  No staged changes found"
  
  echo -e "\n📄 Files to Review:"
  git diff --cached --name-only 2>/dev/null || echo "  No files in staging area"
  
  echo -e "\n📊 Change Impact:"
  LINES_CHANGED=$(git diff --cached --stat 2>/dev/null | tail -1 | grep -oE '[0-9]+' | head -1 || echo "0")
  FILES_CHANGED=$(git diff --cached --name-only 2>/dev/null | wc -l || echo "0")
  echo "  Files: $FILES_CHANGED | Lines: ${LINES_CHANGED:-0}"
  
  if [ "${LINES_CHANGED:-0}" -gt 500 ]; then
    echo "  ⚠️  Large changeset - consider reviewing in smaller chunks"
  fi

  echo -e "\n🔍 Recent Context (last 3 commits):"
  git log --oneline -3 2>/dev/null || echo "  No recent commits"
else
  echo "⚠️  No git repository found"
  echo "📁 Reviewing current project structure instead"
  ls -la | head -10
fi`

## Step 2: Systematic Quality Analysis

**Performing comprehensive review using systematic checklist:**

### Code Structure & Quality Assessment
!`echo "🔍 Analyzing code structure and quality..."

if git diff --cached --name-only 2>/dev/null | head -1 > /dev/null; then
  echo "📄 Reviewing code changes:"
  git diff --cached 2>/dev/null | head -100 || echo "No changes to analyze"
else
  echo "ℹ️  No specific changes staged - providing general project feedback"
  find . -name "*.js" -o -name "*.ts" -o -name "*.tsx" -o -name "*.jsx" | head -3
fi`

### Systematic Quality Checklist

**📋 Comprehensive Review Areas:**

#### ✅ **Code Quality Standards**
- **Function Size**: Are functions focused and reasonably sized (< 50 lines)?
- **Naming**: Are variables, functions, and classes clearly named?
- **DRY Principle**: Is there unnecessary code duplication?  
- **Error Handling**: Are errors handled gracefully with clear messages?
- **Comments**: Are complex logic sections explained?

#### ✅ **Testing & Reliability**
- **Test Coverage**: Do new features have corresponding tests?
- **Test Quality**: Are both happy path and edge cases covered?
- **Error Scenarios**: Are error conditions tested?
- **Integration**: Are integration points validated?

#### ✅ **Security & Safety**  
- **Secrets**: No hardcoded credentials or API keys?
- **Input Validation**: User inputs properly validated and sanitized?
- **Authentication**: Access controls properly implemented?
- **Vulnerabilities**: No obvious injection or XSS risks?

#### ✅ **Performance & Maintainability**
- **Efficiency**: No obvious performance bottlenecks?
- **Resource Usage**: Reasonable memory and processing demands?
- **Database**: Queries optimized and indexed appropriately?
- **Conventions**: Code follows established project patterns?

#### ✅ **User Experience & Accessibility** (when applicable)
- **Semantic HTML**: Proper HTML structure and ARIA labels?
- **Keyboard Navigation**: All functionality accessible via keyboard?
- **Visual Design**: Adequate color contrast and text sizing?
- **Error UX**: User-friendly error messages and recovery paths?

## Step 3: Detailed Review Results

**🎯 Review Findings:**

Based on systematic analysis of the changes:

### 🏆 **Strengths Identified**
[I'll highlight specific positive aspects of the code]

### ⚠️ **Areas for Improvement**
[I'll provide specific, actionable feedback with priorities]

### 🔧 **Specific Recommendations**
[Detailed suggestions with file/line references where applicable]

## Step 4: Review Decision & Next Steps

**Review Status Assessment:**
!`echo "📊 Review Summary:"
if git diff --cached --quiet; then
  echo "  ℹ️  No staged changes to review"
else
  echo "  ✅ Changes analyzed systematically"
  echo "  📋 Feedback provided above"
fi`

---

**🔄 Review Decision & Next Actions:**

- **✅ Approved for Commit**: Code meets quality standards → Ready for `/commit [message]`
- **⚠️ Minor Issues Found**: Small improvements recommended → Address feedback, then `/commit`
- **❌ Major Issues Identified**: Significant problems need fixing → Address critical issues, then `/review` again  
- **🔬 Uncertain Areas**: Complex changes need validation → Use `/experiment` to test approaches
- **📚 Learning Opportunity**: Use `/retro` to capture insights from this review

**💡 Coaching Tip**: Systematic code review builds quality habits and catches issues early when they're cheapest to fix. Even experienced developers benefit from methodical quality assessment - it's not about perfection, it's about continuous improvement!