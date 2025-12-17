# User Story Template

Use this template when creating user stories in Azure DevOps via MCP.

---

## Title Format
`[User Story]: [Brief Description]`

Example: `[User Story]: Size recommendation on product pages`

---

## Description

```
As a [persona]
I want to [action]
So that [benefit]
```

Example:
```
As a Sophie (fashion-forward shopper)
I want to see recommended sizes based on my past purchases
So that I can order confidently without trying multiple sizes
```

---

## Acceptance Criteria

**Given** [context]  
**When** [action]  
**Then** [expected outcome]

Example:
```
AC1: Display size recommendation
Given: User is on PDP and has purchase history
When: User views size selector
Then: See "Your usual size" badge on recommended size

AC2: Recommendation accuracy
Given: User has ordered same brand before
When: Recommendation is shown
Then: Match their most common size in that brand (>80% accuracy)

AC3: Handle no data
Given: New customer with no history
When: Viewing size selector
Then: Show size guide link instead of recommendation
```

---

## Priority
- P0: Must Have (blocker for release)
- P1: Should Have (important but not blocker)
- P2: Could Have (nice to have)
- P3: Won't Have (deferred)

---

## Story Points
Use Fibonacci: 1, 2, 3, 5, 8, 13, 21

**Guideline:**
- 1-2: Simple, clear, low risk (< 1 day)
- 3-5: Moderate complexity (1-3 days)
- 8-13: Complex, unclear, risky (3-5 days)
- 21+: Epic, needs breakdown

---

## Tags
Use lowercase, hyphen-separated:
- Feature area: `checkout`, `pdp`, `search`, `basket`
- Theme: `personalization`, `conversion`, `performance`
- Customer segment: `new-customer`, `loyal-customer`

Example: `["pdp", "personalization", "conversion"]`

---

## Links
- **Parent**: Link to Epic
- **Related**: Link to PRD (Confluence)
- **Depends On**: Link to prerequisite stories
- **Blocks**: Link to dependent stories

---

## Definition of Done
- [ ] Code complete and peer reviewed
- [ ] Unit tests written (>80% coverage)
- [ ] QA test cases created and passed
- [ ] Acceptance criteria validated
- [ ] Documentation updated
- [ ] Deployed to staging
- [ ] PM sign-off obtained

---

## Example Complete User Story

**ID:** #4567  
**Title:** [User Story]: Size recommendation on PDP  
**Type:** User Story  
**Priority:** P0  
**Points:** 5  
**Sprint:** Sprint 23  
**Tags:** `pdp`, `personalization`, `conversion`

**Description:**
```
As a Sophie (fashion-forward shopper)
I want to see recommended sizes based on my past purchases
So that I can order confidently without trying multiple sizes
```

**Acceptance Criteria:**
```
AC1: Display size recommendation
Given: User is logged in on PDP with purchase history
When: User views size selector
Then: See "Your usual size" badge on recommended size

AC2: Recommendation algorithm
Given: User has ordered same brand 3+ times
When: Recommendation is calculated
Then: Match their most common size in that brand

AC3: Fallback for new customers
Given: New customer with no history
When: Viewing size selector
Then: Show size guide link instead of recommendation

AC4: Mobile responsive
Given: User on mobile device
When: Viewing size recommendation
Then: Badge displays correctly without breaking layout
```

**Technical Notes:**
- Use existing order history API
- Implement client-side caching (1 hour TTL)
- A/B test at 10% traffic initially

**Links:**
- Parent: Epic #4500 - Personalization V2
- Related: Confluence PRD (link)
- Depends On: #4555 - Order history API enhancement

**Comments:**
- Engineering: "Estimated 3 days dev + 1 day testing"
- Design: "Mockups ready in Figma (link)"
- PM: "Priority for Q4 conversion goals"
