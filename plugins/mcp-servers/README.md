# MCP Servers

This directory contains MCP (Model Context Protocol) server configurations and integrations.

## What are MCP Servers?

MCP servers provide Claude Code with access to:
- External tools and APIs
- Databases and data sources
- Custom integrations
- Specialized capabilities

They follow the open-source MCP standard - "USB-C for AI".

## Available MCP Servers

<!-- MCP servers will be listed here automatically as they're added -->

## How to Use

MCP servers are added using:
```bash
claude mcp add --transport http <name> <url>
```

Or configured in your project's Claude Code settings.

## How to Contribute

See [CONTRIBUTING.md](../../CONTRIBUTING.md) for guidelines on contributing MCP server configurations.

### Example Structure

```
plugins/mcp-servers/your-server-name/
├── README.md              # Documentation
├── server-config.json     # MCP server configuration
├── SETUP.md               # Installation instructions
└── examples/              # Usage examples
    └── example-usage.md
```

## Resources

- [MCP Documentation](https://modelcontextprotocol.io)
- [MCP Server Directory](https://mcp.so)
- [Building MCP Servers](https://github.com/modelcontextprotocol)
