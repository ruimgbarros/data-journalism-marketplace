# Data Journalism Marketplace - Implementation Plan

## Project Vision
Create a community-driven Claude Code marketplace specifically for data journalists, enabling sharing and discovery of slash commands, skills, subagents, and MCP servers tailored to investigative reporting, data analysis, and visualization.

## Target Audience
- Data journalists worldwide
- Investigative reporters working with data
- News organizations' data teams
- Freelance data journalists
- Anyone doing data-driven storytelling

---

## Stage 1: Core Marketplace Infrastructure

**Goal**: Set up the foundational marketplace structure that follows Claude Code plugin standards

**Success Criteria**:
- ✓ Marketplace can be added via `/plugin marketplace add ruibarros/data-journalism-marketplace`
- ✓ Users can browse available plugins via `/plugin` command
- ✓ Clear directory structure for different plugin types
- ✓ Working marketplace.json with proper schema

**Implementation Tasks**:
1. Create `.claude-plugin/marketplace.json` with metadata:
   - Marketplace name: "data-journalism-marketplace"
   - Owner information
   - Description focused on data journalism community
   - Version tracking (start at 1.0.0)

2. Set up plugin directory structure:
   ```
   plugins/
   ├── slash-commands/
   │   └── discover-api/
   ├── skills/
   ├── subagents/
   └── mcp-servers/
   ```

3. Create category system for data journalism:
   - API Discovery & Web Scraping
   - Data Analysis & Statistics
   - Data Visualization
   - Document Processing (PDFs, spreadsheets)
   - OSINT (Open Source Intelligence)
   - Team Collaboration & Workflows

**Tests**:
- Clone repo and run: `/plugin marketplace add ruibarros/data-journalism-marketplace`
- Verify marketplace appears in `/plugin` list
- Confirm JSON validates against Claude Code schema

**Status**: ✅ Complete

---

## Stage 2: Package First Plugin - discover-api

**Goal**: Package the `/discover-api` slash command as a proper plugin with documentation and dependencies clearly specified

**Success Criteria**:
- ✓ `/discover-api` installable via marketplace
- ✓ Clear documentation on Chrome DevTools MCP requirement
- ✓ Working examples for common data journalism use cases
- ✓ Beginner-friendly setup instructions

**Implementation Tasks**:
1. Create `plugins/slash-commands/discover-api/` with:
   - `README.md` - Full documentation
   - `discover-api.md` - The actual slash command (refined for friendliness)
   - `DEPENDENCIES.md` - Chrome DevTools MCP setup guide
   - `EXAMPLES.md` - Real data journalism scenarios

2. Refine the command for data journalists:
   - Add common scenarios (government portals, court records, etc.)
   - Include tips for authentication/cookies
   - Add error handling guidance
   - Suggest best practices for ethical scraping

3. Document real-world use cases:
   - Reverse engineering government data portals
   - Discovering hidden court record APIs
   - Finding legislative tracking endpoints
   - Accessing public procurement systems

4. Add plugin entry to marketplace.json:
   ```json
   {
     "name": "discover-api",
     "source": "./plugins/slash-commands/discover-api",
     "description": "Reverse engineer hidden APIs in web portals - perfect for finding data in government sites, court records, and public databases",
     "version": "1.0.0",
     "author": {"name": "Rui Barros"},
     "keywords": ["api", "reverse-engineering", "scraping", "investigation"],
     "category": "api-discovery",
     "dependencies": ["chrome-devtools-mcp"]
   }
   ```

**Tests**:
- Install plugin: `/plugin install discover-api@data-journalism-marketplace`
- Run command on a test government portal
- Verify MCP dependency instructions are clear
- Test with R code generation

**Status**: ✅ Complete

---

## Stage 3: Community Contribution Framework

**Goal**: Create clear guidelines and workflows for the data journalism community to submit their own plugins

**Success Criteria**:
- ✓ Contributors understand how to package their plugins
- ✓ Quality standards ensure plugins work reliably
- ✓ Simple PR template for submissions
- ✓ Review process is documented

**Implementation Tasks**:
1. Create `CONTRIBUTING.md` with:
   - Plugin packaging guidelines
   - Directory structure requirements
   - Documentation standards (README, examples, dependencies)
   - Testing requirements
   - Code of conduct for data journalism ethics

2. Set up GitHub templates:
   - Pull request template for new plugins
   - Issue templates for:
     - Bug reports
     - Plugin requests
     - Improvement suggestions

3. Create `PLUGIN_TEMPLATE/` directory with:
   - Template README.md
   - Example slash command structure
   - Example skill structure
   - Metadata requirements

4. Establish quality criteria:
   - Must include working examples
   - Dependencies clearly documented
   - Tested on at least 2 real-world scenarios
   - Follows data journalism ethics (no scraping paywalled content, respects robots.txt)
   - Clear licensing (suggest MIT)

5. Define categories and tags:
   - Categories: API Discovery, Analysis, Visualization, OSINT, Documents, Workflow
   - Required tags: language (R/Python/JavaScript), difficulty (beginner/intermediate/advanced)

**Tests**:
- Walk through contribution guide as if submitting a new plugin
- Verify PR template captures all necessary info
- Test that plugin template is clear and complete

**Status**: ✅ Complete

---

## Stage 4: Comprehensive Documentation & README

**Goal**: Create welcoming, comprehensive documentation that makes the marketplace accessible to data journalists of all skill levels

**Success Criteria**:
- ✓ Clear installation instructions
- ✓ Plugin browser/discovery experience
- ✓ Beginner-friendly language
- ✓ Real examples from journalism

**Implementation Tasks**:
1. Create main `README.md` with:
   - Project vision and mission
   - Quick start (3 steps to get first plugin)
   - Installation instructions
   - Featured plugins showcase
   - How to contribute
   - Community links (Slack/Discord?)

2. Add `GETTING_STARTED.md` for beginners:
   - What is Claude Code?
   - What are plugins/slash commands/skills?
   - Setting up Claude Code
   - Installing the marketplace
   - Using your first plugin
   - Troubleshooting common issues

3. Create `USE_CASES.md` with journalism scenarios:
   - Investigating government spending (API discovery)
   - Analyzing election results (data analysis)
   - Mapping crime data (visualization)
   - Tracking legislation (monitoring)
   - FOIA request automation (document processing)

4. Add `FAQ.md`:
   - Technical questions
   - Ethical guidelines
   - Legal considerations (fair use, copyright)
   - Best practices for different scenarios

5. Create visual assets:
   - Banner/logo for the marketplace
   - Screenshots of plugins in action
   - Diagram of plugin types

**Tests**:
- Have a non-technical journalist follow README to install
- Verify all links work
- Check that examples are reproducible

**Status**: ✅ Complete

---

## Stage 5: Community Launch & Growth

**Goal**: Publicly launch the marketplace and attract initial contributors from the data journalism community

**Success Criteria**:
- ✓ Announced in data journalism communities
- ✓ At least 3-5 initial plugins available
- ✓ First external contributor submits a plugin
- ✓ Documentation translated to other languages (optional)

**Implementation Tasks**:
1. Pre-launch preparation:
   - Test all documentation with fresh users
   - Ensure at least 3-5 diverse plugins are available
   - Set up issue tracking and response workflow
   - Prepare social media posts

2. Launch announcement targets:
   - NICAR-L mailing list (investigative reporters)
   - News Nerdery Slack
   - Data Journalism Slack communities
   - r/dataisbeautiful, r/datajournalism
   - Twitter/X data journalism community
   - LinkedIn journalism groups

3. Content creation:
   - Blog post: "Introducing the Data Journalism Claude Code Marketplace"
   - Tutorial video: Installing and using your first plugin
   - Case study: Real investigation using marketplace plugins

4. Partnerships:
   - Reach out to NICAR, IRE, GIJN
   - Contact data journalism schools/programs
   - Connect with newsroom data teams

5. Growth tracking:
   - Monitor installations (GitHub stars, clones)
   - Track plugin submissions
   - Gather user feedback
   - Iterate based on community needs

**Tests**:
- Soft launch with 5-10 trusted journalists
- Gather feedback before public announcement
- Verify support workflow handles inquiries

**Status**: ✅ Complete

---

## Success Metrics

### Technical Metrics
- Marketplace successfully added by 100+ users in first month
- Zero critical bugs in installation process
- Average plugin installation time < 2 minutes

### Community Metrics
- At least 10 plugins available within 3 months
- Contributions from 5+ different journalists/organizations
- Active usage in at least 3 newsrooms

### Impact Metrics
- Plugins used in at least 1 published investigation
- Positive feedback from data journalism community
- Reduced time for common data journalism tasks

---

## Risk Management

### Technical Risks
- **Risk**: Claude Code plugin system changes
  - **Mitigation**: Monitor Claude Code updates, maintain backward compatibility

- **Risk**: Dependencies (MCP servers) break
  - **Mitigation**: Document versions, provide fallback options

### Community Risks
- **Risk**: Low adoption
  - **Mitigation**: Focus on solving real pain points, showcase actual journalism work

- **Risk**: Low-quality submissions
  - **Mitigation**: Clear quality guidelines, review process, maintainer curation

### Ethical Risks
- **Risk**: Plugins used for unethical scraping
  - **Mitigation**: Clear ethical guidelines, respect robots.txt, no paywall circumvention

- **Risk**: Legal issues (copyright, terms of service)
  - **Mitigation**: Legal disclaimer, focus on public data, ethical guidelines

---

## Timeline (Estimated)

- **Stage 1**: 1-2 hours (infrastructure setup)
- **Stage 2**: 2-3 hours (first plugin packaging)
- **Stage 3**: 2-3 hours (contribution framework)
- **Stage 4**: 3-4 hours (comprehensive docs)
- **Stage 5**: Ongoing (community growth)

**Total initial setup**: ~10-12 hours
**Maintenance**: 2-4 hours/week initially

---

## Next Steps

1. Get approval on this plan
2. Begin Stage 1: Set up core marketplace infrastructure
3. Iterate based on feedback from initial users
4. Build the data journalism plugin ecosystem together!

---

_This plan follows the planning-first workflow with incremental progress in clear stages._
