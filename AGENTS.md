# Agent Configuration for oh-my-zsh GitHub CLI Plugin

## Overview
This repository contains an oh-my-zsh plugin that provides convenient aliases for the GitHub CLI (`gh`) commands. The plugin is written in Zsh and focuses on maintaining simple, reliable aliases for common GitHub operations.

## Build/Lint/Test Commands

### Syntax Checking
Since this is a Zsh plugin, syntax validation is the primary "build" step:
```bash
zsh -n gh.plugin.zsh
```

This command checks for syntax errors in the Zsh script without executing it.

### Testing Aliases
Test individual aliases by sourcing the plugin and running them:
```bash
# Source the plugin
source gh.plugin.zsh

# Test an alias
ghal  # Should run 'gh auth login'
```

### Running All Checks
```bash
# Syntax check
zsh -n gh.plugin.zsh && echo "Syntax OK"

# Manual verification
source gh.plugin.zsh && echo "Plugin loaded successfully"
```

## Code Style Guidelines

### Zsh Scripting Conventions

#### Alias Definition
- Use the `alias` command for all alias definitions
- Format: `alias alias_name='command'`
- Single quotes preferred to prevent premature expansion
- One alias per line for readability

#### Example Structure
```zsh
# Group related aliases with comments
# Auth
alias ghal='gh auth login'

# Copilot
alias ghcp='gh copilot'
alias ghcpe='gh copilot explain'
```

### Naming Conventions

#### Alias Names
- All aliases must start with `gh` prefix (GitHub CLI)
- Use lowercase letters only
- Keep names concise but descriptive
- Follow existing patterns:
  - `ghal` for auth login
  - `ghcp*` for copilot commands
  - `ghpr*` for pull request commands
  - `ghr*` for repository commands
  - `ghi*` for issue commands

#### Group Organization
Organize aliases by functional groups:
1. Auth (authentication)
2. Copilot (GitHub Copilot features)
3. PR (pull requests)
4. Repo (repositories)
5. Issues

### Formatting and Style

#### Indentation
- Use 2 spaces for indentation (following Zsh plugin conventions)
- Align alias definitions consistently

#### Comments
- Use `#` for single-line comments
- Group comments should describe the functional area
- Keep comments concise and descriptive

#### Line Length
- Aim for lines under 80 characters when possible
- Break long commands if needed (though aliases are typically short)

### Imports and Dependencies

#### External Commands
- All aliases depend on the `gh` command being available
- No additional dependencies required
- Assume `gh` is installed and configured by the user

### Error Handling

#### Alias Design
- Keep aliases simple - avoid complex error handling
- Let the underlying `gh` command handle errors
- Users should see `gh` error messages directly

#### Plugin Loading
- Plugin should load without errors in oh-my-zsh
- Test with `source gh.plugin.zsh` before committing

### Documentation Updates

#### README.md Maintenance
When adding new aliases, update the README.md table:
- Add entry to the aliases table
- Include: Alias, Command, Description
- Keep table sorted alphabetically by alias

#### Example Table Entry
```markdown
| ghex    | `gh example command`    | Example command description    |
```

## Git Workflow

### Commit Message Format
Follow conventional commit format:
```
<type>(<scope>): <description>
```

#### Types
- `feat`: New feature (adding new aliases)
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, etc.)
- `refactor`: Code refactoring
- `chore`: Maintenance tasks

#### Scope
- Use the filename: `gh.plugin.zsh`
- Or functional area: `readme`, `aliases`

#### Examples
```
feat(gh.plugin.zsh): add copilot aliases
docs(readme): update alias table
style(gh.plugin.zsh): fix indentation
```

### Branching Strategy
- Use feature branches for changes
- Branch naming: `feature/add-copilot-aliases` or `fix/readme-typo`

### Pull Request Process
- Create PRs for all changes
- Include description of what aliases were added/modified
- Test aliases manually before submitting

## Security Guidelines

### Secrets and Credentials
- This plugin deals with GitHub CLI authentication
- Never hardcode tokens or credentials
- All authentication handled through `gh auth login`
- Plugin only provides aliases, no credential storage

### Command Safety
- Aliases should not execute destructive commands automatically
- Use safe defaults (e.g., `--dry-run` where available)
- Let users confirm destructive operations

## Testing Approach

### Manual Testing
Since this is a simple alias plugin, testing is manual:

1. **Syntax Check**: `zsh -n gh.plugin.zsh`
2. **Load Test**: `source gh.plugin.zsh`
3. **Alias Test**: Run each alias to verify it works
4. **oh-my-zsh Integration**: Test loading in actual zsh session

### Verification Steps
```bash
# 1. Syntax check
zsh -n gh.plugin.zsh

# 2. Load plugin
zsh -c 'source gh.plugin.zsh; echo "Loaded successfully"'

# 3. Test key aliases
zsh -c 'source gh.plugin.zsh; type ghal'  # Should show: ghal is aliased to 'gh auth login'
```

### Compatibility Testing
- Test on different systems (macOS, Linux)
- Verify `gh` command availability
- Test in both interactive and non-interactive shells

## File Structure

### Required Files
- `gh.plugin.zsh`: Main plugin file with aliases
- `README.md`: Documentation and installation instructions
- `LICENSE`: MIT license

### Optional Files
- `AGENTS.md`: This configuration file for coding agents

## Performance Considerations

### Plugin Loading
- Keep plugin lightweight - only aliases, no functions
- Minimize startup time impact on shell
- Avoid complex initialization

### Alias Efficiency
- Use direct command aliases (no functions unless necessary)
- Avoid piping or complex command chains in aliases
- Prefer simple, fast-executing commands

## Maintenance Guidelines

### Adding New Aliases
1. Identify the `gh` command and common use case
2. Choose appropriate alias name following conventions
3. Add to correct functional group in `gh.plugin.zsh`
4. Update README.md table
5. Test the alias
6. Commit with descriptive message

### Updating Existing Aliases
1. Verify the change doesn't break existing functionality
2. Update any affected documentation
3. Test thoroughly
4. Consider backward compatibility

### Deprecation Process
1. Mark deprecated aliases with comments
2. Update documentation to reflect deprecation
3. Remove in future major version if needed

## Quality Assurance

### Code Review Checklist
- [ ] Syntax validates with `zsh -n`
- [ ] Alias naming follows conventions
- [ ] README.md table updated
- [ ] Manual testing completed
- [ ] Commit message follows format
- [ ] No breaking changes without documentation

### Release Process
1. Update version if applicable (though this is a simple plugin)
2. Test all aliases
3. Update documentation
4. Create git tag for releases if needed