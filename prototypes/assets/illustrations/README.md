# Chatverce UI Illustrations

SVG illustrations for empty states and key UI moments.

## Files

### Empty States
- **dashboard-welcome.svg** (240×180) - Connected channels hub concept
- **ai-agents.svg** (240×180) - Robot builder with tool icons
- **empty-chat.svg** (200×150) - Message bubbles (conversation placeholder)
- **empty-crm.svg** (200×150) - Contact cards with add icon
- **empty-campaigns.svg** (200×150) - Megaphone with broadcast waves
- **empty-inbox.svg** (160×120) - Inbox tray with envelope

## Design Principles

### Color Palette
All illustrations use design system colors:
- **Primary green**: `#16a34a`
- **Light green backgrounds**: `#f0fdf4`, `#dcfce7`
- **Neutral greys**: `#f3f4f6`, `#d1d5db`, `#6b7280`
- **Accent colors**: `#3b82f6` (blue), `#f59e0b` (orange), `#ec4899` (pink)

### Style
- **Clean and minimal** - No unnecessary detail
- **Flat design** - Limited use of gradients/shadows
- **Rounded corners** - 8px-12px border radius
- **Consistent stroke width** - 2-2.5px for outlines
- **Purposeful** - Each element communicates function

### Size Guidelines
- **Large empty states** (Dashboard, AI Agents): 240×180px
- **Medium empty states** (Chat, CRM, Campaigns): 200×150px
- **Small empty states** (Inbox): 160×120px

## Usage

### In HTML
```html
<img src="assets/illustrations/dashboard-welcome.svg" alt="Connected channels" />
```

### As Background
```css
.empty-state {
  background-image: url('assets/illustrations/empty-chat.svg');
  background-repeat: no-repeat;
  background-position: center;
  background-size: contain;
}
```

### Inline SVG
Copy the SVG code directly into HTML for full CSS control:
```html
<div class="empty-state">
  <svg width="240" height="180" viewBox="0 0 240 180" fill="none">
    <!-- SVG content -->
  </svg>
</div>
```

## Customization

All SVGs can be customized:
- **Colors**: Replace hex values in `fill` and `stroke` attributes
- **Size**: Adjust `width` and `height` (viewBox preserves aspect ratio)
- **Animation**: Add CSS animations to individual elements

## Accessibility

When using illustrations:
- Add meaningful `alt` text for `<img>` tags
- Use `aria-label` for inline SVGs
- Ensure illustrations enhance, don't replace, text content

Example:
```html
<img 
  src="assets/illustrations/empty-inbox.svg" 
  alt="Empty inbox illustration showing an envelope" 
  aria-hidden="true"
/>
<p>No conversations yet. Start a new conversation to get started.</p>
```

---

**Created**: February 6, 2026  
**Designer**: Jony Ive  
**License**: Proprietary (Sihari Labs)
