# Chatverce Animation & Transition Specifications

**Motion design creates understanding and delight**

---

## Philosophy

Animation should:
1. **Explain** - Show relationships and cause-and-effect
2. **Guide** - Direct attention to important changes
3. **Reassure** - Provide feedback that actions succeeded
4. **Never distract** - Subtle, purposeful, fast

---

## Timing Standards

### Micro-interactions (< 100ms)
**Use for**: Button presses, checkbox toggles, radio selections

```css
transition: all 100ms cubic-bezier(0.4, 0, 0.2, 1);
```

**Example**:
```css
.btn-primary:active {
  transform: scale(0.98);
  transition: transform 100ms cubic-bezier(0.4, 0, 0.2, 1);
}
```

---

### Standard Transitions (200ms)
**Use for**: Hover states, color changes, opacity, most UI feedback

```css
transition: all 200ms ease-in-out;
```

**Examples**:
```css
/* Button hover */
.btn-primary {
  transition: background 200ms ease-in-out;
}

/* Input focus */
.input {
  transition: border-color 200ms ease-in-out,
              box-shadow 200ms ease-in-out;
}

/* Dropdown appearance */
.dropdown-menu {
  opacity: 0;
  transform: translateY(-8px);
  transition: opacity 200ms ease-out,
              transform 200ms ease-out;
}

.dropdown-menu.open {
  opacity: 1;
  transform: translateY(0);
}
```

---

### Medium Transitions (300ms)
**Use for**: Modals, overlays, content swapping

```css
transition: all 300ms ease-out;
```

**Examples**:
```css
/* Modal entrance */
.modal {
  animation: modalSlideUp 300ms cubic-bezier(0.16, 1, 0.3, 1);
}

@keyframes modalSlideUp {
  from {
    opacity: 0;
    transform: translateY(24px) scale(0.96);
  }
  to {
    opacity: 1;
    transform: translateY(0) scale(1);
  }
}

/* Toast notification */
.toast {
  animation: toastSlideIn 300ms cubic-bezier(0.16, 1, 0.3, 1);
}

@keyframes toastSlideIn {
  from {
    opacity: 0;
    transform: translateX(100%);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}
```

---

## Easing Functions

### Standard Easing (Most Common)
```css
ease-in-out /* Use for bi-directional transitions */
```

### Emphasis Easing (Attention-grabbing)
```css
cubic-bezier(0.16, 1, 0.3, 1) /* "easeOutExpo" - fast then slow */
```
**Use for**: Modals, toasts, important notifications

### Subtle Easing (Background changes)
```css
cubic-bezier(0.4, 0, 0.2, 1) /* "easeInOut" - smooth acceleration */
```
**Use for**: List reordering, content loading

### Exit Easing (Dismissals)
```css
cubic-bezier(0.4, 0, 1, 1) /* "easeIn" - slow then fast */
```
**Use for**: Closing modals, dismissing notifications

---

## Specific Component Animations

### Buttons

#### Press Animation
```css
.btn-primary:active {
  transform: scale(0.98);
  transition: transform 100ms cubic-bezier(0.4, 0, 0.2, 1);
}
```

#### Ripple Effect (Optional Enhancement)
```css
.btn-primary {
  position: relative;
  overflow: hidden;
}

.btn-primary::after {
  content: '';
  position: absolute;
  top: 50%;
  left: 50%;
  width: 0;
  height: 0;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.3);
  transform: translate(-50%, -50%);
  transition: width 600ms, height 600ms;
}

.btn-primary:active::after {
  width: 300px;
  height: 300px;
}
```

---

### Dropdowns

```css
.dropdown-menu {
  opacity: 0;
  transform: translateY(-8px);
  pointer-events: none;
  transition: opacity 200ms ease-out,
              transform 200ms cubic-bezier(0.16, 1, 0.3, 1);
}

.dropdown.open .dropdown-menu {
  opacity: 1;
  transform: translateY(0);
  pointer-events: auto;
}
```

---

### Modals

#### Overlay Fade In
```css
.modal-overlay {
  animation: overlayFadeIn 200ms ease-out;
}

@keyframes overlayFadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}
```

#### Modal Slide Up + Scale
```css
.modal {
  animation: modalEnter 300ms cubic-bezier(0.16, 1, 0.3, 1);
}

@keyframes modalEnter {
  from {
    opacity: 0;
    transform: translateY(24px) scale(0.96);
  }
  to {
    opacity: 1;
    transform: translateY(0) scale(1);
  }
}
```

#### Exit Animation
```css
.modal.closing {
  animation: modalExit 200ms cubic-bezier(0.4, 0, 1, 1);
}

@keyframes modalExit {
  from {
    opacity: 1;
    transform: translateY(0) scale(1);
  }
  to {
    opacity: 0;
    transform: translateY(-16px) scale(0.98);
  }
}
```

---

### Toasts

#### Slide In from Right
```css
.toast {
  animation: toastSlideIn 300ms cubic-bezier(0.16, 1, 0.3, 1);
}

@keyframes toastSlideIn {
  from {
    opacity: 0;
    transform: translateX(100%);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}
```

#### Slide Out to Right
```css
.toast.removing {
  animation: toastSlideOut 200ms cubic-bezier(0.4, 0, 1, 1);
}

@keyframes toastSlideOut {
  from {
    opacity: 1;
    transform: translateX(0);
  }
  to {
    opacity: 0;
    transform: translateX(100%);
  }
}
```

---

### Tables

#### Row Hover
```css
.table tbody tr {
  transition: background 150ms ease-in-out;
}

.table tbody tr:hover {
  background: #f9fafb;
}
```

#### Row Selection
```css
.table tbody tr.selected {
  background: #f0fdf4;
  transition: background 200ms ease-out;
}
```

---

### Tabs

```css
.tab {
  position: relative;
  transition: color 200ms ease-in-out;
}

.tab::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  height: 2px;
  background: #16a34a;
  transform: scaleX(0);
  transition: transform 250ms cubic-bezier(0.16, 1, 0.3, 1);
}

.tab.active::after {
  transform: scaleX(1);
}
```

---

### Loading Spinners

#### Rotating Spinner
```css
.spinner {
  width: 24px;
  height: 24px;
  border: 3px solid #f3f4f6;
  border-top-color: #16a34a;
  border-radius: 50%;
  animation: spin 800ms linear infinite;
}

@keyframes spin {
  to { transform: rotate(360deg); }
}
```

#### Pulsing Dots
```css
.dots {
  display: flex;
  gap: 6px;
}

.dot {
  width: 8px;
  height: 8px;
  background: #9ca3af;
  border-radius: 50%;
  animation: pulse 1.4s ease-in-out infinite;
}

.dot:nth-child(1) { animation-delay: 0ms; }
.dot:nth-child(2) { animation-delay: 200ms; }
.dot:nth-child(3) { animation-delay: 400ms; }

@keyframes pulse {
  0%, 80%, 100% {
    opacity: 0.4;
    transform: scale(0.8);
  }
  40% {
    opacity: 1;
    transform: scale(1);
  }
}
```

---

### Skeleton Screens

```css
.skeleton {
  background: linear-gradient(
    90deg,
    #f3f4f6 0%,
    #e5e7eb 50%,
    #f3f4f6 100%
  );
  background-size: 200% 100%;
  animation: shimmer 1.5s ease-in-out infinite;
}

@keyframes shimmer {
  0% { background-position: 200% 0; }
  100% { background-position: -200% 0; }
}
```

**Example Usage**:
```html
<div class="skeleton" style="width: 100%; height: 20px; border-radius: 4px;"></div>
<div class="skeleton" style="width: 80%; height: 16px; border-radius: 4px; margin-top: 8px;"></div>
```

---

## Scroll Animations

### Smooth Scrolling
```css
html {
  scroll-behavior: smooth;
}

/* For programmatic scrolling with custom easing */
element.scrollTo({
  top: 0,
  behavior: 'smooth'
});
```

### Fade In on Scroll (Optional)
```css
.fade-in {
  opacity: 0;
  transform: translateY(20px);
  transition: opacity 400ms ease-out,
              transform 400ms ease-out;
}

.fade-in.visible {
  opacity: 1;
  transform: translateY(0);
}
```

**JavaScript**:
```javascript
const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add('visible');
    }
  });
}, { threshold: 0.1 });

document.querySelectorAll('.fade-in').forEach(el => {
  observer.observe(el);
});
```

---

## Accessibility Considerations

### Respect `prefers-reduced-motion`
```css
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```

### Focus Indicators
```css
:focus-visible {
  outline: 2px solid #16a34a;
  outline-offset: 2px;
  transition: outline-offset 150ms ease-out;
}
```

---

## Performance Tips

### Use `transform` and `opacity`
These properties are GPU-accelerated and perform best:
```css
/* ✅ GOOD */
.element {
  transform: translateY(10px);
  opacity: 0.5;
}

/* ❌ AVOID */
.element {
  top: 10px;
  margin-top: 10px;
}
```

### Use `will-change` Sparingly
```css
/* Only for elements that will definitely animate soon */
.modal {
  will-change: transform, opacity;
}

/* Remove after animation completes */
.modal.visible {
  will-change: auto;
}
```

### Avoid Animating Expensive Properties
```css
/* ❌ AVOID - causes layout recalculation */
.element {
  transition: width 300ms;
}

/* ✅ BETTER - use transform scale */
.element {
  transition: transform 300ms;
}
```

---

## Quick Reference

| Duration | Use Case | Easing |
|----------|----------|--------|
| 100ms | Micro-interactions | `cubic-bezier(0.4, 0, 0.2, 1)` |
| 200ms | Hover, focus, color | `ease-in-out` |
| 300ms | Modals, toasts | `cubic-bezier(0.16, 1, 0.3, 1)` |
| 200ms | Exit animations | `cubic-bezier(0.4, 0, 1, 1)` |

---

## Testing Checklist

Before shipping animations:

- [ ] All transitions under 400ms (except special cases)
- [ ] Easing curves feel natural
- [ ] `prefers-reduced-motion` respected
- [ ] No janky performance (60fps maintained)
- [ ] Animations convey meaning, not just decoration
- [ ] Focus states remain visible during transitions

---

**Remember**: Animation should enhance understanding, not complicate it. When in doubt, go faster and more subtle.

---

**Last Updated**: February 6, 2026  
**Version**: 1.0  
**Maintainer**: Jony Ive, Chief Design Officer
