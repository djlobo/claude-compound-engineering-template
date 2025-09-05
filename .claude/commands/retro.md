---
allowed-tools: Read, Write, Edit, Bash(git:*), TodoWrite, Glob, Grep
description: Systematic learning capture and workflow improvement analysis
---

# Learning Retrospective & Continuous Improvement

Let me systematically analyze our recent work to capture lessons and improve our workflow.

## Step 1: Session Activity Analysis

### Recent Work Review
!`echo "📊 Analyzing recent activity..."

# Recent commits for context
if git rev-parse --git-dir > /dev/null 2>&1; then
  echo -e "\n🔍 Recent Commits (last 10):"
  git log --oneline -10 2>/dev/null | head -5 || echo "No recent commits found"
  
  echo -e "\n📈 Commit Activity Summary:"
  git log --since="24 hours ago" --pretty=format:"%s" 2>/dev/null | wc -l | xargs printf "Commits in last 24h: %s\n" || echo "Cannot analyze recent commit activity"
  
  echo -e "\n📝 Files Changed Recently:"
  git diff --name-only HEAD~5 2>/dev/null | head -10 || echo "No recent file changes to analyze"
else
  echo "ℹ️  No git repository found - analyzing current project state instead"
fi

# Check for recent experiments
echo -e "\n🧪 Recent Experiments:"
if [ -f "tasks/_experiments.md" ]; then
  tail -20 "tasks/_experiments.md" | grep -E "^## Experiment:" | head -3 || echo "No recent experiments found"
else
  echo "No experiments logged yet"
fi`

### Work Pattern Analysis
!`echo "🔄 Analyzing work patterns..."

# Look for patterns in file types changed
if git rev-parse --git-dir > /dev/null 2>&1; then
  echo -e "\n📁 File Types Modified:"
  git diff --name-only HEAD~10 2>/dev/null | sed 's/.*\.//' | sort | uniq -c | head -5 || echo "No pattern data available"
fi

# Check current task status
echo -e "\n📋 Current Task Status:"
find ./tasks -name "*.md" -not -name "_*" 2>/dev/null | head -3 | while read task; do
  echo "- $(basename "$task" .md): $(head -1 "$task" 2>/dev/null || echo "No description")"
done || echo "No active tasks found"`

## Step 2: Lesson Extraction & Learning Analysis

### What Worked Well ✅
Let me identify successful patterns from recent work:

!`echo "🏆 Analyzing successful approaches..."

# Look for completed experiments
if [ -f "tasks/_experiments.md" ]; then
  echo "📊 Experiment Success Patterns:"
  grep -A 5 "Result.*success\|Lesson.*" "tasks/_experiments.md" 2>/dev/null | head -10 || echo "No successful experiments to analyze yet"
fi

# Check for established patterns
if [ -f "tasks/_patterns.md" ]; then
  echo -e "\n✅ Established Successful Patterns:"
  grep "^## Pattern:" "tasks/_patterns.md" 2>/dev/null | head -3 || echo "No patterns documented yet"
fi`

### What Needed Improvement ⚠️
Analyzing areas that caused friction or challenges:

!`echo "🔍 Identifying improvement areas..."

# Look for failed experiments or challenges
if [ -f "tasks/_experiments.md" ]; then
  echo "📉 Learning from Challenges:"
  grep -A 3 "Result.*fail\|Lesson.*avoid" "tasks/_experiments.md" 2>/dev/null | head -10 || echo "No failures documented - good start!"
fi

# Check git history for reverted changes (learning opportunities)
if git rev-parse --git-dir > /dev/null 2>&1; then
  REVERTS=$(git log --oneline --grep="revert\|fix\|undo" --since="1 week ago" 2>/dev/null | wc -l)
  if [ "$REVERTS" -gt 0 ]; then
    echo "🔄 Recent fixes/reverts (learning opportunities): $REVERTS"
  fi
fi`

## Step 3: Memory System Updates

### Update Learning Files
!`echo "📚 Updating learning repository..."

DATE=$(date +%Y-%m-%d)

# Add retrospective insights to patterns file
cat >> tasks/_patterns.md << EOF

## Pattern: Retrospective Insights ($DATE)
**Context**: Regular session retrospective analysis
**Approach**: Systematic review of recent commits, experiments, and workflows
**Benefits**: Continuous improvement and knowledge retention
**Example**: Using git analysis to identify work patterns and success indicators
**Related**: Combines with experiment tracking for comprehensive learning

EOF

echo "✅ Added retrospective insights to patterns"

# Update experiment reflection
if ! grep -q "Session Retrospective" "tasks/_experiments.md" 2>/dev/null; then
  cat >> tasks/_experiments.md << EOF

## Session Retrospective: $DATE
**Date**: $DATE
**Hypothesis**: Regular retrospectives will improve workflow and learning retention
**Approach**: Analyze git history, experiments, and patterns for insights
**Result**: [Ongoing - building systematic learning habits]
**Lesson**: Retrospectives help identify both successful patterns and improvement areas
**Next Action**: Apply insights to refine workflow and coaching system

EOF
  echo "✅ Documented retrospective process in experiments log"
fi`

## Step 4: Workflow Improvement Suggestions

Based on my analysis, here are specific improvements to consider:

### 🎯 **Key Insights from This Session**
- **Successful Patterns**: [Based on actual analysis above]
- **Learning Opportunities**: [Based on challenges identified]  
- **Workflow Efficiency**: [Based on commit and work patterns]

### ⚙️ **Recommended Improvements**

1. **Nudging Adjustments**: 
   - Consider adjusting commit frequency based on your actual work patterns
   - Tune test reminders based on how often you naturally run tests

2. **Command Usage Patterns**:
   - Focus on the commands you use most frequently
   - Simplify or enhance workflows that show friction

3. **Learning System Enhancements**:
   - Continue building your pattern library with successful approaches
   - Document challenges immediately when they occur for better learning

### 📈 **Progress Tracking**
!`echo "📊 Learning System Growth:"
PATTERNS=$(grep -c "^## Pattern:" "tasks/_patterns.md" 2>/dev/null || echo "0")
EXPERIMENTS=$(grep -c "^## Experiment:" "tasks/_experiments.md" 2>/dev/null || echo "0")
DECISIONS=$(grep -c "^## Decision:" "tasks/_decisions.md" 2>/dev/null || echo "0")

echo "- Documented patterns: $PATTERNS"
echo "- Tracked experiments: $EXPERIMENTS"  
echo "- Recorded decisions: $DECISIONS"
echo "- Total learning entries: $((PATTERNS + EXPERIMENTS + DECISIONS))"`

---

**🔄 Next Actions for Continuous Improvement**:

- **Apply insights**: Use the patterns identified above in your next feature work
- **Refine workflow**: Adjust CLAUDE.md nudging based on your actual work patterns
- **Plan next feature**: Use `/plan [feature-name]` with insights from this retrospective
- **Take a break**: Consider stepping away to let insights settle before the next work session

**💡 Coaching Tip**: Regular retrospectives are like compound interest for learning - small, consistent improvements create dramatic long-term growth in your engineering capabilities!