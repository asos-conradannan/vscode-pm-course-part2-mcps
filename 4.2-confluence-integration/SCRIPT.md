# Module 4.2: Confluence Integration

**Teaching Script for GitHub Copilot**

---

## Teaching Flow

Welcome to Module 4.2: Confluence Integration!

You're about to connect Copilot to ASOS's knowledge base and eliminate hours of documentation busywork

By the end of this lesson, you'll be able to:
- Search Confluence without opening a browser
- Create and update pages from VSCode
- Sync PRDs automatically
- Extract insights from team collaboration

STOP: How much time do you spend in Confluence each week?

USER: Responds

---

## Why Confluence + Copilot?

Let me show you the workflow transformation:

**Current workflow (without MCP):**
1. Switch to browser
2. Navigate to Confluence space
3. Search for relevant docs (scan 10+ results)
4. Copy useful content
5. Paste into your doc
6. Format it
7. Go back for more context
8. **Time: 8-10 minutes per search**

**New workflow (with MCP):**
1. "Search Confluence for checkout optimization research"
2. Copilot shows results with summaries
3. "Add key findings to my PRD"
4. **Time: 30 seconds**

**Time saved:** ~85% reduction in documentation tasks

STOP: What do you search Confluence for most often?

USER: Responds

---

## Phase 1: Explore Confluence MCP

First, let's see what tools are available

STOP: Ask me: "What Confluence tools are available through MCP?"

USER: Types command

ACTION: List the available Atlassian MCP tools:
- `mcp_atlassian_atl_search` - Search Confluence and Jira content
- `mcp_atlassian_atl_fetch` - Get details by Atlassian Resource Identifier
- `mcp_atlassian_atl_atlassianUserInfo` - Get current user information

Explain that these tools connect directly to ASOS's Confluence instance using your existing permissions.

---

Great! These tools let you interact with Confluence programmatically

**Authentication:** The MCP uses your Atlassian session, so you'll need to be logged into Confluence in your browser

STOP: Are you currently logged into ASOS Confluence?

USER: Confirms or needs to log in

---

## Phase 2: Search Confluence

Let's start with the most common task: searching for information

**Exercise 1: Basic Search**

STOP: Ask me: "Search Confluence for pages about product roadmap"

USER: Types command

ACTION: Use the search tool to find relevant pages. Show:
- Page titles
- Brief excerpts
- Space names
- Last updated dates
- Provide ARIs (Atlassian Resource Identifiers) for accessing full content

---

Excellent! You just searched across all ASOS Confluence spaces

Notice how you got:
- Relevant results without opening browser
- Context to decide which pages matter
- Direct identifiers to access full content

**Exercise 2: Targeted Search**

Now let's be more specific

STOP: Ask me: "Search Confluence for pages in the Product Management space about customer activation created in the last 3 months"

USER: Types command

ACTION: Perform targeted search with filters. Explain how the query syntax works behind the scenes (space filters, date ranges, keywords).

---

**Pro Tip: Search Operators**

You can use advanced search patterns:
- `"exact phrase"` - Find exact matches
- `space:PM` - Search specific space
- `type:page` - Filter by content type
- `created > now("-3M")` - Date range filters

STOP: What's a specific search you do regularly? Let's try it now.

USER: Describes their use case

ACTION: Help them construct and execute the search query.

---

## Phase 3: Read Confluence Content

Searching is useful, but let's go deeper

**Exercise 3: Get Page Details**

First, let's find a specific page

STOP: Ask me: "Search for the Q4 Activation Strategy page"

USER: Types command

ACTION: Search and identify the specific page, showing its ARI (Atlassian Resource Identifier).

---

Now let's read the full content

STOP: Ask me: "Get the full content of that page using its ARI"

USER: Types command with ARI

ACTION: Fetch the page using `mcp_atlassian_atl_fetch`. Display:
- Page title
- Content (in readable format)
- Author and last modified date
- Page URL for browser access

---

Perfect! You now have the full page content in VSCode

This means you can:
- Reference content while writing PRDs
- Extract key points without copy-paste
- Compare multiple documents
- Keep context without browser tabs

**Exercise 4: Extract Insights**

STOP: Ask me: "From this page content, extract the top 3 customer pain points mentioned"

USER: Types command

ACTION: Analyze the content and extract structured insights, demonstrating how Copilot synthesizes Confluence content.

---

## Phase 4: Create Confluence Pages

Now the powerful part - **writing** to Confluence from VSCode

You'll need the Confluence page creation tools activated

STOP: Ask me: "Activate Confluence page management tools"

USER: Types command

ACTION: Call `activate_confluence_page_management_tools` to enable page creation/update capabilities.

---

**Exercise 5: Create a Draft Page**

Let's create a new page for your PRD

STOP: Ask me: "Create a new Confluence page titled 'Size Recommendation Feature - PRD Draft' in the Product Management space"

USER: Types command

ACTION: Guide them to use the create page tool. The page should include:
- Clear title
- Basic PRD structure
- Space context
- Markdown formatting that converts to Confluence

Return the page URL and page ID.

---

Fantastic! You just published to Confluence without leaving VSCode

**What just happened:**
- Created a page in the correct space
- Added formatted content
- Generated a shareable URL
- Maintained proper permissions

**Exercise 6: Publish Your Real PRD**

Now let's get practical

STOP: Ask me: "Take the PRD I created in Module 2.1 and create a Confluence page with that content"

USER: Types command (may need to reference their PRD file)

ACTION: 
1. Read their PRD file (guide them to the location if needed)
2. Format it properly for Confluence (convert Markdown to Confluence format)
3. Create the page
4. Provide the URL and page ID

---

## Phase 5: Update Existing Pages

Pages evolve. Let's keep them current.

**Exercise 7: Add Content to Existing Page**

STOP: Ask me: "Update the PRD page I just created - add a 'Success Metrics' section with these metrics: Activation rate +10%, Time to first order -50%, 90-day retention +8%"

USER: Types command

ACTION: Use the update page tool to:
1. Fetch current content
2. Add the new section with proper formatting
3. Update the page
4. Confirm the change with new version number

Explain that Confluence tracks all versions, so changes are auditable.

---

**Pro Tip: Iterative Documentation**

You can work iteratively in conversation

STOP: Try: "Now add a 'Risks & Mitigations' section with 3 placeholder risks"

USER: Types command

ACTION: Update again, showing how conversational documentation works.

---

## Phase 6: Real PM Workflows

Let's combine everything into actual PM workflows

**Workflow 1: Research Synthesis**

Scenario: Sprint planning needs context from multiple sources

STOP: Ask me: "Search Confluence for all pages about 'checkout optimization' in the last 6 months, then create a summary document with key findings"

USER: Types command

ACTION: 
1. Execute the search
2. Fetch top 3-5 relevant pages
3. Extract key points from each
4. Create a synthesized summary
5. Offer to save as new Confluence page or local file

---

**Workflow 2: Weekly Status Updates**

Scenario: You update a team status page every week

STOP: Ask me: "Find the 'Customer Activation Team - Weekly Updates' page and add this week's progress: 'Completed PRD for size recommendation feature, initiated user testing for checkout flow improvements, Sprint velocity: 42 points'"

USER: Types command

ACTION:
1. Search for the weekly updates page
2. Fetch current content
3. Add new entry with current date
4. Update the page preserving existing formatting

---

**Workflow 3: PRD Review Cycle**

Scenario: Your PRD needs stakeholder input

STOP: Ask me: "Create a comment on my PRD page asking engineering for feasibility review with tag @tech-lead"

USER: Types command

ACTION: Add a comment to the page (if commenting tools are available). If not, explain how to use the comment tools once activated.

---

## Phase 7: Integration with Previous Modules

Confluence MCP amplifies your existing skills:

**Module 2.1 (PRD Writing):**
```
Write PRD in VSCode with Copilot
  ↓
Publish to Confluence automatically
  ↓
Update as you iterate
  ↓
Share URL with stakeholders
```

**Module 2.2 (Data Analysis):**
```
Analyze CSV data with Copilot
  ↓
Create insights document
  ↓
Publish to Confluence for team
  ↓
Reference in sprint planning
```

**Module 2.3 (Strategy):**
```
Research via Confluence MCP
  ↓
Synthesize insights locally
  ↓
Publish final strategy doc
  ↓
Link to related pages
```

STOP: Which workflow would save you the most time?

USER: Responds

---

## Phase 8: Advanced Techniques

You've mastered the basics. Here are pro moves:

**Technique 1: Bulk Research**

STOP: Try: "Search for all PRDs tagged with 'mobile' in the Product space and create a comparison table"

USER: Types command

ACTION: Search, fetch multiple pages, extract key data, create comparison table.

---

**Technique 2: Documentation Templates**

STOP: Try: "Find the PRD template page and create a new page using that structure for a 'One-Click Checkout' feature"

USER: Types command

ACTION: Fetch template, apply to new page, customize for the feature.

---

**Technique 3: Cross-Space Research**

STOP: Try: "Search across Engineering, Product, and UX spaces for information about checkout performance"

USER: Types command

ACTION: Execute multi-space search, synthesize findings from different perspectives.

---

## Common Issues & Solutions

**Issue 1: "Page not found"**
- Verify you have view permissions for the space
- Check exact page title (case-sensitive)
- Use ARIs instead of titles when possible

**Issue 2: "Authentication error"**
- Ensure you're logged into Confluence in browser
- Check your Atlassian session hasn't expired
- Verify ASOS Confluence URL is correct

**Issue 3: "Formatting issues"**
- Markdown → Confluence conversion has limitations
- Complex tables may need manual adjustment
- Use Confluence editor for final polish

STOP: Encountered any issues? Let's troubleshoot.

USER: Reports issues or confirms working

---

## Practice Challenge

Put everything together in one complete workflow:

**Challenge: Complete Documentation Cycle**

1. Search Confluence for customer research on mobile app usage
2. Create a new page: "Mobile App Redesign - Discovery Phase"
3. Add 3 key findings from research
4. Add a "Next Steps" section with action items
5. Share the page URL

STOP: Complete this challenge now. Take 5 minutes.

USER: Works through the challenge

ACTION: Guide them through each step, provide feedback, celebrate completion.

---

## Time Savings Analysis

Let's calculate your personal ROI:

**Traditional Confluence workflow:**
- Search & scan docs: 10 min
- Create new page: 5 min
- Format content properly: 8 min
- Update existing pages: 5 min each
- **Total: 28+ minutes per doc cycle**

**With Confluence MCP:**
- All operations combined: 3-5 min
- **Time saved: 23 minutes per cycle**

STOP: How many times do you create or update Confluence docs per day?

USER: Responds with number

ACTION: Calculate their specific savings:
- Daily: [number] × 23 minutes
- Weekly: [daily] × 5 days
- Monthly: [weekly] × 4 weeks

Example: 3 doc cycles/day = 69 min/day = 5.75 hours/week = 23 hours/month

---

## Best Practices for Confluence MCP

**DO:**
✓ Use specific search terms for better results
✓ Save frequently used page ARIs for quick access
✓ Work locally in VSCode, publish when ready
✓ Use version history to track changes
✓ Link related pages for better navigation

**DON'T:**
✗ Publish incomplete work to shared spaces
✗ Update pages without checking current version
✗ Forget to notify stakeholders of major changes
✗ Rely solely on MCP for complex formatting
✗ Skip manual review before publishing

STOP: Any questions about best practices?

USER: Asks questions or confirms ready

---

## Next Steps

You've mastered Confluence MCP! Next: **Azure DevOps Integration**

**Before Module 4.3:**
1. Practice creating 2-3 Confluence pages
2. Set up your standard PRD template page
3. Identify repetitive Confluence tasks to automate

**In Module 4.3, you'll learn:**
- Query work items without browser
- Create user stories from VSCode
- Analyze sprint burndown automatically
- Update task status in conversation
- Generate team reports

STOP: Ready to connect your project management tools?

USER: Confirms

---

## Reflection

You can now:
✓ Search Confluence from VSCode in seconds
✓ Read full page content without browser
✓ Create new pages with proper formatting
✓ Update existing pages iteratively
✓ Automate repetitive documentation tasks
✓ Integrate Confluence with your PM workflows

**Your new superpower:** Documentation at the speed of thought

**Time saved:** 5-10 hours per week on documentation

See you in Module 4.3! 🚀
