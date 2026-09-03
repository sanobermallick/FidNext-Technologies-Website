```markdown
---
Artifact: Design System Specification
Producing Agent: 05 - Design System
Project: FidNext Technologies Website
Status: REVIEW_PENDING
Last Updated: 2026-09-03
---

# Design System Specification

## 1. Design System Foundation & Principles

### 1.1 Purpose

The FidNext Technologies Design System defines the reusable visual, interaction, accessibility, and implementation rules required to translate the approved UI/UX Design Specification into a consistent production-ready website.

It acts as the implementation contract between:

- UI/UX design
- Figma
- Stitch
- Google AI Studio
- Claude or other AI development agents
- Frontend development
- QA

The system must support:

- consistency
- reusability
- scalability
- responsive behavior
- accessibility
- machine readability
- developer implementation
- AI-assisted development
- design-to-code fidelity

### 1.2 Source-of-Truth Hierarchy

The design system follows this priority order:

1. Approved business requirements
2. Approved UX architecture
3. Approved content strategy
4. Approved UI/UX Design Specification
5. Design System rules
6. General design and frontend best practices

The Design System Agent must not override approved business, UX, content, or UI/UX decisions.

If a conflict exists, the conflict must be documented and sent back for validation.

### 1.3 Actual Project Sources

The current FidNext project uses the following approved artifacts:

- `01-business-discovery/business-brief.md`
- `02-ux/sitemap.md`
- `02-ux/page-architecture.md`
- `02-ux/navigation.md`
- `02-ux/user-flows.md`
- `03-content/content-strategy.md`
- `04-design/ui-ux-design-specification.md`

The consolidated Agent 04 file:

`04-design/ui-ux-design-specification.md`

is the canonical UI/UX source for Agent 05.

Several filenames referenced by the generic Agent 05 definition do not currently exist in this project, including separate design-direction, component-specification, token, responsive-specification, and interaction-specification files.

These files must not be artificially created simply to satisfy the generic agent definition.

### 1.4 Design Philosophy

The design system follows:

**CLARITY → HIERARCHY → TRUST → DIFFERENTIATION → CONVERSION**

The visual language should feel:

- premium
- modern
- trustworthy
- strategic
- technology-focused
- sophisticated
- human
- enterprise-ready
- conversion-focused

Avoid:

- generic IT-company templates
- excessive gradients
- excessive rounded cards
- random decorative blobs
- excessive glassmorphism
- crowded layouts
- unnecessary decorative UI
- stock-photo-heavy presentation

### 1.5 Implementation Principle

Every reusable UI element should have:

- a semantic name
- predictable structure
- defined variants
- defined states
- responsive behavior
- accessibility requirements
- clear content rules
- machine-readable representation where appropriate

---

# 2. Token System

## 2.1 Token Strategy

Design tokens provide the single source of truth for reusable visual values.

Token categories include:

- colors
- typography
- spacing
- breakpoints
- containers
- radius
- borders
- shadows
- motion
- z-index
- icons
- component-level references

### 2.2 Brand Colors

The UI/UX specification establishes a color strategy but does not provide final validated hexadecimal brand values.

Therefore:

- primary brand color: `REQUIRES_INPUT`
- secondary brand color: `REQUIRES_INPUT`
- accent color: `REQUIRES_INPUT`
- background colors: `REQUIRES_INPUT`
- text colors: `REQUIRES_INPUT`

No unapproved brand color values should be invented.

Semantic color roles must be maintained even after final values are supplied.

Recommended semantic roles:

- `color.brand.primary`
- `color.brand.secondary`
- `color.brand.accent`
- `color.background.primary`
- `color.background.secondary`
- `color.background.inverse`
- `color.text.primary`
- `color.text.secondary`
- `color.text.muted`
- `color.text.inverse`
- `color.border.default`
- `color.border.strong`
- `color.state.success`
- `color.state.warning`
- `color.state.error`
- `color.state.info`

### 2.3 Typography

The final brand typeface has not been explicitly approved.

Therefore:

- heading font family: `REQUIRES_INPUT`
- body font family: `REQUIRES_INPUT`
- UI font family: `REQUIRES_INPUT`

Typography must establish clear hierarchy and support a premium technology-consulting presentation.

Required semantic levels:

- Display
- H1
- H2
- H3
- H4
- Body Large
- Body
- Body Small
- Label
- Caption

Typography should prioritize:

- readability
- strong hierarchy
- restrained weight usage
- comfortable line height
- responsive scaling

### 2.4 Spacing

The approved UI/UX specification defines an 8-based spacing approach.

Approved spacing scale:

| Token | Value |
|---|---:|
| `space-1` | 8px |
| `space-2` | 16px |
| `space-3` | 24px |
| `space-4` | 32px |
| `space-5` | 40px |
| `space-6` | 48px |
| `space-7` | 64px |
| `space-8` | 80px |
| `space-9` | 96px |
| `space-10` | 128px |

Spacing should be used consistently for:

- component padding
- card spacing
- section spacing
- content grouping
- page layout
- responsive adjustments

### 2.5 Section Spacing

Recommended section spacing:

- compact section: 48–64px
- standard section: 72–96px
- major section: 96–128px

Exact implementation may be adjusted during responsive and visual QA.

### 2.6 Breakpoints

The UI/UX specification defines mobile, tablet, and desktop behavior but does not prescribe exact pixel breakpoints.

The following are system defaults pending implementation validation:

| Breakpoint | Range |
|---|---|
| Mobile | 0–767px |
| Tablet | 768–1023px |
| Desktop | 1024–1279px |
| Large Desktop | 1280px+ |

These values are system defaults, not confirmed brand requirements.

### 2.7 Containers

Recommended system defaults:

| Container | Maximum Width |
|---|---:|
| Page | 1280px |
| Content | 1200px |
| Reading | 720px |

The UI/UX specification indicates an approximate 1200–1280px content boundary.

### 2.8 Grid

The approved conceptual grid is:

| Viewport | Columns |
|---|---:|
| Mobile | 4 |
| Tablet | 8 |
| Desktop | 12 |

Recommended system-default gutters:

- Mobile: 16px
- Tablet: 24px
- Desktop: 24px

These values remain subject to visual validation.

### 2.9 Border Radius

The UI/UX specification does not prescribe final radius values.

System defaults pending visual validation:

| Token | Value |
|---|---:|
| `radius-none` | 0px |
| `radius-sm` | 4px |
| `radius-md` | 8px |
| `radius-lg` | 12px |
| `radius-xl` | 16px |
| `radius-full` | 9999px |

Radius should remain restrained and should not create an overly playful SaaS aesthetic.

### 2.10 Borders

Recommended semantic border tokens:

- default border
- strong border
- focus border
- divider

Exact color values remain `REQUIRES_INPUT`.

### 2.11 Shadows

System defaults pending visual validation:

- none
- small
- medium
- large
- extra-large

Shadows must remain subtle and purposeful.

The system should avoid excessive floating-card treatment.

### 2.12 Motion

System defaults pending interaction validation:

| Token | Duration |
|---|---:|
| `motion-fast` | 150ms |
| `motion-normal` | 250ms |
| `motion-slow` | 400ms |

Motion should be:

- subtle
- purposeful
- responsive
- accessible
- non-distracting

Preferred easing:

`cubic-bezier(0.2, 0.8, 0.2, 1)`

Reduced-motion preferences must be respected.

### 2.13 Z-Index

Recommended stacking system:

| Layer | Value |
|---|---:|
| Base | 0 |
| Content | 1 |
| Sticky elements | 20 |
| Header | 30 |
| Dropdown | 40 |
| Modal | 60 |
| Toast | 70 |

### 2.14 Icons

The final icon library is not specified.

Therefore:

`icon-library = REQUIRES_INPUT`

Icon requirements:

- consistent visual style
- simple geometry
- appropriate stroke weight
- accessible labeling when interactive
- no decorative icons without purpose

Recommended size tokens:

- 16px
- 20px
- 24px
- 32px
- 40px

---

# 3. Grid & Breakpoint System

## 3.1 Desktop

Desktop uses a 12-column grid.

Primary layout goals:

- strong horizontal alignment
- generous whitespace
- clear content hierarchy
- editorial/grid-based compositions
- prominent CTA placement

## 3.2 Tablet

Tablet uses an 8-column grid.

Layouts should:

- reduce horizontal density
- preserve hierarchy
- collapse multi-column sections where necessary
- maintain readable text widths
- keep CTA visibility high

## 3.3 Mobile

Mobile uses a 4-column conceptual grid.

Mobile layouts should:

- become primarily single-column
- preserve content order
- avoid horizontal overflow
- maintain touch-friendly controls
- prioritize the primary CTA
- simplify navigation
- reduce visual density

## 3.4 Responsive Principle

Responsive behavior is not simply desktop scaling.

Components should adapt according to:

- available space
- hierarchy
- content importance
- interaction requirements
- readability

---

# 4. Component Architecture & Contracts

## 4.1 Component Architecture

Components are organized into:

### Foundations

- Logo
- Icon
- Typography
- Container
- Grid

### Navigation

- Header
- Navigation
- Mobile Navigation
- Footer
- Breadcrumbs

### Content

- Section Header
- Hero
- Service Block
- Problem Block
- Process Step
- Technology Item
- Case Study Card
- Testimonial
- Base Card

### Conversion

- Primary Button
- Secondary Button
- Text Button
- Icon Button
- Final CTA
- Form

### Form Controls

- Text Input
- Textarea
- Select
- Checkbox
- Radio

### Interaction

- Accordion
- Modal

## 4.2 Component Contract

Every component should define:

- component ID
- semantic name
- purpose
- content structure
- variants
- states
- responsive behavior
- accessibility
- allowed usage
- prohibited usage
- dependencies

## 4.3 Buttons

### Primary Button

Purpose:

Primary conversion action.

Primary use:

**Book a Free Consultation**

States:

- default
- hover
- focus
- active
- disabled
- loading

### Secondary Button

Purpose:

Secondary navigation or exploration.

Examples:

- View Our Work
- Explore Case Studies
- Learn More

States:

- default
- hover
- focus
- active
- disabled

### Text Button

Used for lower-emphasis actions.

### Icon Button

Used for compact controls such as:

- mobile menu
- close
- utility controls

Interactive icon buttons must have accessible names.

## 4.4 Header

The header must provide:

- FidNext branding
- primary navigation
- primary CTA
- responsive mobile navigation

Desktop navigation:

- Services
- How We Work
- Technology
- About
- Contact
- Book a Free Consultation

States:

- default
- scrolled
- mobile-menu-open
- focus

## 4.5 Hero

The hero establishes:

- business positioning
- value proposition
- primary CTA
- secondary exploration path

Approved content direction:

**Build Better Technology. Move Your Business Forward.**

Supporting message:

**FidNext Technologies helps businesses turn technology challenges into practical digital solutions through strategy, design, engineering, and Agile delivery.**

Primary CTA:

**Book a Free Consultation**

Secondary CTA:

**View Our Work**

Any proof metrics or client logos must be validated before implementation.

## 4.6 Section Header

Provides:

- section eyebrow where required
- section title
- supporting description
- optional CTA

Must maintain consistent hierarchy.

## 4.7 Service Block

Services currently confirmed or proposed:

Confirmed:

- Software Consulting
- Custom Software Development

Validation-gated:

- AI Solutions
- Product Design & UX
- Application Modernization
- Cloud & DevOps
- Technology Team Augmentation

Validation-gated services must not be presented as confirmed capabilities without approval.

## 4.8 Problem Block

Used to communicate customer problems such as:

- unclear technology strategy
- software limitations
- risky technology decisions
- manual processes
- limited internal technology capacity
- unclear AI opportunities

Content should focus on business outcomes and clarity rather than technical jargon.

## 4.9 Process Step

The process component communicates FidNext's Agile-oriented approach.

Approved themes:

- Iterative Development
- Cross-Functional Teams
- Customer Collaboration
- Continuous Improvement

## 4.10 Technology Item

Confirmed technology/service references include:

- Web Development
- Android
- iOS
- Cloud Applications
- Java
- React Native
- Python

Technology should support credibility without becoming an excessive technology-logo wall.

## 4.11 Case Study Card

Case studies must only use verified information.

Do not invent:

- client names
- logos
- metrics
- outcomes
- project values
- dates
- testimonials

If evidence is unavailable:

`REQUIRES INPUT`

## 4.12 Testimonial

Testimonials require real approved client statements.

No fabricated testimonials are permitted.

If testimonials are unavailable, the component may remain structurally defined but should not be populated with invented content.

## 4.13 Forms

The primary conversion form should support:

- name
- email
- company
- project/business context
- optional service interest
- optional message

Final fields must follow approved UX and content requirements.

States:

- default
- focus
- filled
- error
- disabled
- success
- submission/loading

## 4.14 Accordion

Recommended for:

- FAQs
- expandable service information
- secondary explanatory content

States:

- collapsed
- expanded
- focus
- disabled

## 4.15 Modal

Use only when necessary.

Potential uses:

- consultation interaction
- secondary information
- confirmation

Avoid using modals for core content that should remain discoverable on the page.

## 4.16 Breadcrumbs

Use on deeper pages when useful for orientation.

Not required on the homepage.

## 4.17 Final CTA

The final CTA should reinforce the primary conversion journey.

Primary CTA:

**Book a Free Consultation**

Supporting messaging should reinforce clarity, confidence, and low-friction engagement.

---

# 5. Interaction & Motion System

## 5.1 Interaction Principles

Interactions must communicate:

- affordance
- feedback
- state
- hierarchy

Interactions should never exist only for decoration.

## 5.2 Hover

Hover interactions may include:

- subtle color transition
- border transition
- controlled elevation
- underline transition
- icon movement

Avoid excessive movement.

## 5.3 Focus

All interactive elements must provide visible keyboard focus.

Focus indicators must not rely on color alone.

## 5.4 Active

Active states should provide immediate interaction feedback.

## 5.5 Loading

Loading states should prevent duplicate submissions and clearly communicate progress.

## 5.6 Error

Errors should:

- identify the affected field
- explain what is wrong
- provide corrective guidance
- remain accessible

## 5.7 Success

Successful actions should provide clear confirmation.

## 5.8 Scroll Animation

Permitted uses:

- subtle section reveal
- controlled content entrance
- restrained image movement

Do not use:

- excessive parallax
- distracting looping animation
- motion that delays access to content

## 5.9 Reduced Motion

When `prefers-reduced-motion` is enabled:

- minimize non-essential animation
- remove parallax
- reduce transitions
- preserve functionality

---

# 6. Accessibility System

## 6.1 Core Requirement

The design system must support WCAG-oriented accessible implementation.

## 6.2 Keyboard Navigation

All interactive components must be keyboard accessible.

Required:

- visible focus
- logical tab order
- keyboard-operable controls
- no keyboard traps

## 6.3 Semantic HTML

Components should map to semantic HTML wherever possible.

Examples:

- navigation → `nav`
- headings → `h1–h6`
- buttons → `button`
- links → `a`
- forms → semantic form controls

## 6.4 Color

Color must not be the sole mechanism for communicating:

- error
- success
- selection
- state

Final contrast must be validated after actual brand colors are supplied.

## 6.5 Images

Images require appropriate alternative text.

Decorative images should use empty alternative text where appropriate.

## 6.6 Forms

Form controls must have:

- accessible labels
- clear error messages
- focus states
- appropriate input types
- understandable validation

## 6.7 Motion

Respect user reduced-motion preferences.

---

# 7. Implementation Guidelines

## 7.1 General

The design system should be implemented using semantic, reusable components.

Do not create separate one-off components when an existing component can be reused.

## 7.2 Naming

Use stable semantic names.

Examples:

- `PrimaryButton`
- `SectionHeader`
- `ServiceBlock`
- `CaseStudyCard`
- `ConsultationForm`

Avoid presentation-only names such as:

- `BlueBox`
- `BigCard`
- `HeroLeft`
- `RoundButton`

## 7.3 Component Variants

Variants should represent meaningful design differences.

Do not create variants for arbitrary page-specific styling.

## 7.4 Content Rules

Components must support content hierarchy defined by Agent 03.

Do not:

- fabricate proof
- invent metrics
- invent testimonials
- invent client names
- invent certifications
- invent partnerships

Validation-gated services and claims must remain clearly controlled.

## 7.5 Figma Implementation

Figma should use:

- shared styles
- reusable components
- variants
- auto layout
- semantic naming
- consistent spacing
- token references

Design components should map directly to implementation components.

## 7.6 Stitch Implementation

Stitch should use the design system as the visual contract.

Generated screens should preserve:

- hierarchy
- spacing
- typography
- responsive behavior
- component consistency
- CTA priority

Stitch-generated components should not introduce unapproved visual patterns.

## 7.7 Google AI Studio

AI-generated frontend code should consume the token and component definitions rather than inventing independent styling values.

AI implementation instructions should prioritize:

1. token usage
2. reusable components
3. semantic structure
4. responsive behavior
5. accessibility
6. approved content

## 7.8 Claude / AI Development Agents

AI development agents should:

- read the design system before implementation
- use machine-readable tokens
- use component contracts
- avoid inventing brand values
- flag `REQUIRES_INPUT`
- preserve component boundaries
- avoid unnecessary dependencies

## 7.9 Frontend Handoff

Agent 06 should use this design system to define:

- frontend architecture
- component structure
- styling strategy
- token integration
- responsive implementation
- development constraints

Agent 07 should use Agent 06's architecture together with this design system for implementation.

---

# 8. Design System QA

## 8.1 Visual QA

Validate:

- spacing consistency
- typography hierarchy
- component consistency
- CTA prominence
- responsive layout
- image treatment
- alignment
- visual rhythm

## 8.2 Component QA

Validate:

- variants
- states
- responsive behavior
- content flexibility
- reusable implementation

## 8.3 Accessibility QA

Validate:

- keyboard navigation
- focus states
- semantic markup
- color contrast
- labels
- alternative text
- reduced motion

## 8.4 Token QA

Validate that:

- repeated values use tokens
- no unnecessary hardcoded values exist
- semantic naming is maintained
- unresolved values are explicitly marked

## 8.5 Machine-Readable QA

Validate:

- JSON syntax
- stable IDs
- predictable structure
- no duplicate component IDs
- no conflicting token names
- valid references

## 8.6 Open Questions

The following require validation before final production implementation:

1. Final brand color palette
2. Final typography/font family
3. Final icon library
4. Final border treatment
5. Final shadow treatment
6. Final breakpoint validation
7. Final container/gutter validation
8. Availability and approval of case studies
9. Availability and approval of testimonials
10. Validation of proposed services
11. Validation of any business metrics or proof points

## 8.7 Design System Status

Current status:

**REVIEW_PENDING**

The design system is implementation-ready as a structured foundation, while unresolved brand-specific values remain explicitly marked as `REQUIRES_INPUT`.

---

# HANDOFF

### Agent 06 - Frontend Architect

Agent 06 receives:

- `design-system.md`
- `design-system.tokens.json`
- `design-system.components.json`

Agent 06 must use these artifacts to define the technical frontend architecture.

### Agent 07 - Development

Agent 07 will receive the implementation architecture from Agent 06 and use this design system as the visual and component implementation contract.

### Final Rule

Agent 05 stops after producing the three Design System deliverables.

No frontend code is produced by Agent 05.
```
