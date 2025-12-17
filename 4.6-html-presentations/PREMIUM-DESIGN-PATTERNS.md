# Premium HTML Presentation Design Patterns

*Research and analysis of world-class reveal.js presentations used by Stripe, Linear, Vercel, and Apple*

## Executive Summary: What's Missing

Your current ASOS presentation has good foundations (design tokens, shadows, glassmorphism) but lacks:

1. **Typography sophistication** - No hierarchy scale, missing font features (tracking, optical sizing)
2. **Color depth** - Basic tokens without contextual alpha variations
3. **Layout tension** - Safe, centered layouts; missing asymmetry and intentional whitespace
4. **Interactive polish** - No micro-transitions on state changes
5. **Visual rhythm** - Every slide feels similar; no pacing variation
6. **Data visualization refinement** - Charts lack thoughtful color application
7. **Brand subtlety** - Heavy-handed use of brand colors; missing understated elegance

---

## 1. Typography Hierarchy & Sophistication

### What Top Companies Do

**Stripe** uses a sophisticated type scale with:
- Display fonts for hero moments (60-96px)
- Body hierarchy (14px, 16px, 18px, 21px)
- Micro-copy (11px, 13px) for metadata
- Font features: kerning, ligatures, optical sizing

**Linear** implements:
- Custom font stack with fallbacks
- Tight tracking (-0.02em) for headlines
- Wide tracking (0.1em) for labels
- Variable font weights (300, 400, 500, 600, 700)

### Implementation Pattern

```css
:root {
  /* Type Scale - Perfect Fourth (1.333) + Golden Ratio (1.618) */
  --text-xs: clamp(0.69rem, 0.66rem + 0.15vw, 0.75rem);      /* 11-12px */
  --text-sm: clamp(0.81rem, 0.77rem + 0.2vw, 0.875rem);      /* 13-14px */
  --text-base: clamp(0.94rem, 0.89rem + 0.26vw, 1rem);       /* 15-16px */
  --text-md: clamp(1.09rem, 1.01rem + 0.38vw, 1.18rem);      /* 17-19px */
  --text-lg: clamp(1.27rem, 1.16rem + 0.52vw, 1.41rem);      /* 20-23px */
  --text-xl: clamp(1.48rem, 1.33rem + 0.73vw, 1.69rem);      /* 24-27px */
  --text-2xl: clamp(1.72rem, 1.52rem + 0.98vw, 2.03rem);     /* 28-32px */
  --text-3xl: clamp(2.00rem, 1.74rem + 1.31vw, 2.44rem);     /* 32-39px */
  --text-4xl: clamp(2.33rem, 1.98rem + 1.73vw, 2.93rem);     /* 37-47px */
  --text-5xl: clamp(2.71rem, 2.26rem + 2.27vw, 3.52rem);     /* 43-56px */
  --text-6xl: clamp(3.16rem, 2.58rem + 2.96vw, 4.23rem);     /* 51-68px */
  
  /* Font Features - Modern Browsers */
  --font-feature-settings: "kern" 1, "liga" 1, "calt" 1;
  --font-variant-numeric: tabular-nums;
  
  /* Letter Spacing - Contextual */
  --tracking-tighter: -0.05em;
  --tracking-tight: -0.025em;
  --tracking-normal: 0;
  --tracking-wide: 0.025em;
  --tracking-wider: 0.05em;
  --tracking-widest: 0.1em;
  
  /* Line Height - Responsive */
  --leading-none: 1;
  --leading-tight: 1.25;
  --leading-snug: 1.375;
  --leading-normal: 1.5;
  --leading-relaxed: 1.625;
  --leading-loose: 2;
}

/* Typography Classes */
.text-display {
  font-size: var(--text-6xl);
  font-weight: 700;
  line-height: var(--leading-tight);
  letter-spacing: var(--tracking-tighter);
  font-feature-settings: var(--font-feature-settings);
}

.text-headline {
  font-size: var(--text-4xl);
  font-weight: 600;
  line-height: var(--leading-snug);
  letter-spacing: var(--tracking-tight);
}

.text-title {
  font-size: var(--text-2xl);
  font-weight: 600;
  line-height: var(--leading-normal);
  letter-spacing: var(--tracking-normal);
}

.text-body-lg {
  font-size: var(--text-lg);
  font-weight: 400;
  line-height: var(--leading-relaxed);
  letter-spacing: var(--tracking-normal);
}

.text-body {
  font-size: var(--text-base);
  font-weight: 400;
  line-height: var(--leading-relaxed);
  letter-spacing: var(--tracking-normal);
}

.text-caption {
  font-size: var(--text-sm);
  font-weight: 500;
  line-height: var(--leading-normal);
  letter-spacing: var(--tracking-wide);
  text-transform: uppercase;
  color: var(--color-text-tertiary);
}

.text-label {
  font-size: var(--text-xs);
  font-weight: 600;
  line-height: var(--leading-tight);
  letter-spacing: var(--tracking-widest);
  text-transform: uppercase;
}

/* Optical Sizing for Variable Fonts */
@supports (font-variation-settings: normal) {
  .text-display {
    font-variation-settings: 'opsz' 72;
  }
  
  .text-body {
    font-variation-settings: 'opsz' 16;
  }
}
```

### Font Pairing Recommendations

**Option 1: Modern Tech (Vercel, Linear)**
```css
:root {
  --font-display: 'Inter Display', -apple-system, BlinkMacSystemFont, sans-serif;
  --font-body: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
  --font-mono: 'JetBrains Mono', 'Fira Code', 'SF Mono', Consolas, monospace;
}
```

**Option 2: Premium Editorial (Stripe)**
```css
:root {
  --font-display: 'Sohne', 'Helvetica Neue', Arial, sans-serif;
  --font-body: 'Sohne', 'Helvetica Neue', Arial, sans-serif;
  --font-mono: 'Sohne Mono', 'SF Mono', monospace;
}
```

**Option 3: Open Source Alternative**
```css
:root {
  --font-display: 'Cal Sans', 'Inter', -apple-system, sans-serif;
  --font-body: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
  --font-mono: 'JetBrains Mono', monospace;
}
```

---

## 2. Color Systems Beyond Basic Tokens

### What Top Companies Do

**Stripe** uses:
- 9 shades per color (50, 100, 200...900)
- Alpha variants for overlays (rgb(0 0 0 / 0.04))
- Semantic color mapping
- Dark mode inversion with adjusted opacity

**Linear** implements:
- Color scales with perceptual uniformity
- Context-specific alpha channels
- Elevated backgrounds (not just flat colors)

### Implementation Pattern

```css
:root {
  /* ========== BASE PALETTE ========== */
  /* Gray Scale - 11 steps (Radix UI inspired) */
  --gray-1: #fcfcfc;
  --gray-2: #f9f9f9;
  --gray-3: #f0f0f0;
  --gray-4: #e8e8e8;
  --gray-5: #e0e0e0;
  --gray-6: #d9d9d9;
  --gray-7: #cecece;
  --gray-8: #bbbbbb;
  --gray-9: #8d8d8d;
  --gray-10: #838383;
  --gray-11: #646464;
  --gray-12: #202020;
  
  /* Brand Scale - ASOS Red */
  --red-1: #fffcfc;
  --red-2: #fff7f7;
  --red-3: #feebec;
  --red-4: #ffdbdc;
  --red-5: #ffcdce;
  --red-6: #fdbdbe;
  --red-7: #f4a9aa;
  --red-8: #eb8e8f;
  --red-9: #d01345;    /* ASOS Brand */
  --red-10: #bd0f3c;
  --red-11: #a00d35;
  --red-12: #5c0920;
  
  /* Success Scale */
  --green-1: #fbfefc;
  --green-2: #f4fbf6;
  --green-3: #e6f6eb;
  --green-4: #d6f1df;
  --green-5: #c4e8d1;
  --green-6: #adddc0;
  --green-7: #8eceaa;
  --green-8: #5bb98b;
  --green-9: #018849;    /* ASOS Success */
  --green-10: #01763f;
  --green-11: #006235;
  --green-12: #002616;
  
  /* ========== SEMANTIC MAPPING ========== */
  /* Backgrounds - Layered System */
  --bg-base: var(--gray-1);
  --bg-subtle: var(--gray-2);
  --bg-muted: var(--gray-3);
  --bg-elevated: white;
  --bg-overlay: rgb(0 0 0 / 0.5);
  
  /* Text - Hierarchy */
  --text-primary: var(--gray-12);
  --text-secondary: var(--gray-11);
  --text-tertiary: var(--gray-10);
  --text-quaternary: var(--gray-9);
  --text-placeholder: var(--gray-8);
  --text-inverse: white;
  
  /* Borders - Subtle Hierarchy */
  --border-subtle: var(--gray-4);
  --border-default: var(--gray-6);
  --border-strong: var(--gray-8);
  --border-brand: var(--red-7);
  
  /* Interactive States */
  --bg-hover: var(--gray-4);
  --bg-active: var(--gray-5);
  --bg-selected: var(--red-3);
  --bg-selected-hover: var(--red-4);
  
  /* Alpha Variants - For Overlays */
  --alpha-1: rgb(0 0 0 / 0.02);
  --alpha-2: rgb(0 0 0 / 0.04);
  --alpha-3: rgb(0 0 0 / 0.06);
  --alpha-4: rgb(0 0 0 / 0.08);
  --alpha-5: rgb(0 0 0 / 0.12);
  --alpha-6: rgb(0 0 0 / 0.16);
  --alpha-7: rgb(0 0 0 / 0.24);
  --alpha-8: rgb(0 0 0 / 0.36);
  
  /* Brand Alpha - For Tinted Overlays */
  --brand-alpha-subtle: rgb(208 19 69 / 0.04);
  --brand-alpha-muted: rgb(208 19 69 / 0.08);
  --brand-alpha-emphasis: rgb(208 19 69 / 0.12);
}

/* Dark Mode - Adjusted Alpha */
@media (prefers-color-scheme: dark) {
  :root {
    --gray-1: #161616;
    --gray-2: #1c1c1c;
    --gray-3: #232323;
    --gray-4: #282828;
    --gray-5: #2e2e2e;
    --gray-6: #343434;
    --gray-7: #3e3e3e;
    --gray-8: #505050;
    --gray-9: #707070;
    --gray-10: #7e7e7e;
    --gray-11: #a0a0a0;
    --gray-12: #ededed;
    
    /* Increased alpha for visibility */
    --alpha-1: rgb(255 255 255 / 0.03);
    --alpha-2: rgb(255 255 255 / 0.05);
    --alpha-3: rgb(255 255 255 / 0.07);
    --alpha-4: rgb(255 255 255 / 0.09);
    --alpha-5: rgb(255 255 255 / 0.11);
    --alpha-6: rgb(255 255 255 / 0.14);
    --alpha-7: rgb(255 255 255 / 0.19);
    --alpha-8: rgb(255 255 255 / 0.27);
  }
}
```

---

## 3. Layout Patterns: Breaking the Grid

### What Top Companies Do

**Vercel** uses:
- Asymmetric layouts (60/40 splits)
- Content blocks that intentionally bleed
- Floating elements with depth
- Negative space as a design element

**Apple** implements:
- Edge-to-edge hero images
- Text overlays with smart contrast
- Sparse layouts with dramatic whitespace

### Implementation Patterns

```css
/* ========== LAYOUT PRIMITIVES ========== */

/* Asymmetric Grid */
.layout-split-60-40 {
  display: grid;
  grid-template-columns: 60fr 40fr;
  gap: var(--space-12);
  align-items: center;
}

.layout-split-70-30 {
  display: grid;
  grid-template-columns: 70fr 30fr;
  gap: var(--space-16);
  align-items: start;
}

/* Content Bleed */
.content-bleed {
  width: 100vw;
  margin-left: 50%;
  transform: translateX(-50%);
  padding: var(--space-16) var(--space-8);
}

/* Floating Element with Depth */
.float-right {
  float: right;
  margin: var(--space-6) 0 var(--space-6) var(--space-8);
  shape-outside: margin-box;
}

/* Intentional Whitespace */
.spacer-xs { height: var(--space-4); }
.spacer-sm { height: var(--space-8); }
.spacer-md { height: var(--space-16); }
.spacer-lg { height: var(--space-24); }
.spacer-xl { height: var(--space-32); }

/* ========== SLIDE COMPOSITIONS ========== */

/* Hero Slide - Dramatic Entry */
.slide-hero {
  display: flex;
  flex-direction: column;
  justify-content: center;
  min-height: 100vh;
  padding: var(--space-16);
  position: relative;
}

.slide-hero::before {
  content: '';
  position: absolute;
  inset: 0;
  background: radial-gradient(circle at 30% 20%, var(--brand-alpha-subtle) 0%, transparent 50%);
  pointer-events: none;
}

/* Content-Heavy Slide */
.slide-content {
  display: grid;
  grid-template-columns: 1fr;
  gap: var(--space-8);
  max-width: 72ch; /* Optimal reading width */
  margin: 0 auto;
  padding: var(--space-12);
}

/* Visual-First Slide */
.slide-visual {
  display: grid;
  grid-template-rows: auto 1fr;
  gap: var(--space-6);
  padding: var(--space-8);
}

.slide-visual__media {
  position: relative;
  border-radius: var(--radius-xl);
  overflow: hidden;
  box-shadow: var(--shadow-2xl);
}

/* Split Slide - Text + Visual */
.slide-split {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: var(--space-12);
  align-items: center;
  padding: var(--space-12);
}

/* Asymmetric Split */
.slide-split--asymmetric {
  grid-template-columns: 2fr 3fr;
}

/* Grid Showcase */
.slide-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: var(--space-8);
  padding: var(--space-12);
}
```

### Slide Layout Examples

```html
<!-- Hero Slide with Asymmetry -->
<section class="slide-hero">
  <div style="max-width: 60%; margin-left: 10%;">
    <h1 class="text-display" style="margin-bottom: var(--space-6);">
      The future of<br>
      <span style="color: var(--red-9);">product discovery</span>
    </h1>
    <p class="text-body-lg" style="color: var(--text-secondary); max-width: 50ch;">
      How personalized recommendations increased conversion by 32%
    </p>
  </div>
  <div class="spacer-lg"></div>
</section>

<!-- Content + Visual Split -->
<section class="slide-split slide-split--asymmetric">
  <div>
    <span class="text-label" style="color: var(--red-9);">Discovery</span>
    <h2 class="text-headline" style="margin: var(--space-4) 0;">
      Smart search that understands context
    </h2>
    <div class="spacer-sm"></div>
    <ul class="text-body" style="list-style: none; padding: 0;">
      <li style="padding-left: var(--space-6); position: relative; margin-bottom: var(--space-3);">
        <span style="position: absolute; left: 0; color: var(--red-9);">→</span>
        Natural language processing
      </li>
      <li style="padding-left: var(--space-6); position: relative; margin-bottom: var(--space-3);">
        <span style="position: absolute; left: 0; color: var(--red-9);">→</span>
        Visual similarity matching
      </li>
      <li style="padding-left: var(--space-6); position: relative;">
        <span style="position: absolute; left: 0; color: var(--red-9);">→</span>
        Behavioral learning
      </li>
    </ul>
  </div>
  <div style="background: var(--bg-muted); border-radius: var(--radius-xl); aspect-ratio: 16/9; display: flex; align-items: center; justify-content: center;">
    <!-- Visual content -->
    <img src="..." style="width: 100%; height: 100%; object-fit: cover; border-radius: var(--radius-xl);">
  </div>
</section>
```

---

## 4. Interactive Elements: Microinteractions

### What Top Companies Do

**Linear** has:
- Subtle hover lift (2-4px)
- State transitions at 200-300ms
- Focus rings that match brand
- Loading states with skeleton screens

**Stripe** implements:
- Button press feedback
- Smooth color transitions
- Cascading animations on lists
- Smart focus indicators

### Implementation Patterns

```css
/* ========== BUTTON SYSTEM ========== */

.btn {
  /* Base Styles */
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: var(--space-2);
  padding: var(--space-3) var(--space-6);
  font-size: var(--text-base);
  font-weight: 600;
  line-height: 1;
  border-radius: var(--radius-md);
  border: none;
  cursor: pointer;
  transition: all var(--duration-fast) var(--ease-smooth);
  position: relative;
  overflow: hidden;
  
  /* Focus Visible */
  outline: 2px solid transparent;
  outline-offset: 2px;
}

.btn:focus-visible {
  outline-color: var(--red-9);
  outline-offset: 2px;
}

/* Primary Button */
.btn--primary {
  background: var(--red-9);
  color: white;
  box-shadow: 
    0 1px 2px rgb(0 0 0 / 0.08),
    inset 0 1px 0 rgb(255 255 255 / 0.1);
}

.btn--primary:hover {
  background: var(--red-10);
  transform: translateY(-1px);
  box-shadow: 
    0 4px 8px rgb(0 0 0 / 0.12),
    0 2px 4px rgb(0 0 0 / 0.08),
    inset 0 1px 0 rgb(255 255 255 / 0.1);
}

.btn--primary:active {
  transform: translateY(0);
  box-shadow: 
    0 1px 2px rgb(0 0 0 / 0.08),
    inset 0 1px 2px rgb(0 0 0 / 0.1);
}

/* Ghost Button */
.btn--ghost {
  background: transparent;
  color: var(--text-primary);
  border: 1px solid var(--border-default);
}

.btn--ghost:hover {
  background: var(--bg-hover);
  border-color: var(--border-strong);
}

/* Ripple Effect on Click */
.btn::after {
  content: '';
  position: absolute;
  inset: 0;
  background: radial-gradient(circle, white 10%, transparent 10.01%);
  opacity: 0;
  transform: scale(0);
  transition: transform 0.6s, opacity 0.6s;
}

.btn:active::after {
  opacity: 0.3;
  transform: scale(2.5);
  transition: 0s;
}

/* ========== CARD INTERACTIONS ========== */

.card-interactive {
  background: var(--bg-elevated);
  border: 1px solid var(--border-subtle);
  border-radius: var(--radius-lg);
  padding: var(--space-6);
  cursor: pointer;
  transition: all var(--duration-normal) var(--ease-smooth);
  position: relative;
}

/* Subtle Border Gradient on Hover */
.card-interactive::before {
  content: '';
  position: absolute;
  inset: -1px;
  border-radius: inherit;
  padding: 1px;
  background: linear-gradient(135deg, var(--red-9), var(--green-9));
  -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
  -webkit-mask-composite: xor;
  mask-composite: exclude;
  opacity: 0;
  transition: opacity var(--duration-normal) var(--ease-smooth);
}

.card-interactive:hover {
  transform: translateY(-4px);
  box-shadow: 
    0 12px 24px rgb(0 0 0 / 0.12),
    0 4px 8px rgb(0 0 0 / 0.06);
}

.card-interactive:hover::before {
  opacity: 1;
}

/* ========== NAVIGATION INDICATORS ========== */

.nav-dot {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background: var(--gray-6);
  transition: all var(--duration-fast) var(--ease-smooth);
  cursor: pointer;
}

.nav-dot:hover {
  background: var(--gray-8);
  transform: scale(1.2);
}

.nav-dot--active {
  background: var(--red-9);
  width: 24px;
  border-radius: 4px;
}

/* ========== LOADING STATES ========== */

/* Skeleton Loader */
.skeleton {
  background: linear-gradient(
    90deg,
    var(--gray-3) 0%,
    var(--gray-4) 50%,
    var(--gray-3) 100%
  );
  background-size: 200% 100%;
  animation: shimmer 1.5s infinite;
  border-radius: var(--radius-md);
}

@keyframes shimmer {
  0% { background-position: -200% 0; }
  100% { background-position: 200% 0; }
}

/* Spinner */
.spinner {
  width: 20px;
  height: 20px;
  border: 2px solid var(--gray-4);
  border-top-color: var(--red-9);
  border-radius: 50%;
  animation: spin 0.6s linear infinite;
}

@keyframes spin {
  to { transform: rotate(360deg); }
}

/* ========== PROGRESS INDICATOR ========== */

.progress-bar {
  height: 2px;
  background: var(--gray-4);
  position: relative;
  overflow: hidden;
  border-radius: 1px;
}

.progress-bar__fill {
  height: 100%;
  background: linear-gradient(90deg, var(--red-9), var(--red-10));
  transition: width var(--duration-slow) var(--ease-smooth);
  position: relative;
}

.progress-bar__fill::after {
  content: '';
  position: absolute;
  inset: 0;
  background: linear-gradient(90deg, transparent, white, transparent);
  animation: progress-shimmer 1.5s infinite;
}

@keyframes progress-shimmer {
  0% { transform: translateX(-100%); }
  100% { transform: translateX(100%); }
}
```

---

## 5. Data Visualization Styling

### What Top Companies Do

**Stripe Dashboard** has:
- Soft, desaturated chart colors
- Subtle grid lines (alpha 0.1)
- Contextual highlights
- Animated number counters

**Linear Insights** uses:
- Single accent color for key data
- Gray for comparison data
- Minimalist axes and labels

### Implementation Pattern

```css
/* ========== CHART STYLES ========== */

.chart-wrapper {
  background: var(--bg-elevated);
  border: 1px solid var(--border-subtle);
  border-radius: var(--radius-lg);
  padding: var(--space-8);
  box-shadow: var(--shadow-sm);
}

.chart-title {
  font-size: var(--text-lg);
  font-weight: 600;
  color: var(--text-primary);
  margin-bottom: var(--space-6);
}

/* Chart Colors - Desaturated Palette */
:root {
  --chart-primary: var(--red-9);
  --chart-primary-light: var(--red-7);
  --chart-secondary: var(--gray-9);
  --chart-success: var(--green-9);
  --chart-warning: #f59e0b;
  --chart-info: #3b82f6;
  
  /* Grid & Axes */
  --chart-grid: rgb(0 0 0 / 0.06);
  --chart-axis: var(--gray-7);
  --chart-label: var(--text-tertiary);
}

/* Metric Display */
.metric {
  display: flex;
  flex-direction: column;
  gap: var(--space-2);
}

.metric__value {
  font-size: var(--text-5xl);
  font-weight: 700;
  line-height: 1;
  letter-spacing: var(--tracking-tight);
  font-variant-numeric: tabular-nums;
  color: var(--text-primary);
}

.metric__label {
  font-size: var(--text-sm);
  font-weight: 500;
  color: var(--text-secondary);
  text-transform: uppercase;
  letter-spacing: var(--tracking-wider);
}

.metric__change {
  display: inline-flex;
  align-items: center;
  gap: var(--space-1);
  font-size: var(--text-sm);
  font-weight: 600;
  padding: var(--space-1) var(--space-2);
  border-radius: var(--radius-sm);
}

.metric__change--positive {
  color: var(--green-11);
  background: var(--green-3);
}

.metric__change--negative {
  color: var(--red-11);
  background: var(--red-3);
}

/* Animated Counter */
@property --num {
  syntax: "<integer>";
  initial-value: 0;
  inherits: false;
}

.counter {
  animation: counter 2s var(--ease-smooth);
  counter-reset: num var(--num);
}

.counter::after {
  content: counter(num);
}

@keyframes counter {
  from { --num: 0; }
  to { --num: var(--target); }
}

/* Table Styles */
.data-table {
  width: 100%;
  border-collapse: separate;
  border-spacing: 0;
  font-variant-numeric: tabular-nums;
}

.data-table thead {
  border-bottom: 1px solid var(--border-default);
}

.data-table th {
  text-align: left;
  padding: var(--space-3) var(--space-4);
  font-size: var(--text-sm);
  font-weight: 600;
  color: var(--text-secondary);
  text-transform: uppercase;
  letter-spacing: var(--tracking-wider);
}

.data-table td {
  padding: var(--space-4);
  border-bottom: 1px solid var(--border-subtle);
  font-size: var(--text-base);
  color: var(--text-primary);
}

.data-table tbody tr {
  transition: background var(--duration-fast) var(--ease-smooth);
}

.data-table tbody tr:hover {
  background: var(--bg-hover);
}
```

### Chart.js Configuration

```javascript
// Premium Chart.js Configuration
const chartConfig = {
  options: {
    responsive: true,
    maintainAspectRatio: false,
    plugins: {
      legend: {
        display: true,
        position: 'bottom',
        labels: {
          font: {
            family: 'Inter',
            size: 13,
            weight: 500
          },
          color: '#646464',
          padding: 16,
          usePointStyle: true,
          pointStyle: 'circle'
        }
      },
      tooltip: {
        backgroundColor: 'rgba(0, 0, 0, 0.9)',
        titleFont: {
          family: 'Inter',
          size: 13,
          weight: 600
        },
        bodyFont: {
          family: 'Inter',
          size: 13,
          weight: 400
        },
        padding: 12,
        cornerRadius: 8,
        displayColors: false,
        callbacks: {
          label: function(context) {
            return context.parsed.y.toLocaleString();
          }
        }
      }
    },
    scales: {
      x: {
        grid: {
          display: false
        },
        ticks: {
          font: {
            family: 'Inter',
            size: 12
          },
          color: '#8d8d8d'
        }
      },
      y: {
        grid: {
          color: 'rgba(0, 0, 0, 0.06)',
          drawBorder: false
        },
        ticks: {
          font: {
            family: 'Inter',
            size: 12
          },
          color: '#8d8d8d',
          padding: 8
        }
      }
    },
    animation: {
      duration: 800,
      easing: 'easeInOutQuart'
    }
  }
};
```

---

## 6. Visual Rhythm & Pacing

### What Top Companies Do

**Apple Keynotes**:
- Dramatic full-screen visuals
- Text-only "pause" slides
- 3-slide bursts for features
- White space as a beat

**Vercel Conf**:
- Hero → Problem → Solution rhythm
- Data slides with minimal text
- Code demo breaks
- Summary cards

### Pattern Library

```css
/* ========== SLIDE TYPES FOR RHYTHM ========== */

/* Beat Slide - Pause Moment */
.slide-beat {
  display: flex;
  align-items: center;
  justify-content: center;
  background: var(--bg-base);
  padding: var(--space-16);
}

.slide-beat h2 {
  font-size: var(--text-5xl);
  font-weight: 700;
  text-align: center;
  color: var(--text-primary);
  max-width: 20ch;
}

/* Impact Slide - Big Number */
.slide-impact {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: var(--space-4);
  background: var(--red-9);
  color: white;
}

.slide-impact__number {
  font-size: clamp(4rem, 15vw, 12rem);
  font-weight: 800;
  line-height: 1;
  letter-spacing: var(--tracking-tighter);
}

.slide-impact__label {
  font-size: var(--text-2xl);
  font-weight: 400;
  color: rgba(255, 255, 255, 0.9);
}

/* Quote Slide */
.slide-quote {
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: var(--space-20);
  background: var(--bg-subtle);
}

.slide-quote blockquote {
  font-size: var(--text-3xl);
  font-weight: 400;
  line-height: var(--leading-relaxed);
  color: var(--text-primary);
  border-left: 4px solid var(--red-9);
  padding-left: var(--space-8);
  margin: 0;
}

.slide-quote__citation {
  margin-top: var(--space-6);
  font-size: var(--text-base);
  color: var(--text-tertiary);
}

/* Section Break */
.slide-section-break {
  display: flex;
  align-items: center;
  justify-content: center;
  background: linear-gradient(135deg, var(--gray-12), var(--gray-11));
  color: white;
}

.slide-section-break h2 {
  font-size: var(--text-6xl);
  font-weight: 800;
  text-transform: uppercase;
  letter-spacing: var(--tracking-wide);
}
```

### Suggested Rhythm Pattern

```
1. Hero (Impact) - 5sec
2. Problem (Content) - 20sec
3. Data (Visual) - 15sec
4. Beat (Pause) - 3sec "This is the moment"
5. Solution (Split) - 30sec
6. Features (Grid) - 20sec
7. Impact (Number) - 10sec "+32% conversion"
8. Quote (Testimonial) - 15sec
9. Demo (Visual) - 45sec
10. Beat (Pause) - 3sec "Simple"
11. Pricing (Table) - 20sec
12. CTA (Hero) - 10sec
```

---

## 7. Brand Sophistication

### What Top Companies Do

**Stripe**:
- Gradient overlays on images
- Subtle brand color in unexpected places (borders, accents)
- Black & white with color pops
- Minimalist logo usage

**Linear**:
- Monochrome base + single accent
- Logo as a pattern/texture
- Branded micro-animations

### Implementation Patterns

```css
/* ========== BRAND ELEMENTS ========== */

/* Subtle Brand Gradient Background */
.brand-gradient-subtle {
  position: relative;
}

.brand-gradient-subtle::before {
  content: '';
  position: absolute;
  inset: 0;
  background: 
    radial-gradient(circle at 15% 80%, var(--brand-alpha-subtle) 0%, transparent 40%),
    radial-gradient(circle at 85% 20%, rgba(1, 136, 73, 0.04) 0%, transparent 40%);
  pointer-events: none;
}

/* Brand Accent Line */
.brand-accent-line {
  position: relative;
  padding-left: var(--space-8);
}

.brand-accent-line::before {
  content: '';
  position: absolute;
  left: 0;
  top: 0;
  bottom: 0;
  width: 3px;
  background: linear-gradient(180deg, var(--red-9), var(--green-9));
  border-radius: 2px;
}

/* Watermark Logo */
.brand-watermark {
  position: fixed;
  bottom: var(--space-8);
  right: var(--space-8);
  opacity: 0.1;
  font-size: var(--text-6xl);
  font-weight: 800;
  letter-spacing: var(--tracking-widest);
  color: var(--gray-12);
  pointer-events: none;
  transform: rotate(-3deg);
}

/* Branded Focus Ring */
*:focus-visible {
  outline: 2px solid var(--red-9);
  outline-offset: 2px;
  border-radius: var(--radius-sm);
}

/* Selection Color */
::selection {
  background: var(--red-9);
  color: white;
}

/* Branded Scrollbar */
::-webkit-scrollbar {
  width: 8px;
  height: 8px;
}

::-webkit-scrollbar-track {
  background: var(--bg-subtle);
}

::-webkit-scrollbar-thumb {
  background: var(--gray-7);
  border-radius: 4px;
}

::-webkit-scrollbar-thumb:hover {
  background: var(--red-9);
}
```

---

## 8. Putting It All Together: Premium Slide Example

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Premium ASOS Presentation</title>
  <link rel="stylesheet" href="reveal.css">
  <link rel="stylesheet" href="premium-patterns.css">
  
  <style>
    /* Import Inter font */
    @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap');
    
    :root {
      --font-body: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    }
    
    body {
      font-family: var(--font-body);
      font-feature-settings: "kern" 1, "liga" 1;
    }
  </style>
</head>
<body>
  <div class="reveal">
    <div class="slides">
      
      <!-- Hero Slide -->
      <section class="slide-hero brand-gradient-subtle">
        <div style="max-width: 60%;">
          <span class="text-label" style="color: var(--red-9); display: block; margin-bottom: var(--space-4);">
            Product Innovation • Q4 2025
          </span>
          <h1 class="text-display" style="margin-bottom: var(--space-6);">
            Size Intelligence<br>
            <span style="background: linear-gradient(135deg, var(--red-9), var(--green-9)); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;">
              That Actually Works
            </span>
          </h1>
          <p class="text-body-lg" style="color: var(--text-secondary); max-width: 50ch;">
            How machine learning reduced returns by 28% and increased customer satisfaction to 4.8/5
          </p>
        </div>
      </section>
      
      <!-- Problem Slide -->
      <section class="slide-content">
        <span class="text-label" style="color: var(--red-9);">The Problem</span>
        <h2 class="text-headline" style="margin: var(--space-4) 0 var(--space-8);">
          Returns cost us £127M annually
        </h2>
        
        <div class="card-interactive" style="margin-bottom: var(--space-6);">
          <div class="metric">
            <div class="metric__value" style="color: var(--red-9);">34%</div>
            <div class="metric__label">Average Return Rate</div>
            <div class="metric__change metric__change--negative">
              ↑ +2.3% vs last year
            </div>
          </div>
        </div>
        
        <div class="brand-accent-line">
          <p class="text-body" style="margin-bottom: var(--space-3);">
            <strong>Primary reason:</strong> Size uncertainty
          </p>
          <p class="text-body" style="color: var(--text-secondary);">
            Customers order multiple sizes, return 2 out of 3 items
          </p>
        </div>
      </section>
      
      <!-- Impact Slide -->
      <section class="slide-impact">
        <div class="slide-impact__number">28%</div>
        <div class="slide-impact__label">Reduction in returns</div>
        <div style="height: var(--space-8);"></div>
        <div class="text-body" style="opacity: 0.9;">
          After implementing ML-powered size recommendations
        </div>
      </section>
      
      <!-- Data Visualization -->
      <section class="slide-content">
        <h2 class="text-headline" style="margin-bottom: var(--space-8);">
          Performance Metrics
        </h2>
        
        <div style="display: grid; grid-template-columns: repeat(3, 1fr); gap: var(--space-6);">
          <div class="metric">
            <div class="metric__value">4.8</div>
            <div class="metric__label">Satisfaction Score</div>
            <div class="metric__change metric__change--positive">
              ↑ +0.6
            </div>
          </div>
          
          <div class="metric">
            <div class="metric__value">92%</div>
            <div class="metric__label">Accuracy Rate</div>
            <div class="metric__change metric__change--positive">
              ↑ +18%
            </div>
          </div>
          
          <div class="metric">
            <div class="metric__value">2.1M</div>
            <div class="metric__label">Active Users</div>
            <div class="metric__change metric__change--positive">
              ↑ +430K
            </div>
          </div>
        </div>
        
        <div class="spacer-lg"></div>
        
        <div class="chart-wrapper">
          <div class="chart-title">Return Rate Trend</div>
          <canvas id="returnChart" style="height: 300px;"></canvas>
        </div>
      </section>
      
    </div>
  </div>
  
  <script src="reveal.js"></script>
  <script>
    Reveal.initialize({
      hash: true,
      transition: 'fade',
      transitionSpeed: 'fast'
    });
  </script>
</body>
</html>
```

---

## Quick Wins You Can Implement Today

### 1. Typography
- Switch to Inter font
- Add clamp() for responsive sizing
- Implement tracking adjustments
- Add optical size variations

### 2. Colors
- Create 11-step gray scale
- Add alpha variants for overlays
- Use semantic color mapping
- Implement dark mode properly

### 3. Layout
- Try 60/40 splits instead of 50/50
- Add intentional whitespace (spacers)
- Float elements for visual interest
- Use max-width constraints (72ch for text)

### 4. Interactions
- Add subtle hover lift (2-4px)
- Implement focus-visible styles
- Add ripple effects on buttons
- Create loading skeletons

### 5. Polish
- Add gradient borders on cards
- Implement smooth transitions (200-300ms)
- Use tabular numbers for metrics
- Add subtle brand gradients in backgrounds

---

## Resources

### Fonts
- Inter: https://rsms.me/inter/
- Cal Sans: https://github.com/calcom/font
- JetBrains Mono: https://www.jetbrains.com/lp/mono/

### Color Tools
- Radix Colors: https://www.radix-ui.com/colors
- Color Box: https://colorbox.io
- Contrast Checker: https://webaim.org/resources/contrastchecker/

### Inspiration
- Stripe Press: https://press.stripe.com
- Linear Blog: https://linear.app/blog
- Vercel Design: https://vercel.com/design
- Apple Events: https://www.apple.com/apple-events/

### Tools
- Reveal.js: https://revealjs.com
- Chart.js: https://www.chartjs.org
- Animate.css: https://animate.style

---

## Next Steps

1. **Audit your current presentation** - Identify template-like patterns
2. **Implement new type scale** - Start with clamp() and tracking
3. **Refine color system** - Add alpha variants and semantic mapping
4. **Add microinteractions** - Focus on hover states first
5. **Test rhythm and pacing** - Vary slide types intentionally
6. **Polish one slide perfectly** - Use as template for others

The difference between "good" and "premium" is in the **details** - tracking, alpha channels, subtle hover states, intentional whitespace, and thoughtful transitions.
