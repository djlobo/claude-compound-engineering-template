---
allowed-tools: [Read, Write, Edit, Bash(git:*), TodoWrite, Glob, Grep]
argument-hint: [hypothesis]
description: Safe experimentation with git branching and structured learning capture
---

# Structured Experimentation with Rollback Safety

I'll help you safely test uncertain approaches with proper isolation and learning capture.

**Hypothesis to test**: $ARGUMENTS

## Step 1: Experiment Setup & Safety

### Create Isolated Environment
!`HYPOTHESIS="$ARGUMENTS"
BRANCH_NAME="experiment/$(echo "$HYPOTHESIS" | tr ' ' '-' | tr '[:upper:]' '[:lower:]' | tr -cd 'a-z0-9-')"

echo "🧪 Starting Experiment: $HYPOTHESIS"
echo "📝 Creating safe experiment branch: $BRANCH_NAME"

# Check current git status
if git rev-parse --git-dir > /dev/null 2>&1; then
  echo "✅ Git repository detected"
  
  # Ensure working directory is clean
  if [ -n "$(git status --porcelain)" ]; then
    echo "⚠️  Working directory has uncommitted changes."
    echo "Please commit or stash changes before experimenting."
    git status --short
    exit 1
  fi
  
  # Create experiment branch
  git checkout -b "$BRANCH_NAME" 2>/dev/null || (
    echo "⚠️  Branch $BRANCH_NAME already exists. Switching to it..."
    git checkout "$BRANCH_NAME"
  )
  echo "✅ Now on experiment branch: $BRANCH_NAME"
else
  echo "⚠️  No git repository found. Experiment will run without version control safety."
fi`

## Step 2: Document Experiment Start

Let me log this experiment in our learning system:

!`DATE=$(date +%Y-%m-%d)
HYPOTHESIS="$ARGUMENTS"
BRANCH_NAME="experiment/$(echo "$HYPOTHESIS" | tr ' ' '-' | tr '[:upper:]' '[:lower:]' | tr -cd 'a-z0-9-')"

# Add to experiment log
cat >> tasks/_experiments.md << EOF

## Experiment: $HYPOTHESIS
**Date**: $DATE
**Branch**: $BRANCH_NAME (if git available)
**Hypothesis**: $HYPOTHESIS
**Expected Outcome**: [What I think will happen and why]
**Approach**: [Specific steps to test the hypothesis]
**Result**: [To be filled after testing]
**Evidence**: [Data/observations that support the conclusion]
**Lesson**: [Key insight gained regardless of success/failure]
**Confidence Level**: [How certain I am about the result]
**Next Action**: [What this means for the main approach]

---

EOF

echo "📋 Experiment logged in tasks/_experiments.md"
echo "🎯 Ready to implement and test your hypothesis"`

## Step 3: Implementation Guidance

Now I'm ready to help implement your experimental approach:

### What to Focus On:
- **Minimal viable test** of the hypothesis
- **Clear success/failure criteria** 
- **Reversible changes** that can be easily rolled back
- **Specific learning objectives** rather than perfect implementation

### Experiment Boundaries:
- Keep changes focused on testing the specific hypothesis
- Don't worry about code quality - this is for learning
- Document observations and unexpected findings
- Set a time limit to prevent endless exploration

## Step 4: Next Steps for Implementation

Ready to start experimenting! Here's what happens next:

1. **Implement your hypothesis** using normal commands (`/do`, editing files, etc.)
2. **Test the approach** to see if it works as expected
3. **Document results** - both positive and negative findings
4. **Make decision** about keeping, modifying, or discarding the approach

---

**🔄 Experiment Navigation Options**:

- **Continue implementing**: Use normal workflow commands to test your hypothesis
- **Document findings**: I'll help update the experiment log with results
- **Successful experiment**: Merge back with `/commit [message]` 
- **Failed experiment**: Safe rollback with `git checkout main && git branch -D [branch-name]`
- **Partial success**: Extract useful parts and document trade-offs

**💡 Coaching Tip**: Experiments are for learning, not perfection! Document both failures and successes - failed experiments often provide the most valuable insights.