# Proscan Integration Examples

Configuration examples for integrating Proscan into CI/CD pipelines, IDEs, and external services.

These are starting points. Adjust paths, tokens, and scan types to match your environment.

## CI/CD Pipelines

| Platform | Config |
|----------|--------|
| [GitHub Actions](cicd/github-actions.yml) | Workflow using the [Proscan Action](https://github.com/Proscan-hub/action) |
| [GitLab CI](cicd/gitlab-ci.yml) | Pipeline with SAST and SCA stages |
| [Jenkins](cicd/Jenkinsfile) | Declarative pipeline |
| [Azure Pipelines](cicd/azure-pipelines.yml) | YAML pipeline |
| [CircleCI](cicd/circleci.yml) | Orb-style config |

## IDE Setup

| Editor | Guide |
|--------|-------|
| [VS Code](ide/vscode.md) | Extension setup |
| [IntelliJ IDEA](ide/intellij.md) | Plugin setup |
| [Neovim](ide/neovim.md) | LSP client configuration |

## Webhooks

| Example | Description |
|---------|-------------|
| [Slack notification](webhooks/slack.md) | Post scan results to a Slack channel |
| [Custom webhook](webhooks/custom.md) | Generic webhook receiver example |

## Prerequisites

All CI/CD examples assume:

- Proscan is running on your network
- The CI runner has network access to the Proscan instance
- You have an API token (generate one from Settings > API Tokens in the Proscan web UI)
- Credentials are stored as secrets in your CI platform (never hardcoded)
