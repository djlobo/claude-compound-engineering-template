# Help - Claude Code Coaching System Reference

Your complete reference for the personalized compound engineering coaching system.

## Instructions

1. **Display System Overview**
   - Show my role as your active coding coach
   - Explain the compound engineering philosophy 
   - List core capabilities and workflow benefits

2. **Show Available Commands**
   - Display all 8 slash commands with descriptions
   - Explain when to use each command
   - Show typical workflow sequence

3. **Check Current System Status**
   - Verify command directory setup
   - Check learning system files
   - Show git integration status
   - Display learning progress metrics

4. **Provide Quick Start Guide**
   - Give next action recommendations
   - Show typical development workflow
   - Explain coaching behavior

## 🤖 **I'm Your Active Coding Coach**

Helping you (David - founder/product manager) build systematic engineering skills through:

- ✅ **Proactive coaching**: Next-action suggestions after every response
- ✅ **Quality automation**: Tests, commits, and reviews with built-in gates
- ✅ **Learning system**: Systematic capture of patterns and experiments
- ✅ **Workflow commands**: 8 specialized commands for compound engineering

## 📋 **Available Commands**

### Core Workflow Commands
- **`/plan [feature-name]`** - Structured feature planning (creates tasks/[feature].md)
- **`/do [task-id]`** - Focused task implementation (single-task focus)
- **`/test`** - Intelligent test runner with plain-language analysis
- **`/commit [message]`** - Quality-gated commits with conventional format
- **`/review`** - Comprehensive code quality analysis with systematic checklist

### Learning & Experimentation Commands  
- **`/experiment [hypothesis]`** - Safe risk-taking with git branching and rollback
- **`/retro`** - Learning capture and workflow improvement analysis
- **`/help`** - This complete reference guide

## 📊 **Current System Status**

**Configuration Check:**
!`echo "🔧 Setup Status:"
echo "📁 Commands: $(ls -1 .claude/commands/*.md 2>/dev/null | wc -l) available"
echo "📚 Learning system:"
[ -f "tasks/_experiments.md" ] && echo "  ✅ Experiment tracking ready" || echo "  ⚠️  Experiment tracking needs setup"
[ -f "tasks/_patterns.md" ] && echo "  ✅ Pattern library ready" || echo "  ⚠️  Pattern library needs setup"  
[ -f "tasks/_decisions.md" ] && echo "  ✅ Decision log ready" || echo "  ⚠️  Decision log needs setup"`

**Git Integration:**
!`if git rev-parse --git-dir > /dev/null 2>&1; then
  echo "✅ Git repository detected"
  echo "📝 Current branch: $(git branch --show-current 2>/dev/null)"
else
  echo "⚠️ No git repository - some features limited"
fi`

**Learning Progress:**
!`echo "📈 Learning System:"
PATTERNS=$(grep -c "^## Pattern:" "tasks/_patterns.md" 2>/dev/null || echo "0")
EXPERIMENTS=$(grep -c "^## Experiment:" "tasks/_experiments.md" 2>/dev/null || echo "0")
DECISIONS=$(grep -c "^## Decision:" "tasks/_decisions.md" 2>/dev/null || echo "0")
echo "  📋 Patterns documented: $PATTERNS"
echo "  🧪 Experiments tracked: $EXPERIMENTS"  
echo "  🎯 Decisions recorded: $DECISIONS"`

## 🚀 **Quick Start Workflow**

**Typical Development Flow:**
1. 🎯 `/plan [feature-name]` - Create structured plan
2. ⚡ `/do 1` - Implement first task  
3. 🧪 `/test` - Run tests with analysis
4. 💾 `/commit "feat: add [feature]"` - Quality-gated commit
5. 🔍 `/review` - Code quality check
6. 📚 `/retro` - Capture lessons learned

**When Things Get Complex:**
- 🔬 Uncertain approach? → `/experiment [hypothesis]` 
- 🏗️ Major changes? → Break into smaller `/plan` cycles
- 📊 Need insights? → `/retro` to analyze and improve

## 🎯 **Compound Engineering Philosophy**

- **Systematic over ad-hoc**: Every action follows a deliberate process
- **Learning over perfection**: Capture lessons from both success and failure  
- **Quality by design**: Built-in gates prevent technical debt
- **Continuous improvement**: Regular retrospectives refine the system

---

**🔄 Your Next Best Action**: Ready to start? Try `/plan [feature-name]` to begin systematic feature development!

**💡 Coaching Tip**: This system becomes more powerful with use. Each command builds systematic engineering habits!