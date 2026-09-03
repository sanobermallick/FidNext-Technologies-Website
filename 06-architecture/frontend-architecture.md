---

Artifact: Frontend Architecture Specification
Producing Agent: 06 - Frontend Architect
Project: FidNext Technologies Website
Status: REVIEW_PENDING
Last Updated: 2026-09-03
------------------------

# FRONTEND ARCHITECTURE SPECIFICATION

## 1. Technology Stack & Project Structure

### 1.1 Architecture Objective

The frontend architecture for the FidNext Technologies website must provide a scalable, maintainable, responsive, accessible, performant, SEO-friendly, and AI-agent-friendly implementation structure.

The architecture must preserve the approved outputs from Agents 01–05.

The frontend must follow this hierarchy:

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

The implementation must avoid disconnected page-specific components and duplicated UI patterns.

---

### 1.2 Recommended Technology Stack

| Area                  | Technology                                      | Decision    |
| --------------------- | ----------------------------------------------- | ----------- |
| Framework             | React                                           | Required    |
| Language              | TypeScript                                      | Required    |
| Build Tool            | Vite                                            | Recommended |
| Routing               | React Router                                    | Recommended |
| Styling               | CSS Modules + CSS Custom Properties             | Recommended |
| State Management      | React component state                           | Default     |
| Form Handling         | Native React form state and validation          | Default     |
| Animation             | CSS transitions/keyframes + native browser APIs | Default     |
| Testing               | Vitest + React Testing Library                  | Recommended |
| Browser Testing       | Playwright                                      | Recommended |
| Accessibility Testing | Playwright + axe integration                    | Recommended |
| Code Quality          | ESLint + Prettier                               | Required    |
| Package Manager       | npm                                             | Recommended |

Major versions should be pinned during Agent 07 project initialization and committed through the package lockfile.

No dependency should be introduced only for convenience when the same requirement can be satisfied using the existing platform, React, CSS, or browser APIs.

---

### 1.3 Architecture Principles

The frontend must follow these principles:

1. Reuse before duplication.
2. Components must have a single clear responsibility.
3. Pages compose sections rather than containing large amounts of UI logic.
4. Sections compose reusable compound components.
5. Primitive components must remain generic.
6. Content must remain separate from presentation logic.
7. Design tokens must be consumed rather than recreated in component CSS.
8. Responsive behavior must be defined systematically.
9. Accessibility must be considered during implementation rather than added later.
10. SEO metadata must be route-specific.
11. Animation must support the experience without becoming the experience.
12. No unsupported business claims may be introduced through frontend copy.
13. No new functionality may be invented during implementation.
14. Architecture changes require documentation through an Architecture Decision Record.

---

### 1.4 Project Structure

The recommended frontend structure is:

```text
src/
├── app/
│   ├── App.tsx
│   └── router.tsx
│
├── layouts/
│   └── SiteLayout.tsx
│
├── pages/
│   ├── HomePage.tsx
│   ├── ServicesPage.tsx
│   ├── SoftwareConsultingPage.tsx
│   ├── CustomSoftwareDevelopmentPage.tsx
│   ├── HowWeWorkPage.tsx
│   ├── TechnologyPage.tsx
│   ├── AboutPage.tsx
│   ├── ContactPage.tsx
│   └── NotFoundPage.tsx
│
├── sections/
│   ├── home/
│   ├── services/
│   ├── how-we-work/
│   ├── technology/
│   ├── about/
│   └── contact/
│
├── components/
│   ├── primitives/
│   └── compounds/
│
├── config/
│   ├── navigation.ts
│   └── site-config.ts
│
├── data/
│   ├── services.ts
│   ├── technology.ts
│   └── content.ts
│
├── hooks/
│
├── lib/
│
├── types/
│
├── assets/
│   ├── images/
│   ├── icons/
│   └── fonts/
│
└── styles/
    ├── globals.css
    └── tokens.css
```

Agent 07 may refine this structure only when required by implementation, and any structural deviation must be documented.

---

### 1.5 File Ownership

| Directory                | Primary Responsibility                 |
| ------------------------ | -------------------------------------- |
| `app/`                   | Application initialization and routing |
| `layouts/`               | Shared page layouts                    |
| `pages/`                 | Route-level composition                |
| `sections/`              | Page-level visual sections             |
| `components/primitives/` | Reusable low-level UI                  |
| `components/compounds/`  | Reusable business/UI patterns          |
| `config/`                | Static application configuration       |
| `data/`                  | Structured website content             |
| `hooks/`                 | Reusable React behavior                |
| `lib/`                   | Shared technical utilities             |
| `types/`                 | Shared TypeScript types                |
| `assets/`                | Static frontend assets                 |
| `styles/`                | Global styles and token consumption    |

---

## 2. Routing & Page Architecture

### 2.1 Approved Core Routes

The initial implementation must support:

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

A catch-all route must provide a user-friendly 404 page.

---

### 2.2 Consultation CTA Routing

The primary CTA is:

```text
Book a Free Consultation
```

The CTA should lead to the approved Contact/Consultation experience.

A separate `/book-consultation` route must not be created unless explicitly approved.

The preferred implementation is:

```text
Book a Free Consultation
        ↓
/contact
        ↓
Consultation Form
```

---

### 2.3 Route Configuration

Routes must be defined centrally in:

```text
src/app/router.tsx
```

Navigation labels and destination paths should be maintained in:

```text
src/config/navigation.ts
```

Components must not contain duplicated hard-coded navigation definitions.

---

### 2.4 Page Architecture

Pages are route-level composition containers.

A page should primarily:

1. establish the page structure;
2. compose approved sections;
3. provide route-level metadata;
4. pass structured content to sections;
5. avoid containing reusable UI implementation.

Example:

```text
HomePage
├── HeroSection
├── TrustSection
├── ProblemsSection
├── ServicesSection
├── WhyFidNextSection
├── HowWeWorkSection
├── CaseStudiesSection
├── TechnologySection
├── TestimonialsSection
├── InsightsSection
└── FinalCTASection
```

The homepage section sequence follows the approved Content Strategy.

---

### 2.5 Services Architecture

```text
ServicesPage
├── PageHero
├── ServicesOverview
└── FinalCTA
```

Service detail pages:

```text
SoftwareConsultingPage
├── ServiceHero
├── ProblemOrNeedSection
├── ServiceApproachSection
├── CapabilitiesSection
└── FinalCTA
```

```text
CustomSoftwareDevelopmentPage
├── ServiceHero
├── ProblemOrNeedSection
├── DevelopmentApproachSection
├── CapabilitiesSection
└── FinalCTA
```

Exact content must come from Agent 03 and approved client information.

---

### 2.6 Optional Pages

The following are not part of the initial mandatory route set unless validated and approved:

```text
/industries
/case-studies
/insights
/solutions
```

They must not be implemented simply because they appear as proposed opportunities in earlier strategy documentation.

---

## 3. Component Architecture & Data Flow

### 3.1 Component Layers

The implementation must use four practical UI layers.

```text
Primitive Components
        ↓
Compound Components
        ↓
Sections
        ↓
Pages
```

---

### 3.2 Primitive Components

Primitive components provide reusable low-level UI behavior.

Examples:

```text
Button
TextLink
IconButton
Input
Textarea
Select
Checkbox
Radio
Container
Heading
Text
Image
```

Primitive components must not contain page-specific business content.

---

### 3.3 Compound Components

Compound components combine primitives into reusable website patterns.

Examples:

```text
ServiceCard
ProblemBlock
ProcessStep
TechnologyItem
CaseStudyCard
Testimonial
SectionHeader
FinalCTA
ConsultationForm
```

---

### 3.4 Section Components

Sections represent meaningful page-level content blocks.

Examples:

```text
HeroSection
ServicesSection
TechnologySection
HowWeWorkSection
TestimonialsSection
FinalCTASection
```

Sections may compose multiple compound components.

---

### 3.5 Page Components

Pages should contain composition only.

Example:

```tsx
export function HomePage() {
  return (
    <>
      <HeroSection />
      <TrustSection />
      <ProblemsSection />
      <ServicesSection />
      <WhyFidNextSection />
      <HowWeWorkSection />
      <CaseStudiesSection />
      <TechnologySection />
      <TestimonialsSection />
      <InsightsSection />
      <FinalCTASection />
    </>
  );
}
```

The example is architectural guidance. Agent 07 must use actual approved content and section contracts.

---

### 3.6 Component Naming

Use PascalCase for React components.

Examples:

```text
PrimaryButton.tsx
ServiceCard.tsx
HeroSection.tsx
ContactPage.tsx
```

Avoid vague names such as:

```text
Box.tsx
Thing.tsx
Section1.tsx
ComponentA.tsx
```

---

### 3.7 Props Architecture

Props must be explicit and typed.

Example:

```ts
interface ServiceCardProps {
  title: string;
  description: string;
  href?: string;
  eyebrow?: string;
}
```

Avoid excessive optional props.

If a component requires many unrelated configuration flags, reconsider whether it represents multiple components.

---

### 3.8 Data Flow

Preferred data flow:

```text
Content/Data
    ↓
Page
    ↓
Section
    ↓
Compound Component
    ↓
Primitive
```

Data should generally flow downward through props.

Avoid:

```text
Page ↔ Component ↔ Global State ↔ Component
```

unless global state is genuinely required.

---

### 3.9 Global State

No global state management library is required for Version 1.

Do not introduce Redux, Zustand, MobX, or similar libraries unless a real requirement emerges.

Local React state is sufficient for:

* navigation menu state;
* accordion state;
* modal state;
* form state;
* UI interaction state.

---

### 3.10 Content/UI Separation

Website content should not be deeply embedded inside reusable components.

Preferred:

```text
data/
    services.ts
    technology.ts
    content.ts
```

Components consume structured data.

Example:

```ts
const services = [
  {
    title: "...",
    description: "...",
    href: "..."
  }
];
```

Actual copy must come from approved Agent 03 content.

---

## 4. Design Token Integration

### 4.1 Token Source of Truth

The following file is the machine-readable design token source:

```text
05-design-system/design-system.tokens.json
```

The following document remains the human-readable design system:

```text
05-design-system/design-system.md
```

The frontend must not independently recreate the design token system.

---

### 4.2 Token Consumption

Design tokens should be exposed to CSS through CSS custom properties.

Recommended implementation:

```text
design-system.tokens.json
        ↓
token transformation/validation
        ↓
src/styles/tokens.css
        ↓
component styles
```

Agent 07 must ensure that the generated CSS remains consistent with the approved JSON.

---

### 4.3 Spacing Tokens

The approved spacing scale is:

```text
8px
16px
24px
32px
40px
48px
64px
80px
96px
128px
```

Components must use these values rather than introducing arbitrary spacing.

---

### 4.4 Unresolved Tokens

Agent 05 identifies certain brand values as:

```text
REQUIRES_INPUT
```

This includes unresolved visual decisions such as brand colors, typography, icon library, and some shadow values.

Agent 07 must not replace these with invented values.

Before production implementation, unresolved tokens must either:

1. receive approved values; or
2. remain explicitly blocked from production use.

---

### 4.5 Design Token Rules

Do not write:

```css
padding: 37px;
```

when an approved token can be used.

Prefer:

```css
padding: var(--space-32);
```

Do not introduce one-off colors, radii, shadows, or typography values without documenting the decision.

---

## 5. Responsive, Asset & Image Architecture

### 5.1 Responsive Strategy

The frontend must follow the design system breakpoint structure.

Current breakpoint guidance:

```text
Mobile:        0–767px
Tablet:        768–1023px
Desktop:       1024–1279px
Large Desktop: 1280px+
```

These values remain subject to final visual validation.

---

### 5.2 Layout Grid

Approved grid direction:

```text
Mobile
4 columns
16px gutter

Tablet
8 columns
24px gutter

Desktop
12 columns
24px gutter
```

Container guidance:

```text
Page container:    1280px
Content container: 1200px
Reading width:      720px
```

---

### 5.3 Responsive Rules

Responsive behavior must be implemented through layout adaptation rather than separate desktop and mobile pages.

Prefer:

```text
same component
+
responsive CSS
+
responsive assets
```

Avoid:

```text
DesktopComponent
MobileComponent
```

unless there is a genuine structural requirement.

---

### 5.4 Asset Organization

Assets should be organized by type:

```text
src/assets/
├── images/
├── icons/
└── fonts/
```

Original client assets remain in:

```text
INPUT/client-assets/
```

Only approved assets required by the frontend should be copied or referenced into the implementation.

---

### 5.5 Image Architecture

Images must:

* use meaningful filenames;
* include alternative text when meaningful;
* use appropriate dimensions;
* avoid unnecessary oversized files;
* support responsive rendering;
* preserve aspect ratio;
* use lazy loading where appropriate;
* avoid layout shifts.

Prefer responsive image techniques:

```html
<picture>
  <source ... />
  <img ... />
</picture>
```

or equivalent React implementation.

Hero/above-the-fold images must be handled carefully to avoid delayed rendering.

---

### 5.6 Image Content Rules

Do not invent:

* client logos;
* customer logos;
* project screenshots;
* team photographs;
* office photographs;
* awards;
* certifications;
* testimonials;
* case-study imagery.

Use supplied or approved assets only.

---

### 5.7 Typography Architecture

Typography must consume the typography decisions from the Design System.

Do not select a new production font merely to complete the implementation.

If the approved font family is still unresolved, mark it as a dependency for final visual validation.

---

## 6. Accessibility, SEO & Performance

### 6.1 Accessibility

All components must support accessible interaction.

Required principles:

* semantic HTML;
* keyboard accessibility;
* visible focus states;
* sufficient color contrast;
* descriptive accessible names;
* correct heading hierarchy;
* form labels;
* useful validation messages;
* accessible navigation;
* reduced-motion support.

Avoid using `div` elements where semantic elements are appropriate.

---

### 6.2 Keyboard Navigation

Interactive elements must be reachable through keyboard navigation.

Do not create clickable `div` elements when a native button or link is appropriate.

---

### 6.3 Focus Management

Interactive controls must have visible focus indicators.

Dialogs and mobile navigation must manage focus appropriately when implemented.

---

### 6.4 Reduced Motion

The design system specifies reduced-motion behavior.

Animations must respect:

```css
@media (prefers-reduced-motion: reduce) {
  /* reduce or disable non-essential animation */
}
```

---

### 6.5 SEO Architecture

Each route should have:

```text
title
meta description
canonical URL
Open Graph metadata
structured heading hierarchy
```

Where applicable.

SEO metadata must be route-specific.

Do not duplicate the same page title across all routes.

---

### 6.6 Heading Architecture

Each page should have one clear primary heading.

Use:

```text
H1
  ↓
H2
  ↓
H3
```

Do not use heading elements purely for visual sizing.

---

### 6.7 Semantic HTML

Prefer:

```html
<header>
<nav>
<main>
<section>
<article>
<footer>
```

over generic containers wherever semantic meaning exists.

---

### 6.8 Performance Principles

The implementation should prioritize:

* minimal JavaScript;
* code splitting by route where beneficial;
* optimized images;
* lazy loading;
* efficient font loading;
* limited third-party scripts;
* avoidance of unnecessary dependencies;
* stable layout dimensions;
* fast first render.

---

### 6.9 Core Performance Targets

Agent 07 should target strong Lighthouse performance without compromising the approved design.

Performance should be evaluated using:

```text
Performance
Accessibility
Best Practices
SEO
```

Actual scores belong to QA stages and must not be invented in advance.

---

### 6.10 Error Handling

The frontend must include:

```text
404 Not Found
form validation errors
form submission failure state
loading states where applicable
empty states where applicable
```

Error messages must be understandable to users.

Do not expose internal technical errors or stack traces.

---

## 7. AI Development Contract

### 7.1 Purpose

This architecture is designed to be implemented by AI coding agents while preserving design and business intent.

Agent 07 must treat this document and the approved upstream artifacts as implementation contracts.

---

### 7.2 Source-of-Truth Hierarchy

When instructions conflict, use this hierarchy:

```text
Approved Client Inputs
        ↓
Agent 01 Business Discovery
        ↓
Agent 02 UX / Information Architecture
        ↓
Agent 03 Content Strategy
        ↓
Agent 04 UI/UX Design
        ↓
Agent 05 Design System
        ↓
Agent 06 Frontend Architecture
        ↓
Agent 07 Development
```

Later agents must not silently override approved upstream decisions.

---

### 7.3 AI Implementation Rules

AI coding agents must:

1. inspect existing files before creating new files;
2. reuse existing components;
3. reuse existing tokens;
4. reuse existing content;
5. avoid duplicated UI;
6. avoid unnecessary dependencies;
7. preserve responsive behavior;
8. preserve accessibility;
9. preserve semantic HTML;
10. avoid invented content;
11. avoid invented functionality;
12. avoid changing approved UX;
13. avoid changing the approved technology stack;
14. document architecture changes.

---

### 7.4 Single Responsibility

Each implementation task should have a clear boundary.

Examples:

```text
Implement global header
Implement homepage hero
Implement services section
Implement contact form
Implement responsive navigation
```

Do not ask an AI coding agent to redesign the entire website and implement all functionality in one uncontrolled operation.

---

### 7.5 File Ownership

Agent 07 should respect the ownership boundaries:

```text
app/          → application/routing
pages/        → page composition
sections/     → page sections
components/   → reusable UI
data/         → structured content
styles/       → global/token styling
assets/       → visual assets
hooks/        → reusable behavior
lib/          → technical utilities
types/        → shared types
```

---

### 7.6 Change Protocol

If implementation reveals a requirement that conflicts with this architecture:

```text
STOP
↓
Document the conflict
↓
Create ADR
↓
Get approval
↓
Implement approved change
```

Do not silently change architecture.

---

### 7.7 No Design Drift

Agent 07 must not:

* introduce new visual styles;
* replace approved typography;
* replace approved spacing;
* introduce unrelated animations;
* redesign components;
* add random gradients;
* introduce excessive rounded cards;
* introduce stock imagery;
* add unsupported sections.

---

### 7.8 No Business Claim Drift

Frontend implementation must not introduce unsupported:

* metrics;
* customer counts;
* revenue claims;
* awards;
* certifications;
* partnerships;
* client logos;
* testimonials;
* case-study outcomes;
* years of experience;
* team-size claims.

---

### 7.9 Validation Before Completion

Agent 07 must validate:

```text
TypeScript
Lint
Build
Routes
Responsive behavior
Accessibility basics
Component reuse
Token usage
Asset references
SEO metadata
```

Agent 07 must not claim QA approval. Formal QA belongs to Agents 08–11.

---

## 8. Architecture Decisions & Open Questions

### 8.1 Architecture Decision Record

Architecture decisions should be stored in:

```text
DECISIONS/
```

Recommended naming:

```text
ADR-001-react-typescript-vite.md
ADR-002-styling-strategy.md
ADR-003-routing-strategy.md
```

Only create an ADR when a meaningful architectural decision needs to be recorded.

---

### 8.2 Decision: React + TypeScript

**Decision:** Use React with TypeScript.

**Reason:** Provides a component-based architecture, strong typing, reusable UI patterns, and good compatibility with AI-assisted development.

---

### 8.3 Decision: Vite

**Decision:** Use Vite as the frontend build tool.

**Reason:** Provides a lightweight development environment and modern production build workflow without introducing unnecessary framework complexity.

---

### 8.4 Decision: CSS Modules + CSS Custom Properties

**Decision:** Use CSS Modules for component styling and CSS custom properties for design tokens.

**Reason:** Supports encapsulation, token reuse, responsive CSS, and close alignment with the approved custom design system.

No CSS framework or UI component library is required unless a later approved requirement justifies one.

---

### 8.5 Decision: No Global State Library

**Decision:** Do not introduce a global state-management library in Version 1.

**Reason:** The website is primarily content-driven and does not currently require complex cross-page application state.

---

### 8.6 Decision: Native Browser Animation

**Decision:** Use CSS transitions/keyframes and native browser APIs for initial motion.

**Reason:** Agent 05 defines a relatively lightweight motion system. A dedicated animation dependency is not currently justified.

---

### 8.7 Decision: No Mandatory Third-Party Integrations

No CRM, analytics, chatbot, CMS, payment system, map provider, or external application integration is currently mandatory.

Any future integration must be:

1. explicitly approved;
2. documented;
3. isolated behind a clear integration boundary;
4. configured through environment variables where appropriate.

---

### 8.8 Environment Variables

Frontend environment variables must use the Vite public-variable convention:

```text
VITE_*
```

Only values safe for exposure to the browser may be stored in frontend environment variables.

Never store:

```text
API secrets
private keys
database credentials
authentication secrets
```

in frontend source code or public environment variables.

---

### 8.9 Form Architecture

The consultation form should initially use:

```text
React state
+
controlled inputs
+
client-side validation
+
accessible error messages
```

Actual form submission infrastructure remains dependent on the approved business/technical requirement.

Do not invent a CRM or backend integration.

---

### 8.10 Open Question: Brand Colors

Agent 05 marks brand color decisions as unresolved.

**Status: REQUIRES_INPUT**

Do not invent final brand colors.

---

### 8.11 Open Question: Typography

Typography is not fully approved.

**Status: REQUIRES_INPUT**

Final font selection must be validated before production implementation.

---

### 8.12 Open Question: Icon Library

Agent 05 identifies the icon library as unresolved.

**Status: REQUIRES_INPUT**

Agent 07 must not arbitrarily select an icon library without recording the decision.

---

### 8.13 Open Question: Form Submission

The exact destination of the consultation form is not established.

Possible future implementations include:

```text
approved backend endpoint
approved CRM
approved email service
approved form service
```

No implementation should be invented until the requirement is approved.

---

### 8.14 Open Question: Analytics

No analytics platform is currently mandated.

If analytics is approved later, it must be implemented with:

* minimal performance impact;
* privacy-conscious configuration;
* documented ownership;
* appropriate consent requirements where applicable.

---

### 8.15 Open Question: Optional Content

Case studies, testimonials, insights, industries, and additional solution pages must use validated content before being implemented as factual production content.

---

### 8.16 Implementation Order

Agent 07 should implement in this order:

```text
1. Project initialization
2. Global styles and token integration
3. Application shell
4. Header and navigation
5. Footer
6. Primitive components
7. Compound components
8. Homepage sections
9. Homepage composition
10. Services page
11. Service detail pages
12. How We Work page
13. Technology page
14. About page
15. Contact/Consultation page
16. 404 page
17. Responsive refinement
18. Accessibility refinement
19. SEO metadata
20. Performance optimization
21. Automated tests
22. Production build validation
```

---

### 8.17 Definition of Architecture Completion

Agent 06 is complete when:

* frontend stack is defined;
* project structure is defined;
* routes are defined;
* page architecture is defined;
* component hierarchy is defined;
* data flow is defined;
* token integration is defined;
* responsive architecture is defined;
* asset architecture is defined;
* accessibility architecture is defined;
* SEO architecture is defined;
* performance architecture is defined;
* testing direction is defined;
* AI implementation rules are defined;
* open architectural questions are recorded;
* Agent 07 has a clear implementation contract.

**Final Status: REVIEW_PENDING**
