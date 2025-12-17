# Module 4.6: Build HTML Presentations (Bonus)

**Teaching Script for GitHub Copilot**

---

## Teaching Flow

Welcome to Module 4.6: Build HTML Presentations!

The grand finale - combine everything you've learned to create stunning stakeholder presentations

By the end of this lesson, you'll be able to:
- Pull data from all your connected tools
- Build reveal.js presentations from scratch
- Create interactive dashboards
- Generate charts and visualizations
- Export in multiple formats

STOP: How much time do you spend building presentations for stakeholders?

USER: Responds

---

## Why HTML Presentations?

**The presentation challenge:**

**Traditional workflow (PowerPoint/Slides):**
1. Gather data from Confluence, Azure DevOps, Figma, Miro
2. Create slides manually
3. Format charts and graphics
4. Keep updating as data changes
5. Export to PDF
6. Repeat for every update
7. **Time: 2-4 hours per deck**

**New workflow (HTML presentations):**
1. "Build a stakeholder presentation with:
   - Sprint progress from Azure DevOps
   - Customer insights from Confluence
   - Design previews from Figma
   - Workshop outputs from Miro"
2. Copilot generates reveal.js presentation
3. **Time: 15-20 minutes**

**Time saved:** 90% reduction + presentations are **live-updating**

STOP: What type of presentations do you create most often?

USER: Responds

---

## Phase 1: Introduction to reveal.js

**What is reveal.js?**
- HTML/CSS/JS presentation framework
- Works in any browser
- Keyboard navigation (arrow keys)
- Responsive (desktop/mobile/projector)
- Exportable to PDF
- Themeable and extensible

**Why reveal.js for PMs?**
- Write in Markdown (your existing skill)
- Version control (Git)
- Programmatically generate content
- Embed live data
- Interactive charts
- No PowerPoint license needed

STOP: Have you seen HTML presentations before?

USER: Responds

---

## Phase 2: Build Your First Presentation

**Exercise 1: Basic Structure**

Let's create a simple presentation

STOP: Ask me: "Create a reveal.js presentation with 5 slides: title, problem, solution, metrics, next steps"

USER: Types command

ACTION: Generate a basic HTML file with reveal.js structure:

```html
<!DOCTYPE html>
<html>
<head>
  <title>Feature Proposal</title>
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/reveal.js@4.5.0/dist/reveal.css">
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/reveal.js@4.5.0/dist/theme/white.css">
</head>
<body>
  <div class="reveal">
    <div class="slides">
      
      <!-- Slide 1: Title -->
      <section>
        <h1>Size Recommendation Feature</h1>
        <p>Product Proposal</p>
        <p><small>Your Name | Date</small></p>
      </section>

      <!-- Slide 2: Problem -->
      <section>
        <h2>The Problem</h2>
        <ul>
          <li>30% return rate driven by size issues</li>
          <li>Customers order multiple sizes</li>
          <li>Uncertainty reduces conversion</li>
        </ul>
      </section>

      <!-- Slide 3: Solution -->
      <section>
        <h2>Proposed Solution</h2>
        <p>AI-powered size recommendation based on purchase history</p>
        <img src="design-preview.png" alt="Design" style="max-height: 400px;">
      </section>

      <!-- Slide 4: Metrics -->
      <section>
        <h2>Success Metrics</h2>
        <table>
          <tr><th>Metric</th><th>Current</th><th>Target</th></tr>
          <tr><td>Return Rate</td><td>30%</td><td>22%</td></tr>
          <tr><td>Conversion</td><td>2.5%</td><td>3.2%</td></tr>
        </table>
      </section>

      <!-- Slide 5: Next Steps -->
      <section>
        <h2>Next Steps</h2>
        <ol>
          <li>Engineering feasibility (2 weeks)</li>
          <li>Design mockups (1 week)</li>
          <li>User testing (2 weeks)</li>
          <li>Sprint planning (Q1)</li>
        </ol>
      </section>

    </div>
  </div>
  <script src="https://cdn.jsdelivr.net/npm/reveal.js@4.5.0/dist/reveal.js"></script>
  <script>Reveal.initialize();</script>
</body>
</html>
```

Save as `presentation.html` and open in browser.

---

Great! You just created your first HTML presentation

**Navigation:**
- Arrow keys: Next/previous slide
- ESC: Overview mode
- S: Speaker notes
- F: Fullscreen

STOP: Open the file in your browser and try navigating

USER: Opens and explores

---

## Phase 3: Pull Data from MCPs

Now let's make it dynamic with real data

**Exercise 2: Add Confluence Content**

STOP: Ask me: "Search Confluence for customer pain points about sizing and add them to slide 2 of my presentation"

USER: Types command

ACTION:
1. Search Confluence (Module 4.2 skills)
2. Extract key pain points
3. Update slide 2 HTML with real data
4. Format as bullet points

---

**Exercise 3: Add Azure DevOps Sprint Data**

STOP: Ask me: "Get current sprint progress from Azure DevOps and add to slide 4"

USER: Types command

ACTION:
1. Query sprint work items (Module 4.3 skills)
2. Calculate completion percentage
3. Create progress visual
4. Add to metrics slide

Example output:
```html
<section>
  <h2>Sprint Progress</h2>
  <div style="text-align: left;">
    <p><strong>Sprint 23 - Size Recommendation</strong></p>
    <div style="background: #eee; height: 30px; border-radius: 5px;">
      <div style="background: #4CAF50; height: 100%; width: 65%; border-radius: 5px;"></div>
    </div>
    <p>65% Complete (13/20 story points)</p>
    <ul>
      <li>✓ API endpoint created</li>
      <li>✓ Frontend component developed</li>
      <li>⏳ User testing in progress</li>
    </ul>
  </div>
</section>
```

---

**Exercise 4: Add Figma Design Preview**

STOP: Ask me: "Get the latest size recommendation design from Figma and add a preview to slide 3"

USER: Types command

ACTION: 
1. Reference Figma file (Module 4.4 skills)
2. Get frame link
3. Add as image embed or link

---

**Exercise 5: Add Miro Workshop Insights**

STOP: Ask me: "Get sticky notes from our customer workshop Miro board and add top insights to slide 2"

USER: Types command

ACTION:
1. Extract Miro content (Module 4.5 skills)
2. Summarize top 3 insights
3. Add to problem slide
4. Include visual quote format

---

## Phase 4: Add Visualizations

Make data compelling with charts

**Exercise 6: Create Chart with Chart.js**

STOP: Ask me: "Add a chart showing returns trend over last 6 months to slide 4"

USER: Types command

ACTION: Generate slide with Chart.js:

```html
<section>
  <h2>Returns Trend</h2>
  <canvas id="returnsChart" width="800" height="400"></canvas>
  <script>
    const ctx = document.getElementById('returnsChart').getContext('2d');
    new Chart(ctx, {
      type: 'line',
      data: {
        labels: ['July', 'Aug', 'Sept', 'Oct', 'Nov', 'Dec'],
        datasets: [{
          label: 'Return Rate %',
          data: [28, 30, 29, 31, 30, 30],
          borderColor: '#d01345',
          tension: 0.1
        }]
      },
      options: {
        scales: {
          y: { beginAtZero: false, max: 35 }
        }
      }
    });
  </script>
</section>
```

Include Chart.js library in `<head>`:
```html
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
```

---

**Exercise 7: Sprint Burndown Chart**

STOP: Ask me: "Create a burndown chart from Azure DevOps sprint data"

USER: Types command

ACTION:
1. Get sprint work items and completion dates
2. Calculate remaining work per day
3. Generate Chart.js line chart
4. Show ideal vs actual burndown

---

## Phase 5: Advanced Presentation Features

**Exercise 8: Speaker Notes**

STOP: Ask me: "Add speaker notes to each slide with key talking points"

USER: Types command

ACTION: Add `<aside class="notes">` to each slide:

```html
<section>
  <h2>The Problem</h2>
  <ul>
    <li>30% return rate</li>
    <li>Size uncertainty</li>
  </ul>
  <aside class="notes">
    Key points:
    - Returns cost us £12M annually
    - #1 customer complaint in surveys
    - Affects brand perception
    - Quick win opportunity
  </aside>
</section>
```

Press 'S' during presentation to see notes.

---

**Exercise 9: Vertical Slides**

Create sub-slides for details

STOP: Ask me: "Create a vertical slide stack showing 3 customer personas with pain points for each"

USER: Types command

ACTION: Generate nested sections:

```html
<section>
  <section>
    <h2>Customer Personas</h2>
    <p>Press ↓ to explore each persona</p>
  </section>
  
  <section>
    <h3>Sophie - Trend Hunter</h3>
    <ul>
      <li>Orders frequently</li>
      <li>Pain: Returns take too long</li>
      <li>Wants: Instant size confidence</li>
    </ul>
  </section>
  
  <section>
    <h3>Emma - Brand Loyalist</h3>
    <ul>
      <li>Knows what she likes</li>
      <li>Pain: Inconsistent sizing across brands</li>
      <li>Wants: Size history tracking</li>
    </ul>
  </section>
  
  <section>
    <h3>Marcus - Occasional Shopper</h3>
    <ul>
      <li>Shops for events</li>
      <li>Pain: No size guidance for new brands</li>
      <li>Wants: Smart recommendations</li>
    </ul>
  </section>
</section>
```

---

**Exercise 10: Fragments (Incremental Display)**

Reveal points one at a time

STOP: Ask me: "Make the metrics slide reveal each metric one by one as I click"

USER: Types command

ACTION: Add `class="fragment"`:

```html
<section>
  <h2>Expected Impact</h2>
  <ul>
    <li class="fragment">Return rate: 30% → 22% (-25%)</li>
    <li class="fragment">Conversion: 2.5% → 3.2% (+28%)</li>
    <li class="fragment">Customer satisfaction: +15 NPS points</li>
    <li class="fragment">Projected revenue impact: +£8M annually</li>
  </ul>
</section>
```

Click or press space to reveal each item.

---

## Phase 6: Styling & Themes

**Exercise 11: Custom Theme**

STOP: Ask me: "Style the presentation with ASOS brand colors"

USER: Types command

ACTION: Add custom CSS:

```html
<style>
  .reveal {
    background: #ffffff;
  }
  .reveal h1, .reveal h2, .reveal h3 {
    color: #2d2d2d;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.05em;
  }
  .reveal strong {
    color: #d01345;
  }
  .reveal .progress {
    background: #d01345;
  }
  .reveal .controls {
    color: #2d2d2d;
  }
</style>
```

Now it matches ASOS design system!

---

## Phase 7: Export & Share

**Exercise 12: Export to PDF**

STOP: Ask me: "How do I export this presentation to PDF?"

USER: Types command

ACTION: Explain the process:

```
Method 1: Browser Print
1. Open presentation in browser
2. Add ?print-pdf to URL: file:///.../presentation.html?print-pdf
3. File → Print → Save as PDF
4. Result: One slide per PDF page

Method 2: decktape (command line)
npm install -g decktape
decktape reveal presentation.html presentation.pdf

Method 3: Screenshot each slide
Use browser dev tools or screenshot tool
```

---

**Exercise 13: Host Online**

STOP: Ask me: "How can I share this presentation with a URL?"

USER: Types command

ACTION: Explain hosting options:

```
Option 1: GitHub Pages (free)
1. Push presentation.html to GitHub repo
2. Enable GitHub Pages in repo settings
3. Share: https://[username].github.io/[repo]/presentation.html

Option 2: Vercel/Netlify (free)
1. Connect GitHub repo
2. Auto-deploys on push
3. Get custom URL

Option 3: ASOS internal hosting
Upload to your team's hosting space
```

---

## Phase 8: Real PM Presentations

**Template 1: Feature Proposal**

STOP: Ask me: "Create a feature proposal presentation template with problem, solution, metrics, timeline, and ask"

USER: Types command

ACTION: Generate complete template with all sections, styled professionally.

---

**Template 2: Sprint Review**

STOP: Ask me: "Create a sprint review presentation pulling completed work items from Azure DevOps and showing before/after metrics"

USER: Types command

ACTION: Generate template that:
1. Queries Azure DevOps for completed items
2. Groups by epic/theme
3. Shows sprint metrics
4. Includes demo links
5. Lists next sprint priorities

---

**Template 3: Quarterly Business Review**

STOP: Ask me: "Create a QBR presentation with:
- Customer metrics from Confluence
- Sprint velocity trends from Azure DevOps  
- Feature screenshots from Figma
- Workshop insights from Miro"

USER: Types command

ACTION: Generate comprehensive QBR template pulling from all integrated tools.

---

## Phase 9: Interactive Dashboards

**Exercise 14: Live Dashboard**

Let's create a dashboard that updates in real-time

STOP: Ask me: "Create a live dashboard slide showing current sprint status that refreshes when I reload"

USER: Types command

ACTION: Generate slide with JavaScript that fetches data:

```html
<section data-auto-animate>
  <h2>Live Sprint Dashboard</h2>
  <div id="dashboard">Loading...</div>
  <script>
    async function updateDashboard() {
      // In real implementation, this would call Azure DevOps API
      // For demo, we'll show the structure
      const data = {
        completed: 13,
        inProgress: 5,
        todo: 2,
        velocity: 42
      };
      
      document.getElementById('dashboard').innerHTML = `
        <div style="display: grid; grid-template-columns: repeat(2, 1fr); gap: 20px;">
          <div style="background: #4CAF50; padding: 20px; border-radius: 10px;">
            <h3 style="margin: 0; color: white;">${data.completed}</h3>
            <p style="color: white;">Completed</p>
          </div>
          <div style="background: #FF9800; padding: 20px; border-radius: 10px;">
            <h3 style="margin: 0; color: white;">${data.inProgress}</h3>
            <p style="color: white;">In Progress</p>
          </div>
          <div style="background: #2196F3; padding: 20px; border-radius: 10px;">
            <h3 style="margin: 0; color: white;">${data.todo}</h3>
            <p style="color: white;">To Do</p>
          </div>
          <div style="background: #9C27B0; padding: 20px; border-radius: 10px;">
            <h3 style="margin: 0; color: white;">${data.velocity}</h3>
            <p style="color: white;">Sprint Velocity</p>
          </div>
        </div>
      `;
    }
    updateDashboard();
  </script>
</section>
```

---

## Phase 10: Best Practices

**DO:**
✓ Keep slides simple (one idea per slide)
✓ Use ASOS brand colors consistently
✓ Include speaker notes for context
✓ Test presentation on projector before meeting
✓ Export backup PDF in case of tech issues
✓ Version control presentations (Git)

**DON'T:**
✗ Overload slides with text
✗ Use tiny fonts (min 24px)
✗ Forget to test navigation
✗ Embed huge images (optimize first)
✗ Rely solely on live data (have static backup)

---

**Presentation Tips:**

**Before presenting:**
- Test in actual presentation environment
- Have PDF backup ready
- Pre-load all network resources
- Practice with speaker notes

**During presenting:**
- Use presenter mode (press 'S')
- Navigate with confidence (arrow keys)
- ESC for overview if you lose place
- Have water nearby (static can cause clicks!)

---

## Common Issues & Solutions

**Issue 1: "Presentation doesn't load"**
- Check internet connection (CDN resources)
- Use local copies of libraries if offline
- Validate HTML structure

**Issue 2: "Charts don't display"**
- Verify Chart.js is loaded
- Check browser console for errors
- Ensure canvas IDs are unique

**Issue 3: "Slides look different on projector"**
- Test beforehand with actual projector
- Check aspect ratio settings
- Adjust font sizes if needed

STOP: Any concerns about using HTML presentations in stakeholder meetings?

USER: Responds

---

## Practice Challenge

**Challenge: Build Your Signature Presentation**

Create a complete presentation for your next stakeholder meeting:

1. Choose your topic (feature proposal, sprint review, or QBR)
2. Pull real data from 2+ integrated tools
3. Add 3+ visualizations (charts, progress bars, metrics)
4. Style with ASOS brand colors
5. Add speaker notes to all slides
6. Test navigation
7. Export to PDF
8. Share with me for feedback

STOP: Complete this challenge - allocate 30 minutes

USER: Works through challenge

ACTION: Review their presentation, provide feedback on:
- Data integration
- Visual clarity
- Story flow
- Technical execution
- Professional polish

---

## Time Savings Analysis

**Traditional presentation creation:**
- Gather data from tools: 45 min
- Create slides manually: 60 min
- Format and polish: 30 min
- Export and share: 10 min
- Updates for each iteration: 30 min
- **Total: 2.5-3 hours per deck**

**With HTML presentations + MCPs:**
- Generate from integrated data: 15 min
- Customize and polish: 10 min
- Export: 2 min
- Updates: 5 min (regenerate)
- **Total: 27-32 minutes**

**Time saved:** 2+ hours per presentation

STOP: How many presentations do you create per quarter?

USER: Responds

ACTION: Calculate quarterly savings: [number] × 2 hours = [X] hours saved

---

## Module 4 Complete!

Congratulations! You've completed all of Module 4: MCP Integration

**You can now:**
✓ Search and create Confluence pages (Module 4.2)
✓ Query and manage Azure DevOps work items (Module 4.3)
✓ Reference and extract Figma designs (Module 4.4)
✓ Extract and synthesize Miro boards (Module 4.5)
✓ Build stunning HTML presentations (Module 4.6)

**Total time saved per week with all Module 4 skills:**
- Confluence: 5-10 hours
- Azure DevOps: 2-4 hours
- Figma: 3-5 hours (when available)
- Miro: 5-10 hours
- Presentations: 2-4 hours
- **Total: 17-33 hours per week**

That's equivalent to **2-4 days** back in your calendar each week!

---

## What's Next?

You've completed the entire VSCode PM Course:
- Module 1: Copilot Fundamentals ✓
- Module 2: PM Skills (PRD, Data, Strategy) ✓
- Module 3: Rapid Prototyping ✓
- Module 4: MCP Integration ✓

**Recommended next steps:**

1. **Practice daily** - Use these skills in real work immediately
2. **Share with team** - Teach colleagues what you've learned
3. **Automate workflows** - Identify repetitive tasks to eliminate
4. **Build templates** - Create reusable patterns for your work
5. **Stay updated** - New MCPs and features launch regularly

---

## Share Your Success

**We want to hear from you:**
- What workflow saved you the most time?
- What feature are you most excited about?
- What should be added to this course?

**Share with your team:**
- Demo your HTML presentation skills
- Show off your MCP integrations
- Evangelize AI-assisted PM work

---

## Final Reflection

Think back to Module 1.1 when you started this course.

**Then:** Switching between 5-10 tools daily, manual documentation, hours on slides

**Now:** Integrated workflow, automated documentation, minutes on presentations

**ROI:** 20-40 hours per week saved = **50-100% productivity increase**

You're not just a PM anymore - you're an **AI-augmented PM**

Use these superpowers to focus on what matters:
- Strategic thinking
- Customer empathy
- Creative problem-solving
- Team leadership

Let AI handle the busywork. You handle the breakthroughs.

---

## Thank You!

**Course created by:** Conrad Annan  
**For:** ASOS Product Managers  
**With:** GitHub Copilot & Claude

You've completed the journey from Copilot beginner to integration expert.

Now go build something amazing! 🚀

STOP: What will you build first with your new skills?

USER: Responds with their plans

ACTION: Celebrate their completion, encourage them, and wish them success!

---

**You did it! 🎉**

Welcome to the future of product management.
