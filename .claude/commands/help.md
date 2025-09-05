---
allowed-tools: Read, Bash(git:*)
description: Complete reference for your Claude Code coaching system and commands
---

# Claude Code Coaching System - Complete Reference

Welcome to your personalized compound engineering coaching system!

## 🤖 My Role & Capabilities

**I'm your active coding coach**, helping you (David - founder/product manager) build systematic engineering skills through:

### Core Capabilities
- ✅ **Smart model switching**: Opus for planning/review ↔ Sonnet for implementation
- ✅ **Proactive coaching**: Next-action suggestions after every response
- ✅ **Quality automation**: Tests, commits, and reviews with built-in quality gates
- ✅ **Learning system**: Systematic capture of patterns, experiments, and decisions
- ✅ **Workflow commands**: 8 specialized slash commands for compound engineering

## 📋 Available Commands

### 🎯 Core Workflow Commands
- **`/plan [feature-name]`** - Structured feature planning (Opus mode, creates tasks/[feature].md)
- **`/do [task-id]`** - Focused task implementation (Sonnet mode, single-task focus)
- **`/test`** - Intelligent test runner with plain-language analysis
- **`/commit [message]`** - Quality-gated commits with conventional format
- **`/review`** - Comprehensive code quality analysis (Opus mode, systematic checklist)

### 🔬 Learning & Experimentation Commands  
- **`/experiment [hypothesis]`** - Safe risk-taking with git branching and rollback
- **`/retro`** - Learning capture and workflow improvement analysis
- **`/help`** - This complete reference guide

## 🔄 Coaching Behavior

### After Every Response, I Will:
✅ **Suggest specific next action** based on current context  
✅ **Provide contextual nudging** for workflow optimization  
✅ **Guide you through systematic processes** for compound engineering

### Context-Aware Suggestions
- 📋 **Planning context**: "Ready to implement? Try `/plan [feature-name]`"
- ⚡ **Implementation**: "Good progress! Consider `/test` to validate"
- 🔒 **Quality gates**: "200+ lines changed. Time for `/commit [message]`?"
- 🧪 **When stuck**: "Try `/experiment [hypothesis]` to test assumptions"
- 📚 **Session end**: "Consider `/retro` to capture lessons learned"

## 📊 Current System Status

### Configuration Check
!`echo "🔧 Current Setup Status:"
echo "📁 Commands available:"
ls -la .claude/commands/ 2>/dev/null | grep -E "\.md$" | wc -l | xargs printf "  Slash commands: %s\n"

echo -e "\n📚 Learning system:"
[ -f "tasks/_experiments.md" ] && echo "  ✅ Experiment tracking ready" || echo "  ⚠️  Experiment tracking needs setup"
[ -f "tasks/_patterns.md" ] && echo "  ✅ Pattern library ready" || echo "  ⚠️  Pattern library needs setup"
[ -f "tasks/_decisions.md" ] && echo "  ✅ Decision log ready" || echo "  ⚠️  Decision log needs setup"

echo -e "\n⚙️ Git integration:"
if git rev-parse --git-dir > /dev/null 2>&1; then
  echo "  ✅ Git repository detected"
  echo "  📝 Current branch: $(git branch --show-current 2>/dev/null)"
else
  echo "  ⚠️  No git repository - some features limited"
fi`

### Learning System Growth
!`echo "📈 Learning Progress:"
if [ -f "tasks/_patterns.md" ]; then
  PATTERNS=$(grep -c "^## Pattern:" "tasks/_patterns.md" 2>/dev/null || echo "0")
  echo "  📋 Documented patterns: $PATTERNS"
fi
if [ -f "tasks/_experiments.md" ]; then
  EXPERIMENTS=$(grep -c "^## Experiment:" "tasks/_experiments.md" 2>/dev/null || echo "0")
  echo "  🧪 Tracked experiments: $EXPERIMENTS"
fi
if [ -f "tasks/_decisions.md" ]; then
  DECISIONS=$(grep -c "^## Decision:" "tasks/_decisions.md" 2>/dev/null || echo "0")
  echo "  🎯 Recorded decisions: $DECISIONS"
fi`

## 🚀 Quick Start Guide

### First Time Setup (if needed)
1. **Initialize git**: `git init` (if not already a repo)
2. **Test a command**: Try `/help` (you're doing this now! ✅)
3. **Plan your first feature**: `/plan hello-world`

### Typical Workflow
1. 🎯 **Plan**: `/plan [your-feature-name]` - Creates structured plan with Opus
2. ⚡ **Implement**: `/do 1` - Executes first task with Sonnet
3. 🧪 **Test**: `/test` - Runs tests with intelligent analysis
4. 💾 **Commit**: `/commit "feat: add [feature]"` - Quality-gated commit
5. 🔍 **Review**: `/review` - Comprehensive code quality check
6. 📚 **Learn**: `/retro` - Capture insights for next time

### When Things Get Complex
- 🔬 **Uncertain approach**: `/experiment [hypothesis]` - Safe exploration
- 🏗️ **Major changes**: Break into smaller `/plan` → `/do` cycles
- 📊 **Progress check**: `/retro` to analyze and improve

## 🎯 System Philosophy

### Compound Engineering Principles
- **Systematic over ad-hoc**: Every action follows a deliberate process
- **Learning over perfection**: Capture lessons from both success and failure  
- **Quality by design**: Built-in gates prevent technical debt
- **Continuous improvement**: Regular retrospectives refine the system

---

**🔄 Your Next Best Action**: Ready to start? Try `/plan [feature-name]` to begin your first systematic feature development, or tell me what you're working on and I'll suggest the best command to use!

**💡 Coaching Tip**: This system becomes more powerful the more you use it. Each command builds on the others to create a comprehensive compound engineering workflow.