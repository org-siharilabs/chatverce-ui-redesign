# Chatverce Design Documentation Site - Refactor Plan

**For**: Woz (Implementation)  
**From**: Jony (Design & Specification)  
**Date**: February 6, 2026, 10:05 AM IST  
**Timeline**: 3-5 days  
**Tech Stack**: Next.js 16 + MDX + Tailwind CSS + GitHub Pages

---

## The Problem

The current repository is **unusable**:
- 19 markdown files scattered across folders
- No clear entry point or navigation
- HTML prototypes disconnected from docs
- No visual hierarchy or search
- Impossible to find what you need quickly

**This is a design documentation site. It must be exemplary.**

---

## The Vision

A **world-class design documentation site** that:
- Showcases the Chatverce redesign professionally
- Serves as the single source of truth for design decisions
- Helps developers implement designs correctly
- Demonstrates our design capabilities to stakeholders
- Works offline, loads instantly, looks perfect

**Reference sites** (for inspiration):
- Stripe Design System (stripe.com/docs)
- Linear Design (linear.app/design)
- Vercel Design (vercel.com/design)
- Material Design 3 (m3.material.io)

---

## Information Architecture

### Site Structure

```
/
├── Home (Landing)
├── Design System
│   ├── Overview
│   ├── Colors
│   ├── Typography
│   ├── Spacing
│   ├── Components
│   │   ├── Buttons
│   │   ├── Inputs
│   │   ├── Tables
│   │   ├── Cards
│   │   └── ... (all components)
│   └── Animations
├── Screens
│   ├── Dashboard
│   ├── Conversations
│   ├── Chat View
│   ├── CRM Table
│   ├── Campaigns
│   ├── AI Agents
│   └── Settings
├── Research
│   ├── Market Analysis
│   ├── Competitive Landscape
│   ├── Product Vision
│   └── User Insights
├── Implementation
│   ├── Getting Started
│   ├── Developer Handoff
│   ├── Week 1 Tasks
│   ├── Week 2 Tasks
│   └── Week 3 Tasks
├── Resources
│   ├── Downloads
│   ├── Figma Files
│   ├── Illustrations
│   └── Assets
└── About
    ├── Design Principles
    ├── Process
    └── Team
```

---

## Visual Design Direction

### Design Language

**Inspired by**: Apple HIG, Linear, Stripe Docs  
**Feeling**: Clean, professional, authoritative, trustworthy

**Key principles**:
1. **Generous whitespace** - Let content breathe
2. **Strong typography hierarchy** - Make scanning effortless
3. **Subtle color** - Green accent (#16a34a), mostly monochrome
4. **Consistent spacing** - 8px grid, predictable rhythm
5. **Fast animations** - 200ms transitions, smooth scrolling

---

### Layout System

**Sidebar + Content** (classic docs layout):

```
┌─────────────────────────────────────────────────────┐
│  Logo            Search                    GitHub   │ <- Top bar (64px)
├───────────┬─────────────────────────────────────────┤
│           │                                         │
│ Sidebar   │  Content Area                           │
│ (260px)   │  (max-width: 800px, centered)           │
│           │                                         │
│ - Home    │  # Page Title                           │
│ - Design  │  Breadcrumb > Path                      │
│   System  │                                         │
│   • Colors│  Content with headings, code,           │
│   • Type  │  images, interactive examples           │
│ - Screens │                                         │
│ - Research│  → On this page (right sidebar)         │
│           │                                         │
│           │                                         │
└───────────┴─────────────────────────────────────────┘
```

**Responsive**:
- Desktop: Sidebar always visible
- Tablet: Sidebar collapsible
- Mobile: Hamburger menu

---

### Color Palette

**Primary**:
- Green: `#16a34a` (brand color, links, accents)
- Dark: `#0a0a0a` (headings, primary text)
- Grey: `#6b7280` (body text)
- Light Grey: `#f9fafb` (backgrounds)

**Semantic**:
- Success: `#16a34a`
- Warning: `#f59e0b`
- Error: `#dc2626`
- Info: `#3b82f6`

**Code syntax highlighting**:
- Use GitHub Dark theme or Nord theme

---

### Typography

**Font stack**:
```css
--font-sans: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", sans-serif;
--font-mono: "SF Mono", "Fira Code", "Consolas", monospace;
```

**Scale**:
- Display: 48px / 3rem (page titles)
- H1: 36px / 2.25rem
- H2: 28px / 1.75rem
- H3: 20px / 1.25rem
- Body: 16px / 1rem
- Small: 14px / 0.875rem
- Caption: 12px / 0.75rem

**Weights**:
- Regular: 400
- Medium: 500
- Semibold: 600
- Bold: 700

---

### Component Patterns

#### Navigation Sidebar

```
┌─────────────────────┐
│ Chatverce Design    │ <- Logo + title
├─────────────────────┤
│                     │
│ 🏠 Home             │ <- Active (green bg)
│                     │
│ 🎨 Design System    │ <- Expandable
│   → Overview        │
│   → Colors          │
│   → Typography      │
│                     │
│ 📱 Screens          │
│   → Dashboard       │
│   → Conversations   │
│                     │
│ 🔬 Research         │
│                     │
│ 👨‍💻 Implementation  │
│                     │
│ 📦 Resources        │
└─────────────────────┘
```

**Specs**:
- Width: 260px
- Item height: 40px
- Active: Green background (#f0fdf4), green text
- Hover: Light grey background (#f9fafb)
- Font: 15px, medium weight
- Icons: 20px, Lucide icons

---

#### Search

**Algolia DocSearch** or custom search:
- Cmd+K to open
- Full-text search across all pages
- Show results with context snippets
- Keyboard navigable

---

#### Code Blocks

**Features**:
- Syntax highlighting
- Copy button (top right)
- Language label
- Line numbers (optional)
- Diff highlighting (for before/after)

**Example**:
````
```tsx
// Component example
export function Button({ children, variant = 'primary' }) {
  return (
    <button className={`btn btn-${variant}`}>
      {children}
    </button>
  )
}
```
````

---

#### Interactive Examples

**Live component previews**:
- Show component in action
- Toggle between variants
- View code below
- Responsive preview

**Example**:

```
┌─────────────────────────────────┐
│ Preview                    [⚙️] │
├─────────────────────────────────┤
│                                 │
│   [Primary Button]              │ <- Live preview
│                                 │
├─────────────────────────────────┤
│ Code                       [📋] │
├─────────────────────────────────┤
│ <Button variant="primary">     │
│   Primary Button                │
│ </Button>                       │
└─────────────────────────────────┘
```

---

#### Before/After Comparisons

**For screen specs**:

```
┌──────────────┬──────────────┐
│   Before     │    After     │
├──────────────┼──────────────┤
│  [Screenshot]│ [Screenshot] │
│              │              │
│  Issues:     │  Fixed:      │
│  • Problem 1 │  ✓ Solution  │
│  • Problem 2 │  ✓ Better    │
└──────────────┴──────────────┘
```

---

## Technical Requirements

### Tech Stack

**Framework**: Next.js 16 (App Router)  
**Styling**: Tailwind CSS  
**Content**: MDX (Markdown + React components)  
**Deployment**: GitHub Pages (static export)  
**Search**: Algolia DocSearch (or Fuse.js)  
**Icons**: Lucide React  
**Code highlighting**: Shiki or Prism  

---

### Project Structure

```
chatverce-design-docs/
├── src/
│   ├── app/
│   │   ├── layout.tsx           # Root layout
│   │   ├── page.tsx             # Home page
│   │   ├── design-system/
│   │   │   ├── page.tsx
│   │   │   ├── colors/page.mdx
│   │   │   ├── typography/page.mdx
│   │   │   └── components/
│   │   │       ├── buttons/page.mdx
│   │   │       └── inputs/page.mdx
│   │   ├── screens/
│   │   │   ├── dashboard/page.mdx
│   │   │   └── conversations/page.mdx
│   │   ├── research/
│   │   │   └── market-analysis/page.mdx
│   │   └── implementation/
│   │       └── getting-started/page.mdx
│   ├── components/
│   │   ├── Sidebar.tsx
│   │   ├── CodeBlock.tsx
│   │   ├── BeforeAfter.tsx
│   │   └── LivePreview.tsx
│   ├── content/                 # All existing .md files
│   └── public/
│       ├── illustrations/       # SVG files
│       └── screenshots/         # Screen images
├── next.config.js
├── tailwind.config.js
└── package.json
```

---

### Content Migration

**Map existing files to new structure**:

| Old File | New Location |
|----------|--------------|
| `design-system.md` | `/design-system/overview` |
| `COMPONENT-LIBRARY.md` | `/design-system/components` |
| `ANIMATIONS.md` | `/design-system/animations` |
| `ACCESSIBILITY.md` | `/design-system/accessibility` |
| `01-chat-view-spec.md` | `/screens/chat-view` |
| `02-conversations-list-spec.md` | `/screens/conversations` |
| `03-empty-states-spec.md` | `/screens/empty-states` |
| `04-crm-table-spec.md` | `/screens/crm-table` |
| `COMPETITIVE-ANALYSIS.md` | `/research/competitive-analysis` |
| `PRODUCT-VISION-2026.md` | `/research/product-vision` |
| `MARKET-DISRUPTION-SUMMARY.md` | `/research/market-strategy` |
| `DEVELOPER-HANDOFF.md` | `/implementation/getting-started` |
| `SCREEN-BY-SCREEN-ANALYSIS.md` | `/implementation/task-breakdown` |

---

### Key Features to Build

#### 1. MDX Support
- Parse markdown files
- Render with custom components
- Support frontmatter (title, description, date)

#### 2. Syntax Highlighting
- Code blocks with language detection
- Copy button
- Line highlighting

#### 3. Navigation
- Auto-generate sidebar from file structure
- Active page highlighting
- Expandable sections

#### 4. Search
- Full-text search
- Keyboard shortcuts (Cmd+K)
- Result previews

#### 5. Responsive
- Mobile hamburger menu
- Collapsible sidebar
- Touch-friendly

#### 6. Performance
- Static site generation
- Image optimization
- Fast page loads (<1s)

---

## Implementation Plan

### Phase 1: Setup & Structure (Day 1 - 6 hours)

**Deliverable**: Working Next.js 16 site with basic routing

**Tasks**:
- [ ] Initialize Next.js 16 project
- [ ] Install dependencies (Tailwind, MDX, Lucide, Shiki)
- [ ] Create folder structure
- [ ] Set up Tailwind config with design tokens
- [ ] Create basic layout (header, sidebar, content area)
- [ ] Set up MDX rendering
- [ ] Configure static export for GitHub Pages

**Code needed**:
- `next.config.js` with MDX + static export
- `tailwind.config.js` with design system colors/spacing
- `app/layout.tsx` with root layout
- `components/Sidebar.tsx`
- `components/MDXComponents.tsx`

---

### Phase 2: Content Migration (Day 2 - 8 hours)

**Deliverable**: All existing content migrated and accessible

**Tasks**:
- [ ] Convert all .md files to .mdx
- [ ] Add frontmatter (title, description, category)
- [ ] Move files to correct routes
- [ ] Update internal links
- [ ] Copy images/SVGs to public/
- [ ] Create navigation data structure
- [ ] Build sidebar navigation
- [ ] Test all pages render correctly

**Content checklist**:
- [ ] Design System (5 pages)
- [ ] Screens (7 pages)
- [ ] Research (3 pages)
- [ ] Implementation (4 pages)
- [ ] Resources (1 page)

---

### Phase 3: Components & Styling (Day 3 - 8 hours)

**Deliverable**: Beautiful, branded design system site

**Tasks**:
- [ ] Create CodeBlock component with syntax highlighting
- [ ] Create BeforeAfter comparison component
- [ ] Create ComponentPreview for live examples
- [ ] Create PropsTable for component APIs
- [ ] Style all MDX elements (h1, h2, p, ul, etc.)
- [ ] Add "On this page" right sidebar
- [ ] Add breadcrumbs
- [ ] Add copy buttons to code blocks
- [ ] Polish typography and spacing
- [ ] Add smooth scroll behavior

**Components to build**:
- `<CodeBlock language="tsx" />`
- `<BeforeAfter before={} after={} />`
- `<ComponentPreview name="Button" />`
- `<PropsTable data={} />`
- `<Callout type="warning" />`

---

### Phase 4: Advanced Features (Day 4 - 6 hours)

**Deliverable**: Search, animations, polish

**Tasks**:
- [ ] Implement search (Algolia or Fuse.js)
- [ ] Add Cmd+K keyboard shortcut
- [ ] Add smooth page transitions
- [ ] Add scroll progress indicator
- [ ] Add "Edit this page on GitHub" links
- [ ] Add "Last updated" timestamps
- [ ] Optimize images with Next.js Image
- [ ] Add meta tags for SEO
- [ ] Test accessibility (keyboard nav, screen readers)

---

### Phase 5: Deployment & Testing (Day 5 - 4 hours)

**Deliverable**: Live site on GitHub Pages

**Tasks**:
- [ ] Configure GitHub Pages deployment
- [ ] Add GitHub Actions for auto-deploy
- [ ] Test build process
- [ ] Fix any build errors
- [ ] Test on multiple browsers
- [ ] Test on mobile devices
- [ ] Set up custom domain (if applicable)
- [ ] Add analytics (optional)
- [ ] Create README for repo
- [ ] Document how to add new pages

---

## File Structure Example

### Home Page (`app/page.tsx`)

```tsx
export default function HomePage() {
  return (
    <div className="max-w-4xl mx-auto py-16 px-8">
      {/* Hero Section */}
      <div className="text-center mb-16">
        <h1 className="text-6xl font-bold mb-6">
          Chatverce Design System
        </h1>
        <p className="text-xl text-gray-600 mb-8">
          Complete design specifications, components, and implementation guides
        </p>
        <div className="flex gap-4 justify-center">
          <Link href="/design-system" className="btn-primary">
            Explore Design System →
          </Link>
          <Link href="/implementation" className="btn-secondary">
            Developer Guide
          </Link>
        </div>
      </div>

      {/* Quick Links Grid */}
      <div className="grid grid-cols-3 gap-6">
        <QuickLinkCard
          href="/design-system/colors"
          icon="🎨"
          title="Colors"
          description="Brand colors and semantic palette"
        />
        <QuickLinkCard
          href="/screens/dashboard"
          icon="📊"
          title="Screens"
          description="Detailed screen specifications"
        />
        <QuickLinkCard
          href="/research/market-analysis"
          icon="🔬"
          title="Research"
          description="Market insights and strategy"
        />
      </div>
    </div>
  )
}
```

---

### MDX Page Example (`app/design-system/colors/page.mdx`)

```mdx
---
title: Colors
description: Brand colors, semantic palette, and usage guidelines
---

# Colors

The Chatverce color system is built on a foundation of green (#16a34a) as the primary brand color, with a carefully crafted palette of neutrals and semantic colors.

## Primary Colors

<ColorSwatch
  name="Primary Green"
  hex="#16a34a"
  usage="Primary actions, links, brand elements"
/>

<ColorSwatch
  name="Primary Green Hover"
  hex="#15803d"
  usage="Hover states for primary elements"
/>

## Usage Guidelines

### Do's ✅
- Use primary green for all primary action buttons
- Use hover state for interactive elements
- Maintain 4.5:1 contrast ratio for text

### Don'ts ❌
- Don't use green for destructive actions
- Don't use multiple shades in same component
- Don't use green on green backgrounds

## Code Example

```tsx
// Using primary color
<button className="bg-primary hover:bg-primary-hover">
  Submit
</button>
```
```

---

### Sidebar Component (`components/Sidebar.tsx`)

```tsx
'use client'

import { useState } from 'react'
import Link from 'next/link'
import { usePathname } from 'next/navigation'

const navigation = [
  {
    title: 'Home',
    href: '/',
    icon: '🏠'
  },
  {
    title: 'Design System',
    icon: '🎨',
    items: [
      { title: 'Overview', href: '/design-system' },
      { title: 'Colors', href: '/design-system/colors' },
      { title: 'Typography', href: '/design-system/typography' },
      { title: 'Components', href: '/design-system/components' },
    ]
  },
  {
    title: 'Screens',
    icon: '📱',
    items: [
      { title: 'Dashboard', href: '/screens/dashboard' },
      { title: 'Conversations', href: '/screens/conversations' },
      { title: 'Chat View', href: '/screens/chat-view' },
    ]
  },
  // ... more sections
]

export function Sidebar() {
  const pathname = usePathname()
  const [expandedSections, setExpandedSections] = useState<string[]>([])

  return (
    <nav className="w-64 border-r border-gray-200 h-screen overflow-y-auto">
      <div className="p-6">
        <h2 className="font-semibold text-lg">Chatverce Design</h2>
      </div>
      
      <ul className="space-y-1 px-3">
        {navigation.map((section) => (
          <li key={section.title}>
            {section.items ? (
              <NavSection
                section={section}
                pathname={pathname}
                expanded={expandedSections.includes(section.title)}
                onToggle={() => {/* toggle logic */}}
              />
            ) : (
              <NavLink href={section.href} active={pathname === section.href}>
                {section.icon} {section.title}
              </NavLink>
            )}
          </li>
        ))}
      </ul>
    </nav>
  )
}
```

---

## Deliverables Checklist

### For Woz to Complete

**Phase 1** (Day 1):
- [ ] Next.js 16 project initialized
- [ ] Tailwind configured with design tokens
- [ ] Basic layout with sidebar working
- [ ] MDX rendering functional
- [ ] Routes created for all sections

**Phase 2** (Day 2):
- [ ] All 19 markdown files converted to MDX
- [ ] All files in correct routes
- [ ] Navigation sidebar populated
- [ ] Images/SVGs in public/ folder
- [ ] All pages accessible and rendering

**Phase 3** (Day 3):
- [ ] CodeBlock component with syntax highlighting
- [ ] BeforeAfter comparison component
- [ ] All MDX elements styled beautifully
- [ ] "On this page" sidebar
- [ ] Copy buttons on code blocks

**Phase 4** (Day 4):
- [ ] Search functionality working
- [ ] Cmd+K shortcut
- [ ] Smooth animations
- [ ] SEO meta tags
- [ ] Accessibility tested

**Phase 5** (Day 5):
- [ ] Deployed to GitHub Pages
- [ ] Custom domain configured (if needed)
- [ ] GitHub Actions for auto-deploy
- [ ] README documentation
- [ ] Tested on all devices

---

## Success Criteria

The site will be considered **successful** when:

1. ✅ **Beautiful** - Looks like a professional design system site
2. ✅ **Fast** - Loads in <1 second, smooth interactions
3. ✅ **Easy to navigate** - Find any spec in <10 seconds
4. ✅ **Developer-friendly** - Copy code easily, clear examples
5. ✅ **Mobile-ready** - Works perfectly on phone/tablet
6. ✅ **Accessible** - Keyboard nav, screen reader compatible
7. ✅ **Searchable** - Full-text search across all content
8. ✅ **Maintainable** - Easy to add new pages/update content

---

## Design Principles for the Site

**The site itself must exemplify our design principles**:

1. **Simplicity** - Clean layouts, no clutter
2. **Speed** - Instant page loads, smooth scrolling
3. **Clarity** - Obvious navigation, clear hierarchy
4. **Consistency** - Same patterns throughout
5. **Delight** - Subtle animations, perfect details

**This is our portfolio piece. It must be flawless.**

---

## Timeline Summary

| Phase | Duration | Deliverable |
|-------|----------|-------------|
| Phase 1: Setup | 6 hours | Working Next.js site |
| Phase 2: Content | 8 hours | All content migrated |
| Phase 3: Components | 8 hours | Beautiful UI |
| Phase 4: Features | 6 hours | Search, polish |
| Phase 5: Deploy | 4 hours | Live on GitHub Pages |
| **Total** | **32 hours** | **3-5 days** |

---

## Next Steps

**For Woz**:
1. Read this entire specification
2. Ask questions if anything is unclear
3. Create a new repo: `chatverce-design-docs`
4. Start Phase 1 (setup)
5. Share progress daily
6. Tag me for design reviews

**For Jony (me)**:
1. Provide design feedback during development
2. Review each phase before moving to next
3. Test final site before launch
4. Write launch announcement

---

**This is our chance to build something exemplary. Let's make it perfect.**

— Jony

---

**Document version**: 1.0  
**Last updated**: February 6, 2026, 10:30 AM IST  
**Status**: Ready for Woz to implement
