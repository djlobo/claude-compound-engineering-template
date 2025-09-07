# Compound Engineering Template Setup Guide

This guide will help you set up the Claude Code Compound Engineering template in your new projects.

## Quick Start (GitHub Template)

### Option 1: Using GitHub Template Repository

1. **Create Template Repository**
   ```bash
   # First, push this setup to GitHub
   git remote add origin https://github.com/your-username/claude-compound-engineering-template.git
   git push -u origin main
   
   # Then make it a template in GitHub:
   # Go to Settings > General > Template repository (check the box)
   ```

2. **Create New Projects**
   - Go to your template repository on GitHub
   - Click "Use this template" → "Create a new repository"
   - Clone your new project locally
   - You're ready to start coding with compound engineering!

### Option 2: Manual Setup

1. **Copy Template Files**
   ```bash
   # In your new project directory
   cp -r /path/to/cc-setup/.claude .
   cp -r /path/to/cc-setup/reflections .
   cp /path/to/cc-setup/CLAUDE.md .
   cp /path/to/cc-setup/future_upgrades.md .
   cp /path/to/cc-setup/.gitignore .
   ```

2. **Initialize Git** (if not already initialized)
   ```bash
   git init
   git add .
   git commit -m "feat: initialize compound engineering setup"
   ```

## Template Customization

### Essential Files to Review

1. **CLAUDE.md** - Main coaching system
   - Review nudge triggers (line counts, timing)
   - Adjust coaching intensity if needed
   - Customize for your specific domain/tech stack

2. **.claude/settings.local.json** - Permissions and hooks
   - Adjust file permissions for your project structure
   - Add project-specific bash commands to allow list
   - Customize hooks for your workflow

3. **reflections/** - Learning capture system
   - Files are ready with templates
   - Will populate automatically as you work

### Project-Specific Customization

1. **Update README.md**
   - Replace with your project's actual README
   - Keep reference to compound engineering setup if desired

2. **Adjust .gitignore**
   - Add project-specific ignore patterns
   - Remove sections that don't apply to your tech stack

3. **Customize Workflow Guides** (optional)
   - Edit `.claude/guides/*.md` files for project-specific practices
   - Add technology-specific testing or deployment steps

## Verification

After setup, verify the system works:

1. **Check Claude Code loads the config**
   ```bash
   # Should see session start message about CLAUDE.md
   # Should see compound engineering context active
   ```

2. **Test basic workflow**
   - Start a small feature in planning mode
   - Follow planning → implementation → testing → commit
   - Check that learning capture triggers work

3. **Verify reflections system**
   - After completing a task, check if patterns are captured
   - Try adding an experiment or decision record

## Template Maintenance

### Keeping Template Updated

1. **Regular Updates**
   - Periodically sync improvements back to template repo
   - Update workflow guides based on learnings
   - Evolve CLAUDE.md based on what works

2. **Version Management**
   - Tag template versions for stability
   - Update existing projects selectively
   - Document breaking changes in template updates

### Contributing Improvements

If you improve the template:
1. Test improvements in a real project first
2. Update documentation
3. Consider creating a PR back to the template repo
4. Share successful patterns with the community

## Troubleshooting

### Common Issues

1. **Claude Code doesn't load CLAUDE.md**
   - Check file is in project root
   - Verify Claude Code is in project directory
   - Check for syntax errors in CLAUDE.md

2. **Permissions errors**
   - Review `.claude/settings.local.json` permissions
   - Add necessary paths to "allow" list
   - Check file paths are correct for your project structure

3. **Hooks not firing**
   - Verify hook syntax in settings.local.json
   - Check command paths and permissions
   - Test hooks manually first

### Getting Help

- Review the workflow guides in `.claude/guides/`
- Check `future_upgrades.md` for advanced features
- Reference the compound engineering article principles
- Ask Claude Code to explain any part of the system

---

## Next Steps

Once setup is complete:

1. **Start with planning** - Use the planning guide for your first feature
2. **Follow the workflow** - Trust the system and coaching
3. **Capture everything** - Let the learning system work
4. **Iterate and improve** - The system gets better with each use

The compound engineering system is designed to make you more effective over time. Every project becomes easier as patterns accumulate and quality gates evolve.

**Remember**: This isn't just a template—it's a learning system that compounds your engineering effectiveness with every use.