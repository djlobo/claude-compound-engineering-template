# Testing Guide

## Intelligent Testing Approach

Testing is a crucial quality gate. Follow this systematic approach:

### 1. Test Framework Detection
Before running tests, understand what's available:
- Check package.json for testing frameworks (Jest, Vitest, Playwright, Cypress)
- Look for test configuration files
- Identify available test scripts

### 2. Execute Tests
Run tests using the appropriate method:
- Use existing npm scripts (preferred)
- Framework-specific commands
- For specific areas: run targeted test suites

### 3. Analyze Results
When tests fail:
- Parse output for specific failures
- Provide plain-language explanations
- Give file/line references
- Suggest prioritized fixes

### 4. Next Actions
- ✅ Tests pass → Ready to commit
- ❌ Tests fail → Fix and retest
- ⚠️ No tests → Consider adding coverage

## Common Test Commands

## Test Analysis Framework

### When Tests Pass
- Implementation meets requirements
- No regressions detected
- Safe to commit or continue

### When Tests Fail
Look for:
- **Assertion failures**: Expected vs actual values
- **Syntax errors**: Code doesn't compile/parse
- **Runtime errors**: Exceptions during execution
- **Timeout issues**: Tests taking too long

### When No Tests Exist
Consider adding tests for:
- New functionality just implemented
- Critical user flows and business logic
- Edge cases and error conditions
- API endpoints and data validation

## Testing Best Practices

### Test-First Mindset
- Run tests before committing changes
- Add tests for new functionality
- Fix failing tests immediately
- Don't skip test failures

### Quality Gates
- All tests must pass before commits
- Maintain or improve test coverage
- Test critical user paths
- Validate edge cases and errors

### Debugging Test Failures
1. Read the error message carefully
2. Check the expected vs actual values
3. Look at the specific line causing failure
4. Consider recent changes that might affect this area
5. Run individual test files to isolate issues

## Coaching Notes
- Green tests = confidence to refactor
- Tests document expected behavior  
- Failing tests are feedback, not failure
- Test early, test often, test consistently