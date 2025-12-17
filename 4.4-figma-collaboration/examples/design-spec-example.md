# Example: Design Specification Document

**Generated from Figma using MCP integration**

---

## Feature: Personalised Onboarding - Style Quiz

**Design File:** ASOS Mobile App - Onboarding Redesign  
**Last Updated:** January 2025  
**Designer:** UX Design Team  

---

## Screen: Style Quiz - Brand Selection

### Component Overview

**Screen Name:** `quiz/brand-selection`  
**Frame Size:** 390 x 844px (iPhone 14)  
**Status:** Ready for development  

---

### Typography Specifications

| Element | Font | Size | Weight | Line Height | Color |
|---------|------|------|--------|-------------|-------|
| Title | ASOS Sans | 24px | Bold (700) | 32px | #2D2D2D |
| Subtitle | ASOS Sans | 16px | Regular (400) | 24px | #666666 |
| Brand Label | ASOS Sans | 12px | Medium (500) | 16px | #2D2D2D |
| Skip Link | ASOS Sans | 14px | Medium (500) | 20px | #0770CF |

---

### Color Palette

| Usage | Color | Hex | RGB |
|-------|-------|-----|-----|
| Primary Background | White | #FFFFFF | 255, 255, 255 |
| Selected State | ASOS Teal | #018849 | 1, 136, 73 |
| Unselected Border | Light Grey | #E8E8E8 | 232, 232, 232 |
| Selected Border | ASOS Teal | #018849 | 1, 136, 73 |
| Text Primary | Charcoal | #2D2D2D | 45, 45, 45 |
| Text Secondary | Grey | #666666 | 102, 102, 102 |

---

### Component: Brand Tile

**Structure:**
- Container: 112 x 112px
- Border Radius: 8px
- Border: 1px solid #E8E8E8 (unselected) / 2px solid #018849 (selected)
- Background: #FFFFFF
- Brand Logo: 80 x 40px (centered)
- Brand Name: 12px, centered below logo
- Selection Checkmark: 20x20px, top-right corner (selected state only)

**States:**
| State | Border | Background | Checkmark |
|-------|--------|------------|-----------|
| Default | 1px #E8E8E8 | #FFFFFF | Hidden |
| Hover | 1px #CCCCCC | #FAFAFA | Hidden |
| Selected | 2px #018849 | #F0FBF6 | Visible |
| Disabled | 1px #E8E8E8 | #F5F5F5 | Hidden |

**Animation:**
- Selection: Scale 1.0 → 1.02 → 1.0 (100ms ease-out)
- Checkmark: Fade in with slight bounce (150ms)

---

### Component: Progress Indicator

**Structure:**
- Container width: 100% - 48px padding
- Height: 4px
- Background: #E8E8E8
- Progress fill: #018849
- Border radius: 2px

**Behaviour:**
- Current step: "Step 1 of 5" - 20% filled
- Animation: Width transition 300ms ease-in-out

---

### Component: CTA Button

**Primary Continue Button:**
- Width: 100% - 48px padding
- Height: 52px
- Background: #2D2D2D
- Text: "Continue" - 16px, Bold, #FFFFFF
- Border radius: 4px
- Position: Fixed bottom, 24px from safe area

**States:**
| State | Background | Text |
|-------|------------|------|
| Default | #2D2D2D | #FFFFFF |
| Hover | #1A1A1A | #FFFFFF |
| Disabled | #CCCCCC | #FFFFFF |
| Loading | #2D2D2D | Spinner |

**Disabled condition:** Fewer than 3 brands selected

---

### Layout Specifications

```
┌─────────────────────────────────────┐
│ ← Back                    Skip →    │ 44px header
├─────────────────────────────────────┤
│ Step 1 of 5    ████░░░░░░░░░░░░░░░ │ 32px progress
├─────────────────────────────────────┤
│                                     │
│     Which brands speak to you?      │ 24px title
│     Pick 3-5 that match your vibe   │ 16px subtitle
│                                     │
│  ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐   │
│  │Nike │ │Adidas│ │ CK  │ │Levi's│  │ Brand grid
│  └─────┘ └─────┘ └─────┘ └─────┘   │ 3 columns
│  ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐   │ 16px gap
│  │Puma │ │Tommy │ │Guess│ │ Gap │   │
│  └─────┘ └─────┘ └─────┘ └─────┘   │
│         ... more rows ...           │
│                                     │
├─────────────────────────────────────┤
│        [ Continue (3/5) ]           │ 52px CTA
│                                     │ 24px safe area
└─────────────────────────────────────┘
```

---

### Spacing System

| Element | Spacing |
|---------|---------|
| Screen padding (horizontal) | 24px |
| Header to progress | 16px |
| Progress to title | 24px |
| Title to subtitle | 8px |
| Subtitle to grid | 32px |
| Grid gap | 16px |
| Grid to CTA | 24px |
| CTA to safe area | 24px |

---

### Interaction Notes

1. **Brand selection:** Users can select 3-5 brands; Continue button disabled until minimum reached
2. **Scroll behaviour:** Grid scrolls; header and CTA remain fixed
3. **Skip flow:** Takes user to generic homepage with reminder prompt
4. **Back navigation:** Returns to previous screen with state preserved
5. **Haptic feedback:** Light impact on brand selection (iOS)

---

### Accessibility Requirements

- All brand logos have alt text
- Selected state announced by screen reader
- Minimum touch target: 44x44px
- Color contrast: WCAG AA compliant
- Focus indicators visible for keyboard navigation

---

### Asset Export List

| Asset | Format | Sizes |
|-------|--------|-------|
| Brand logos | SVG | 1x |
| Checkmark icon | SVG | 24x24 |
| Spinner animation | Lottie | 24x24 |
| Back arrow | SVG | 24x24 |

---

*Specifications extracted from Figma using MCP integration - January 2025*
