# Contributing

Thanks for considering contributing! This marketplace helps data journalists share tools and workflows.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How to Contribute](#how-to-contribute)
- [Plugin Types](#plugin-types)
- [Submission Guidelines](#submission-guidelines)
- [Quality Standards](#quality-standards)
- [Ethical Guidelines](#ethical-guidelines)

---

## Code of Conduct

This marketplace serves the public interest through journalism. All contributors must:

✅ **DO**:

- Focus on public data and legitimate journalism use cases
- Respect copyright, terms of service, and `robots.txt`
- Provide clear documentation
- Test plugins thoroughly
- Be welcoming to contributors of all skill levels
- Give credit where due

❌ **DON'T**:

- Create tools for circumventing paywalls or authentication
- Enable unethical scraping or data collection
- Include proprietary code without permission
- Submit low-quality or untested plugins
- Use offensive language or imagery

---

## How to Contribute

### 1. Fork and Clone

```bash
git fork https://github.com/ruimgbarros/data-journalism-marketplace
cd data-journalism-marketplace
```

### 2. Create a Branch

```bash
git checkout -b add-my-plugin-name
```

### 3. Add Your Plugin

See [Plugin Types](#plugin-types) for structure requirements.

### 4. Test Locally

```bash
# Add your local marketplace
/plugin marketplace add file:///path/to/data-journalism-marketplace

# Install your plugin
/plugin install your-plugin-name@data-journalism-marketplace

# Test thoroughly!
```

### 5. Submit Pull Request

- Fill out the PR template
- Include examples and screenshots
- Describe the journalism use case

---

## Plugin Types

### Slash Commands

**Location**: `plugins/slash-commands/your-command-name/`

**Required Files**:

```
your-command-name/
├── README.md              # Full documentation
├── your-command-name.md   # The command itself
├── EXAMPLES.md            # Real-world usage (can be brief initially)
└── DEPENDENCIES.md        # Requirements (optional if no dependencies)
```

**Command File Format** (`your-command-name.md`):

```markdown
---
description: Brief description of what your command does
---

Your command prompt goes here.

Use {{variable}} for user inputs.
Use {{variable:default}} for optional inputs with defaults.
```

**README.md Requirements**:

- What it does
- Prerequisites
- Installation instructions
- Usage examples
- Troubleshooting section

### Skills

**Location**: `plugins/skills/your-skill-name/`

**Required Files**:

```
your-skill-name/
├── SKILL.md               # Main skill instructions
├── README.md              # Documentation
├── scripts/               # Helper scripts (optional)
└── examples/              # Example usage (optional)
```

### Subagents

**Location**: `plugins/subagents/your-agent-name/`

**Required Files**:

```
your-agent-name/
├── README.md              # Documentation
├── agent-config.json      # Agent configuration
└── examples/              # Usage examples
```

### MCP Servers

**Location**: `plugins/mcp-servers/your-server-name/`

**Required Files**:

```
your-server-name/
├── README.md              # Documentation
├── server-config.json     # MCP configuration
├── SETUP.md               # Installation guide
└── examples/              # Usage examples
```

---

## Submission Guidelines

### Marketplace Entry

Add your plugin to `.claude-plugin/marketplace.json`:

```json
{
  "name": "your-plugin-name",
  "source": "./plugins/[type]/your-plugin-name",
  "description": "Brief description for the marketplace (max 200 chars)",
  "version": "1.0.0",
  "author": {
    "name": "Your Name",
    "email": "your@email.com",
    "url": "https://your-website.com"
  },
  "keywords": ["relevant", "searchable", "keywords"],
  "category": "API Discovery & Web Scraping",
  "language": "R",
  "difficulty": "beginner|intermediate|advanced",
  "dependencies": [
    {
      "name": "dependency-name",
      "type": "mcp-server|npm|python|r-package",
      "required": true,
      "description": "What this dependency does"
    }
  ]
}
```

### Categories

Choose the most appropriate category:

- **API Discovery & Web Scraping** - Tools for finding and accessing data
- **Data Analysis & Statistics** - Statistical analysis, modeling, validation
- **Data Visualization** - Charts, maps, interactive graphics
- **Document Processing** - PDFs, spreadsheets, OCR
- **OSINT** - Open source intelligence gathering
- **Team Collaboration & Workflows** - Productivity and teamwork tools

### Difficulty Levels

- **Beginner**: Works out of the box, minimal setup
- **Intermediate**: Requires some configuration or technical knowledge
- **Advanced**: Complex setup, assumes familiarity with tools

### Language Tags

Specify primary language if your plugin generates code:

- R
- Python
- JavaScript
- SQL
- Other (specify in description)

---

## Ethical Guidelines

All plugins must serve legitimate journalism purposes and respect ethical boundaries.

### Acceptable

✅ Accessing public government data
✅ Scraping publicly available information
✅ Automating FOIA request tracking
✅ Analyzing public records
✅ Data visualization for storytelling
✅ Statistical analysis and validation

### Not Acceptable

❌ Circumventing paywalls or authentication
❌ Scraping personal data without consent
❌ Violating terms of service
❌ Overwhelming servers (DDoS)
❌ Accessing restricted/private data
❌ Ignoring robots.txt

### Best Practices

1. **Respect Rate Limits**: Add delays between requests (1-2 seconds)
2. **Check robots.txt**: Honor crawling restrictions
3. **Attribution**: Credit data sources in your reporting
4. **Privacy**: Be careful with personal information
5. **Terms of Service**: Follow website rules
6. **Public Interest**: Focus on legitimate journalism

---

## Pull Request Template

When submitting a PR, include:

### Plugin Information

- **Name**: Your plugin name
- **Type**: Slash command / Skill / Subagent / MCP Server
- **Category**: Which category it belongs to
- **Difficulty**: Beginner / Intermediate / Advanced

### Description

- What problem does this solve?
- What journalism use case does it serve?
- How is it different from existing plugins?

### Testing

- [ ] Tested locally
- [ ] Works as documented
- [ ] Examples are reproducible
- [ ] Dependencies clearly listed
- [ ] Handles errors gracefully

### Journalism Use Case

- Describe a real story or investigation this could help with
- Optional: Link to published work using this tool

### Checklist

- [ ] README.md is complete
- [ ] Examples are provided
- [ ] Code follows ethical guidelines
- [ ] Dependencies are documented
- [ ] Added to marketplace.json
- [ ] Follows naming conventions
- [ ] Version number included

---

## Review Process

1. **Automated Checks**: PR triggers basic validation
2. **Community Review**: Other contributors provide feedback
3. **Maintainer Review**: Core team reviews for quality and ethics
4. **Testing**: Plugin is tested in real scenarios
5. **Merge**: Once approved, plugin is added to marketplace

---

## Recognition

All contributors are credited in:

- Plugin author field in marketplace.json
- README.md contributors section
