# Chatverce Component Library

**Comprehensive reference for all UI components**

---

## Table of Contents

1. [Buttons](#buttons)
2. [Inputs](#inputs)
3. [Dropdowns](#dropdowns)
4. [Status Pills](#status-pills)
5. [Avatars](#avatars)
6. [Cards](#cards)
7. [Tables](#tables)
8. [Empty States](#empty-states)
9. [Modals](#modals)
10. [Toasts](#toasts)

---

## Buttons

### Primary Button
**Use for**: Main actions (Create, Save, Send, etc.)

```css
.btn-primary {
  background: #16a34a;
  color: white;
  padding: 10px 16px;
  border-radius: 6px;
  font-size: 14px;
  font-weight: 500;
  height: 40px;
  border: none;
  cursor: pointer;
  transition: background 200ms ease-in-out;
}

.btn-primary:hover {
  background: #15803d;
}

.btn-primary:active {
  background: #166534;
}

.btn-primary:disabled {
  background: #86efac;
  cursor: not-allowed;
  opacity: 0.6;
}
```

**Example**:
```html
<button class="btn-primary">+ New Campaign</button>
```

---

### Secondary Button (Ghost)
**Use for**: Secondary actions, cancel, dismiss

```css
.btn-secondary {
  background: transparent;
  color: #374151;
  border: 1px solid #d1d5db;
  padding: 10px 16px;
  border-radius: 6px;
  font-size: 14px;
  font-weight: 500;
  height: 40px;
  cursor: pointer;
  transition: all 200ms ease-in-out;
}

.btn-secondary:hover {
  background: #f9fafb;
  border-color: #9ca3af;
}

.btn-secondary:active {
  background: #f3f4f6;
}
```

**Example**:
```html
<button class="btn-secondary">Cancel</button>
```

---

### Icon Button
**Use for**: Toolbar actions, close buttons

```css
.btn-icon {
  background: transparent;
  padding: 8px;
  border-radius: 6px;
  width: 36px;
  height: 36px;
  border: none;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: background 200ms ease-in-out;
}

.btn-icon:hover {
  background: #f3f4f6;
}

.btn-icon:active {
  background: #e5e7eb;
}
```

**Example**:
```html
<button class="btn-icon" aria-label="Close">
  <svg width="20" height="20"><!-- close icon --></svg>
</button>
```

---

### Button Sizes

```css
/* Small (32px height) */
.btn-sm {
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
}

/* Medium (40px height) - default */
.btn-md {
  height: 40px;
  padding: 10px 16px;
  font-size: 14px;
}

/* Large (48px height) */
.btn-lg {
  height: 48px;
  padding: 12px 20px;
  font-size: 15px;
}
```

---

## Inputs

### Text Input
**Use for**: Forms, search, filters

```css
.input {
  width: 100%;
  height: 40px;
  padding: 8px 12px;
  border: 1px solid #d1d5db;
  border-radius: 6px;
  font-size: 14px;
  color: #0a0a0a;
  background: white;
  transition: all 200ms ease-in-out;
}

.input:focus {
  outline: none;
  border-color: #16a34a;
  box-shadow: 0 0 0 3px rgba(22, 163, 74, 0.1);
}

.input:disabled {
  background: #f9fafb;
  color: #9ca3af;
  cursor: not-allowed;
}

.input::placeholder {
  color: #9ca3af;
}
```

**Example**:
```html
<input 
  type="text" 
  class="input" 
  placeholder="Search conversations..."
/>
```

---

### Input with Label

```css
.input-group {
  display: flex;
  flex-direction: column;
  gap: 6px;
}

.input-label {
  font-size: 13px;
  font-weight: 500;
  color: #374151;
}

.input-hint {
  font-size: 12px;
  color: #6b7280;
  margin-top: 4px;
}

.input-error {
  font-size: 12px;
  color: #dc2626;
  margin-top: 4px;
}
```

**Example**:
```html
<div class="input-group">
  <label class="input-label" for="campaign-name">Campaign Name</label>
  <input 
    type="text" 
    id="campaign-name"
    class="input" 
    placeholder="Enter campaign name..."
  />
  <span class="input-hint">Choose a descriptive name</span>
</div>
```

---

### Textarea

```css
.textarea {
  width: 100%;
  min-height: 100px;
  padding: 12px;
  border: 1px solid #d1d5db;
  border-radius: 6px;
  font-size: 14px;
  color: #0a0a0a;
  background: white;
  resize: vertical;
  font-family: inherit;
  transition: all 200ms ease-in-out;
}

.textarea:focus {
  outline: none;
  border-color: #16a34a;
  box-shadow: 0 0 0 3px rgba(22, 163, 74, 0.1);
}
```

---

## Dropdowns

### Basic Dropdown

```css
.dropdown {
  position: relative;
  display: inline-block;
}

.dropdown-trigger {
  min-width: 160px;
  height: 40px;
  padding: 0 36px 0 12px;
  border: 1px solid #d1d5db;
  border-radius: 6px;
  background: white;
  font-size: 14px;
  color: #0a0a0a;
  cursor: pointer;
  display: flex;
  align-items: center;
  position: relative;
  transition: all 200ms ease-in-out;
}

.dropdown-trigger:hover {
  border-color: #9ca3af;
}

.dropdown-trigger::after {
  content: '';
  position: absolute;
  right: 12px;
  width: 0;
  height: 0;
  border-left: 4px solid transparent;
  border-right: 4px solid transparent;
  border-top: 5px solid #6b7280;
}

.dropdown-menu {
  position: absolute;
  top: calc(100% + 4px);
  left: 0;
  min-width: 100%;
  background: white;
  border: 1px solid #e5e7eb;
  border-radius: 8px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  padding: 4px;
  display: none;
  z-index: 100;
}

.dropdown.open .dropdown-menu {
  display: block;
}

.dropdown-item {
  padding: 8px 12px;
  font-size: 14px;
  color: #374151;
  border-radius: 4px;
  cursor: pointer;
  transition: background 150ms ease-in-out;
}

.dropdown-item:hover {
  background: #f9fafb;
}

.dropdown-item.selected {
  background: #f0fdf4;
  color: #16a34a;
  font-weight: 500;
}
```

---

## Status Pills

### Pill Variants

```css
.pill {
  display: inline-flex;
  align-items: center;
  padding: 4px 10px;
  border-radius: 12px;
  font-size: 12px;
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 0.025em;
}

/* Pending / Warning */
.pill-pending {
  background: #fef3c7;
  color: #92400e;
}

/* Qualified / Success */
.pill-qualified {
  background: #d1fae5;
  color: #065f46;
}

/* Completed */
.pill-completed {
  background: #d1fae5;
  color: #065f46;
}

/* Paused / Inactive */
.pill-paused {
  background: #e5e7eb;
  color: #374151;
}

/* Active */
.pill-active {
  background: #dbeafe;
  color: #1e40af;
}

/* Failed / Error */
.pill-failed {
  background: #fee2e2;
  color: #991b1b;
}
```

**Example**:
```html
<span class="pill pill-pending">PENDING</span>
<span class="pill pill-qualified">QUALIFIED</span>
```

---

## Avatars

### Avatar Sizes

```css
.avatar {
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: 600;
  color: white;
  flex-shrink: 0;
}

.avatar-sm {
  width: 28px;
  height: 28px;
  font-size: 12px;
}

.avatar-md {
  width: 40px;
  height: 40px;
  font-size: 16px;
}

.avatar-lg {
  width: 48px;
  height: 48px;
  font-size: 18px;
}

.avatar-xl {
  width: 64px;
  height: 64px;
  font-size: 24px;
}
```

### Avatar Colors (Generated)

Use a hash function to generate consistent colors per user:

```javascript
function getAvatarColor(name) {
  const colors = [
    '#16a34a', // green
    '#3b82f6', // blue
    '#f59e0b', // orange
    '#ec4899', // pink
    '#8b5cf6', // purple
    '#14b8a6', // teal
    '#f97316', // red-orange
    '#06b6d4', // cyan
  ];
  
  const hash = name.split('').reduce((acc, char) => {
    return char.charCodeAt(0) + ((acc << 5) - acc);
  }, 0);
  
  return colors[Math.abs(hash) % colors.length];
}
```

**Example**:
```html
<div class="avatar avatar-md" style="background: #16a34a;">
  V
</div>
```

---

## Cards

### Basic Card

```css
.card {
  background: white;
  border: 1px solid #e5e7eb;
  border-radius: 8px;
  padding: 16px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
  transition: all 200ms ease-in-out;
}

.card:hover {
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.08);
}

.card-header {
  font-size: 16px;
  font-weight: 600;
  color: #0a0a0a;
  margin-bottom: 12px;
}

.card-body {
  font-size: 14px;
  color: #374151;
  line-height: 1.6;
}

.card-footer {
  margin-top: 16px;
  padding-top: 16px;
  border-top: 1px solid #f3f4f6;
  display: flex;
  gap: 8px;
  justify-content: flex-end;
}
```

---

## Tables

### Data Table

```css
.table-container {
  background: white;
  border: 1px solid #e5e7eb;
  border-radius: 8px;
  overflow: hidden;
}

.table {
  width: 100%;
  border-collapse: collapse;
}

.table thead {
  background: #f9fafb;
  border-bottom: 1px solid #e5e7eb;
}

.table th {
  padding: 12px 16px;
  text-align: left;
  font-size: 12px;
  font-weight: 600;
  color: #6b7280;
  text-transform: uppercase;
  letter-spacing: 0.05em;
}

.table tbody tr {
  border-bottom: 1px solid #f3f4f6;
  transition: background 150ms ease-in-out;
}

.table tbody tr:last-child {
  border-bottom: none;
}

.table tbody tr:hover {
  background: #f9fafb;
}

.table td {
  padding: 16px;
  font-size: 14px;
  color: #374151;
  vertical-align: middle;
}

.table td:first-child {
  font-weight: 500;
  color: #0a0a0a;
}
```

---

## Empty States

### Structure

```css
.empty-state {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 64px 32px;
  max-width: 480px;
  margin: 0 auto;
}

.empty-state-illustration {
  width: 200px;
  height: 150px;
  margin-bottom: 24px;
}

.empty-state-title {
  font-size: 20px;
  font-weight: 600;
  color: #0a0a0a;
  margin-bottom: 8px;
}

.empty-state-description {
  font-size: 15px;
  color: #6b7280;
  line-height: 1.6;
  margin-bottom: 24px;
}

.empty-state-actions {
  display: flex;
  gap: 12px;
  flex-wrap: wrap;
  justify-content: center;
}
```

**Example**:
```html
<div class="empty-state">
  <img 
    src="assets/illustrations/empty-inbox.svg" 
    class="empty-state-illustration"
    alt="Empty inbox"
  />
  <h3 class="empty-state-title">No conversations yet</h3>
  <p class="empty-state-description">
    Start a new conversation or wait for incoming messages.
  </p>
  <div class="empty-state-actions">
    <button class="btn-primary">+ New Conversation</button>
    <button class="btn-secondary">Import Contacts</button>
  </div>
</div>
```

---

## Modals

### Modal Structure

```css
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1000;
  animation: fadeIn 200ms ease-out;
}

@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}

.modal {
  background: white;
  border-radius: 12px;
  box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1);
  max-width: 500px;
  width: 90%;
  max-height: 90vh;
  overflow: auto;
  animation: slideUp 200ms ease-out;
}

@keyframes slideUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.modal-header {
  padding: 20px 24px;
  border-bottom: 1px solid #e5e7eb;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.modal-title {
  font-size: 18px;
  font-weight: 600;
  color: #0a0a0a;
}

.modal-body {
  padding: 24px;
}

.modal-footer {
  padding: 16px 24px;
  border-top: 1px solid #e5e7eb;
  display: flex;
  gap: 12px;
  justify-content: flex-end;
}
```

---

## Toasts

### Toast Notification

```css
.toast-container {
  position: fixed;
  top: 24px;
  right: 24px;
  z-index: 2000;
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.toast {
  min-width: 320px;
  background: white;
  border: 1px solid #e5e7eb;
  border-radius: 8px;
  padding: 16px;
  box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
  display: flex;
  align-items: flex-start;
  gap: 12px;
  animation: slideInRight 300ms ease-out;
}

@keyframes slideInRight {
  from {
    opacity: 0;
    transform: translateX(100%);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

.toast-success {
  border-left: 4px solid #16a34a;
}

.toast-error {
  border-left: 4px solid #dc2626;
}

.toast-warning {
  border-left: 4px solid #f59e0b;
}

.toast-info {
  border-left: 4px solid #3b82f6;
}

.toast-content {
  flex: 1;
}

.toast-title {
  font-size: 14px;
  font-weight: 600;
  color: #0a0a0a;
  margin-bottom: 4px;
}

.toast-message {
  font-size: 13px;
  color: #6b7280;
  line-height: 1.5;
}

.toast-close {
  cursor: pointer;
  color: #9ca3af;
  transition: color 150ms;
}

.toast-close:hover {
  color: #374151;
}
```

---

## Usage Guidelines

### Spacing
Use consistent spacing from the design system:
- **Small gap**: 8px
- **Medium gap**: 16px
- **Large gap**: 24px

### Transitions
All interactive elements should transition smoothly:
```css
transition: all 200ms ease-in-out;
```

### Focus States
Always provide visible focus indicators:
```css
:focus-visible {
  outline: 2px solid #16a34a;
  outline-offset: 2px;
}
```

### Accessibility
- Use semantic HTML (`<button>`, not `<div onclick>`)
- Provide `aria-label` for icon-only buttons
- Ensure sufficient color contrast (WCAG AA)
- Support keyboard navigation

---

**Last Updated**: February 6, 2026  
**Version**: 1.0  
**Maintainer**: Jony Ive, Chief Design Officer
