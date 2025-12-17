# Module 4.1: Introduction to MCPs

**Teaching Script for GitHub Copilot**  
**Duration:** ~20 minutes

---

## Teaching Flow

Welcome to Module 4: MCP Integration for Product Managers!

This is where you unlock **supercharged PM workflows** by connecting Copilot to your actual tools

**What are MCPs?** Model Context Protocol servers - they let Copilot directly interact with tools like Confluence, Azure DevOps, Figma, and Miro

Instead of copying/pasting between tools, Copilot can read from and write to them directly

STOP: Have you used any integrations with AI tools before? Or is this concept new?

USER: Responds

---

## Why MCPs Matter for PMs

Let me show you the difference:

**Without MCPs:**
- You: Copy issue from Azure DevOps → Paste into Copilot → Get analysis → Copy back
- Time: 5-10 minutes per task
- Context: Lost in translation

**With MCPs:**
- You: "Analyse sprint burndown from Azure DevOps project"
- Copilot: Fetches data, analyses, suggests actions
- Time: 30 seconds
- Context: Perfect accuracy

MCPs eliminate the "swivel chair" problem - switching between tools constantly

STOP: What tool do you spend the most time switching to and from?

USER: Responds

---

## What You'll Learn in Module 4

Over the next 5 lessons, you'll master MCP integration with:

**4.2 Confluence** - Read/write docs, search knowledge base, sync PRDs  
**4.3 Azure DevOps** - Create work items, query sprints, update boards  
**4.4 Figma** - Reference designs, extract specs, sync with docs  
**4.5 Miro** - Create boards, extract insights, collaborate visually

Each lesson follows the same pattern:
1. **Connect** - Set up the MCP
2. **Explore** - See what it can do
3. **Practice** - Real PM workflows
4. **Integrate** - Combine with existing work

STOP: Which tool are you most excited to connect?

USER: Responds

---

## How MCPs Work (Simple Version)

You don't need to understand the technical details, but here's the concept:

```
┌─────────────┐
│   VSCode    │
│  + Copilot  │
└──────┬──────┘
       │
       │ MCP Protocol
       │
┌──────┴─────────────────────────────┐
│                                    │
│  ┌──────────┐  ┌──────────┐      │
│  │Confluence│  │Azure DevOps│     │
│  │   MCP    │  │    MCP    │      │
│  └────┬─────┘  └─────┬─────┘      │
│       │              │             │
│       │              │             │
│  ┌────▼─────┐  ┌─────▼──────┐    │
│  │Confluence│  │Azure DevOps│    │
│  │   API    │  │    API     │    │
│  └──────────┘  └────────────┘    │
└────────────────────────────────────┘
```

MCPs are like translators - they speak "Copilot language" and "Tool API language"

You just talk to Copilot naturally. The MCP handles the rest.

STOP: Ready to see this in action?

USER: Confirms

---

## Setting Up Your First MCP

**Prerequisites** (check with your IT team):
- VSCode with Copilot installed ✓ (you have this)
- MCP extension installed (we'll do this)
- Access credentials for each tool (Confluence, Azure DevOps, etc.)

**The Setup Process** (3 steps):
1. Install MCP extension in VSCode
2. Configure connection to each tool
3. Authenticate with your credentials

Don't worry - each lesson in Module 4 will walk you through setup for that specific tool

STOP: Do you have admin access to Confluence and Azure DevOps at ASOS?

USER: Responds

---

## MCP Commands You'll Use

Once connected, you'll use Copilot naturally:

**Confluence Examples:**
- "Search Confluence for PRDs about checkout"
- "Create a new page in the PM space with my PRD"
- "Get comments from the returns strategy doc"

**Azure DevOps Examples:**
- "Show me all bugs assigned to me"
- "Create a user story for the size recommendation feature"
- "What's our sprint velocity over the last 3 sprints?"

**Figma Examples:**
- "Show me the latest designs for the PDP redesign"
- "Extract colour tokens from the design system"
- "What components are in the header mockup?"

**Miro Examples:**
- "Create a new board for the Q1 roadmap"
- "Get all sticky notes from the customer journey board"
- "Add a card for the new feature idea"

See the pattern? **Natural language, tool-specific actions**

STOP: Try drafting a command you'd like to use. Format: "[Tool]: [Action]"

USER: Writes example command

---

ACTION: Review their command and give feedback:
- Is it specific enough?
- Is the tool correct for that action?
- How could it be more effective?

---

## MCP Benefits for PMs

Let me be specific about time savings:

| Task | Without MCP | With MCP | Savings |
|------|-------------|----------|---------|
| Find related Confluence docs | 10 min | 30 sec | 95% |
| Create Azure DevOps story | 5 min | 1 min | 80% |
| Reference Figma design specs | 8 min | 45 sec | 91% |
| Export Miro board insights | 15 min | 2 min | 87% |
| Build stakeholder presentation | 60 min | 15 min | 75% |

**Total weekly time saved:** 10-15 hours (assuming these tasks happen daily)

That's 2 full workdays per week back in your calendar

STOP: Which task would save you the most time?

USER: Responds

---

## Real PM Workflow with MCPs

Here's what a typical day looks like with MCP integration:

**9:00 AM - Daily Standup Prep**
- "Get all work items updated yesterday in Azure DevOps"
- Review blockers, prepare update

**10:00 AM - Refine User Story**
- "Search Confluence for user research on checkout flow"
- Add insights to Azure DevOps story
- "Get latest Figma designs for checkout"
- Reference in acceptance criteria

**2:00 PM - Sprint Planning Prep**
- "Analyse last 3 sprints velocity in Azure DevOps"
- "Get roadmap from Miro board"
- Create sprint plan doc in Confluence

**4:00 PM - Stakeholder Update**
- Pull data from all tools
- Build HTML presentation
- Share with leadership

**Total tool switches:** 0 (everything in VSCode/Copilot)

STOP: How does your current workflow compare?

USER: Responds

---

## Important: MCP Limitations

MCPs are powerful, but they have boundaries:

**What MCPs CAN do:**
✓ Read data from tools
✓ Create/update items
✓ Search and filter
✓ Extract information
✓ Automate repetitive tasks

**What MCPs CANNOT do:**
✗ Make strategic decisions for you
✗ Replace human judgment
✗ Fix broken processes
✗ Work without proper permissions
✗ Guarantee 100% accuracy (always verify)

**Best Practice:** Use MCPs for **speed and efficiency**, not as a replacement for PM thinking

STOP: Does this make sense? Any concerns about relying on MCPs?

USER: Responds

---

## Security & Permissions

Important security notes:

**Your data stays secure:**
- MCPs use your existing credentials
- Same permissions as when you use tools directly
- No data stored by Copilot/MCPs
- All connections encrypted

**Best practices:**
1. Only connect to official MCPs
2. Review permissions when authenticating
3. Don't share credentials in prompts
4. Disconnect MCPs you're not using
5. Follow ASOS security policies

**Check with your IT team** before connecting to production systems

STOP: Any security questions before we proceed?

USER: Asks questions or confirms ready

---

## Module 4 Roadmap

Here's what's coming:

**Lesson 4.2: Confluence** (~30 min)
- Search across spaces
- Create/update pages
- Sync PRDs
- Comment workflows

**Lesson 4.3: Azure DevOps** (~30 min)
- Query work items
- Create stories/bugs
- Sprint analytics
- Board automation

**Lesson 4.4: Figma** (~25 min)
- Design exploration
- Component extraction
- Design system sync
- Handoff automation

**Lesson 4.5: Miro** (~25 min)
- Board creation
- Sticky note extraction
- Workshop synthesis
- Roadmap visualization

**Lesson 4.6: HTML Presentations** (~35 min)
- Pull data from all tools
- Build reveal.js slides
- Interactive dashboards
- Stakeholder-ready outputs

**Total time investment:** ~2.5 hours  
**Time saved weekly:** 10-15 hours

That's a **500-600% ROI** in your first week

STOP: Ready to start connecting tools?

USER: Confirms

---

## Next Steps

To prepare for the next lessons, do this:

**Before Lesson 4.2 (Confluence):**
1. Confirm you have Confluence access
2. Note which spaces you use most
3. Think of a doc you want to create

**Before Lesson 4.3 (Azure DevOps):**
1. Confirm you have Azure DevOps access
2. Know your project name
3. Identify a repetitive task to automate

**Before Lesson 4.4 (Figma):**
1. Confirm you have Figma access (view/edit)
2. Find a design file you reference often

**Before Lesson 4.5 (Miro):**
1. Confirm you have Miro access
2. Find a board you collaborate on

**All set?** Let's move to Lesson 4.2 and connect Confluence!

STOP: Any final questions about MCPs?

USER: Asks questions or confirms ready

---

## Reflection

You now understand:
✓ What MCPs are and why they matter
✓ How they save PMs 10-15 hours per week
✓ Which tools you'll connect
✓ Security and permission considerations
✓ Real workflow examples

Next up: **Hands-on Confluence integration**

See you in Module 4.2! 🚀
