# Experiment - Safe Risk-Taking with Rollback

Safely test uncertain approaches with git branching, structured learning capture, and easy rollback.

## Instructions

1. **Create Isolated Environment**  
   - Check for clean working directory
   - Create experiment branch for safe isolation
   - Document hypothesis and expected outcome

2. **Structure the Experiment**
   - Log experiment start in learning system
   - Define success/failure criteria clearly
   - Set boundaries for what will be tested

3. **Guide Implementation**
   - Provide framework for testing the hypothesis
   - Focus on minimal viable test approach
   - Document observations during implementation

4. **Capture Results**
   - Record what worked and what didn't
   - Extract specific lessons learned
   - Provide rollback or merge guidance

**Hypothesis to test**: $ARGUMENTS

**🧪 Starting structured experimentation...**

## Step 1: Experiment Setup & Safety

**Creating safe experimentation environment:**
!`HYPOTHESIS="$ARGUMENTS"
BRANCH_NAME="experiment/$(echo "$HYPOTHESIS" | tr ' ' '-' | tr '[:upper:]' '[:lower:]' | tr -cd 'a-z0-9-' | cut -c1-50)"

echo "🧪 Experiment: $HYPOTHESIS"
echo "📝 Safe branch: $BRANCH_NAME"

# Check git status and create experiment branch
if git rev-parse --git-dir > /dev/null 2>&1; then
  echo "✅ Git repository detected"
  
  # Ensure working directory is clean
  if [ -n "$(git status --porcelain)" ]; then
    echo "⚠️  Working directory has uncommitted changes:"
    git status --short
    echo "💡 Commit or stash changes before experimenting to ensure safe rollback"
    exit 1
  fi
  
  # Create experiment branch
  if git checkout -b "$BRANCH_NAME" 2>/dev/null; then
    echo "✅ Created experiment branch: $BRANCH_NAME"
    echo "🔄 Safe rollback available: git checkout main && git branch -D $BRANCH_NAME"
  else
    echo "⚠️  Branch may already exist. Switching to: $BRANCH_NAME"
    git checkout "$BRANCH_NAME"
  fi
else
  echo "⚠️  No git repository found - experiment will run without version control safety"
  echo "💡 Consider initializing git for safer experimentation"
fi`

## Step 2: Experiment Documentation

**Recording experiment in learning system:**
!`DATE=$(date +%Y-%m-%d)
HYPOTHESIS="$ARGUMENTS"
BRANCH_NAME="experiment/$(echo "$HYPOTHESIS" | tr ' ' '-' | tr '[:upper:]' '[:lower:]' | tr -cd 'a-z0-9-' | cut -c1-50)"

# Log experiment start
cat >> tasks/_experiments.md << EOF

## Experiment: $HYPOTHESIS
**Date**: $DATE
**Branch**: $BRANCH_NAME (if git available)
**Hypothesis**: $HYPOTHESIS
**Expected Outcome**: What I think will happen and why
**Success Criteria**: Specific conditions that indicate success
**Failure Criteria**: What would indicate the approach doesn't work
**Approach**: [To be filled during implementation]
**Results**: [To be determined after testing]
**Evidence**: [Observations and data supporting the conclusion]
**Lesson Learned**: [Key insight regardless of success/failure]
**Confidence Level**: [How certain I am about the results]
**Next Action**: [What this means for the main implementation]

---

EOF

echo "📋 Experiment logged in tasks/_experiments.md"
echo "🎯 Experiment framework ready"`

## Step 3: Experimentation Guidelines

**Ready to test your hypothesis!** Here's how to proceed:

### Focus Areas for Testing:
- **Minimal viable test**: Implement just enough to validate/invalidate the hypothesis
- **Clear boundaries**: Stay focused on testing the specific hypothesis
- **Rapid iteration**: Prioritize quick feedback over perfect implementation
- **Evidence collection**: Document what you observe, not just what you expect

### Experiment Scope:
- ✅ **Do**: Make focused changes to test the specific hypothesis
- ✅ **Do**: Document unexpected discoveries and side effects
- ✅ **Do**: Take notes on what works and what doesn't
- ❌ **Don't**: Worry about code quality - this is for learning
- ❌ **Don't**: Expand scope beyond testing the hypothesis
- ❌ **Don't**: Spend excessive time perfecting the experiment

## Step 4: Implementation & Results

**Continue experimenting using normal workflow commands:**
- Use regular file editing, `/test`, and other commands
- Focus on validating or invalidating your hypothesis
- Document observations as you work

**When ready to conclude the experiment:**
- Update the experiment log in tasks/_experiments.md with your findings
- Decide whether to keep, modify, or discard the approach

---

**🔄 Experiment Navigation Options:**

- **Successful experiment**: Merge changes back with `/commit [message]` describing what worked
- **Failed experiment**: Safe rollback with `git checkout main && git branch -D [branch-name]`  
- **Partial success**: Keep useful parts, document trade-offs, and plan refinements
- **Need more data**: Continue experimenting with additional tests
- **Ready to apply**: Use insights to refine main approach with `/plan` updates

**💡 Coaching Tip**: The best experiments are designed to fail fast and cheaply. Don't aim for perfection - aim for learning! Failed experiments that teach you something valuable are more useful than "successful" experiments that don't provide clear insights.