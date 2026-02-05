# Chatverce Design System

## Color Palette

### Primary Colors
- **Primary Green**: `#16a34a` (rgb(22, 163, 74))
  - Use for: All primary action buttons, active states, key indicators
  - Hover: `#15803d`
  - Disabled: `#86efac` (50% opacity)

- **Neutral Grey Scale**:
  - Grey 950 (Text Primary): `#0a0a0a`
  - Grey 700 (Text Secondary): `#374151`
  - Grey 500 (Text Tertiary): `#6b7280`
  - Grey 300 (Borders): `#d1d5db`
  - Grey 100 (Backgrounds): `#f3f4f6`
  - Grey 50 (Surfaces): `#f9fafb`

- **Status Colors**:
  - Success: `#16a34a` (same as primary)
  - Warning: `#f59e0b`
  - Error: `#dc2626`
  - Info: `#3b82f6`

### Semantic Usage
- **Unread indicator**: Primary Green
- **Status pills**: 
  - PENDING: `#fef3c7` background, `#92400e` text
  - QUALIFIED: `#d1fae5` background, `#065f46` text
  - COMPLETED: `#d1fae5` background, `#065f46` text
  - PAUSED: `#e5e7eb` background, `#374151` text

## Typography

### Font Stack
```css
font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Helvetica Neue', Arial, sans-serif;
```

### Scale
- **Display**: 32px / 2rem, weight 600, line-height 1.2
- **H1**: 24px / 1.5rem, weight 600, line-height 1.3
- **H2**: 20px / 1.25rem, weight 600, line-height 1.4
- **H3**: 18px / 1.125rem, weight 600, line-height 1.4
- **Body Large**: 16px / 1rem, weight 400, line-height 1.5
- **Body**: 14px / 0.875rem, weight 400, line-height 1.5
- **Body Small**: 13px / 0.8125rem, weight 400, line-height 1.5
- **Caption**: 12px / 0.75rem, weight 400, line-height 1.4

### Weights
- Regular: 400
- Medium: 500
- Semibold: 600
- Bold: 700

## Spacing System

Use 4px base unit. Common values:
- `xs`: 4px
- `sm`: 8px
- `md`: 12px
- `base`: 16px
- `lg`: 20px
- `xl`: 24px
- `2xl`: 32px
- `3xl`: 40px
- `4xl`: 48px

## Components

### Buttons

#### Primary
```css
background: #16a34a
color: white
padding: 10px 16px
border-radius: 6px
font-size: 14px
font-weight: 500
height: 40px
```

Hover: `background: #15803d`

#### Secondary (Ghost)
```css
background: transparent
color: #374151
border: 1px solid #d1d5db
padding: 10px 16px
border-radius: 6px
font-size: 14px
font-weight: 500
height: 40px
```

Hover: `background: #f9fafb`

#### Icon Button
```css
background: transparent
padding: 8px
border-radius: 6px
width: 36px
height: 36px
```

Hover: `background: #f3f4f6`

### Status Pills
```css
display: inline-flex
padding: 4px 10px
border-radius: 12px
font-size: 12px
font-weight: 500
text-transform: uppercase
letter-spacing: 0.025em
```

### Cards
```css
background: white
border: 1px solid #e5e7eb
border-radius: 8px
padding: 16px
box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05)
```

### Input Fields
```css
border: 1px solid #d1d5db
border-radius: 6px
padding: 8px 12px
height: 40px
font-size: 14px
background: white
```

Focus: `border-color: #16a34a, box-shadow: 0 0 0 3px rgba(22, 163, 74, 0.1)`

## Layout

### Sidebar
- Width (collapsed): 64px
- Width (expanded): 240px
- Background: `#ffffff`
- Border right: `1px solid #e5e7eb`

### Top Bar
- Height: 64px
- Background: `#ffffff`
- Border bottom: `1px solid #e5e7eb`
- Padding: `0 24px`

### Main Content
- Max width: none (full width within container)
- Padding: `24px 32px`
- Background: `#f9fafb`

## Elevation (Shadows)

- **Level 1**: `box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05)`
- **Level 2**: `box-shadow: 0 2px 4px rgba(0, 0, 0, 0.06)`
- **Level 3**: `box-shadow: 0 4px 6px rgba(0, 0, 0, 0.07)`
- **Level 4**: `box-shadow: 0 8px 16px rgba(0, 0, 0, 0.08)`

## Animation

All transitions: `200ms ease-in-out`

Hover states, button interactions, dropdown opens: 200ms
Loading states, content transitions: 300ms
Modal/overlay appearances: 200ms with ease-out
