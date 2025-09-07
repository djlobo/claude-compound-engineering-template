# Commit Guide

## Smart Git Commits with Quality Gates

Follow this systematic approach for professional commits:

### 1. Pre-Commit Quality Gates
Before committing, ensure quality:
- **Run tests**: All tests must pass
- **Review changes**: Use `git diff` to see what's changing
- **Check scope**: Ensure changes are focused and related
- **Scan for secrets**: Never commit keys, passwords, or tokens

### 2. Review Changes
Understand what you're committing:
```bash
git status          # See all changed files
git diff --cached   # Review staged changes
git diff            # See unstaged changes
```

### 3. Commit Message Format
Use conventional commit format:
```
type(scope): description

- feat: new feature
- fix: bug fix
- docs: documentation
- refactor: code restructuring
- test: adding tests
- chore: maintenance
```

Examples:
- `feat(auth): add login validation`
- `fix(api): handle null response errors`
- `docs(readme): update installation steps`

### 4. Create the Commit
Best practices:
- Stage related changes: `git add [files]`
- Write clear commit message
- Include co-authorship when appropriate
- Review before finalizing

## Commit Workflow

### Standard Process
1. **Check status**: `git status`
2. **Stage changes**: `git add .` or `git add [specific-files]`
3. **Review staged**: `git diff --cached`
4. **Run tests**: Ensure all pass
5. **Commit**: `git commit -m "type(scope): description"`

### Quality Checks
- **Tests passing**: Green tests before commits
- **Related changes**: Keep commits focused
- **Clear message**: Describe the "why", not just "what"
- **No secrets**: Double-check for sensitive data

### Conventional Commit Types
- **feat**: New feature for users
- **fix**: Bug fix for users  
- **docs**: Documentation changes
- **style**: Code style changes (formatting, etc.)
- **refactor**: Code changes that neither fix bugs nor add features
- **perf**: Performance improvements
- **test**: Adding or updating tests
- **chore**: Build process, dependencies, etc.

## Common Patterns

### Good Commit Messages
```
feat(user-auth): implement OAuth login flow
fix(api): resolve timeout issues in data fetch
docs(contributing): add code review guidelines
refactor(utils): extract common validation logic
```

### Avoid These Patterns
```
fix stuff                    # Too vague
WIP                         # Work in progress commits
Fixed bug                   # Not conventional format  
Updated files               # Doesn't explain what changed
```

## Next Actions After Commit
- **Continue development**: Move to next planned task
- **Quality review**: Analyze code quality and coverage
- **Share progress**: Push changes when ready
- **Document insights**: Capture lessons learned

## Coaching Notes
Regular, well-formatted commits create:
- Clear project history
- Better collaboration
- Easier debugging
- Professional development practices
- Confidence in codebase changes