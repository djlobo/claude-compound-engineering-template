# Test - Intelligent Test Runner & Analysis

Run tests with automatic framework detection and plain-language analysis of results.

## Instructions

1. **Detect Test Framework**
   - Scan package.json for testing frameworks (Jest, Vitest, Playwright, Cypress)
   - Check for test configuration files
   - Identify the appropriate test command to run

2. **Execute Tests**
   - Run the detected test framework with appropriate command
   - Capture both successful and failing test results
   - Handle different test output formats

3. **Analyze Results**
   - Parse test output for specific failures
   - Provide plain-language explanations of what failed
   - Give file/line references for failing tests
   - Suggest specific fixes with priority order

4. **Provide Next Action Guidance**
   - Suggest commit if tests pass
   - Recommend fixes if tests fail
   - Advise on adding tests if none found

## Step 1: Test Framework Detection

**Checking your testing setup:**
!`echo "🔍 Detecting test framework..."
if [ -f "package.json" ]; then
  echo "📦 Found package.json"
  echo "🧪 Testing frameworks detected:"
  grep -E "(jest|vitest|playwright|cypress|mocha|ava|tap)" package.json 2>/dev/null || echo "  ⚠️  No recognized testing frameworks found"
  
  echo -e "\n📝 Available test scripts:"
  grep -A 10 '"scripts"' package.json 2>/dev/null | grep -E '"test.*":' || echo "  ⚠️  No test scripts found"
else
  echo "⚠️ No package.json found"
fi

echo -e "\n📁 Test files found:"
find . -name "*.test.*" -o -name "*.spec.*" -o -path "*/test/*" -o -path "*/tests/*" | head -5 || echo "  ⚠️  No test files found"`

## Step 2: Test Execution

**Running tests with detected framework:**
!`echo "🧪 Executing tests..."
if [ -f "package.json" ]; then
  # Try common test commands in order of preference
  if grep -q '"test"' package.json && ! grep -q '"test": "echo \\"Error:' package.json; then
    echo "Running npm test..."
    npm test
  elif grep -q "jest" package.json; then
    echo "Running Jest tests..."
    npx jest
  elif grep -q "vitest" package.json; then
    echo "Running Vitest tests..."
    npx vitest run
  elif grep -q "playwright" package.json; then
    echo "Running Playwright tests..."
    npx playwright test
  elif grep -q "cypress" package.json; then
    echo "Running Cypress tests..."
    npx cypress run
  else
    echo "⚠️ No test command or framework detected"
    echo "💡 Consider setting up tests for your code"
    exit 0
  fi
else
  echo "⚠️ Cannot run tests without package.json"
  echo "💡 Initialize a Node.js project with 'npm init' first"
fi`

## Step 3: Test Results Analysis

**📊 Test Results Summary:**

Based on the test execution above:

### ✅ **If Tests Pass**
- All tests are passing - excellent work!
- Your implementation meets the defined requirements
- No regressions detected in existing functionality

### ❌ **If Tests Fail**
I'll analyze the failures and provide:
- **Specific file/line references** for each failing test
- **Plain-language explanations** of what the tests expect vs. what they found
- **Actionable suggestions** for fixes prioritized by impact
- **Related test guidance** for similar issues

### ⚠️ **If No Tests Found**
Consider adding tests for:
- **New functionality** you've recently implemented
- **Critical user flows** and business logic
- **Edge cases** and error conditions
- **API endpoints** and data validation

---

**🔄 Next Action Recommendations:**

- **✅ Tests passing**: Ready to `/commit [message]` your changes or continue development with `/do [next-task]`
- **❌ Tests failing**: Fix the issues identified above, then run `/test` again to verify fixes
- **🔬 Need new tests**: Use `/experiment test-setup` to add testing infrastructure
- **📊 Want insights**: Use `/review` to analyze code coverage and test quality

**💡 Coaching Tip**: Green tests before commits is a fundamental quality gate. Tests give you confidence to refactor and extend code without fear of breaking existing functionality!