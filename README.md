# omz-plugin-gh

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

| Alias   | Command                   | Description                       |
|---------|---------------------------|-----------------------------------|
| ghal    | `gh auth login`           | Authenticate with GitHub          |
| ghcp    | `gh copilot`              | GitHub Copilot                    |
| ghcpa   | `gh copilot alias`        | Generate shell-specific aliases   |
| ghcpe   | `gh copilot explain`      | Explain code using Copilot        |
| ghcps   | `gh copilot suggest`      | Suggest code using Copilot        |
| ghcpd   | `gh copilot debug`        | Debug code using Copilot          |
| ghcpc   | `gh copilot config`       | Configure Copilot                 |
| ghpr    | `gh pr create`            | Create a pull request             |
| ghprl   | `gh pr list`              | List pull requests                |
| ghprc   | `gh pr checkout`          | Checkout a pull request           |
| ghprm   | `gh pr merge`             | Merge a pull request              |
| ghprcmt | `gh pr comment`           | Comment on a pull request         |
| ghprsts | `gh pr status`            | Show pull request status          |
| ghr     | `gh repo create`          | Create a repository               |
| ghrl    | `gh repo list`            | List repositories                 |
| ghrcl   | `gh repo clone`           | Clone a repository                |
| ghi     | `gh issue create`         | Create an issue                   |
| ghil    | `gh issue list`           | List issues                       |
| ghic    | `gh issue comment`        | Comment on an issue               |
