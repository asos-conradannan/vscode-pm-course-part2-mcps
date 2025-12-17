# Module 4.5: Miro Visual Collaboration

**Teaching Script for GitHub Copilot**

---

## Teaching Flow

Welcome to Module 4.5: Miro Visual Collaboration!

Connect Copilot to your visual thinking workspace and synthesize insights at scale

By the end of this lesson, you'll be able to:
- Access Miro boards from VSCode
- Extract sticky notes and workshop output
- Create boards programmatically
- Synthesize visual brainstorming
- Automate roadmap documentation

STOP: How often do you use Miro for workshops or brainstorming?

USER: Responds

---

## Why Miro + Copilot?

The visual collaboration challenge:

**Current workflow (without MCP):**
1. Run workshop in Miro (2 hours)
2. Screenshot the board
3. Manually type up all sticky notes
4. Group and categorize insights
5. Create summary document
6. Share with stakeholders
7. **Post-workshop synthesis: 60-90 minutes**

**New workflow (with MCP):**
1. Run workshop in Miro (2 hours)
2. "Get all sticky notes from [Board Name]"
3. "Categorize by theme and create summary"
4. "Generate action items"
5. **Post-workshop synthesis: 5-10 minutes**

**Time saved:** 50-80 minutes per workshop = **80-90% reduction**

STOP: How many workshops or brainstorming sessions do you facilitate per month?

USER: Responds

ACTION: Calculate their time savings: [number] × 60 minutes saved = [X] hours per month

---

## Phase 1: Explore Miro MCP

Let's see what's available

STOP: Ask me: "What Miro tools are available through MCP?"

USER: Types command

ACTION: List available Miro MCP tools:

**Board Management:**
- `mcp_my-mcp-server_board_get_items` - Get items from board with pagination
- `mcp_my-mcp-server_board_get_image_data` - Get image data for items
- `mcp_my-mcp-server_board_get_image_download_url` - Get download URLs for images

Explain these give read access to Miro boards, perfect for extracting workshop outputs and documenting visual work.

---

**Authentication:**

The Miro MCP requires authentication

STOP: Are you currently logged into ASOS Miro workspace?

USER: Confirms

ACTION: If they need to authenticate, guide them through the process or note they'll need proper access setup.

---

## Phase 2: Access Miro Boards

**Exercise 1: List Board Items**

First, you need your board ID (from the Miro URL)

Example: `https://miro.com/app/board/uXjVN-abc123=/` → Board ID: `uXjVN-abc123=`

STOP: Ask me: "Get all items from Miro board [BoardID]"

USER: Types command with their board ID

ACTION: Use `mcp_my-mcp-server_board_get_items` to fetch board items. Display:
- Item types (sticky note, card, text, shape, frame, image)
- Item IDs
- Content preview
- Position coordinates
- Total item count

---

Excellent! You just accessed your Miro board without opening browser

Notice you got:
- All board elements
- Item types and content
- Structured data you can analyze

**Exercise 2: Filter by Item Type**

STOP: Ask me: "Get only sticky notes from the board"

USER: Types command

ACTION: Query with `item_type: "sticky_note"` filter. Show just the sticky notes with their text content.

---

## Phase 3: Extract Workshop Insights

**Exercise 3: Get Sticky Note Content**

Scenario: You ran a customer pain points workshop

STOP: Ask me: "Extract all sticky note text from the workshop board and group by similar themes"

USER: Types command

ACTION:
1. Fetch all sticky notes
2. Read text content
3. Analyze and categorize (e.g., "checkout friction", "sizing uncertainty", "delivery concerns")
4. Group similar notes
5. Present categorized summary

Example output:
```
Theme 1: Checkout Friction (8 notes)
- "Too many steps to complete order"
- "Have to create account first"
- "Lost items in basket when session expired"
...

Theme 2: Sizing Uncertainty (12 notes)
- "Never sure what size to order"
- "Size charts are confusing"
...
```

---

Perfect! You just synthesized 2 hours of workshop into organized insights

**What happened:**
- Extracted all text automatically
- AI categorized by theme
- No manual typing needed
- Ready for documentation

**Exercise 4: Generate Action Items**

STOP: Ask me: "From these insights, generate prioritized action items for the product team"

USER: Types command

ACTION: Analyze the categorized themes and create:
1. High priority actions (most mentioned)
2. Medium priority actions
3. Quick wins (easy to implement)
4. Format as actionable tasks

Example:
```
HIGH PRIORITY:
1. Design size recommendation feature (addresses 12 pain points)
2. Reduce checkout steps from 5 to 3 (addresses 8 pain points)

MEDIUM PRIORITY:
3. Implement guest checkout (addresses 5 pain points)
...
```

---

## Phase 4: Roadmap Visualization

**Exercise 5: Extract Roadmap Data**

Scenario: Your Q1 roadmap is visualized in Miro

STOP: Ask me: "Get all cards from the 'Q1 2025 Roadmap' board and create a timeline document"

USER: Types command

ACTION:
1. Fetch all card items
2. Extract titles and descriptions
3. Organize by position (boards often use spatial layout for time)
4. Create formatted timeline

Example output:
```
Q1 2025 Product Roadmap

JANUARY:
- Size Recommendation MVP
- Checkout Flow Simplification

FEBRUARY:
- Mobile App Performance Improvements
- Wishlist Sharing Feature

MARCH:
- AR Try-On Pilot
- Returns Process Redesign
```

---

**Exercise 6: Convert to Confluence**

STOP: Ask me: "Create a Confluence page with this roadmap and link to the Miro board"

USER: Types command

ACTION: 
1. Format roadmap for Confluence
2. Add Miro board link
3. Create page using Confluence MCP (Module 4.2)
4. Return URL

Now your roadmap lives in both visual (Miro) and document (Confluence) formats.

---

## Phase 5: Create Documentation from Boards

**Exercise 7: Workshop Summary Report**

STOP: Ask me: "Create a complete workshop summary document including: participants, sticky notes by theme, action items, and next steps"

USER: Types command

ACTION: Generate comprehensive summary:

```markdown
# Customer Pain Points Workshop - Summary
Date: [Today]
Facilitator: [User name]

## Participants
[Extract from board if available, or prompt for]

## Workshop Output
Total items collected: 47 sticky notes, 12 cards

## Key Themes

### 1. Checkout Friction (8 notes, 34% of feedback)
[Grouped sticky note content]
**Impact:** High - affects conversion rate

### 2. Sizing Uncertainty (12 notes, 26% of feedback)
[Grouped sticky note content]
**Impact:** High - affects returns rate

[Continue for all themes...]

## Action Items
[Prioritized list from Exercise 4]

## Next Steps
1. Schedule follow-up with engineering
2. Prioritize in Q1 sprint planning
3. Create PRDs for top 3 items

## Links
- Miro Board: [link]
- Related Confluence Docs: [links]
```

---

**Exercise 8: Export for Stakeholders**

STOP: Ask me: "Create an executive summary (3 paragraphs) of the workshop for leadership"

USER: Types command

ACTION: Distill insights into executive format:

```
We conducted a customer pain points workshop with 15 cross-functional 
stakeholders, collecting 47 distinct pain points from recent customer 
research. The findings revealed three critical themes...

The highest-impact opportunity is size recommendation, mentioned in 26% 
of feedback and directly linked to our returns problem. Addressing this 
could reduce returns by an estimated 15-20%...

We recommend prioritizing size recommendation for Q1, with a projected 
8-week delivery timeline. Full workshop outputs and action plan are 
available in [Confluence link].
```

---

## Phase 6: Real PM Workflows

**Workflow 1: Sprint Planning from Miro**

STOP: Ask me: "Extract sprint planning cards from Miro and create corresponding work items in Azure DevOps"

USER: Types command

ACTION: Demonstrate full integration:

```
1. "Get all cards from Sprint Planning board"
2. For each card:
   - Extract title
   - Extract description
   - Identify story points (if noted)
3. "Create user stories in Azure DevOps"
4. "Link each story back to Miro card"

Result: Sprint backlog populated from visual planning session
```

---

**Workflow 2: Customer Journey Mapping**

STOP: Ask me: "Get our customer journey map from Miro and identify pain points vs. delight moments"

USER: Types command

ACTION:

```
1. Fetch journey map items
2. Categorize by sentiment (pain/neutral/delight)
3. Map to journey stages
4. Generate insights document

Output:
AWARENESS STAGE:
✓ Delight: Personalized ads performing well
✗ Pain: Hard to find specific items (7 mentions)

CONSIDERATION STAGE:
...
```

---

**Workflow 3: Retro Analysis**

STOP: Ask me: "Extract our last 3 sprint retros from Miro and identify recurring themes"

USER: Types command

ACTION:

```
1. Get items from each retro board
2. Group feedback across sprints
3. Identify patterns
4. Suggest systemic improvements

Output:
RECURRING THEMES (appeared 3/3 retros):
- Testing time underestimated
- Dependency on design team
- Unclear acceptance criteria

RECOMMENDATIONS:
1. Add 20% buffer to testing estimates
2. Align design reviews earlier in sprint
3. Use PRD template with explicit AC format
```

---

## Phase 7: Advanced Techniques

**Technique 1: Visual Voting Results**

Many workshops use voting dots in Miro

STOP: Ask me: "Analyze voting on feature ideas board - count votes per card and rank by priority"

USER: Types command

ACTION: If voting data is extractable, show ranked results. Otherwise, guide them to use positioning or labels as proxies.

---

**Technique 2: Cross-Board Analysis**

STOP: Ask me: "Compare customer pain points from Q3 workshop with Q4 workshop - what changed?"

USER: Types command

ACTION:
1. Extract from both boards
2. Compare themes
3. Identify new pain points
4. Track if old pain points resolved

Shows trend analysis across time.

---

**Technique 3: Image Extraction**

STOP: Ask me: "Get all images from the board and download for documentation"

USER: Types command

ACTION: Use `board_get_image_download_url` to fetch image URLs, providing links for download.

---

## Phase 8: Integration with Other Modules

**Module 2.1 (PRD Writing):**
```
Miro workshop → Extract insights → Add to PRD → Publish to Confluence
```

**Module 2.3 (Strategy):**
```
Strategy brainstorm in Miro → Extract decisions → Create strategy doc
```

**Module 4.2 (Confluence):**
```
Miro board → Extract content → Create Confluence summary → Link back
```

**Module 4.3 (Azure DevOps):**
```
Miro planning → Extract cards → Create work items → Link boards
```

STOP: Which integration would streamline your workflow most?

USER: Responds

---

## Phase 9: Best Practices

**DO:**
✓ Name boards descriptively (include date)
✓ Use consistent structure (frames, zones)
✓ Tag items for easy filtering
✓ Extract insights while fresh (same day)
✓ Keep Miro as source, sync to docs

**DON'T:**
✗ Delete boards after extracting (keep archive)
✗ Assume MCP captures visual layout perfectly
✗ Skip manual review of synthesis
✗ Over-rely on automation for nuanced insights
✗ Forget to credit participants

---

**Workshop Facilitation Tips:**

**Before workshop:**
- Set up board structure in advance
- Brief participants on how you'll capture output
- Test MCP extraction with sample data

**During workshop:**
- Encourage clear, complete sticky notes
- Use frames to organize themes
- Tag items with metadata

**After workshop:**
- Extract within 24 hours while context is fresh
- Review synthesis for accuracy
- Share back with participants for validation

STOP: What's your typical post-workshop process?

USER: Responds

---

## Common Issues & Solutions

**Issue 1: "Board not found"**
- Verify board ID from URL
- Check you have board access
- Try board_get_items to test connection

**Issue 2: "Too many items"**
- Use pagination (limit parameter)
- Filter by item type
- Focus on specific frames

**Issue 3: "Can't read text in images"**
- Miro MCP gets item metadata, not image OCR
- Sticky notes as text items work best
- Images require manual documentation

STOP: Hit any issues? Let's troubleshoot.

USER: Reports issues or confirms working

---

## Practice Challenge

**Challenge: Complete Workshop Documentation Workflow**

You ran a feature prioritization workshop. Now:

1. Get all sticky notes from the board
2. Group into themes
3. Identify top 3 priorities by vote count
4. Generate action items
5. Create Confluence summary page
6. Create Azure DevOps epics for top 3
7. Link everything together

STOP: Complete this workflow (or document the steps if you don't have a live board)

USER: Works through challenge

ACTION: Guide through each step, provide feedback

---

## Time Savings Analysis

**Traditional post-workshop workflow:**
- Manual transcription: 45 min
- Categorization: 20 min
- Document creation: 15 min
- Stakeholder distribution: 10 min
- **Total: 90 minutes**

**With Miro MCP:**
- Extraction: 2 min
- AI categorization: 1 min
- Document generation: 3 min
- Distribution (Confluence): 1 min
- **Total: 7 minutes**

**Time saved:** 83 minutes per workshop

STOP: How many workshops do you facilitate per quarter?

USER: Responds

ACTION: Calculate quarterly savings: [number] × 83 minutes / 60 = [X] hours saved

---

## Next Steps

You've mastered Miro collaboration! Next: **Build HTML Presentations (Bonus)**

**Before Module 4.6:**
1. Review your recent Miro boards
2. Practice extracting from 2-3 boards
3. Set up board templates for future workshops

**In Module 4.6, you'll learn:**
- Pull data from all MCPs (Confluence, Azure DevOps, Figma, Miro)
- Build reveal.js presentations
- Create interactive dashboards
- Generate stakeholder-ready outputs
- Export in multiple formats

STOP: Ready to create stunning presentations from your integrated data?

USER: Confirms

---

## Reflection

You can now:
✓ Access Miro boards from VSCode
✓ Extract workshop outputs automatically
✓ Synthesize visual brainstorming at scale
✓ Create documentation from boards
✓ Integrate Miro with other PM tools

**Your new superpower:** Visual thinking at machine speed

**Time saved:** 5-10 hours per month on workshop synthesis

See you in Module 4.6! 🎬
