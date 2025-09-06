# Workflow Validation Test - Simple Demo Feature

**Purpose**: Validate our complete Claude Code coaching system by implementing a basic feature using the full workflow.

**Test Feature**: Simple "Hello World" API endpoint with tests
**Started**: 2025-09-05
**Status**: Ready for testing

## Test Plan

### Phase 1: Planning Test
- [ ] Use `/plan hello-api` command
- [ ] Verify Opus model activation for planning
- [ ] Check structured plan creation in tasks/hello-api.md
- [ ] Validate approval process works
- [ ] Test nudging suggests `/do 1` after planning

### Phase 2: Implementation Test  
- [ ] Use `/do 1` command for first task
- [ ] Verify Sonnet model switch for implementation
- [ ] Check task progress tracking
- [ ] Validate nudging suggests `/test` or next task

### Phase 3: Testing Workflow
- [ ] Use `/test` command 
- [ ] Verify test framework detection
- [ ] Check plain-language test result analysis
- [ ] Validate nudging suggests `/commit` on success

### Phase 4: Quality Gates
- [ ] Use `/commit` command with conventional message
- [ ] Verify pre-commit quality checks
- [ ] Test git operations work correctly
- [ ] Check co-authorship attribution

### Phase 5: Code Review
- [ ] Use `/review` command
- [ ] Verify Opus model switch for thorough analysis
- [ ] Check systematic quality checklist execution
- [ ] Validate specific feedback with file/line references

### Phase 6: Learning Capture
- [ ] Use `/retro` command
- [ ] Verify lesson extraction and memory updates
- [ ] Check pattern/experiment file updates
- [ ] Validate workflow improvement suggestions

### Phase 7: Help System
- [ ] Use `/reference` command
- [ ] Verify capability map display
- [ ] Check command reference completeness
- [ ] Validate next action suggestions

## Expected Nudging Behaviors

### Throughout Workflow
- [ ] After every response: specific next action suggestion
- [ ] Context-aware nudging based on current stage
- [ ] Appropriate intensity (coaching level)
- [ ] Clear, actionable suggestions

### Trigger Validation
- [ ] 200+ lines changed → commit suggestion
- [ ] 20+ minutes → test reminder  
- [ ] Multiple failures → experiment suggestion
- [ ] Session boundaries → retro suggestion

## Success Criteria

### Technical Functionality
- ✅ All commands execute without errors
- ✅ Model switching works correctly (Opus ↔ Sonnet)
- ✅ File operations create expected outputs
- ✅ Git operations work properly
- ✅ Quality gates function as designed

### Coaching Behavior
- ✅ Consistent next action nudging after every response
- ✅ Context-appropriate suggestions
- ✅ Clear, specific guidance (not generic advice)
- ✅ Builds workflow muscle memory through repetition

### Learning System
- ✅ Experiment tracking captures lessons
- ✅ Pattern recognition identifies successes
- ✅ Decision documentation maintains context
- ✅ Memory updates improve future sessions

## Test Implementation

### Simple Feature Spec
**Feature**: Hello World API endpoint
**Requirements**: 
- GET /api/hello endpoint returns "Hello, World!"
- Include input validation for query parameters
- Add unit tests for happy path and edge cases
- Follow conventional commit format

### Expected File Creation
```
src/
├─ api/
│  └─ hello.ts          # API endpoint implementation
tests/
├─ api/
│  └─ hello.test.ts     # Unit tests
tasks/
├─ hello-api.md         # Feature implementation plan
├─ _experiments.md      # Updated with any experiments
├─ _patterns.md         # Updated with successful patterns
└─ _decisions.md        # Updated with architecture decisions
```

## Validation Results

*To be filled during testing*

### What Worked Well
- [List successful behaviors and features]

### Issues Discovered  
- [List problems or missing functionality]

### Lessons Learned
- [Key insights from testing process]

### Workflow Improvements
- [Suggested refinements based on real usage]

---

**Next Steps After Validation**:
1. Address any issues discovered during testing
2. Refine nudging triggers based on actual workflow
3. Update documentation with real usage examples  
4. Create quick-start guide for David
5. Document troubleshooting for common issues