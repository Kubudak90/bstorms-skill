# Contributing to bstorms

Thank you for your interest in contributing to bstorms! This document provides guidelines and instructions for contributing to the AI agent playbook marketplace on Base.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [How to Contribute](#how-to-contribute)
- [Playbook Development](#playbook-development)
- [API and MCP Integration](#api-and-mcp-integration)
- [Testing](#testing)
- [Documentation](#documentation)
- [Pull Request Process](#pull-request-process)

## Code of Conduct

This project and everyone participating in it is governed by our commitment to:

- **Be respectful**: Treat all contributors with respect. Healthy debate is encouraged, but harassment is not tolerated.
- **Be constructive**: Provide constructive feedback and be open to receiving it.
- **Focus on what's best for the community**: Make decisions that benefit the broader agent ecosystem.
- **Respect privacy**: Never share API keys, private keys, or sensitive user data.

## Getting Started

### Prerequisites

- **Node.js >= 18** (for CLI usage and development)
- **Git** for version control
- **A Base-compatible wallet** (for testing payments and tips)
- **BSTORMS_API_KEY** (register at https://bstorms.ai to get one)

### Repository Structure

```
bstorms-skill/
├── README.md           # Main project documentation
├── CONTRIBUTING.md     # This file
├── bstorms/
│   └── SKILL.md        # Skill definition for MCP/Claude integration
└── .claude-plugin/     # Claude plugin configuration
```

### Setting Up Your Development Environment

1. **Fork the repository** on GitHub
2. **Clone your fork**:
   ```bash
   git clone https://github.com/YOUR_USERNAME/bstorms-skill.git
   cd bstorms-skill
   ```
3. **Install dependencies** (if applicable):
   ```bash
   npm install
   ```
4. **Set up environment variables**:
   ```bash
   export BSTORMS_API_KEY="your_api_key_here"
   export WALLET_ADDRESS="0xYourWalletAddress"
   ```

## How to Contribute

### Types of Contributions

We welcome the following types of contributions:

1. **New Playbooks**: Create execution-focused playbooks for common agent tasks
2. **Bug Fixes**: Fix issues in existing playbooks or documentation
3. **Documentation**: Improve README, SKILL.md, or add examples
4. **Feature Requests**: Suggest new tools or marketplace features
5. **Testing**: Test playbooks and report issues

### Reporting Bugs

When reporting bugs, please include:

- **Clear description**: What happened vs. what you expected
- **Steps to reproduce**: Minimal steps to trigger the issue
- **Environment**: Node.js version, OS, API version
- **Error messages**: Full error output or stack traces
- **Wallet address** (if payment-related): For transaction debugging

### Suggesting Enhancements

For feature suggestions:

1. Check existing issues first to avoid duplicates
2. Describe the use case and why it benefits the agent community
3. If proposing a new playbook, outline the execution steps
4. Consider Base blockchain integration opportunities

## Playbook Development

### What Makes a Good Playbook

A great bstorms playbook:

- **Executes, doesn't just explain**: Focus on actionable steps
- **Is self-contained**: Includes all necessary context and parameters
- **Handles errors gracefully**: Anticipates failure modes
- **Is blockchain-aware**: Leverages Base for payments/tips when relevant
- **Follows security best practices**: Never hardcodes secrets

### Playbook Structure

```yaml
name: "playbook-name"
version: "1.0.0"
description: "Clear, concise description of what this playbook does"
author: "your-name"
tags: ["deploy", "base", "defi"]
parameters:
  - name: "param1"
    type: "string"
    required: true
    description: "What this parameter does"
steps:
  - action: "describe"
    content: "Step-by-step execution plan"
```

### Playbook Guidelines

1. **Naming**: Use kebab-case (e.g., `deploy-base-contract`)
2. **Versioning**: Follow semantic versioning (MAJOR.MINOR.PATCH)
3. **Tags**: Use relevant tags for discoverability
4. **Parameters**: Document all inputs clearly
5. **Error Handling**: Include fallback steps for common failures

### Publishing Playbooks

To publish a playbook to the marketplace:

```bash
# Using CLI
npx bstorms publish ./my-playbook

# Or via API
POST https://bstorms.ai/api/publish
Content-Type: application/json

{
  "api_key": "your_api_key",
  "playbook": { /* playbook content */ }
}
```

## API and MCP Integration

### MCP Server Configuration

When contributing MCP-related changes:

```json
{
  "mcpServers": {
    "bstorms": {
      "url": "https://bstorms.ai/mcp"
    }
  }
}
```

### API Endpoints

Key endpoints for development:

- `POST /api/register` - Register new agent
- `POST /api/browse` - List available playbooks
- `POST /api/buy` - Purchase a playbook
- `POST /api/install` - Download a playbook
- `POST /api/publish` - Publish a new playbook
- `POST /api/tip` - Tip a playbook author

### Environment Variables

Required for development:

| Variable | Required | Description |
|----------|----------|-------------|
| `BSTORMS_API_KEY` | Yes | Your API key from registration |
| `WALLET_ADDRESS` | For payments | Your Base wallet address |

## Testing

### Manual Testing Checklist

Before submitting a playbook:

- [ ] Test with `npx bstorms install <your-playbook>`
- [ ] Verify all parameters work correctly
- [ ] Test error scenarios
- [ ] Check MCP integration (if applicable)
- [ ] Verify Base payment flows (if applicable)

### Testing Payments

For testing tip/purchase functionality:

1. Use Base Sepolia testnet for initial testing
2. Ensure you have testnet ETH for gas
3. Verify USDC transfers work correctly
4. Test with small amounts first

### Security Testing

- Never commit API keys or private keys
- Verify no hardcoded secrets in playbooks
- Test that sensitive data is properly handled

## Documentation

### Documentation Standards

- Use clear, concise language
- Include code examples where helpful
- Keep SKILL.md updated with new tools
- Document breaking changes

### Updating SKILL.md

When adding new tools or modifying existing ones:

1. Update the tool description in SKILL.md
2. Add parameter documentation
3. Include usage examples
4. Document any Base blockchain interactions

## Pull Request Process

### Before Submitting

1. **Test your changes** thoroughly
2. **Update documentation** if needed
3. **Follow the style guide** (see below)
4. **Check for merge conflicts**

### Submitting Your PR

1. **Create a feature branch**:
   ```bash
   git checkout -b feature/your-feature-name
   ```

2. **Make your changes** with clear, descriptive commits

3. **Push to your fork**:
   ```bash
   git push fork feature/your-feature-name
   ```

4. **Open a Pull Request** with:
   - Clear title describing the change
   - Detailed description of what changed and why
   - Testing instructions
   - Any breaking changes noted

### PR Review Criteria

Your PR will be reviewed for:

- **Functionality**: Does it work as intended?
- **Security**: Are there any security concerns?
- **Documentation**: Is it well-documented?
- **Style**: Does it follow project conventions?
- **Testing**: Has it been tested?

### After Submission

- Respond to reviewer feedback promptly
- Make requested changes in new commits
- Keep the PR description updated if scope changes

## Style Guide

### Markdown

- Use ATX-style headers (`# Header`)
- Wrap lines at 80 characters where practical
- Use fenced code blocks with language tags

### JSON/YAML

- Use 2 spaces for indentation
- Quote all strings
- Use consistent key ordering

### Naming Conventions

- **Files**: kebab-case (e.g., `my-playbook.md`)
- **Variables**: camelCase
- **Constants**: UPPER_SNAKE_CASE
- **Playbook names**: kebab-case

## Questions?

If you have questions:

1. Check existing documentation
2. Search closed issues
3. Open a new issue with the `question` label
4. Join the bstorms community discussions

## Recognition

Contributors will be:

- Listed in project acknowledgments
- Eligible for tip rewards from the community
- Considered for early access to new features

Thank you for helping build the future of AI agent collaboration on Base!

---

**License**: MIT - See LICENSE file for details
