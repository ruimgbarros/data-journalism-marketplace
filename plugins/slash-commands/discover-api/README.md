# /discover-api - Reverse Engineer Hidden APIs

**Category**: API Discovery & Web Scraping
**Author**: Rui Barros
**Difficulty**: Intermediate
**Language Support**: Python (default), R, JavaScript

## What It Does

Automatically discovers and documents hidden APIs in web portals by:
1. Opening the site in Chrome with DevTools
2. Interacting with forms, filters, and controls
3. Monitoring network traffic
4. Identifying API endpoints
5. Generating comprehensive documentation and working code

Perfect for data journalists who need to access data from:
- Government portals without public APIs
- Court record systems
- Legislative tracking sites
- Public procurement databases
- Election results platforms
- Any data-rich website without documentation

## Prerequisites

### Required
- **Chrome DevTools MCP** - Used to control Chrome and monitor network traffic
  - See [DEPENDENCIES.md](DEPENDENCIES.md) for installation instructions
- **Google Chrome** browser installed

### Optional
- Python with `requests` and `pandas` packages (for Python code generation - default)
- R with `httr2` and `jsonlite` packages (for R code generation)
- Basic understanding of HTTP/REST APIs

## Installation

1. Add the Data Journalism Marketplace:
```bash
/plugin marketplace add ruimgbarros/data-journalism-marketplace
```

2. Install this plugin:
```bash
/plugin install discover-api@data-journalism-marketplace
```

3. Set up Chrome DevTools MCP (see [DEPENDENCIES.md](DEPENDENCIES.md))

## Usage

### Basic Usage

```
/discover-api url=https://example-government-portal.gov
```

This will use Python (default) for code generation.

### Specify Programming Language

```
/discover-api url=https://courts.example.gov language=R
```

Supported languages: Python (default), R, JavaScript

### What You'll Get

After running the command, you'll receive:

1. **API_DOCUMENTATION.md** - Complete API reference with:
   - All discovered endpoints
   - Request/response formats
   - Authentication requirements
   - Pagination strategies
   - Rate limiting notes
   - Example queries

2. **Working Code** - Production-ready code in your chosen language that:
   - Handles authentication
   - Manages pagination automatically
   - Includes error handling and retries
   - Saves data to CSV/JSON
   - Has detailed comments

## Real-World Examples

See [EXAMPLES.md](EXAMPLES.md) for detailed walkthroughs of:
- Discovering APIs in government procurement portals
- Accessing court record systems
- Extracting legislative data
- Downloading election results
- Scraping public health databases

## Ethical Guidelines

This tool is designed for **public interest journalism** on **publicly accessible data**. Always:

✅ **DO**:
- Check `robots.txt` before scraping
- Respect rate limits and add delays
- Use data for legitimate journalistic purposes
- Credit data sources in your reporting
- Cache data locally to minimize requests
- Document your methodology

❌ **DON'T**:
- Circumvent paywalls or authentication
- Scrape personal/private data without consent
- Overwhelm servers with rapid requests
- Use data for commercial purposes without permission
- Ignore copyright or terms of service
- Share API credentials publicly

## Troubleshooting

### "Chrome DevTools MCP not found"
- Install the MCP server (see [DEPENDENCIES.md](DEPENDENCIES.md))
- Verify it's running: `claude mcp list`

### "Cannot interact with page elements"
- Some sites use shadow DOM or iframes - you may need to adjust the approach
- Check if the site requires authentication first

### "No API endpoints found"
- Site might use WebSockets instead of REST APIs
- Try interacting more with different page elements
- Check browser console for errors

### "Rate limited"
- Add delays between requests
- Consider running during off-peak hours
- Contact the site administrator for access

## Tips for Success

1. **Start Simple**: Test with one search query before automating
2. **Document Everything**: Take screenshots and notes during discovery
3. **Test Edge Cases**: Try empty results, pagination limits, special characters
4. **Validate Data**: Cross-check discovered data with the website UI
5. **Ask for Permission**: When in doubt, contact the data provider

## Contributing

Found a bug? Have a suggestion? See our [contribution guidelines](../../../CONTRIBUTING.md).

## License

MIT License - See [LICENSE](../../../LICENSE) for details.

## Support

- Open an issue on GitHub
- Join the data journalism community discussions
- Check the [FAQ](../../../FAQ.md)

---

**Happy API hunting!** 🕵️📊
