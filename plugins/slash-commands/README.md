# Slash Commands

This directory contains slash commands - reusable prompt templates that help automate common data journalism tasks.

## What are Slash Commands?

Slash commands are Markdown files that contain prompts. When you type `/command-name` in Claude Code, the prompt expands and executes.

## Available Commands

<!-- Plugins will be listed here automatically as they're added -->

## How to Use

After installing the marketplace, you can:
1. Type `/` in Claude Code to see all available commands
2. Select a command from the list
3. Provide any required parameters

## How to Contribute

See [CONTRIBUTING.md](../../CONTRIBUTING.md) for guidelines on submitting your own slash commands.

### Example Structure

```
plugins/slash-commands/your-command-name/
├── README.md              # Documentation
├── your-command-name.md   # The actual command
├── EXAMPLES.md            # Real-world usage examples
└── DEPENDENCIES.md        # Any MCP servers or tools needed
```
