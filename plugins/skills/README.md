# Skills

This directory contains skills - task-specific prompts with helper scripts and local resources.

## What are Skills?

Skills are more advanced than slash commands. They:
- Contain a `SKILL.md` file with instructions
- Can include helper scripts (Python, R, JavaScript)
- Can bundle templates, example data, or other resources
- Expand on-demand to provide context to Claude Code

## Available Skills

<!-- Skills will be listed here automatically as they're added -->

## How to Use

Skills are invoked through the Skill tool in Claude Code. They provide specialized capabilities for complex data journalism tasks.

## How to Contribute

See [CONTRIBUTING.md](../../CONTRIBUTING.md) for guidelines on creating and submitting skills.

### Example Structure

```
plugins/skills/your-skill-name/
├── SKILL.md               # Main skill instructions
├── README.md              # Documentation
├── scripts/               # Helper scripts
│   ├── analyze.R
│   └── process.py
├── templates/             # Templates
│   └── report-template.md
└── examples/              # Example data and usage
    └── sample-dataset.csv
```
