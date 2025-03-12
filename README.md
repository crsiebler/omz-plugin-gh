# omz-plugin-bun

oh-my-zsh aliases for common [gh](https://cli.github.com/) commands.

## Installation

- [Oh My Zsh](#oh-my-zsh)

### Oh My Zsh

1. Clone the repository:

```zsh
git clone --depth=1 https://github.com/crsiebler/omz-plugin-gh.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/plugins/gh
```

2. Include it in your `~/.zshrc`:

```zsh
plugins=(... gh)
```

### Others

PRs are always welcome!

## Aliases

| Alias   | Command              | Description                          |
| ------- | -------------------- | ------------------------------------ |
| ghal    | `gh auth login`      | Authentication login command         |
| ghcpe   | `gh copilot explain` | Use Copilot to explain a command     |
| ghcps   | `gh copilot suggest` | Use Copilot to suggest a command     |
| ghpr    | `gh pr create`       | Create a new pull request            |
| ghprl   | `gh pr list`         | List pull requests in the repository |
| ghprm   | `gh pr merge`        | Merge a pull request                 |
| ghprcmt | `gh pr comment`      | Add a comment to a PR                |
| ghprsts | `gh pr status`       | Show the status of a pull request    |