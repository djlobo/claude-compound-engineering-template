# Test Format Command

This is a test command to validate the correct Claude Code slash command format.

## Instructions

1. **Display Current Status**
   - Show current directory and basic system info
   - Verify command recognition is working

2. **Test Basic Operations**
   - List files in current directory
   - Show git status if available

3. **Confirm Success**
   - Display success message
   - Suggest next action

Current directory: !`pwd`

Current files: !`ls -la | head -10`

Git status: !`git status --porcelain 2>/dev/null || echo "No git repository or no changes"`

**✅ Test command is working!** This means slash commands are being recognized properly.

**Next step**: Try the main coaching commands like `/reference` or `/plan`.