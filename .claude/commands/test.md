---
allowed-tools: [Bash(npm:*), Bash(npx:*), Bash(yarn:*), Bash(pnpm:*), Read, Write, Edit, TodoWrite]
description: Run tests with intelligent analysis and plain-language feedback
---

# Test Runner & Analysis

Let me run your tests and provide intelligent analysis of the results.

## Step 1: Test Framework Detection
First, let me check what testing setup you have:

!`cat package.json 2>/dev/null | grep -E "(jest|vitest|playwright|cypress|mocha)" || echo "No package.json found"`

!`ls -la | grep -E "(jest|vitest|playwright|cypress)" || echo "No obvious test config files"`

## Step 2: Test Execution
Now I'll run the appropriate test command based on your setup:

!`if [ -f "package.json" ]; then
  if grep -q "jest" package.json; then
    echo "🧪 Running Jest tests..."
    npm test
  elif grep -q "vitest" package.json; then
    echo "🧪 Running Vitest tests..."
    npm run test
  elif grep -q "playwright" package.json; then
    echo "🧪 Running Playwright tests..."
    npx playwright test
  elif grep -q "cypress" package.json; then
    echo "🧪 Running Cypress tests..."
    npm run test:cypress
  elif grep -q "test" package.json; then
    echo "🧪 Running test script..."
    npm test
  else
    echo "⚠️ No recognized test framework or test script found"
    echo "Consider adding tests for your recent changes"
  fi
else
  echo "⚠️ No package.json found - cannot detect test framework"
fi`

## Step 3: Test Results Analysis

Based on the test results above, let me provide plain-language analysis:

### ✅ If Tests Pass:
- All tests are passing - great work!
- Your recent changes haven't broken existing functionality
- The implementation meets the defined requirements

### ❌ If Tests Fail:
I'll analyze each failure and provide specific guidance:
- **File/line references** for each failing test
- **Plain-language explanation** of what's being tested
- **Specific suggestions** for fixes
- **Priority order** for addressing issues

### ⚠️ If No Tests Found:
Consider adding tests for:
- New functionality you've recently implemented
- Critical user paths and edge cases
- Error conditions and input validation

---

**🔄 Next Action Based on Results**:

- **All tests passing**: Ready to `/commit [message]` your changes or continue with `/do [next-task]`?
- **Tests failing**: Fix the issues above, then run `/test` again to verify
- **No tests found**: Consider adding tests before committing with `/experiment test-setup`

**💡 Coaching Tip**: Green tests before commits! This prevents breaking changes and builds confidence in your code quality.