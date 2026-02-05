# Conversations List Specification

## Current Problem
- Names, phone numbers, timestamps have equal visual weight
- "NEW" badges are easy to miss
- No visual distinction between read and unread
- Filter dropdown ("ALL") is hard to find
- Scanning for urgent conversations is difficult

## Solution Overview
Create clear visual hierarchy using typography weight, spacing, and color. Make unread conversations immediately obvious. Group conversations by time.

---

## Layout Structure

```
┌─────────────────────────────────────┐
│ Chats                            [+]│
├─────────────────────────────────────┤
│ [All] [Unread]                      │
├─────────────────────────────────────┤
│ Filters: [ALL ▼] [Date ▼]          │
├─────────────────────────────────────┤
│ TODAY                               │
│                                     │
│ Conversation Item 1                 │
│ Conversation Item 2                 │
│                                     │
│ YESTERDAY                           │
│                                     │
│ Conversation Item 3                 │
│ ...                                 │
└─────────────────────────────────────┘
```

---

## Header Section

### Dimensions
- Height: `64px`
- Padding: `0 20px`
- Border bottom: `1px solid #e5e7eb`

### Layout (Flexbox: justify-between, align-center)

- **"Chats" Title**:
  - Font size: `20px`
  - Weight: `600`
  - Color: `#0a0a0a`

- **Add Button (+)**:
  - Size: `36px × 36px`
  - Background: transparent
  - Icon: `+`, size `20px`, color `#374151`
  - Border radius: `6px`
  - Hover: Background `#f3f4f6`

---

## Tab Bar

### Container
- Padding: `12px 20px`
- Background: `#ffffff`
- Border bottom: `1px solid #e5e7eb`

### Tabs
```
[All] [Unread]
```

- **Tab Button**:
  - Height: `36px`
  - Padding: `0 16px`
  - Border radius: `6px`
  - Font size: `14px`
  - Font weight: `500`
  - Margin right: `8px`

- **Inactive Tab**:
  - Background: `transparent`
  - Color: `#6b7280`
  - Hover: Background `#f3f4f6`

- **Active Tab**:
  - Background: `#16a34a`
  - Color: `white`

---

## Filters Bar

### Container
- Padding: `12px 20px`
- Background: `#f9fafb`
- Border bottom: `1px solid #e5e7eb`

### Layout (Flexbox, gap 12px)

- **Filter Label**: 
  - Font size: `13px`
  - Color: `#6b7280`
  - Margin right: `8px`

- **Dropdown**:
  - Height: `36px`
  - Padding: `0 12px`
  - Background: `white`
  - Border: `1px solid #d1d5db`
  - Border radius: `6px`
  - Font size: `13px`
  - Color: `#374151`
  - Min width: `120px`

---

## Conversation List

### Container
- Background: `#ffffff`
- Overflow: `scroll-y`
- Padding: `0`

### Time Group Headers

```
TODAY
```

- Font size: `11px`
- Weight: `600`
- Color: `#9ca3af`
- Text transform: `uppercase`
- Letter spacing: `0.05em`
- Padding: `12px 20px 8px 20px`
- Background: `#f9fafb`
- Position: Sticky (stays at top when scrolling)

---

## Conversation Item

### Dimensions
- Height: Auto (min `76px`)
- Padding: `12px 20px`
- Border bottom: `1px solid #f3f4f6`

### States

#### Unread Conversation
- Background: `#f0fdf4` (very light green tint)
- Border left: `3px solid #16a34a`

#### Read Conversation
- Background: `white`
- Border left: none

#### Selected/Active
- Background: `#ecfdf5`
- Border left: `3px solid #16a34a`

#### Hover (any state)
- Background: Slightly darker than current state
- Cursor: `pointer`

---

## Content Layout

```
┌─────────────────────────────────────────────────┐
│ [V] DEVA               NEW      Yesterday       │
│     +916269141202                         1     │
│     Last message preview text goes here...      │
└─────────────────────────────────────────────────┘
```

### Structure (Grid)

```
[Avatar] [Content Area] [Badge] [Time] [Count]
```

#### Avatar
- Size: `48px × 48px`
- Background: Derived from name (consistent color per contact)
- Border radius: `50%`
- Text: First letter, white, 18px, weight 600
- Position: Align-start

**Color Generation** (based on contact name):
```
Colors: ['#16a34a', '#3b82f6', '#f59e0b', '#ec4899', '#8b5cf6']
Use hash of first letter to pick color
```

#### Content Area

**Name Row** (Flex: justify-between)
- **Name**:
  - Font size: `15px`
  - Weight: `600` (unread) or `500` (read)
  - Color: `#0a0a0a`
  - Margin bottom: `2px`

- **NEW Badge** (if unread):
  - Background: `#16a34a`
  - Color: `white`
  - Font size: `10px`
  - Weight: `600`
  - Padding: `2px 6px`
  - Border radius: `4px`
  - Text transform: `uppercase`
  - Letter spacing: `0.05em`
  - Margin left: `8px`

**Phone Row**
- Font size: `13px`
- Weight: `400`
- Color: `#9ca3af`
- Margin bottom: `4px`

**Preview Text**
- Font size: `13px`
- Weight: `400` (unread) or `400` (read)
- Color: `#6b7280` (unread) or `#9ca3af` (read)
- Line height: `1.4`
- Max lines: `1`
- Text overflow: `ellipsis`
- Max width: `calc(100% - 80px)` (leave room for timestamp)

#### Timestamp
- Font size: `12px`
- Weight: `400`
- Color: `#9ca3af`
- Position: Absolute, top-right
- White space: `nowrap`

#### Unread Count Badge
- Size: `20px × 20px`
- Background: `#16a34a`
- Color: `white`
- Border radius: `50%`
- Font size: `12px`
- Weight: `600`
- Display: `flex`, justify-center, align-center
- Position: Absolute, bottom-right
- Only show if unread count > 0

---

## Empty State

When no conversations match filters:

```
┌─────────────────────────────────────┐
│                                     │
│           💬                        │
│                                     │
│     No conversations found          │
│                                     │
│     Try adjusting your filters or   │
│     start a new conversation.       │
│                                     │
│     [Start Conversation]            │
│                                     │
└─────────────────────────────────────┘
```

- Icon: `48px`, color `#d1d5db`
- Heading: `16px`, weight `600`, color `#374151`
- Description: `14px`, color `#6b7280`, line-height `1.5`
- Button: Primary button style (green)
- Padding: `48px 32px`
- Text align: `center`

---

## Behavior Rules

1. **Sort order**: 
   - Unread conversations at top (sorted by most recent)
   - Read conversations below (sorted by most recent)
   - Within each group, sort by last message timestamp

2. **Time grouping**:
   - "TODAY" — last 24 hours
   - "YESTERDAY" — 24-48 hours ago
   - "THIS WEEK" — within last 7 days
   - "OLDER" — everything else

3. **Unread tab**: 
   - Show only conversations with unread count > 0
   - If no unread, show empty state with "All caught up! 🎉"

4. **Search** (future):
   - Add search bar below tabs
   - Filter by name, phone, or message content

5. **Click behavior**:
   - Click anywhere on conversation item → Load conversation in right panel
   - Mark as active (background change)
   - If unread, mark as read after 2 seconds of viewing

---

## Accessibility

- Each conversation item: `role="button"`, `tabindex="0"`
- Keyboard navigation: Arrow keys to move, Enter to select
- Screen reader: Announce "Unread" state and count
- Focus indicators: `outline: 2px solid #16a34a` on keyboard focus

---

## Performance

- Virtual scrolling: Only render visible conversations + 10 above/below
- Lazy load avatars
- Debounce search input by 300ms
- Use CSS transforms for smooth scrolling
