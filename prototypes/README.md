# Chatverce UI Prototypes

**Interactive HTML/CSS mockups for the Chatverce redesign**

---

## Quick Start

Open `index.html` in your browser to see all prototypes and documentation.

```bash
cd designs/prototypes
open index.html
```

Or start a local server:

```bash
# Python
python3 -m http.server 8000

# Node
npx serve

# Then visit: http://localhost:8000
```

---

## What's Included

### Prototypes
- **chat-view.html** — Conversation interface (active + expired states)
- **conversations-list.html** — Inbox sidebar with hierarchy
- **crm-table.html** — Leads table with improved spacing
- **index.html** — Navigation and documentation

### Design System
- **assets/css/design-system.css** — All design tokens (colors, typography, spacing, components)

---

## Key Features

### 1. Pixel-Perfect
Every measurement matches the detailed specifications exactly. No guesswork.

### 2. Interactive
- Hover states
- Click interactions
- Toggle between views (active/expired chat)
- Tab switching (all/unread conversations)
- Row selection (CRM table)

### 3. Developer-Ready
- Inspect element to see exact CSS
- Copy class names and styles directly
- All styles use CSS variables
- Reusable component patterns

### 4. Design System
All prototypes reference `design-system.css` with:
- Color variables (`--color-primary`, `--color-grey-500`, etc.)
- Typography scale (`--font-size-body`, `--font-weight-semibold`, etc.)
- Spacing system (`--space-base`, `--space-xl`, etc.)
- Reusable component classes (`.btn-primary`, `.pill-pending`, etc.)

---

## What's Fixed

### Critical Issues
1. **Chat View** — Removed promotional banner blocking conversation area
2. **Button Consistency** — All primary actions now use green (#16a34a)
3. **Visual Hierarchy** — Bold names, lighter timestamps, clear unread indicators

### Important Improvements
4. **Table Spacing** — Row height increased from 48px to 64px
5. **Empty Cells** — Whitespace instead of "--" dashes
6. **Headers** — Bold, uppercase, visually distinct from content
7. **Interactions** — Smooth hover states and transitions

---

## File Structure

```
prototypes/
├── index.html                    # Navigation + docs
├── chat-view.html                # Conversation interface
├── conversations-list.html       # Inbox sidebar
├── crm-table.html                # Leads table
├── README.md                     # This file
└── assets/
    └── css/
        └── design-system.css     # Design tokens
```

---

## How to Use These

### For Designers
1. Open in browser to review visual design
2. Test interactions (hover, click, scroll)
3. Verify states (active/expired, read/unread)
4. Check spacing and alignment

### For Developers
1. Open in browser
2. Right-click → Inspect Element
3. See exact CSS for any component
4. Copy styles into your codebase
5. Reference `design-system.css` for variables

### For Product Managers
1. Open `index.html` for overview
2. Click through each prototype
3. Review what's fixed vs original design
4. Share links with stakeholders

---

## Browser Support

**Tested on:**
- Chrome 120+
- Firefox 120+
- Safari 17+
- Edge 120+

**Requirements:**
- CSS Variables support
- Flexbox support
- Grid support
- Modern JavaScript (ES6+)

---

## Design System Quick Reference

### Colors
```css
--color-primary: #16a34a         /* Green - all primary actions */
--color-grey-950: #0a0a0a        /* Text primary */
--color-grey-700: #374151        /* Text secondary */
--color-grey-500: #6b7280        /* Text tertiary */
--color-grey-300: #d1d5db        /* Borders */
--color-grey-50: #f9fafb         /* Backgrounds */
```

### Typography
```css
--font-size-body: 0.875rem       /* 14px */
--font-size-body-large: 1rem     /* 16px */
--font-size-caption: 0.75rem     /* 12px */
--font-weight-regular: 400
--font-weight-medium: 500
--font-weight-semibold: 600
```

### Spacing
```css
--space-sm: 8px
--space-base: 16px
--space-lg: 20px
--space-xl: 24px
--space-2xl: 32px
```

### Components
```css
.btn-primary              /* Green button */
.btn-secondary            /* Outline button */
.btn-ghost                /* Transparent button */
.pill-pending             /* Yellow status pill */
.pill-qualified           /* Green status pill */
.avatar-md                /* 40px avatar */
```

---

## Next Steps

1. **Review** — Open each prototype and test interactions
2. **Inspect** — Use browser DevTools to see exact styles
3. **Reference** — Check `../IMPLEMENTATION-GUIDE.md` for priorities
4. **Implement** — Start with Chat View (most critical)

---

## Questions?

- Jony Ive: jony@siharilabs.com
- Clawdbot agent: `jony`
- Design specs: `designs/*.md`

---

## Version

**1.0** — February 4, 2026

Initial release with critical prototypes:
- Chat view (active + expired states)
- Conversations list (with filters)
- CRM table (with improved spacing)

---

Built with precision. Every pixel matters.

— Jony
