# Dependencies for /discover-api

This plugin requires the **Chrome DevTools MCP** server to control Chrome and monitor network traffic.

## What is Chrome DevTools MCP?

Chrome DevTools MCP is a Model Context Protocol server that gives Claude Code the ability to:
- Launch and control Chrome browser
- Navigate to URLs
- Interact with web pages (click, type, scroll)
- Monitor network requests
- Take screenshots
- Execute JavaScript

It's essential for the `/discover-api` command to function.

## Installation

### Option 1: Install via Claude Code (Recommended)

```bash
claude mcp add --transport http chrome-devtools https://chrome-devtools-mcp.example.com
```

### Option 2: Manual Installation

If you need to run the MCP server locally:

1. **Install Node.js** (if not already installed)
   - Download from https://nodejs.org
   - Verify: `node --version`

2. **Install the Chrome DevTools MCP Server**
   ```bash
   npm install -g @modelcontextprotocol/server-chrome-devtools
   ```

3. **Start the server**
   ```bash
   chrome-devtools-mcp
   ```

4. **Add to Claude Code**
   ```bash
   claude mcp add --transport http chrome-devtools http://localhost:3000
   ```

### Option 3: Docker Installation

If you prefer Docker:

```bash
docker run -p 3000:3000 mcp/chrome-devtools
claude mcp add --transport http chrome-devtools http://localhost:3000
```

## Verification

After installation, verify the MCP server is working:

```bash
# List all MCP servers
claude mcp list

# Test the chrome-devtools server
claude mcp get chrome-devtools
```

You should see the Chrome DevTools MCP server listed with available tools.

## Configuration

### Basic Configuration

The default configuration should work for most users. The MCP server will:
- Launch Chrome in headless mode
- Use a temporary user profile
- Clean up after each session

### Advanced Configuration

If you need custom Chrome options, you can configure the MCP server:

```json
{
  "mcpServers": {
    "chrome-devtools": {
      "transport": "http",
      "url": "http://localhost:3000",
      "options": {
        "headless": false,
        "slowMo": 100,
        "devtools": true
      }
    }
  }
}
```

Place this in your project's `.claude/settings.json` or global `~/.claude/settings.json`.

### Headless vs Headed Mode

**Headless (Default)**:
- No visible browser window
- Faster and uses less resources
- Good for automation

**Headed** (for debugging):
```json
{
  "headless": false
}
```
- See the browser window
- Helpful for understanding what's happening
- Useful when debugging API discovery

## Troubleshooting

### "MCP server not found"

**Check if it's installed:**
```bash
claude mcp list
```

**If not listed, add it:**
```bash
claude mcp add --transport http chrome-devtools <url>
```

### "Chrome failed to launch"

**Ensure Chrome is installed:**
- macOS: Install from https://www.google.com/chrome/
- Linux: `sudo apt install chromium-browser`
- Windows: Install from https://www.google.com/chrome/

**Check Chrome path:**
The MCP server auto-detects Chrome. If it fails, set the path manually:
```bash
export CHROME_PATH=/path/to/chrome
```

### "Connection refused"

**If using local server:**
- Ensure the MCP server is running
- Check the port (default: 3000)
- Verify firewall settings

**If using remote server:**
- Check network connectivity
- Verify the URL is correct
- Ensure the server is accessible

### "Token limit exceeded"

The MCP server returns page content which can be large. Configure token limits:

```bash
export MAX_MCP_OUTPUT_TOKENS=50000
```

Default is 25,000 tokens; warning at 10,000 tokens.

## Usage with /discover-api

Once installed, the `/discover-api` command will automatically use Chrome DevTools MCP to:

1. Launch Chrome in the background
2. Navigate to your target URL
3. Interact with page elements
4. Monitor network traffic
5. Capture API requests
6. Close Chrome when done

You don't need to manually control Chrome - the command handles everything!

## Security Considerations

### Data Privacy
- Chrome runs in an isolated profile
- No browser history is saved
- Cookies are cleared after each session
- Use incognito mode for sensitive sites

### Network Security
- Be aware that MCP servers can access any URL
- Only use trusted MCP server implementations
- Review MCP server code if running locally
- Use HTTPS for remote MCP servers

### Credentials
- Never share API keys or passwords in prompts
- Use environment variables for sensitive data
- Don't commit credentials to version control

## Updates

Keep the MCP server updated:

```bash
npm update -g @modelcontextprotocol/server-chrome-devtools
```

Check for breaking changes in release notes.

## Alternative Tools

If Chrome DevTools MCP doesn't meet your needs:

- **Puppeteer** - Direct Node.js automation
- **Selenium** - Multi-browser support
- **Playwright** - Modern automation framework
- **Browser DevTools** - Manual inspection

However, these require more manual setup and don't integrate with Claude Code.

## Resources

- [MCP Documentation](https://modelcontextprotocol.io)
- [Chrome DevTools Protocol](https://chromedevtools.github.io/devtools-protocol/)
- [MCP Server Directory](https://mcp.so)

## Need Help?

- Check the [FAQ](../../../FAQ.md)
- Open an issue on GitHub
- Join the data journalism community

---

**Once you have Chrome DevTools MCP installed, you're ready to discover APIs!** 🚀
