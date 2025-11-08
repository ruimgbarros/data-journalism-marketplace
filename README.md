# Data Journalism Marketplace

**A community-driven Claude Code marketplace for data journalists worldwide.**

Tools for API discovery, data analysis, visualization, OSINT, and investigative reporting.

---

## Why This Exists

Data journalists need better tools. This marketplace shares the commands, scripts, and workflows we actually use to find stories in data.

## 📦 What's Inside

This marketplace provides Claude Code plugins specifically designed for data journalism:

- **Slash Commands** - Automated prompts for common tasks
- **Skills** - Advanced workflows with helper scripts
- **Subagents** - Specialized AI agents for specific journalism needs
- **MCP Servers** - Integrations with external tools and data sources

## 🚀 Quick Start

### 1. Install Claude Code

If you haven't already:

```bash
# Install Claude Code CLI
npm install -g @anthropic-ai/claude-code
```

See [GETTING_STARTED.md](GETTING_STARTED.md) for detailed setup.

### 2. Add This Marketplace

```bash
/plugin marketplace add ruimgbarros/data-journalism-marketplace
```

### 3. Browse & Install Plugins

```bash
# Browse available plugins
/plugin

# Install a specific plugin
/plugin install discover-api@data-journalism-marketplace
```

### 4. Use Your Plugin

```bash
# Example: Reverse engineer a government API
/discover-api url=https://data.example.gov
```

## 📋 Available Plugins

### API Discovery & Web Scraping

#### [discover-api](plugins/slash-commands/discover-api) 🔍

**Reverse engineer hidden APIs in web portals**

- Perfect for government sites, court records, public databases
- Automatically documents endpoints, parameters, and responses
- Generates working code in Python, R, or JavaScript
- **Difficulty**: Intermediate
- **Dependencies**: Chrome DevTools MCP

<!-- More plugins will be listed here as they're added -->

## 🤝 Contributing

Got a useful command or workflow? Share it!

**Ways to contribute:**
- Submit your own plugins - [see the guide](CONTRIBUTING.md)
- Request features you need
- Fix typos, add examples
- Tell us how you used these tools in your stories

Full guidelines in [CONTRIBUTING.md](CONTRIBUTING.md).

### Quality Standards

All plugins must:

- ✅ Work with public data for legitimate journalism
- ✅ Include clear documentation and examples
- ✅ Follow ethical guidelines (respect robots.txt, rate limits, etc.)
- ✅ Be tested on real-world scenarios

## 📖 Documentation

- [**Getting Started**](GETTING_STARTED.md) - New to Claude Code? Start here
- [**Contributing Guide**](CONTRIBUTING.md) - How to submit plugins

## 🛡️ Ethical Guidelines

This marketplace is for **public interest journalism** using **publicly accessible data**.

### We Support

✅ Investigating government spending
✅ Analyzing public records
✅ Tracking legislation
✅ Election analysis
✅ Public health data
✅ FOIA automation

### We Don't Support

❌ Circumventing paywalls
❌ Accessing private/personal data without consent
❌ Violating terms of service
❌ Overwhelming servers (DDoS)
❌ Ignoring robots.txt

## 🔧 Technical Details

### Marketplace Structure

```
data-journalism-marketplace/
├── .claude-plugin/
│   └── marketplace.json      # Plugin registry
├── plugins/
│   ├── slash-commands/        # Automated prompts
│   ├── skills/                # Advanced workflows
│   ├── subagents/             # Specialized agents
│   └── mcp-servers/           # External integrations
├── CONTRIBUTING.md            # Contribution guidelines
├── GETTING_STARTED.md         # Beginner guide
└── README.md                  # This file
```

### Adding the Marketplace

**Via GitHub:**

```bash
/plugin marketplace add ruimgbarros/data-journalism-marketplace
```

**Locally (for development):**

```bash
/plugin marketplace add file:///path/to/data-journalism-marketplace
```

## 🌍 Community

### Get Involved

- 🐛 **Issues**: [Report bugs or request features](https://github.com/ruimgbarros/data-journalism-marketplace/issues)

### Who's Using This?

We'd love to hear from you! If you've used plugins from this marketplace in your reporting:

- Open an issue with the "story" label
- Link to your published work (if public)
- Help inspire other journalists

## 📜 License

MIT License - See [LICENSE](LICENSE) for details.

Plugins may have their own licenses - check individual plugin directories.
