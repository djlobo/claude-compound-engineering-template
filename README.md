# Claude Code Coaching System

Personal compound engineering system for systematic skill development.

## Quick Start

```bash
claude              # Start in default mode
claude --plan       # Start in plan mode
/reference          # See all commands
```

## Directory Structure

```
cc-setup/
├── reflections/           # Learning & knowledge base
│   ├── _patterns.md      # Successful approaches
│   ├── _experiments.md   # Failed attempts & lessons
│   ├── _decisions.md     # Architecture choices
│   └── *.md              # Feature documentation
├── .claude/              # Claude Code configuration
│   ├── agents/           # AI specialists
│   ├── commands/         # Slash commands
│   ├── tasks/            # Generated task plans
│   └── settings.local.json
├── CLAUDE.md             # Coaching instructions
└── README.md            # This file
```

## Core Workflow

1. **Plan**: `/plan <feature>` - Create structured plan
2. **Implement**: `/do <task-id>` - Execute specific task
3. **Test**: `/test` - Run tests with analysis
4. **Commit**: `/commit <message>` - Quality-gated commit
5. **Review**: `/review` - Code quality check
6. **Learn**: `/retro` - Capture lessons

## Advanced Commands

- `/experiment <hypothesis>` - Safe trials with rollback
- `/reference` - Command reference & status

## Philosophy

- **Plan First**: Think deeply before coding (Opus model)
- **Build Fast**: Implement efficiently (Sonnet model)
- **Learn Always**: Document patterns & failures
- **Quality Gates**: Automated checks prevent debt
- **Compound Growth**: Small daily improvements

## Configuration

- Models: Opus 4.1 (planning), Sonnet 4 (implementation)
- Default mode: Plan (safe exploration)
- Permissions: Controlled file access
- Hooks: Contextual coaching

## Tips

- Follow the coaching nudges
- Document failures in `reflections/_experiments.md`
- Capture successes in `reflections/_patterns.md`
- Use `/experiment` for risky changes
- Run `/retro` after each feature