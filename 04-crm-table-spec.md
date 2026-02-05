# CRM Leads Table Specification

## Current Problem
- Dense rows with no breathing room
- Column headers look identical to content
- Multiple "Vicky Kumar Maurya" entries hard to distinguish
- "--" dashes add visual noise
- Truncated columns due to scrollbar placement

## Solution Overview
Add vertical space, strengthen header hierarchy, use whitespace instead of dashes, add hover states, ensure full content visibility.

---

## Layout Structure

```
┌────────────────────────────────────────────────────────────────────────────────┐
│ Leads                                            [Import] [+ New Lead]         │
│ Manage and qualify your leads                                                  │
├────────────────────────────────────────────────────────────────────────────────┤
│ 🔍 Search leads...    [All Sources ▼] [All Statuses ▼] [All Assignees ▼]     │
├────────────────────────────────────────────────────────────────────────────────┤
│ ☐  Name            Phone          Email               Source    Status  Score │
├────────────────────────────────────────────────────────────────────────────────┤
│ ☐  Anurag          8746453524     anu@gmail.com       —         PENDING  —    │
│ ☐  dev             +919516673201  rathore            —         PENDING  —    │
│ ☐  Sandeep         +919044585766  —                  whatsApp  PENDING  —    │
│ ...                                                                            │
└────────────────────────────────────────────────────────────────────────────────┘
```

---

## Page Header

### Container
- Padding: `24px 32px`
- Background: `#ffffff`
- Border bottom: `1px solid #e5e7eb`

### Layout (Flexbox: justify-between, align-center)

#### Left Section
- **Title**: `"Leads"`
  - Font size: `24px`
  - Weight: `600`
  - Color: `#0a0a0a`
  - Margin bottom: `4px`

- **Subtitle**: `"Manage and qualify your leads"`
  - Font size: `14px`
  - Weight: `400`
  - Color: `#6b7280`

#### Right Section (Flexbox, gap 12px)
- **Import Button**:
  - Background: `transparent`
  - Border: `1px solid #d1d5db`
  - Color: `#374151`
  - Padding: `10px 16px`
  - Border radius: `6px`
  - Font size: `14px`
  - Weight: `500`
  - Height: `40px`
  - Icon: `↑` before text

- **+ New Lead Button**:
  - Background: `#16a34a`
  - Color: `white`
  - Padding: `10px 16px`
  - Border radius: `6px`
  - Font size: `14px`
  - Weight: `500`
  - Height: `40px`

---

## Filters Bar

### Container
- Padding: `16px 32px`
- Background: `#f9fafb`
- Border bottom: `1px solid #e5e7eb`

### Layout (Flexbox, gap 12px)

#### Search Input
- Width: `320px`
- Height: `40px`
- Border: `1px solid #d1d5db`
- Border radius: `6px`
- Padding: `0 12px 0 36px`
- Font size: `14px`
- Background: `white`
- Placeholder: `"Search leads..."`
- Icon: `🔍` positioned absolute left `12px`

Focus state: `border-color: #16a34a, box-shadow: 0 0 0 3px rgba(22, 163, 74, 0.1)`

#### Filter Dropdowns
Each dropdown:
- Height: `40px`
- Min width: `160px`
- Border: `1px solid #d1d5db`
- Border radius: `6px`
- Padding: `0 32px 0 12px`
- Font size: `14px`
- Background: `white`
- Arrow icon: `▼` positioned absolute right `12px`

Options:
1. `"All Sources"` → [All, whatsApp, email, web, manual]
2. `"All Statuses"` → [All, PENDING, QUALIFIED, CONTACTED, CONVERTED]
3. `"All Assignees"` → [All, Unassigned, User names...]

---

## Table

### Container
- Background: `#ffffff`
- Border: `1px solid #e5e7eb`
- Border radius: `8px`
- Margin: `24px 32px 32px 32px`
- Overflow: `hidden`

### Table Element
```css
width: 100%
border-collapse: collapse
```

---

## Table Header

### Header Row
- Background: `#f9fafb`
- Border bottom: `2px solid #e5e7eb`
- Height: `48px`

### Header Cells
```css
padding: 12px 16px
text-align: left
font-size: 13px
font-weight: 600
color: #374151
text-transform: uppercase
letter-spacing: 0.05em
```

First cell (checkbox):
```css
width: 48px
padding: 12px 16px
```

Column widths:
- Checkbox: `48px`
- Name: `18%`
- Phone: `16%`
- Email: `20%`
- Source: `12%`
- Status: `12%`
- Score: `10%`
- Assigned: `16%`
- Created: `14%`

---

## Table Body

### Row Specifications

#### Standard Row
```css
height: 64px
border-bottom: 1px solid #f3f4f6
background: white
transition: background-color 200ms ease
```

#### Hover State
```css
background: #f9fafb
cursor: pointer
```

#### Selected Row
```css
background: #f0fdf4
```

---

## Cell Content

### Checkbox Cell
- Size: `18px × 18px`
- Border: `1.5px solid #d1d5db`
- Border radius: `4px`
- Background: `white`
- Checked: Background `#16a34a`, checkmark `white`

### Name Cell
- Font size: `15px`
- Weight: `500`
- Color: `#0a0a0a`
- Text transform: `capitalize`

### Phone Cell
- Font size: `14px`
- Weight: `400`
- Color: `#374151`
- Font family: `tabular-nums` (monospace numbers)

### Email Cell
- Font size: `14px`
- Weight: `400`
- Color: `#374151`
- Max width: Column width
- Text overflow: `ellipsis`
- White space: `nowrap`
- Overflow: `hidden`

### Source Cell
**When value exists**:
- Display: `inline-flex`
- Padding: `4px 10px`
- Background: `#f3f4f6`
- Border radius: `6px`
- Font size: `13px`
- Weight: `500`
- Color: `#374151`
- Text transform: `capitalize`

**When empty**: Show nothing (white space)

### Status Cell
Status pill component:

```css
display: inline-flex
align-items: center
padding: 6px 12px
border-radius: 12px
font-size: 12px
font-weight: 600
text-transform: uppercase
letter-spacing: 0.05em
```

Status colors:
- **PENDING**: 
  - Background: `#fef3c7`
  - Color: `#92400e`
- **QUALIFIED**: 
  - Background: `#d1fae5`
  - Color: `#065f46`
- **CONTACTED**: 
  - Background: `#dbeafe`
  - Color: `#1e40af`
- **CONVERTED**: 
  - Background: `#dcfce7`
  - Color: `#166534`
- **LOST**: 
  - Background: `#fee2e2`
  - Color: `#991b1b`

### Score Cell
**When value exists**:
- Font size: `14px`
- Weight: `600`
- Color: Score-based
  - 80-100: `#16a34a` (green)
  - 50-79: `#f59e0b` (orange)
  - 0-49: `#dc2626` (red)

**When empty**: Show nothing (white space)

### Assigned Cell
**When assigned**:
- Display: Avatar + name
- Avatar: `28px × 28px`, circle, first letter
- Name: `14px`, weight `500`, color `#374151`, margin-left `8px`

**When unassigned**: 
- Text: `"Unassigned"`
- Font size: `13px`
- Color: `#9ca3af`
- Style: `italic`

### Created Cell
- Font size: `13px`
- Weight: `400`
- Color: `#6b7280`
- Format: `"Jan 15"` or `"Feb 4"` (no year if current year)

---

## Row Actions

### Action Menu (appears on hover)
- Position: Absolute right of row
- Background: `white`
- Box shadow: `0 2px 8px rgba(0, 0, 0, 0.1)`
- Border radius: `6px`
- Padding: `4px`

#### Actions
- **View**: 👁️ icon
- **Edit**: ✏️ icon
- **Delete**: 🗑️ icon (red on hover)

Each icon button:
- Size: `32px × 32px`
- Background: transparent
- Border radius: `4px`
- Hover: Background `#f3f4f6`
- Icon size: `18px`

---

## Empty Cell Handling

**Do NOT show**:
- `"--"` dashes
- `"N/A"`
- `"null"`

**DO show**:
- Empty whitespace (just padding)
- Let the cell breathe

This reduces visual noise and makes actual data stand out.

---

## Bulk Actions Bar

When 1+ rows selected, show floating bar at bottom:

```
┌────────────────────────────────────────────────────────────┐
│  3 selected    [Assign to ▼]  [Change Status ▼]  [Delete] │
└────────────────────────────────────────────────────────────┘
```

### Container
- Position: Fixed, bottom `32px`, left/right `32px`
- Background: `#0a0a0a`
- Color: `white`
- Padding: `16px 24px`
- Border radius: `8px`
- Box shadow: `0 8px 24px rgba(0, 0, 0, 0.2)`
- Z-index: `50`

### Content
- **Count**: `"3 selected"`, font-size `14px`, weight `500`
- **Actions**: Buttons with white text, transparent background
- **Delete button**: Red hover (`#dc2626`)

---

## Pagination

At bottom of table:

```
Showing 1-50 of 247 leads    [< Previous]  1  2  3  ...  5  [Next >]
```

### Container
- Padding: `16px 32px`
- Background: `#ffffff`
- Border top: `1px solid #e5e7eb`
- Display: Flexbox, justify-between, align-center

### Text
- Font size: `14px`
- Color: `#6b7280`

### Pagination Buttons
- Height: `36px`
- Min width: `36px`
- Padding: `0 12px`
- Background: `transparent`
- Border: `1px solid #d1d5db`
- Border radius: `6px`
- Font size: `14px`
- Color: `#374151`
- Margin: `0 4px`

Active page:
- Background: `#16a34a`
- Color: `white`
- Border: none

---

## Sorting

Click column header to sort:

1. **First click**: Sort ascending (↑ icon appears)
2. **Second click**: Sort descending (↓ icon appears)
3. **Third click**: Remove sort

Icon appears right of column text:
- Size: `14px`
- Color: `#16a34a`

---

## Responsive Behavior

On smaller screens (< 1024px):
- Hide less critical columns: Score, Created
- Make table horizontally scrollable
- Fix first column (Name) with sticky position

---

## Performance

- Virtual scrolling: Render only visible rows + buffer
- Lazy load data: Fetch 50 rows at a time
- Debounce search by 300ms
- Memoize sorted/filtered data

---

## Accessibility

- Each row: `role="row"`, clickable
- Keyboard navigation: Tab through checkboxes and actions
- Screen reader: Announce selected count, sort direction
- Focus indicators: `outline: 2px solid #16a34a`
- Skip to content link for keyboard users
