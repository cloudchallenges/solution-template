# Solution Template

{{One-sentence description of what this solution implements, including cloud provider and purpose.}}

📋 [View Challenge](https://hyperoot.dev/challenges) · 📖 [Read Solution Guide](https://hyperoot.dev/solutions)

## Architecture

```shell
![Architecture](./assets/{{architecture-diagram}})
```

## Quick Start

### Prerequisites

- Cloud Provider CLI configured (e.g., AWS CLI, Azure CLI, gcloud)
- Terraform installed
- Runtime / Language Version installed (Python, Node, Go, etc.)
- Any other tooling required for building artifacts

### Deploy

```bash
# 1. Build application artifacts
./scripts/build.sh

# 2. Initialize Terraform
cd terraform/environments/dev
terraform init

# 3. Deploy infrastructure
terraform apply
```

### Test

```bash
# Run sample input
./scripts/test.sh
```

### Destroy

```bash
cd terraform/environments/dev
terraform destroy
```

## Development Setup

These instructions help users work inside a consistent development environment if they want to explore, adjust, or extend the solution codebase.

### Option 1: Use Dev Container (Recommended — Easiest)

This is the simplest and most reliable setup.
All tools are installed automatically, and setup scripts run on their own.

#### Requirements

- Docker installed & running
- VS Code installed
- Dev Containers extension installed

#### Steps

1. Open this repository folder in VS Code
2. VS Code detects `.devcontainer/` automatically
3. Choose **“Reopen in Container”**
4. The environment is fully ready — no manual setup required

**Notes:**

- `setup.sh` runs automatically via the Dev Container post-create hook
- `enter_project.sh` runs via Mise directory hooks
- You **do not** need to manually run scripts or install tools

### Option 2: Local Development (Manual or Mise)

If you prefer not to use Dev Containers, you can set up your environment locally.

#### 1. Install required tools

You may install tools in one of two ways:

##### a) **Using Mise (recommended)**

Mise automatically installs the tool versions defined in `mise.toml`.

Install Mise → [https://mise.jdx.dev](https://mise.jdx.dev)

Then run:

```bash
mise install
```

##### b) **Manual installation**

Install the necessary tools yourself:
Terraform, cloud CLI, language runtime, build tools, etc.

#### 2. Enter the environment

If using Mise:

```bash
./scripts/enter_project.sh
```

This loads tool versions, environment variables, and hooks.

#### 3. Begin exploring or modifying the solution

The main implementation lives in:

```shell
├── src/                  # Application / function / service code
├── terraform/            # Infrastructure as Code
└── samples/              # Input / test data
```

## Repository Structure

```shell
├── src/                  # Application/service implementation
├── terraform/            # Infrastructure as Code
├── samples/              # Test data or inputs
│
├── .devcontainer/        # Optional Dev Container setup
├── .github/              # Issue/PR templates & automation
├── docs/                 # Supplemental notes
├── scripts/              # Build, deploy, test, environment scripts
├── mise.toml             # Toolchain definition
└── README.md
```

## Explanation of Other Files

These files support development workflows but are not required for deploying or testing the solution.

- **`.devcontainer/`**
  Reproducible VS Code development environment
  → [https://containers.dev](https://containers.dev)

- **`.pre-commit-config.yaml`**
  Ensures formatting, linting, static checks
  → [https://pre-commit.com](https://pre-commit.com)

- **`.github/`**
  Contains issue templates, PR templates, CODEOWNERS, and workflow automation
  → [https://docs.github.com/repositories](https://docs.github.com/repositories)

- **`mise.toml`**
  Defines the toolchain versions required for this solution
  → [https://mise.jdx.dev](https://mise.jdx.dev)

- **`scripts/`**
  Helper scripts for building artifacts, testing, deploying, cleanup

## License

See [LICENSE](./LICENSE) for details.

## Support

If you find this helpful, consider supporting my work ❤️

[![Sponsor on GitHub](https://img.shields.io/badge/Sponsor-GitHub-ea4aaa?style=for-the-badge\&logo=github)](https://github.com/sponsors/{{your-username}})
