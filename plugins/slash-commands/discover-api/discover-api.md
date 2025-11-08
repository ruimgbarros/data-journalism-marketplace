---
description: Reverse engineer and document hidden APIs in any web portal - perfect for government sites, court records, and public databases
---

I need you to reverse engineer the API for {{url}}.

Here's what I need you to do:

## Step 1: Open and Capture
1. Open the URL in Chrome using Chrome DevTools MCP
2. Take a snapshot of the page structure
3. Identify interactive elements (search filters, date pickers, pagination, dropdowns)

## Step 2: Interaction and Monitoring
Monitor network requests while you interact with the page:
- Fill in search forms with test queries
- Adjust date ranges
- Click pagination controls (next page, previous page, jump to page)
- Change any filters or sorting options
- Trigger any data export/download options

## Step 3: Document Each API Endpoint
For each endpoint that returns data (JSON), document:
- **Full URL pattern** (including any path parameters)
- **HTTP method** (GET, POST, PUT, etc.)
- **Required parameters** (what's needed for the request to work)
- **Optional parameters** (pagination, filtering, sorting)
- **Response structure** (key fields and data types)
- **Pagination mechanism** (offset/limit, cursor, page numbers)
- **Authentication** (if any - cookies, tokens, API keys)
- **Rate limiting** (if you notice any patterns)

## Step 4: Generate Code Examples
Create working code examples in {{language:Python}} that:
- Make authenticated requests (if needed)
- Handle pagination automatically
- Parse JSON responses
- Extract key data fields
- Include error handling
- Show how to save data to CSV/JSON

## Important Guidelines for Data Journalists
- **Focus on public data only** - respect paywalls and authentication
- **Check robots.txt** - note any restrictions
- **Respect rate limits** - don't hammer the server
- **Document authentication** - if the site requires login, explain the process
- **Note data freshness** - when is data updated?
- **Identify unique identifiers** - what fields can be used as primary keys?

## Deliverables
Create two files:

### 1. API_DOCUMENTATION.md
Clean markdown documentation with:
- Overview of the data source
- Base URL and endpoints
- Authentication requirements
- Request/response examples
- Pagination strategy
- Known limitations
- Example queries for common use cases

### 2. Working {{language:Python}} Code
Production-ready code using appropriate HTTP libraries (requests, pandas) that:
- Demonstrates authentication
- Handles pagination
- Includes retry logic
- Saves data in useful formats
- Has clear comments

## Special Considerations
- If you encounter CAPTCHA or bot detection, document it
- If data requires authentication, provide step-by-step setup
- If there's a public API already, compare it to what you discovered
- Note any undocumented endpoints or features
- Check for GraphQL endpoints (look for /graphql paths)

Focus on endpoints that return **data** (JSON, CSV). Ignore assets like images, CSS, and JavaScript files.

Be thorough and document edge cases. This documentation will be used for investigative reporting!
