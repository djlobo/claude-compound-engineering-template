---
allowed-tools: [Bash(git:*), Bash(npm:*), Read, Write, TodoWrite]
argument-hint: [commit-message]
description: Create conventional commit with quality gates and co-authorship
---

# Smart Git Commit with Quality Gates

I'll help you create a high-quality commit with automatic checks and proper formatting.

**Commit message**: $ARGUMENTS

## Step 1: Pre-Commit Quality Gates
Let me run the essential quality checks first:

### Test Validation
!`if [ -f "package.json" ] && grep -q "test" package.json; then
  echo "🧪 Running tests before commit..."
  npm test || (echo "❌ Tests failing - must fix before commit" && exit 1)
  echo "✅ All tests passing!"
else
  echo "ℹ️  No test script found - skipping test validation"
fi`

### Security Check (Basic Secret Scan)
!`echo "🔒 Checking for potential secrets..."
if git diff --cached | grep -iE "(api_key|secret|password|token|private_key)" > /dev/null; then
  echo "⚠️  WARNING: Potential secrets detected in staged changes!"
  echo "Please review and remove any sensitive information before committing."
  git diff --cached | grep -iE "(api_key|secret|password|token|private_key)" || true
else
  echo "✅ No obvious secrets detected"
fi`

## Step 2: Review Changes
Here's what will be committed:

### Git Status
!`git status --porcelain || echo "No git repository found"`

### Staged Changes Summary
!`git diff --cached --stat 2>/dev/null || echo "No staged changes found"`

## Step 3: Commit Message Formatting
Let me ensure your commit follows conventional commit format:

!`MESSAGE="$ARGUMENTS"
if echo "$MESSAGE" | grep -qE "^(feat|fix|docs|style|refactor|test|chore|build|ci|perf|revert)(\(.+\))?!?:"; then
  echo "✅ Already in conventional commit format: $MESSAGE"
else
  echo "🔄 Converting to conventional commit format..."
  # Try to detect commit type from changes
  if git diff --cached --name-only | grep -qE "test|spec"; then
    MESSAGE="test: $MESSAGE"
  elif git diff --cached --name-only | grep -qE "\.md$|README|doc"; then
    MESSAGE="docs: $MESSAGE"  
  elif git diff --cached --name-only | grep -qE "package\.json|\.config\.|\.yml$|\.yaml$"; then
    MESSAGE="chore: $MESSAGE"
  else
    MESSAGE="feat: $MESSAGE"
  fi
  echo "📝 Formatted as: $MESSAGE"
fi

# Create the commit
if git diff --cached --quiet; then
  echo "⚠️  No staged changes to commit. Use 'git add' to stage files first."
else
  echo "💾 Creating commit..."
  git commit -m "$MESSAGE

🤖 Generated with [Claude Code](https://claude.ai/code)

Co-Authored-By: Claude <noreply@anthropic.com>" && echo "✅ Commit created successfully!"
fi`

## Step 4: Next Action Guidance

### Change Summary
!`LINES_CHANGED=$(git diff HEAD~1 --stat 2>/dev/null | tail -1 | grep -oE '[0-9]+' | head -1 || echo "0")
echo "📊 Lines changed in this commit: ${LINES_CHANGED:-0}"
if [ "${LINES_CHANGED:-0}" -gt 200 ]; then
  echo "💡 Tip: Consider smaller, focused commits for easier review and rollback"
fi`

---

**🔄 Next Action Based on Your Progress**:

- **Continue implementation**: Use `/do [next-task-id]` for the next planned task
- **Quality review**: Use `/review` to analyze the committed changes  
- **New feature**: Use `/plan [feature-name]` to start planning the next feature
- **Capture learnings**: Use `/retro` to document insights from this work session

**💡 Coaching Tip**: Great commit! This systematic approach ensures quality and maintains a clean git history. Your commit messages help future you understand the changes.