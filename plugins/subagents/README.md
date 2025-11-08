# Subagents

This directory contains custom subagents - specialized AI agents for specific data journalism tasks.

## What are Subagents?

Subagents are custom agents that:

- Handle specialized tasks autonomously
- Can be delegated work by parent agents
- Run in parallel for improved efficiency
- Have specific expertise (e.g., statistical analysis, fact-checking)

## Available Subagents

<!-- Subagents will be listed here automatically as they're added -->

## How to Use

Subagents are accessible via the `/agents` command in Claude Code. They can work independently or be orchestrated by parent agents.

## How to Contribute

See [CONTRIBUTING.md](../../CONTRIBUTING.md) for guidelines on creating subagents.

### Example Structure

```
plugins/subagents/your-agent-name/
├── README.md              # Documentation
├── agent-config.json      # Agent configuration
├── prompts/               # Agent-specific prompts
│   └── system-prompt.md
└── examples/              # Usage examples
    └── example-task.md
```
