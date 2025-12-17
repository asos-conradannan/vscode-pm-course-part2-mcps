# Module 4.3: Azure DevOps Integration

**Teaching Script for GitHub Copilot**

---

## Teaching Flow

Welcome to Module 4.3: Azure DevOps Integration!

Time to connect Copilot to your project management system and automate the busywork

By the end of this lesson, you'll be able to:
- Query work items without opening browser
- Create user stories and bugs from VSCode
- Analyze sprint metrics automatically
- Update task status conversationally
- Generate team reports instantly

STOP: How much time do you spend in Azure DevOps each day?

USER: Responds

---

## Why Azure DevOps + Copilot?

Let me show you the transformation:

**Current workflow (without MCP):**
1. Open browser → Navigate to Azure DevOps
2. Navigate to correct project/board
3. Search for work items (filter, sort, scroll)
4. Open each item to read details
5. Create new items (fill in all fields manually)
6. Update status (click, select, save)
7. Generate reports (export, analyze, format)
8. **Time: 30-60 minutes per day**

**New workflow (with MCP):**
1. "Show me all my active work items"
2. "Create a user story for size recommendation"
3. "Update task 1234 to 'In Progress'"
4. "Analyze last 3 sprints velocity"
5. **Time: 3-5 minutes total**

**Time saved:** 25-55 minutes daily = **2-4.5 hours per week**

STOP: What Azure DevOps task do you find most repetitive?

USER: Responds

---

## Phase 1: Explore Azure DevOps MCP

Let's see what tools are available

STOP: Ask me: "What Azure DevOps tools are available through MCP?"

USER: Types command

ACTION: List the available Azure DevOps MCP tools:

**Work Item Management:**
- Create, update, get work items
- Query work items by various filters
- Add comments, link work items
- Manage attachments

**Repository Operations:**
- Get repositories, branches, commits
- Create pull requests
- Reply to PR comments

**Build & Pipeline:**
- Get builds, pipelines
- Run pipelines
- Update build stages

**Project Management:**
- List projects, teams
- Get team iterations, capacity
- Query backlogs

Explain these connect to ASOS's Azure DevOps using your authenticated session.

---

Powerful! These tools give you programmatic access to your entire project

**Authentication:** The MCP uses your Azure DevOps session and permissions

STOP: Do you know which Azure DevOps project you work in?

USER: Responds with project name

ACTION: Note the project name for use in examples. If they don't know, guide them to find it.

---

## Phase 2: Query Work Items

Let's start with finding information

**Exercise 1: Get Your Work Items**

STOP: Ask me: "Show me all work items assigned to me in the [ProjectName] project"

USER: Types command with their project name

ACTION: Use the work item query tool to fetch their assigned items. Display:
- Work item ID
- Title
- Type (User Story, Task, Bug)
- State (Active, Resolved, Closed)
- Priority

---

Excellent! You just queried your backlog without opening Azure DevOps

Notice you got:
- Clean, organized list
- Key information at a glance
- Work item IDs for deeper access

**Exercise 2: Filter by Sprint**

STOP: Ask me: "Show me all work items in the current sprint for [ProjectName]"

USER: Types command

ACTION: Query work items filtered by current iteration. Group by state and show sprint progress.

---

**Exercise 3: Search by Keywords**

STOP: Ask me: "Find all user stories related to 'checkout' in [ProjectName]"

USER: Types command

ACTION: Search work items by title/description keywords. Show relevant results with context.

---

## Phase 3: Get Work Item Details

Searching is useful, but let's go deeper

**Exercise 4: Get Full Work Item**

First, note a work item ID from your previous results

STOP: Ask me: "Get all details for work item [ID]"

USER: Types command with specific ID

ACTION: Fetch complete work item using `mcp_azure-devops_wit_get_work_item`. Display:
- Full description
- Acceptance criteria
- Comments/discussions
- Links to related items
- History of changes
- Current assignee and state

---

Perfect! Now you have full context without browser tab switching

**Exercise 5: Analyze Work Item**

STOP: Ask me: "Based on this work item, what are the key risks and what's missing from acceptance criteria?"

USER: Types command

ACTION: Analyze the work item content and provide PM insights on completeness, clarity, and risks.

---

## Phase 4: Create Work Items

Now the powerful part - **creating** work items from VSCode

**Exercise 6: Create a User Story**

STOP: Ask me: "Create a new user story in [ProjectName] with title 'Implement size recommendation feature' and add a basic description"

USER: Types command

ACTION: Use the create work item tool to:
1. Create User Story type
2. Set title
3. Add description field
4. Assign to appropriate area path
5. Return the new work item ID and URL

---

Fantastic! You just created a work item without filling out forms

**What happened:**
- Created proper work item type
- Added core fields
- Generated tracking ID
- Created shareable URL

**Exercise 7: Create with Full Details**

Let's get sophisticated

STOP: Ask me: "Create a user story for one-click checkout with acceptance criteria, tags, and priority High"

USER: Types command

ACTION: Create a more complete work item with:
- Title
- Description (As a user... format)
- Acceptance Criteria (list format)
- Tags: ["checkout", "conversion"]
- Priority: 2 (High)
- Area Path and Iteration

---

## Phase 5: Update Work Items

Work items evolve. Let's keep them current.

**Exercise 8: Update Status**

STOP: Ask me: "Update work item [ID] status to 'In Progress'"

USER: Types command with specific ID

ACTION: Update the work item state field. Confirm the change and show new state.

---

**Exercise 9: Add Comments**

STOP: Ask me: "Add a comment to work item [ID]: 'Completed initial design review, moving to implementation phase'"

USER: Types command

ACTION: Add comment to the work item. Show comment ID and timestamp.

---

**Exercise 10: Link Work Items**

STOP: Ask me: "Link work item [ID1] as a dependency of work item [ID2]"

USER: Types command

ACTION: Create a work item link. Explain the relationship type and show both items are now connected.

---

## Phase 6: Sprint Analytics

Let's unlock insights from your project data

**Exercise 11: Sprint Velocity**

STOP: Ask me: "Calculate the velocity for the last 3 sprints in [ProjectName]"

USER: Types command

ACTION: 
1. Get last 3 completed iterations
2. Query work items completed in each
3. Sum story points
4. Calculate average velocity
5. Show trend (increasing/decreasing/stable)

---

**Exercise 12: Burndown Analysis**

STOP: Ask me: "Show the current sprint burndown status"

USER: Types command

ACTION:
1. Get current iteration dates
2. Query remaining work
3. Calculate ideal burndown vs actual
4. Identify if sprint is on track

---

**Exercise 13: Team Capacity**

STOP: Ask me: "Get the team capacity for current sprint"

USER: Types command

ACTION: Use the team capacity tool to show:
- Team members
- Available days
- Total capacity
- Current allocation

---

## Phase 7: Pull Request Workflows

Integrate with code review processes

**Exercise 14: List Active PRs**

STOP: Ask me: "Show all active pull requests in the [RepositoryName] repository"

USER: Types command

ACTION: List pull requests with:
- PR ID
- Title
- Author
- Status (Active, Completed, Abandoned)
- Created date

---

**Exercise 15: Comment on PR**

STOP: Ask me: "Add a comment to PR [ID]: 'Looks good from PM perspective, confirms requirements in story [StoryID]'"

USER: Types command

ACTION: Add comment to pull request thread. Link back to work item for traceability.

---

## Phase 8: Real PM Workflows

Combine everything into daily workflows

**Workflow 1: Daily Standup Prep**

STOP: Ask me: "Prepare my standup update: Show my work items updated yesterday and any blockers"

USER: Types command

ACTION:
1. Query work items assigned to user
2. Filter by last modified date (yesterday)
3. Check for blocked status
4. Generate standup summary:
   - What I completed
   - What I'm working on
   - Any blockers

---

**Workflow 2: Sprint Planning**

STOP: Ask me: "Prepare sprint planning: Show team velocity, backlog priority items, and capacity for next sprint"

USER: Types command

ACTION:
1. Calculate recent velocity
2. Query top priority backlog items
3. Get next iteration capacity
4. Generate planning summary with recommendations

---

**Workflow 3: Weekly Status Report**

STOP: Ask me: "Generate a weekly status report: completed work items, sprint progress, and upcoming deliverables"

USER: Types command

ACTION:
1. Query completed items this week
2. Calculate sprint progress percentage
3. Query items planned for next week
4. Format as executive summary

---

## Phase 9: Advanced Automation

Pro-level techniques

**Technique 1: Bulk Create from PRD**

STOP: Ask me: "Read my PRD and create user stories for each requirement section"

USER: Types command

ACTION:
1. Read PRD file
2. Extract requirements
3. Create work item for each
4. Link them to parent epic
5. Return list of created IDs

---

**Technique 2: Automated Triage**

STOP: Ask me: "Find all unassigned bugs and prioritize them based on customer impact keywords"

USER: Types command

ACTION:
1. Query unassigned bugs
2. Analyze descriptions for impact keywords
3. Suggest priority levels
4. Offer to update in bulk

---

**Technique 3: Dependency Mapping**

STOP: Ask me: "Show all work items linked to [EpicID] and create a dependency graph"

USER: Types command

ACTION:
1. Query work items by parent link
2. Get all related links
3. Build dependency tree
4. Identify critical path

---

## Phase 10: Integration with Previous Modules

Azure DevOps MCP amplifies your existing workflows:

**Module 2.1 (PRD Writing):**
```
Write PRD in VSCode
  ↓
"Create user stories from PRD sections"
  ↓
Stories created in Azure DevOps
  ↓
Link back to Confluence PRD
```

**Module 2.2 (Data Analysis):**
```
Analyze sprint metrics
  ↓
Identify bottlenecks
  ↓
Create improvement tasks
  ↓
Track in Azure DevOps
```

**Module 4.2 (Confluence):**
```
Research in Confluence
  ↓
Create PRD
  ↓
Generate work items in Azure DevOps
  ↓
Link Confluence page to Epic
```

STOP: Which integration would streamline your workflow most?

USER: Responds

---

## Common Issues & Solutions

**Issue 1: "Project not found"**
- Verify exact project name (case-sensitive)
- Check you have project access
- Try listing all projects first

**Issue 2: "Permission denied"**
- Confirm your Azure DevOps role
- Check area path permissions
- Verify you can perform action in browser

**Issue 3: "Work item type not available"**
- Check project process template (Agile/Scrum/CMMI)
- Use correct type names for your process
- List available types first

STOP: Hit any issues? Let's troubleshoot.

USER: Reports issues or confirms working

---

## Practice Challenge

Complete workflow challenge:

**Challenge: Full Feature Lifecycle**

1. Query backlog for "size recommendation" items
2. Create a new user story if none exists
3. Add acceptance criteria
4. Add a task: "Design review"
5. Link to related Confluence PRD (from Module 4.2)
6. Add yourself as assignee
7. Move to current sprint
8. Update status to "In Progress"

STOP: Complete this 8-step workflow now. Time yourself!

USER: Works through challenge

ACTION: Guide through each step, celebrate completion, note their time.

---

## Time Savings Calculation

Let's measure your specific ROI:

**Traditional Azure DevOps workflow:**
- Query/search: 5 min
- Create work item: 4 min
- Update statuses: 3 min × [X items]
- Sprint analytics: 15 min
- Status report: 20 min
- **Total: 40-60 min daily**

**With Azure DevOps MCP:**
- All operations: 5-8 min total
- **Time saved: 32-52 min daily**

STOP: How many times per day do you create or update work items?

USER: Responds with number

ACTION: Calculate specific savings:
- Daily: [number] × 3 min saved
- Weekly: [daily] × 5 days
- Monthly: [weekly] × 4 weeks

---

## Best Practices

**DO:**
✓ Use specific work item IDs when possible
✓ Keep work item titles descriptive
✓ Link related items (PRD → Epic → Stories)
✓ Add meaningful comments for audit trail
✓ Query before creating duplicates

**DON'T:**
✗ Create work items without checking existing
✗ Update items without reading current state
✗ Change states without team notification
✗ Bulk update without verification
✗ Forget to link to documentation

STOP: Any questions about best practices?

USER: Asks questions or confirms

---

## Next Steps

You've mastered Azure DevOps MCP! Next: **Figma Collaboration**

**Before Module 4.4:**
1. Practice creating 5 work items
2. Query different sprint metrics
3. Automate one repetitive task

**In Module 4.4, you'll learn:**
- Browse Figma files from VSCode
- Extract design specifications
- Sync design tokens with code
- Automate design handoff
- Document components

STOP: Ready to connect your design tools?

USER: Confirms

---

## Reflection

You can now:
✓ Query work items without browser
✓ Create user stories conversationally
✓ Update task status instantly
✓ Analyze sprint metrics automatically
✓ Generate team reports in seconds
✓ Automate your PM workflow

**Your new superpower:** Project management at machine speed

**Time saved:** 2-4 hours per week on project management tasks

See you in Module 4.4! 🎨
