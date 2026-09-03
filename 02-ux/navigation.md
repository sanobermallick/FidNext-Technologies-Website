# FidNext Technologies — Navigation Architecture

## Agent

**Agent 02 — UX & Information Architecture**

---

# 1. Purpose

This document defines the navigation architecture for the FidNext Technologies website.

It establishes:

* Primary navigation
* Secondary navigation
* Desktop navigation
* Mobile navigation
* Service navigation
* CTA hierarchy
* Dropdown behavior
* Footer navigation
* Breadcrumb requirements
* Internal linking principles
* Accessibility requirements
* Responsive navigation behavior

This document uses the following artifacts as its source of truth:

```text
01-business-discovery/business-brief.md
02-ux/sitemap.md
02-ux/page-architecture.md
```

---

# 2. Navigation Objectives

The navigation should help visitors:

1. Understand what FidNext does.
2. Quickly find relevant services.
3. Understand how FidNext works.
4. Explore technology capabilities.
5. Learn about the company.
6. Review verified work and insights where available.
7. Start a conversation easily.

The navigation must support the primary conversion objective:

> Book a Free Consultation

---

# 3. Navigation Principles

## 3.1 Keep Navigation Simple

The website should avoid unnecessary navigation items.

The visitor should not need to understand FidNext's internal organization to find information.

---

## 3.2 Organize Around Visitor Intent

Navigation should primarily reflect what visitors want to know:

* What can FidNext help me with?
* How does FidNext work?
* Does FidNext have relevant technology expertise?
* Who is FidNext?
* Can I trust FidNext?
* How do I contact FidNext?

---

## 3.3 Prioritize Services

Services are one of the most important discovery paths and should be easily accessible from the primary navigation.

---

## 3.4 Maintain One Primary CTA

The main navigation should contain one visually prominent conversion action:

**Book a Free Consultation**

---

## 3.5 Avoid Deep Navigation

Navigation depth should generally remain within:

```text
Primary Navigation
      ↓
Page
      ↓
Optional Detail Page
```

Avoid unnecessary multi-level menus.

---

# 4. Recommended Desktop Header

The recommended desktop header is:

```text
┌──────────────────────────────────────────────────────────────────────┐
│ FidNext Logo                                                        │
│                                                                      │
│ Services   How We Work   Technology   About   Our Work*   Insights* │
│                                                                      │
│                         [ Book a Free Consultation ]                │
└──────────────────────────────────────────────────────────────────────┘
```

`*` = Include only when validated content is available.

---

# 5. Primary Navigation Items

The initial primary navigation should contain:

1. Services
2. How We Work
3. Technology
4. About
5. Our Work*
6. Insights*

The primary CTA should be:

**Book a Free Consultation**

---

# 6. Services Navigation

Services should use a dropdown or mega-menu only if necessary.

For Version 1, a simple dropdown is recommended.

## Proposed Structure

```text
Services
│
├── Software Consulting
├── Custom Software Development
├── AI Solutions*
├── Product Design & UX*
├── Application Modernization*
├── Cloud & DevOps*
└── Technology Team Augmentation*
```

---

# 7. Services Dropdown Behavior

## Desktop

When the visitor interacts with **Services**, the menu should provide access to the service overview and individual service pages.

Recommended structure:

```text
Services

View All Services

Software Consulting
Strategic technology guidance

Custom Software Development
Build software around your business

AI Solutions*
Practical AI opportunities

Product Design & UX*
User-centered digital products

Application Modernization*
Modernize existing systems

Cloud & DevOps*
Cloud and delivery capabilities

Team Augmentation*
Extend technology capacity
```

Descriptions should only be used where they improve clarity.

---

## Mobile

Services should become an expandable navigation group.

Example:

```text
Services
   >
```

On interaction:

```text
Services
   ↓
Software Consulting
Custom Software Development
AI Solutions*
Product Design & UX*
Application Modernization*
Cloud & DevOps*
Team Augmentation*
```

---

# 8. Services Validation Rule

Only confirmed services should be presented as active FidNext offerings.

Proposed services must remain excluded from final navigation until validated.

This prevents navigation itself from becoming a source of unsupported business claims.

---

# 9. How We Work Navigation

Primary navigation item:

**How We Work**

Destination:

```text
/how-we-work
```

Purpose:

Help visitors understand the engagement and delivery approach.

The page should communicate the validated methodology and collaboration model.

---

# 10. Technology Navigation

Primary navigation item:

**Technology**

Destination:

```text
/technology
```

Purpose:

Demonstrate relevant technical expertise.

Known technology references include:

* Web Development
* Android
* iOS
* Cloud Applications
* Java
* React Native
* Python

The navigation should not create individual technology pages unless there is sufficient strategic and SEO justification.

---

# 11. About Navigation

Primary navigation item:

**About**

Destination:

```text
/about
```

Purpose:

Provide access to:

* Company story
* Mission
* Vision
* Values
* Leadership
* Working philosophy

---

# 12. Our Work Navigation

Primary navigation item:

**Our Work**

Destination:

```text
/case-studies
```

## Status

**Proposed — Requires verified case study content.**

If FidNext does not have approved case studies at launch, this navigation item should be removed until sufficient evidence is available.

Alternative wording:

* Case Studies
* Our Work
* Success Stories

Final wording should be determined during Content Strategy.

---

# 13. Insights Navigation

Primary navigation item:

**Insights**

Destination:

```text
/insights
```

## Status

**Proposed — Requires content availability.**

If the website does not launch with meaningful content, this navigation item should not appear in the primary navigation.

---

# 14. Primary CTA

## CTA Text

Recommended:

**Book a Free Consultation**

## Destination

```text
/book-consultation
```

## Placement

The CTA should appear in:

* Desktop header
* Mobile navigation
* Home hero
* Relevant service sections
* Major page endings
* Footer

---

# 15. CTA Hierarchy

The navigation and page experience should follow this hierarchy:

```text
PRIMARY
Book a Free Consultation

        ↓

SECONDARY
View Our Work
Explore Case Studies
Discuss Your Project

        ↓

TERTIARY
Read Insights
Learn More
Explore Technology
```

The visual treatment should clearly distinguish the primary conversion action.

---

# 16. Mobile Header

The mobile header should prioritize:

```text
┌──────────────────────────────────┐
│ FidNext Logo              Menu   │
└──────────────────────────────────┘
```

When opened:

```text
Services
How We Work
Technology
About
Our Work*
Insights*

────────────────────────

[ Book a Free Consultation ]
```

---

# 17. Mobile Menu Behavior

The mobile menu should:

* Open without navigating away from the current page.
* Clearly indicate expandable sections.
* Support touch interaction.
* Provide sufficient tap target size.
* Keep navigation labels readable.
* Avoid excessive nesting.
* Keep the primary CTA prominent.
* Allow the visitor to close the menu easily.

---

# 18. Mobile Services Expansion

The Services item should expand progressively.

Initial state:

```text
Services >
```

Expanded state:

```text
Services

Software Consulting
Custom Software Development
AI Solutions*
Product Design & UX*
Application Modernization*
Cloud & DevOps*
Team Augmentation*
```

The visitor should be able to return to the main menu without losing context.

---

# 19. Sticky Header

A sticky header may be used on desktop and mobile if it improves navigation and conversion.

If implemented, it should:

* Remain visually lightweight.
* Not consume excessive screen space.
* Maintain the primary CTA.
* Avoid covering page content.
* Work correctly with keyboard navigation.
* Behave appropriately on mobile.

Sticky behavior should not negatively affect performance or accessibility.

---

# 20. Breadcrumb Navigation

Breadcrumbs are recommended for deeper pages such as:

* Individual service pages
* Case studies
* Insight articles

Example:

```text
Home
  /
Services
  /
Custom Software Development
```

Breadcrumbs should not be necessary on the homepage or simple top-level pages.

---

# 21. Footer Navigation

The footer should provide a secondary navigation system.

Recommended structure:

```text
FidNext Technologies
────────────────────────────────────

Company
• About
• How We Work
• Contact

Services
• Software Consulting
• Custom Software Development
• AI Solutions*
• Product Design & UX*
• Application Modernization*
• Cloud & DevOps*
• Team Augmentation*

Resources
• Case Studies*
• Insights*

Technology
• Technology

Connect
• Verified contact information
• Verified social links

────────────────────────────────────

[ Book a Free Consultation ]
```

---

# 22. Footer Rules

The footer should:

* Provide useful secondary navigation.
* Repeat important conversion paths.
* Provide verified contact information.
* Avoid excessive link lists.
* Include legal links where required.
* Maintain consistent branding.

Legal links may include, where applicable:

* Privacy Policy
* Terms of Use
* Cookie Policy

These pages should only be added when required and when their content is available.

---

# 23. Internal Linking Strategy

Navigation should be supported by contextual internal links.

Examples:

### Home → Services

```text
Home
  ↓
Services
```

### Services → Consultation

```text
Service Page
  ↓
Book a Free Consultation
```

### Technology → Services

```text
Technology
  ↓
Relevant Service
```

### Case Study → Service

```text
Case Study
  ↓
Related Capability
```

### Insights → Service

```text
Insight
  ↓
Relevant Service
```

Internal linking should help users continue their journey naturally.

---

# 24. Navigation and Conversion Relationship

Navigation should support the visitor journey:

```text
Discover
   ↓
Understand
   ↓
Evaluate
   ↓
Trust
   ↓
Convert
```

Example:

```text
Home
 ↓
Services
 ↓
How We Work
 ↓
Our Work
 ↓
Book a Free Consultation
```

The visitor should never need to return repeatedly to the homepage to navigate between important areas.

---

# 25. Navigation by User Intent

## Visitor Wants to Understand FidNext

Recommended path:

```text
Home → About → How We Work
```

---

## Visitor Wants a Technology Partner

Recommended path:

```text
Home → Services → Technology → How We Work
```

---

## Visitor Has a Software Project

Recommended path:

```text
Home → Custom Software Development → Our Work → Consultation
```

---

## Visitor Has a Technology Strategy Problem

Recommended path:

```text
Home → Software Consulting → How We Work → Consultation
```

---

## Visitor Wants to Explore AI

Recommended path:

```text
Home → AI Solutions* → Technology → Consultation
```

This path becomes active only after AI capability is validated.

---

# 26. Active Navigation States

The navigation should clearly indicate the visitor's current location.

Examples:

```text
Home
Services ← active
How We Work
Technology
About
```

The active state should be distinguishable through more than color alone where appropriate.

---

# 27. Accessibility Requirements

Navigation must support:

* Keyboard navigation
* Visible focus states
* Screen readers
* Semantic navigation landmarks
* Accessible dropdown controls
* Appropriate ARIA attributes where needed
* Logical tab order
* Clear link labels
* Adequate touch target sizes
* Sufficient contrast

Dropdown menus should not rely exclusively on hover.

---

# 28. Responsive Navigation

## Desktop

Use full navigation with visible primary CTA.

## Tablet

Reduce spacing while maintaining the primary navigation hierarchy.

If necessary, transition to a compact menu earlier than desktop.

## Mobile

Use a menu button and expandable navigation groups.

The primary CTA should remain easy to access.

---

# 29. Navigation Performance

Navigation should remain lightweight.

Avoid:

* Large menu images
* Heavy animations
* Unnecessary JavaScript
* Large navigation assets
* Delayed interaction
* Excessive dropdown effects

The navigation should become interactive quickly.

---

# 30. Navigation Content Rules

Navigation labels should be:

* Short
* Clear
* Familiar
* Consistent
* Action-oriented where appropriate

Avoid vague labels such as:

* Solutions
* Excellence
* Innovation
* What We Do

unless their meaning is immediately clear from context.

Preferred labels include:

* Services
* How We Work
* Technology
* About
* Our Work
* Insights
* Contact

---

# 31. Version 1 Navigation Recommendation

For the initial FidNext website, the recommended navigation is:

```text
┌─────────────────────────────────────────────────────────────┐
│ FidNext                                                      │
│                                                             │
│ Services | How We Work | Technology | About | Contact       │
│                                                             │
│                 [ Book a Free Consultation ]               │
└─────────────────────────────────────────────────────────────┘
```

Optional items:

```text
Our Work*
Insights*
```

should only be added when validated content is available.

---

# 32. Recommended Final Version 1 Navigation

The preferred Version 1 structure is:

```text
Services
How We Work
Technology
About
Contact

[ Book a Free Consultation ]
```

This structure is intentionally compact.

It keeps the visitor focused on:

```text
What we do
      ↓
How we work
      ↓
Our expertise
      ↓
Who we are
      ↓
Start a conversation
```

---

# 33. Navigation Decision Rules

### Rule 1 — Navigation Is Not a Content Dump

Only important destinations should appear in primary navigation.

### Rule 2 — Primary CTA Must Stand Out

The consultation CTA should remain visually distinct.

### Rule 3 — Proposed Pages Must Be Validated

Unvalidated pages should not appear in the final navigation.

### Rule 4 — Do Not Create Artificial Depth

Avoid unnecessary dropdown layers.

### Rule 5 — Mobile Must Be Equivalent

Mobile visitors must have access to the same important destinations.

### Rule 6 — Accessibility Is Required

Navigation must be usable without relying on mouse hover or visual cues alone.

### Rule 7 — Performance Matters

Navigation interactions must remain fast and lightweight.

---

# 34. Handoff to User Flows

## Completed Agent 02 Artifacts

```text
02-ux/
├── sitemap.md
├── page-architecture.md
└── navigation.md
```

## Next Artifact

```text
02-ux/
└── user-flows.md
```

The User Flows artifact should define:

* Primary visitor journey
* Consultation conversion journey
* Service discovery flows
* Case study exploration flow
* Technology exploration flow
* Contact flow
* Mobile conversion flow
* Error / recovery considerations
* CTA transitions
* Entry and exit points

The User Flows artifact must use the sitemap, page architecture, and navigation architecture as its source of truth.
