# Getting Started

New to Claude Code? This guide walks through everything you need to use this marketplace.

## Table of Contents

1. [What is Claude Code?](#what-is-claude-code)
2. [What are Plugins?](#what-are-plugins)
3. [Installation](#installation)
4. [Using the Marketplace](#using-the-marketplace)
5. [Your First Plugin](#your-first-plugin)
6. [Troubleshooting](#troubleshooting)

---

## What is Claude Code?

Claude Code is an AI coding assistant from Anthropic. It helps with:

- Writing and analyzing code
- Automating repetitive tasks
- Research and documentation
- Data analysis and visualization

It's like having an expert programmer who can also search the web, run commands, and write code for you.

### How It Works

You interact with Claude Code through:

- **Terminal/Command Line** (CLI)
- **VS Code Extension** (IDE integration)

It understands natural language and can execute commands, read files, write code, and more.

---

## What are Plugins?

Plugins extend Claude Code with specialized capabilities. There are four types:

### 1. Slash Commands

Pre-written prompts that automate common tasks.

**Example:**

```
/discover-api url=https://data.example.gov
```

This runs a full workflow to reverse engineer APIs.

### 2. Skills

More advanced workflows with helper scripts and resources.

### 3. Subagents

Specialized AI agents for specific tasks (fact-checking, analysis, etc.).

### 4. MCP Servers

Connections to external tools and data sources.

---

## Installation

### Install Claude Code

#### Option A: CLI (Terminal)

**macOS/Linux:**

```bash
npm install -g @anthropic-ai/claude-code
```

**Windows:**

```powershell
npm install -g @anthropic-ai/claude-code
```

**Verify installation:**

```bash
claude --version
```

#### Option B: VS Code Extension

1. Open VS Code
2. Go to Extensions (Cmd+Shift+X or Ctrl+Shift+X)
3. Search for "Claude Code"
4. Click Install

### Authenticate

```bash
claude auth login
```

Follow the prompts to connect your Anthropic account.

---

## Using the Marketplace

### Add the Data Journalism Marketplace

```bash
/plugin marketplace add ruimgbarros/data-journalism-marketplace
```

This connects to our GitHub repository containing all the plugins.

### Browse Available Plugins

```bash
/plugin
```

This shows all plugins from added marketplaces. You'll see:

- Plugin names
- Descriptions
- Categories
- Installation commands

### Install a Plugin

```bash
/plugin install discover-api@data-journalism-marketplace
```

The format is: `/plugin install [plugin-name]@[marketplace-name]`

### List Installed Plugins

```bash
/plugin list
```

---

## Your First Plugin

Let's try the `/discover-api` plugin to reverse engineer a public data API.

### Check prerequisites

You'll need Chrome DevTools MCP for this plugin:

```bash
claude mcp add --transport http chrome-devtools http://localhost:3000
```

See [plugins/slash-commands/discover-api/DEPENDENCIES.md](plugins/slash-commands/discover-api/DEPENDENCIES.md) for detailed setup.

### Run the command

```bash
/discover-api url=https://data.example.gov
```

Replace `https://data.example.gov` with any public data portal you want to investigate.

### Watch it work

Claude Code opens the URL in Chrome, interacts with the page (clicking filters, pagination, search forms), monitors network requests, identifies API endpoints, then generates documentation and code.

### Review the output

You get two files:
- **API_DOCUMENTATION.md** - Complete API reference
- **Working code** in Python (or R/JavaScript)

### Use the data

Run the generated code to download data for your story.

---

## Troubleshooting

### "Command not found: claude"

**Problem**: Claude Code CLI isn't installed or not in PATH.

**Solution**:

```bash
# Install Claude Code
npm install -g @anthropic-ai/claude-code

# Verify
which claude
```

### "Plugin marketplace not found"

**Problem**: Marketplace URL is incorrect or repository is private.

**Solution**:

```bash
# Check marketplace list
/plugin marketplace list

# Try adding again with full URL
/plugin marketplace add https://github.com/ruimgbarros/data-journalism-marketplace.git
```

### "MCP server not found"

**Problem**: Required dependency (like Chrome DevTools) isn't installed.

**Solution**:

```bash
# List MCP servers
claude mcp list

# Add the required server
claude mcp add --transport http chrome-devtools http://localhost:3000
```

See plugin-specific DEPENDENCIES.md files for detailed setup.

### "Permission denied"

**Problem**: Need admin/sudo access.

**Solution**:

```bash
# macOS/Linux
sudo npm install -g @anthropic-ai/claude-code

# Windows: Run PowerShell as Administrator
```

### "Rate limited" or "API quota exceeded"

**Problem**: Made too many requests too quickly.

**Solution**:

- Wait a few minutes
- Add delays in your code (1-2 seconds between requests)
- Check the data source's terms of service

### Plugin doesn't work as expected

**Problem**: Plugin may be outdated or have bugs.

**Solution**:

1. Check plugin README for known issues
2. Update the marketplace:
   ```bash
   /plugin marketplace update data-journalism-marketplace
   ```
3. Open an issue on GitHub with details

---

## Next Steps

### Learn More

- **Read the [README](README.md)** - Overview of all available plugins
- **Check [Use Cases](USE_CASES.md)** - Real journalism scenarios (coming soon)
- **Review [FAQ](FAQ.md)** - Common questions (coming soon)

### Contribute

Found a bug? Have an idea? Want to share your own plugin?

See [CONTRIBUTING.md](CONTRIBUTING.md) for how to get involved.

### Join the Community

- GitHub Discussions (coming soon)
- Share your stories and use cases
- Help other journalists get started

---

## Tips

**Start small.** Try one plugin at a time.

**Read the docs.** Each plugin has a README with examples.

**Test first.** Before analyzing real data, test on a sample.

**Keep notes.** Document your workflow for reproducing results and methodology sections.

**Ask for help.** Check documentation, open GitHub issues, or contact plugin authors.

**Share your work.** Published a story using these tools? Open an issue with the "story" label. Sharing your methodology helps other journalists.

---

## Glossary

- **CLI**: Command-Line Interface - text-based interaction with your computer
- **MCP**: Model Context Protocol - standard for connecting AI to external tools
- **Plugin**: Extension that adds functionality to Claude Code
- **Marketplace**: Collection of plugins from a specific source
- **Slash Command**: Quick prompt that starts with `/`
- **Subagent**: Specialized AI agent for specific tasks

---

## Additional Resources

### Claude Code

- [Official Documentation](https://docs.claude.com/claude-code)
- [GitHub Repository](https://github.com/anthropics/claude-code)

### Data Journalism

- [NICAR](https://www.ire.org/training/conferences/nicar/) - Data journalism conferences
- [GIJN](https://gijn.org/) - Global Investigative Journalism Network
- [Source](https://source.opennews.org/) - Journalism code and tools

### Learning Resources

- Command line basics: [The Command Line Crash Course](https://learnpythonthehardway.org/book/appendixa.html)
- Git/GitHub: [GitHub Guides](https://guides.github.com/)
- Python for data analysis: [Python for Data Analysis](https://wesmckinney.com/book/)

---

**Welcome to the community! Happy investigating!** 🔍📊✨
