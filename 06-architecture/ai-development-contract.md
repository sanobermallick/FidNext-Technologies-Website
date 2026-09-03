---

Artifact: AI Development Contract
Producing Agent: 06 - Frontend Architect
Project: FidNext Technologies Website
Status: REVIEW_PENDING
Last Updated: 2026-09-03
------------------------

# AI DEVELOPMENT CONTRACT

## 1. Purpose

This document defines the implementation contract for AI coding agents working on the FidNext Technologies website.

The purpose is to ensure that Agent 07 implements the approved architecture rather than independently redesigning, restructuring, or redefining the website.

---

## 2. Source-of-Truth Hierarchy

AI coding agents must respect the following order:

```text
Approved Client Inputs
        ↓
01 Business Discovery
        ↓
02 UX / Information Architecture
        ↓
03 Content Strategy
        ↓
04 UI/UX Design
        ↓
05 Design System
        ↓
06 Frontend Architecture
        ↓
07 Development
```

If a lower-stage instruction conflicts with an approved higher-stage decision, the conflict must be identified rather than silently resolved.

---

## 3. Approved Source Files

Agent 07 must inspect and use:

```text
01-business-discovery/business-brief.md

02-ux/sitemap.md
02-ux/page-architecture.md
02-ux/navigation.md
02-ux/user-flows.md

03-content/content-strategy.md

04-design/ui-ux-design-specification.md

05-design-system/design-system.md
05-design-system/design-system.tokens.json
05-design-system/design-system.components.json

06-architecture/frontend-architecture.md
06-architecture/frontend-architecture.json
06-architecture/ai-development-contract.md
```

These files are the implementation contract.

---

## 4. Core Architecture

The frontend hierarchy is:

```text
PAGES
↓
SECTIONS
↓
COMPOUND COMPONENTS
↓
PRIMITIVES
↓
DESIGN TOKENS
```

Do not bypass this structure without an approved architectural reason.

---

## 5. Technology Contract

The initial stack is:

```text
React
TypeScript
Vite
React Router
CSS Modules
CSS Custom Properties
npm
```

No framework replacement is permitted without an ADR and approval.

---

## 6. Styling Contract

The implementation must use:

```text
05-design-system/design-system.tokens.json
```

as the token source of truth.

Do not invent:

* colors;
* typography;
* spacing;
* radii;
* shadows;
* breakpoints;
* animation values.

If a token is marked:

```text
REQUIRES_INPUT
```

do not silently replace it with an arbitrary value.

---

## 7. Component Reuse Contract

Before creating a component, Agent 07 must search the existing component structure.

If an existing component can satisfy the requirement, reuse it.

Do not create:

```text
PrimaryButton2
ServiceCardNew
CustomHero
SpecialCard
```

only because a page needs slightly different content.

Extend an existing component only when the extension remains conceptually consistent.

---

## 8. Page Contract

Pages are composition containers.

Pages should not become large files containing:

* duplicated UI;
* repeated styling;
* unrelated business logic;
* hard-coded navigation;
* repeated content structures.

---

## 9. Section Contract

Sections represent meaningful blocks from the approved page architecture.

Homepage sections must follow the approved journey:

```text
CLARITY
↓
TRUST
↓
PROBLEM RECOGNITION
↓
VALUE
↓
PROOF
↓
CONVERSION
```

Do not reorder major sections without approval.

---

## 10. Content Contract

Agent 07 must use approved content.

Do not invent:

```text
statistics
client names
logos
testimonials
case-study results
awards
certifications
partnerships
team-size claims
years of experience
revenue claims
customer counts
```

Placeholder content may be used during development only when clearly marked and must not accidentally reach production.

---

## 11. Route Contract

The initial routes are:

```text
/
/services
/services/software-consulting
/services/custom-software-development
/how-we-work
/technology
/about
/contact
```

A catch-all 404 route is required.

Do not create additional production routes without validation.

---

## 12. CTA Contract

The primary conversion action is:

```text
Book a Free Consultation
```

The CTA should lead to the approved consultation experience through:

```text
/contact
```

Do not invent a separate booking platform.

---

## 13. Data Contract

Content should be separated from UI logic.

Recommended structure:

```text
src/data/
```

Reusable structured content should be stored there where appropriate.

Components should receive data through typed props.

---

## 14. State Contract

No global state library is required.

Use local state for:

```text
mobile navigation
accordions
modals
forms
temporary UI state
```

Do not introduce global state merely to share static content.

---

## 15. Form Contract

The consultation form must support:

```text
semantic labels
keyboard access
client-side validation
clear error messages
submission state
success state
failure state
```

The final submission destination is not yet defined.

Do not invent:

```text
CRM
API endpoint
email provider
database
```

unless separately approved.

---

## 16. Navigation Contract

Navigation must be centrally defined.

Recommended location:

```text
src/config/navigation.ts
```

Navigation components must consume the centralized configuration.

Do not duplicate navigation arrays across pages.

---

## 17. Asset Contract

Use approved client assets.

Source assets are located in:

```text
INPUT/client-assets/
```

Frontend assets should be organized under:

```text
src/assets/
```

Do not invent or download replacement brand assets without approval.

---

## 18. Image Contract

Images must:

* preserve intended aspect ratios;
* use meaningful alt text where appropriate;
* avoid layout shifts;
* be appropriately sized;
* support responsive rendering;
* use lazy loading where appropriate.

Decorative images should use empty alt text.

Meaningful images must have meaningful alternative text.

---

## 19. Typography Contract

Typography must follow Agent 05.

If typography remains unresolved:

```text
REQUIRES_INPUT
```

do not select an arbitrary production font.

---

## 20. Responsive Contract

The implementation must support:

```text
Mobile
Tablet
Desktop
Large Desktop
```

using the approved design system guidance.

Do not create separate desktop and mobile page implementations unless structurally necessary.

---

## 21. Accessibility Contract

Every interactive component must be:

```text
keyboard accessible
focusable where appropriate
semantically structured
screen-reader understandable
```

Required considerations include:

* semantic HTML;
* labels;
* focus states;
* heading hierarchy;
* keyboard navigation;
* accessible names;
* reduced motion;
* form errors.

---

## 22. SEO Contract

Each route must have appropriate:

```text
title
meta description
canonical
Open Graph metadata
```

The implementation must preserve semantic heading hierarchy.

Do not use visual styling as a reason to misuse heading elements.

---

## 23. Performance Contract

Agent 07 must avoid unnecessary performance costs.

Priorities:

```text
small JavaScript footprint
optimized images
route-level code splitting where useful
lazy loading
efficient fonts
minimal dependencies
minimal third-party scripts
stable layout
```

Do not add libraries for functionality already supported by CSS or the browser.

---

## 24. Animation Contract

Motion must remain subtle and purposeful.

Use the approved Agent 05 motion system.

Prefer:

```text
CSS transitions
CSS keyframes
IntersectionObserver
```

Do not introduce an animation framework unless a genuine requirement justifies it.

All non-essential animation must respect:

```text
prefers-reduced-motion
```

---

## 25. Security Contract

Never commit:

```text
API keys
private credentials
database passwords
authentication secrets
```

Frontend environment variables must only contain values safe for browser exposure.

User-provided form data must be handled safely.

Internal errors must never be displayed to users.

---

## 26. Third-Party Integration Contract

No mandatory third-party integration currently exists.

Potential future integrations must be isolated behind a clear technical boundary.

Examples:

```text
analytics
CRM
email
chat
CMS
maps
```

are not automatically approved.

---

## 27. Testing Contract

Agent 07 should establish tests for important reusable behavior.

Recommended tools:

```text
Vitest
React Testing Library
Playwright
```

Tests should prioritize:

```text
critical components
navigation
forms
important interactions
responsive behavior
route rendering
```

Agent 07 performs implementation-level testing.

Formal QA remains the responsibility of Agents 08–11.

---

## 28. File Creation Contract

Before creating a new file:

1. Search for an existing implementation.
2. Determine whether reuse is possible.
3. Confirm the new file has a clear responsibility.
4. Place it in the appropriate architecture layer.
5. Avoid unnecessary abstractions.

---

## 29. Dependency Contract

Every dependency must have a clear reason.

Before adding a package, ask:

```text
Can this be implemented with React?
Can this be implemented with CSS?
Can this be implemented with a browser API?
Can an existing dependency already solve it?
```

If yes, prefer the existing solution.

---

## 30. AI Task Contract

AI coding tasks should be narrow and verifiable.

Good:

```text
Implement the global Header using the approved design system.
```

Good:

```text
Implement the homepage Hero section using the approved content.
```

Good:

```text
Implement responsive navigation behavior.
```

Avoid:

```text
Build the entire website however you think is best.
```

---

## 31. Implementation Validation Contract

Before marking implementation complete, Agent 07 must verify:

```text
TypeScript
Lint
Build
Routes
Responsive behavior
Accessibility basics
Token usage
Asset references
SEO metadata
Component reuse
```

The agent must report actual results rather than claiming success without validation.

---

## 32. Architecture Change Contract

If implementation requires an architectural change:

```text
STOP
↓
Describe the conflict
↓
Create an ADR
↓
Request approval
↓
Update architecture if approved
↓
Implement
```

Do not silently modify:

* framework;
* routing strategy;
* styling strategy;
* component hierarchy;
* token architecture;
* state architecture;
* content architecture.

---

## 33. Design Drift Prevention

Agent 07 must not introduce:

```text
random gradients
generic IT template sections
excessive glassmorphism
excessive rounded cards
random shadows
unapproved colors
unapproved typography
stock photography
unapproved animations
```

The implementation must preserve the premium, modern, trustworthy, strategic, technology-focused, human, sophisticated, conversion-focused direction established by Agents 03–05.

---

## 34. Business Integrity

The website must communicate only validated business information.

The implementation must not transform assumptions into facts.

Where content remains pending validation, the implementation must preserve that status.

---

## 35. AI Agent Handoff

Agent 07 receives:

```text
Business Discovery
+
UX / IA
+
Content Strategy
+
UI/UX Design
+
Design System
+
Frontend Architecture
+
AI Development Contract
```

Agent 07's responsibility is:

```text
ARCHITECTURE → CODE
```

not:

```text
ARCHITECTURE → REDESIGN → CODE
```

---

## 36. Completion Criteria

Agent 07 may consider its implementation phase complete only when:

* approved architecture has been implemented;
* reusable components exist;
* approved routes work;
* tokens are integrated;
* responsive behavior is implemented;
* accessibility basics are implemented;
* SEO metadata is implemented;
* forms have defined UI states;
* tests are established;
* production build succeeds;
* no unsupported business claims have been introduced.

---

## 37. Final Rule

When uncertain:

```text
DO NOT INVENT.
DO NOT REDESIGN.
DO NOT ASSUME.
CHECK THE APPROVED ARTIFACTS.
DOCUMENT THE CONFLICT.
REQUEST APPROVAL.
```

**Final Status: REVIEW_PENDING**
