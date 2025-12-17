# Module 4.4: Figma Collaboration

**Teaching Script for GitHub Copilot**  
**Duration:** ~25 minutes

---

## Teaching Flow

Welcome to Module 4.4: Figma Collaboration!

Connect Copilot to your design files and bridge the PM-Design gap

By the end of this lesson, you'll be able to:
- Browse Figma files from VSCode
- Extract component specifications
- Reference designs in documentation
- Sync design tokens automatically
- Streamline design handoff

STOP: How often do you reference Figma files when writing specs?

USER: Responds

---

## Why Figma + Copilot?

The PM-Design workflow problem:

**Current workflow (without MCP):**
1. Open Figma in browser
2. Navigate to correct file/page
3. Inspect element for specs
4. Screenshot for documentation
5. Copy measurements manually
6. Paste into spec doc
7. Keep checking for design updates
8. **Time: 15-20 min per feature spec**

**New workflow (with MCP):**
1. "Show me the PDP redesign specs from Figma"
2. "Extract button component styles"
3. "Add design specs to my PRD"
4. **Time: 2-3 minutes**

**Time saved:** ~85% on design-related documentation

STOP: What Figma information do you extract most often?

USER: Responds

---

## Phase 1: Understand Figma MCP Limitations

**Important context:** The Figma MCP has **read-only** access

**What you CAN do:**
✓ Browse file structure
✓ Get component information
✓ Extract design properties
✓ Reference in documentation
✓ Track design changes

**What you CANNOT do:**
✗ Edit designs
✗ Create new frames
✗ Change component properties
✗ Export assets directly
✗ Leave Figma comments

This is perfect for PMs - you're **documenting** designs, not creating them

STOP: Does read-only access cover your main use cases?

USER: Responds

---

## Phase 2: Connect to Figma

**Note:** Figma MCP support may require setup

For this lesson, we'll demonstrate **conceptual workflows** you can use when Figma MCP is fully available

If you have Figma MCP configured, we'll use it directly. Otherwise, we'll prepare you for when it's ready.

STOP: Do you have access to ASOS Figma files?

USER: Responds

---

## Phase 3: Browse Design Files

**Exercise 1: List Available Files**

STOP: Ask me: "What are the benefits of connecting Figma to Copilot, and what would I be able to do?"

USER: Types command

ACTION: Explain the workflow possibilities:
- Reference design files in PRDs without screenshots
- Extract component specs automatically
- Keep documentation in sync with designs
- Bridge PM-Design communication gap
- Reduce handoff friction

---

**Typical Figma MCP capabilities:**

**File Discovery:**
- List projects in team
- List files in project
- Get file metadata

**Component Inspection:**
- Get component list
- Extract component properties
- Read style definitions
- Get measurements

**Documentation:**
- Reference frames by ID
- Extract text content
- Get layer hierarchy

---

## Phase 4: Extract Design Specifications

**Exercise 2: Document Button Component**

Scenario: You need button specs for your PRD

STOP: Ask me: "If I had Figma MCP access, show me how I would extract button component specifications including colours, padding, and states"

USER: Types command

ACTION: Demonstrate the workflow:

```
1. Query: "Get button components from [FileName]"
   Returns: List of button variants (primary, secondary, etc.)

2. Query: "Extract specifications for primary button"
   Returns:
   - Background: #2d2d2d
   - Text color: #ffffff
   - Padding: 12px 24px
   - Border radius: 2px
   - Font: 14px, bold, uppercase
   - States: default, hover, disabled
   
3. Query: "Add these specs to my PRD documentation"
   Adds formatted spec table to document
```

---

**What you'd get automatically:**

**Component: Primary Button**
```
Background: #2d2d2d
Text: #ffffff
Padding: 12px vertical, 24px horizontal
Border Radius: 2px
Font Size: 14px
Font Weight: 700 (bold)
Text Transform: Uppercase
Letter Spacing: 0.1em
Min Height: 48px

States:
- Default: White bg, dark border
- Hover: Dark bg, white text (inverted)
- Disabled: 50% opacity
- Focus: 2px outline, 2px offset
```

No manual measurement needed!

---

## Phase 5: Design Token Extraction

**Exercise 3: Extract Colour Palette**

STOP: Ask me: "Explain how Figma MCP could extract our design system colours and convert them to CSS variables"

USER: Types command

ACTION: Explain the workflow:

```
1. Query: "Get all colour styles from design system file"
   Returns: Named colours with hex values

2. Copilot converts to CSS:
   --color-brand-primary: #2d2d2d;
   --color-brand-accent: #d01345;
   --color-bg-primary: #ffffff;
   (etc.)

3. Query: "Compare with our current CSS tokens"
   Copilot highlights differences, suggests updates
```

This keeps your code in sync with design source of truth.

---

**Exercise 4: Extract Typography Scale**

STOP: Ask me: "Show me how to extract typography specifications from Figma"

USER: Types command

ACTION: Demonstrate extracting text styles:

```
Text Style: Heading 1
- Font: Futura PT
- Weight: 700
- Size: 32px
- Line Height: 38px
- Letter Spacing: 0em

Text Style: Body
- Font: Futura PT
- Weight: 400
- Size: 14px
- Line Height: 20px (1.4)
- Letter Spacing: 0em
```

Convert to CSS variables automatically.

---

## Phase 6: Reference Designs in Documentation

**Exercise 5: Link Design to PRD**

Scenario: Your PRD needs design context

STOP: Ask me: "How would I reference specific Figma frames in my PRD to show stakeholders the design context?"

USER: Types command

ACTION: Explain the reference workflow:

```markdown
## 4. Proposed Solution

**User Flow:**
See Figma: [Checkout Flow V3](figma://file/ABC123/page/123)

**Desktop Design:**
Frame: "PDP - Size Selector - Desktop"
File: Product Pages Redesign
[Direct Figma link]

**Mobile Design:**
Frame: "PDP - Size Selector - Mobile"  
[Direct Figma link]

**Component Specifications:**
[Auto-extracted specs from Figma]
```

Stakeholders get design context without leaving your doc.

---

## Phase 7: Real PM Workflows

**Workflow 1: PRD with Design Specs**

STOP: Ask me: "Walk me through creating a PRD that automatically includes design specifications from Figma"

USER: Types command

ACTION: Demonstrate full workflow:

```
1. Write PRD in VSCode (Module 2.1 skills)
2. "Get design specs for size selector from Figma PDP file"
3. Copilot extracts and formats specs
4. "Add these specs to Section 4 of my PRD"
5. Specs inserted with proper formatting
6. "Link to the Figma frame for reference"
7. Clickable link added
8. Publish PRD to Confluence (Module 4.2)

Result: PRD with embedded design specs that stay current
```

---

**Workflow 2: Design Review Preparation**

STOP: Ask me: "How would I prepare for a design review meeting using Figma MCP?"

USER: Types command

ACTION: Show prep workflow:

```
1. "Get all frames from latest design review file"
2. "Summarize changes from previous version"
3. "Extract key decision points (variants, interactions)"
4. "Create review checklist:
   - Alignment with requirements
   - Mobile responsiveness
   - Accessibility considerations
   - Technical feasibility"
5. "Add review notes document to Confluence"

Meeting prep time: 5 min instead of 30 min
```

---

**Workflow 3: Design Handoff Documentation**

STOP: Ask me: "Show me how to create technical handoff docs from Figma designs"

USER: Types command

ACTION: Demonstrate handoff automation:

```
For Engineers:

1. "Extract all components from [FileName]"
2. "For each component, get:
   - Visual specs
   - Interaction states
   - Responsive behaviour
   - Accessibility requirements"
3. "Generate handoff document formatted for engineering"
4. "Create work items in Azure DevOps for each component"
5. "Link Figma frames to work items"

Result: Complete handoff package in minutes
```

---

## Phase 8: Design-Code Sync

**Exercise 6: Compare Design Tokens with Code**

STOP: Ask me: "How would I check if our CSS matches the latest Figma design tokens?"

USER: Types command

ACTION: Show sync validation:

```
1. "Extract colour styles from Figma design system"
2. "Read our starter-tokens.css file"
3. "Compare and report differences"

Copilot reports:
✓ Matched: --color-brand-primary (#2d2d2d)
✓ Matched: --color-bg-primary (#ffffff)
⚠️  Difference: --color-accent
   Code: #d01345
   Figma: #d01344 (updated)
❌ Missing in code: --color-success (#018849)

4. "Update CSS to match Figma"
5. CSS file updated automatically
```

Your code stays in sync with design source of truth.

---

## Phase 9: Integration with Other Modules

**Module 2.1 (PRD Writing):**
```
Write PRD → Extract Figma specs → Embed in PRD → Publish to Confluence
```

**Module 3.1 (Prototyping):**
```
Get Figma design tokens → Use in HTML prototype → Match production exactly
```

**Module 4.2 (Confluence):**
```
Extract Figma specs → Document in Confluence → Link to design files
```

**Module 4.3 (Azure DevOps):**
```
Get Figma components → Create work items → Link frames to stories
```

STOP: Which integration would be most valuable for your workflow?

USER: Responds

---

## Phase 10: Best Practices for Design Collaboration

**DO:**
✓ Reference Figma files by specific frame/page
✓ Extract specs when designs are finalized
✓ Keep design links in documentation
✓ Validate code against design tokens regularly
✓ Document design decisions with context

**DON'T:**
✗ Extract specs from WIP designs
✗ Assume designs are static (they change!)
✗ Skip designer collaboration
✗ Override design system without discussion
✗ Forget to update specs when designs change

---

**Communication Tips:**

**When working with designers:**
- "I'm referencing the [Frame Name] for specs"
- "Can you mark frames as 'Final for Dev'?"
- "I'll extract specs once designs are approved"
- "Should I sync our CSS tokens with your latest?"

**When documenting:**
- Include Figma file name + frame name
- Note extraction date (designs may update)
- Link to source design
- Specify viewport (desktop/mobile/tablet)

STOP: How do you currently collaborate with your designers?

USER: Responds

---

## Common Scenarios & Solutions

**Scenario 1: Design Changes After Specs Extracted**

Solution: 
- Set up regular design sync checkpoints
- "Check if [Frame] has changed since [date]"
- Update docs when designs finalize

**Scenario 2: Designer Uses Different Tool**

Solution:
- Figma MCP only works with Figma
- For Sketch/Adobe XD: Manual extraction still needed
- Advocate for Figma as ASOS standard

**Scenario 3: Designs Not in Figma Yet**

Solution:
- Wait for design finalization
- Use Module 3.1 skills to prototype yourself
- Collaborate on component specifications

STOP: Which scenario matches your current challenge?

USER: Responds

---

## When Figma MCP Isn't Available

**Alternative workflows:**

1. **Screenshot Method:**
   - Export frame as image from Figma
   - Save to design-assets folder
   - Reference in documentation
   - Use Module 3.1 to recreate in HTML

2. **Manual Extraction:**
   - Inspect in Figma
   - Document specs in Markdown table
   - Store in your repo
   - Use as reference

3. **Figma Dev Mode:**
   - Use Figma's built-in Dev Mode
   - Copy code snippets
   - Paste into your components
   - Adapt to your system

**Future-proofing:** Learn these workflows now so you're ready when Figma MCP is available

---

## Practice Challenge

**Challenge: Design Documentation Workflow**

Prepare this workflow for when you have Figma access:

1. List the steps to extract button specifications from Figma
2. Write the commands you would use
3. Create a template for design handoff docs
4. Outline how you'd sync with CSS tokens
5. Document how you'd link to Azure DevOps work items

STOP: Complete this planning exercise

USER: Works through challenge

ACTION: Review their workflow, provide feedback, suggest improvements

---

## Future of Design-PM Collaboration

**What's coming:**
- Real-time design sync in VSCode
- Automated design change notifications
- AI-assisted design validation
- One-click prototype generation from Figma
- Bidirectional sync (code → Figma)

**Your role as early adopter:**
- Master these workflows now
- Provide feedback on Figma MCP
- Champion PM-Design tool integration
- Share learnings with team

STOP: How would perfect Figma integration change your workflow?

USER: Responds

---

## Next Steps

You've learned Figma collaboration patterns! Next: **Miro for Visual Thinking**

**Before Module 4.5:**
1. Audit your Figma usage patterns
2. Map out your ideal design workflow
3. Identify repetitive design documentation tasks

**In Module 4.5, you'll learn:**
- Create Miro boards from VSCode
- Extract workshop insights automatically
- Visualize roadmaps programmatically
- Collaborate visually at scale
- Synthesize stakeholder input

STOP: Ready to unlock visual collaboration?

USER: Confirms

---

## Reflection

You now understand:
✓ Figma MCP capabilities and limitations
✓ How to extract design specifications
✓ Design token synchronization
✓ Design-to-documentation workflows
✓ PM-Design collaboration best practices

**Your future superpower:** Design documentation at design speed

**Time saved (when available):** 10-15 hours per week on design specs

See you in Module 4.5! 🎨
