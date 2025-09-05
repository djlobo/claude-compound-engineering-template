# Commit - Smart Git Commit with Quality Gates

Create conventional commits with automatic quality checks, proper formatting, and co-authorship.

## Instructions

1. **Run Pre-Commit Quality Gates**
   - Execute tests to ensure all pass
   - Perform basic secret scanning
   - Validate that changes are ready for commit

2. **Review Changes**
   - Show git status and staged changes
   - Display diff summary for manual review
   - Highlight any large file changes

3. **Format Commit Message**
   - Ensure conventional commit format (feat:, fix:, docs:, etc.)
   - Auto-detect commit type from changed files if needed
   - Add proper scope and description

4. **Create Commit**
   - Generate commit with co-authorship attribution
   - Provide next action recommendations
   - Track commit statistics for learning

**Commit message**: $ARGUMENTS

## Step 1: Pre-Commit Quality Gates

**Running essential quality checks:**
!`echo "🔍 Quality Gate Checks:"

# Test validation
if [ -f "package.json" ] && grep -q '"test"' package.json && ! grep -q '"test": "echo' package.json; then
  echo "🧪 Running tests before commit..."
  if npm test; then
    echo "✅ All tests passing!"
  else
    echo "❌ Tests failing - must fix before commit"
    exit 1
  fi
else
  echo "ℹ️  No test script found - skipping test validation"
fi

# Basic secret scan
echo "🔒 Checking for potential secrets..."
if git diff --cached | grep -iE "(api_key|secret|password|token|private_key|auth.*key)" > /dev/null; then
  echo "⚠️  WARNING: Potential secrets detected in staged changes!"
  echo "Please review and remove any sensitive information before committing."
else
  echo "✅ No obvious secrets detected"
fi`

## Step 2: Review Changes

**What will be committed:**
!`echo "📋 Git Status:"
git status --porcelain 2>/dev/null || echo "⚠️  No git repository found"

echo -e "\n📊 Staged Changes Summary:"
git diff --cached --stat 2>/dev/null || echo "⚠️  No staged changes found"

echo -e "\n📈 Change Impact:"
LINES_CHANGED=$(git diff --cached --stat 2>/dev/null | tail -1 | grep -oE '[0-9]+' | head -1 || echo "0")
FILES_CHANGED=$(git diff --cached --name-only 2>/dev/null | wc -l || echo "0")
echo "  📄 Files modified: $FILES_CHANGED"
echo "  📝 Lines changed: ${LINES_CHANGED:-0}"

if [ "${LINES_CHANGED:-0}" -gt 200 ]; then
  echo "  💡 Large changeset - consider smaller commits next time"
fi`

## Step 3: Commit Creation

**Creating conventional commit:**
!`MESSAGE="$ARGUMENTS"

# Format as conventional commit if not already
if echo "$MESSAGE" | grep -qE "^(feat|fix|docs|style|refactor|test|chore|build|ci|perf|revert)(\(.+\))?!?:"; then
  echo "✅ Message is already in conventional format: $MESSAGE"
  FINAL_MESSAGE="$MESSAGE"
else
  echo "🔄 Converting to conventional commit format..."
  
  # Auto-detect commit type from changes
  if git diff --cached --name-only | grep -qE "test|spec"; then
    FINAL_MESSAGE="test: $MESSAGE"
  elif git diff --cached --name-only | grep -qE "\.md$|README|doc"; then
    FINAL_MESSAGE="docs: $MESSAGE"  
  elif git diff --cached --name-only | grep -qE "package\.json|\.config\.|\.yml$|\.yaml$"; then
    FINAL_MESSAGE="chore: $MESSAGE"
  elif git diff --cached --name-only | grep -qE "fix|bug"; then
    FINAL_MESSAGE="fix: $MESSAGE"
  else
    FINAL_MESSAGE="feat: $MESSAGE"
  fi
  echo "📝 Formatted as: $FINAL_MESSAGE"
fi

# Create the commit
if git diff --cached --quiet; then
  echo "⚠️  No staged changes to commit. Use 'git add <files>' to stage changes first."
else
  echo "💾 Creating commit with co-authorship..."
  if git commit -m "$FINAL_MESSAGE

🤖 Generated with [Claude Code](https://claude.ai/code)

Co-Authored-By: Claude <noreply@anthropic.com>"; then
    echo "✅ Commit created successfully!"
  else
    echo "❌ Commit failed - check git status and try again"
  fi
fi`

## Step 4: Next Action Guidance

**Post-commit recommendations:**
!`echo "🎯 Commit Statistics:"
if git log -1 --stat 2>/dev/null; then
  echo -e "\n✅ Latest commit created successfully"
else
  echo "⚠️  No recent commit found"
fi`

---

**🔄 Next Action Options**:

- **Continue development**: Use `/do [next-task-id]` to implement the next planned task
- **Quality assurance**: Use `/review` to perform comprehensive code analysis
- **Start new feature**: Use `/plan [feature-name]` to begin systematic planning  
- **Capture insights**: Use `/retro` to document lessons learned from this session
- **Deploy/share**: Push changes with `git push` when ready

**💡 Coaching Tip**: Excellent commit discipline! Regular, well-formatted commits create a clear history that helps with debugging, code reviews, and collaboration. This systematic approach builds trust in your codebase.