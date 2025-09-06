# Experiment Log & Failed Approaches

**Purpose**: Track structured experiments, failed approaches, and lessons learned to avoid repeating mistakes and build systematic problem-solving patterns.

## How to Use This Log

### When to Add Experiments:
- Before trying a risky or uncertain approach
- When you're stuck and need to test assumptions 
- After any failed attempt that taught you something
- When exploring multiple solution paths

### Experiment Format:
```
## Experiment: [Brief Description]
**Date**: YYYY-MM-DD
**Hypothesis**: What you thought would work and why
**Approach**: Specific steps you took
**Result**: What actually happened
**Lesson**: Key insight gained
**Next Action**: How this changes your approach
```

---

## Experiments Log

### Example Entry (Remove when you add real experiments)

## Experiment: Initial Setup Validation
**Date**: 2025-09-05
**Hypothesis**: Claude Code hooks and settings would work as documented in first try
**Approach**: Directly implemented complex settings.json with custom hook format
**Result**: Settings validation failed - hooks need specific array/object structure
**Lesson**: Always validate configuration against schema before assuming format
**Next Action**: Follow Claude Code documentation precisely for hook configuration

---

## Experiment: Claude Code Slash Command Caching 
**Date**: 2024-09-06
**Hypothesis**: Editing slash command files should immediately update their behavior when run
**Approach**: Updated reference.md paths from `tasks/_` to `reflections/_` and tested `/reference` command
**Result**: Failed - command used cached version with old `tasks/_experiments.md` paths despite file showing `reflections/_experiments.md`
**Lesson**: Claude Code loads slash commands at session start and caches them in memory. File edits don't automatically reload commands.
**Next Action**: Must restart Claude Code session after editing slash commands to force reload

---

*Add your experiments above this line. Most recent at the top.*