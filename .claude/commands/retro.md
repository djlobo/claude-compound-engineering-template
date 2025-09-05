# Retro - Learning Capture & Continuous Improvement

Systematically analyze recent work to extract lessons, identify patterns, and improve the development workflow.

## Instructions

1. **Analyze Recent Activity**
   - Review recent commits, experiments, and decisions  
   - Identify work patterns and recurring themes
   - Assess what worked well vs. what caused friction

2. **Extract Key Lessons**
   - Capture successful approaches to replicate
   - Document mistakes and how to avoid them
   - Identify new insights about tools, techniques, or domain

3. **Update Learning System**
   - Add successful patterns to pattern library
   - Record failed approaches in experiment log  
   - Document important decisions and rationale

4. **Propose Workflow Improvements**
   - Suggest refinements to development process
   - Recommend adjustments to coaching triggers
   - Identify skills to focus on developing

**🔄 Starting systematic retrospective analysis...**

## Step 1: Recent Activity Analysis

**Reviewing recent work and patterns:**
!`echo "📊 Session Activity Analysis:"

# Recent commits for context  
if git rev-parse --git-dir > /dev/null 2>&1; then
  echo "🔍 Recent Commits (last 10):"
  git log --oneline -10 2>/dev/null | head -5 || echo "  No recent commits found"
  
  echo -e "\n📈 Commit Activity Summary:"
  RECENT_COMMITS=$(git log --since="24 hours ago" --pretty=format:"%s" 2>/dev/null | wc -l)
  echo "  Commits in last 24h: $RECENT_COMMITS"
  
  echo -e "\n📝 File Change Patterns:"
  git diff --name-only HEAD~10 2>/dev/null | sed 's/.*\.//' | sort | uniq -c | head -5 || echo "  No recent changes to analyze"
else
  echo "ℹ️  No git repository - analyzing current project state"
fi

# Check for recent experiments
echo -e "\n🧪 Recent Experiments:"
if [ -f "tasks/_experiments.md" ]; then
  tail -50 "tasks/_experiments.md" | grep -E "^## Experiment:" | tail -3 || echo "  No experiments logged recently"
else
  echo "  No experiments file found"
fi`

**Work pattern analysis:**
!`echo "🔄 Development Pattern Analysis:"

# Look for work session patterns
echo "📁 File Types Recently Modified:"
if git rev-parse --git-dir > /dev/null 2>&1; then
  git log --name-only --since="3 days ago" --pretty=format: | grep -v '^$' | sort | uniq -c | sort -nr | head -5 2>/dev/null || echo "  No recent file changes found"
fi

echo -e "\n📋 Current Task Status:"
find ./tasks -name "*.md" -not -name "_*" 2>/dev/null | head -3 | while read task; do
  echo "  📄 $(basename "$task" .md): $(head -1 "$task" 2>/dev/null | sed 's/^# //' || echo "No title")"
done || echo "  No active tasks found"`

## Step 2: Lesson Extraction & Learning Analysis

### What Worked Well ✅

**Analyzing successful approaches and patterns:**
!`echo "🏆 Success Pattern Analysis:"

# Look for completed experiments and positive outcomes
if [ -f "tasks/_experiments.md" ]; then
  echo "📊 Successful Experiment Patterns:"
  grep -A 5 "Lesson.*success\|Result.*worked\|Lesson.*effective" "tasks/_experiments.md" 2>/dev/null | head -10 || echo "  No successful experiments documented yet"
fi

# Check for established patterns
if [ -f "tasks/_patterns.md" ]; then
  echo -e "\n✅ Documented Successful Patterns:"
  grep "^## Pattern:" "tasks/_patterns.md" 2>/dev/null | tail -3 || echo "  No patterns documented yet"
fi

echo -e "\n🎯 Recent Accomplishments:"
if git rev-parse --git-dir > /dev/null 2>&1; then
  git log --since="1 week ago" --grep="feat:" --oneline 2>/dev/null | head -3 || echo "  No recent features completed"
fi`

### What Needed Improvement ⚠️

**Identifying friction points and challenges:**
!`echo "🔍 Challenge & Improvement Analysis:"

# Look for failed experiments or repeated issues
if [ -f "tasks/_experiments.md" ]; then
  echo "📉 Learning from Challenges:"
  grep -A 3 "Result.*failed\|Lesson.*avoid\|Result.*didn.*work" "tasks/_experiments.md" 2>/dev/null | head -10 || echo "  No documented challenges - good progress!"
fi

# Check for patterns in reverts or fixes
if git rev-parse --git-dir > /dev/null 2>&1; then
  FIXES=$(git log --oneline --grep="fix:\|revert:\|undo" --since="1 week ago" 2>/dev/null | wc -l)
  if [ "$FIXES" -gt 0 ]; then
    echo -e "\n🔄 Recent fixes/reverts: $FIXES (learning opportunities)"
    git log --oneline --grep="fix:\|revert:" --since="1 week ago" 2>/dev/null | head -2
  else
    echo -e "\n✅ No recent fixes needed - stable development"
  fi
fi`

## Step 3: Learning System Updates

**Updating memory and knowledge base:**
!`echo "📚 Updating Learning Repository:"

DATE=$(date +%Y-%m-%d)

# Add retrospective insights to patterns
cat >> tasks/_patterns.md << EOF

## Pattern: Session Retrospective ($DATE)  
**Context**: Regular analysis of development session and workflow effectiveness
**Approach**: Systematic review of commits, experiments, and work patterns
**Benefits**: Continuous improvement through structured self-reflection and pattern recognition
**Example**: Analyzing git history and experiment outcomes to identify successful approaches
**Related**: Combines with experiment tracking and decision logging for comprehensive learning

EOF

echo "✅ Added retrospective insights to patterns library"

# Update experiment reflection if this is a new retrospective
if ! grep -q "Retrospective Session.*$DATE" "tasks/_experiments.md" 2>/dev/null; then
  cat >> tasks/_experiments.md << EOF

## Retrospective Session: $DATE
**Date**: $DATE  
**Hypothesis**: Regular retrospectives improve development effectiveness and learning retention
**Approach**: Analyze recent commits, experiments, patterns, and workflow friction points
**Result**: [Building systematic learning habits through structured reflection]
**Lesson**: Retrospectives help surface both successful patterns and improvement opportunities
**Next Action**: Apply insights to refine coaching system and development approach

EOF
  echo "✅ Documented retrospective process in experiment log"  
fi`

## Step 4: Workflow Improvement Recommendations

Based on systematic analysis, here are specific improvements to consider:

### 🎯 **Key Insights from This Session**
- **Successful Patterns**: [Based on actual git history and experiment analysis above]
- **Learning Opportunities**: [Based on challenges and friction points identified]
- **Work Rhythm**: [Based on commit patterns and development flow]

### ⚙️ **Recommended Process Improvements**

1. **Coaching System Adjustments**:
   - Review current nudge triggers (commit frequency, test reminders)
   - Adjust coaching intensity based on observed skill development
   - Refine command usage based on actual workflow patterns

2. **Development Workflow Optimizations**:
   - Focus on commands and patterns showing the most value
   - Streamline areas where friction was observed
   - Enhance successful approaches that are working well

3. **Learning System Enhancements**:
   - Continue building pattern library with approaches that work
   - Document challenges immediately for better learning retention
   - Regular retrospectives to maintain improvement momentum

### 📈 **Progress Tracking & Growth Metrics**

**Learning system growth:**
!`echo "📊 Knowledge Base Metrics:"
PATTERNS=$(grep -c "^## Pattern:" "tasks/_patterns.md" 2>/dev/null || echo "0")
EXPERIMENTS=$(grep -c "^## Experiment:" "tasks/_experiments.md" 2>/dev/null || echo "0")
DECISIONS=$(grep -c "^## Decision:" "tasks/_decisions.md" 2>/dev/null || echo "0")

echo "📋 Patterns documented: $PATTERNS"
echo "🧪 Experiments tracked: $EXPERIMENTS"
echo "🎯 Decisions recorded: $DECISIONS"  
echo "📚 Total learning entries: $((PATTERNS + EXPERIMENTS + DECISIONS))"

if [ $((PATTERNS + EXPERIMENTS + DECISIONS)) -gt 5 ]; then
  echo "✅ Strong learning system momentum!"
else
  echo "🌱 Learning system building up - keep documenting insights"
fi`

---

**🔄 Next Actions for Continuous Improvement:**

- **Apply insights**: Use successful patterns identified above in upcoming development work
- **Refine coaching**: Adjust CLAUDE.md triggers based on actual usage patterns observed
- **Plan next work**: Use `/plan [feature-name]` incorporating lessons from this retrospective
- **Schedule next retro**: Plan regular retrospectives (weekly/after major features) for sustained growth
- **Share learnings**: Consider documenting key insights for team/future reference

**💡 Coaching Tip**: Regular retrospectives are compound interest for learning - small, consistent improvements create dramatic long-term gains in development effectiveness. The insights you capture today become the foundation for faster, higher-quality work tomorrow!