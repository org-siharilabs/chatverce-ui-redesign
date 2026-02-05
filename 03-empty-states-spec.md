# Empty States Specification

## Current Problem
- Generic grey icons (house, robot) convey nothing
- No context about what the product does
- No clear next actions
- Feels lifeless and uninspiring

## Design Principle
Empty states are not voids — they're opportunities to educate, inspire, and guide users toward their first success.

---

## Dashboard Empty State

### Layout
```
┌────────────────────────────────────────────────────────────┐
│                                                            │
│                         [Image]                            │
│                                                            │
│              Welcome to Chatverce Dashboard                │
│                                                            │
│     Your command center for WhatsApp customer              │
│     engagement. Connect channels, manage conversations,    │
│     and automate workflows — all in one place.             │
│                                                            │
│     Quick Start:                                           │
│                                                            │
│     [📱 Connect WhatsApp]  [💬 View Inbox]  [📊 Set Up CRM]│
│                                                            │
│                                                            │
│     ─────  What you'll see here  ─────                    │
│                                                            │
│     [Preview of populated dashboard with stats cards]      │
│                                                            │
└────────────────────────────────────────────────────────────┘
```

### Specifications

#### Container
- Max width: `720px`
- Margin: `0 auto`
- Padding: `64px 32px`
- Text align: `center`

#### Illustration
- **Option 1**: Custom illustration showing connected channels, conversations, analytics
- **Option 2**: Screenshot mockup of populated dashboard (blurred/faded)
- **Option 3**: Simple iconography: 3 icons in a row (channel + conversation + chart)
- Size: `240px × 180px`
- Margin bottom: `32px`

**Recommended illustration elements**:
- WhatsApp icon connected to chat bubbles
- Small graphs/metrics in background
- Subtle green accent color (#16a34a)
- Clean, modern style (not clipart)

#### Heading
- Text: `"Welcome to Chatverce Dashboard"`
- Font size: `28px`
- Weight: `600`
- Color: `#0a0a0a`
- Line height: `1.3`
- Margin bottom: `16px`

#### Description
- Font size: `16px`
- Weight: `400`
- Color: `#6b7280`
- Line height: `1.6`
- Max width: `560px`
- Margin: `0 auto 32px auto`

#### Quick Start Section

**"Quick Start:" Label**
- Font size: `14px`
- Weight: `600`
- Color: `#374151`
- Margin bottom: `16px`

**Action Cards** (Horizontal flex, gap 16px)

Each card:
```css
background: white
border: 2px solid #e5e7eb
border-radius: 12px
padding: 20px 24px
min-width: 180px
cursor: pointer
transition: all 200ms ease
```

Hover:
```css
border-color: #16a34a
box-shadow: 0 4px 12px rgba(22, 163, 74, 0.15)
transform: translateY(-2px)
```

**Card Content**:
- Icon: `32px`, color `#16a34a`, margin-bottom `12px`
- Title: `15px`, weight `600`, color `#0a0a0a`
- Subtitle: `13px`, color `#6b7280`, margin-top `4px`

Example cards:
1. 📱 Connect WhatsApp → "Add your first channel"
2. 💬 View Inbox → "See all conversations"
3. 📊 Set Up CRM → "Organize your leads"

#### Preview Section

**Divider**
- Text: `"What you'll see here"`
- Font size: `13px`
- Weight: `500`
- Color: `#9ca3af`
- Display: flex with lines on either side
- Lines: `1px solid #e5e7eb`
- Margin: `48px 0 32px 0`

**Preview Image**
- Screenshot of populated dashboard with:
  - 4 stat cards showing metrics
  - Recent conversations list
  - Quick actions section
- Apply: `opacity: 0.6`, `filter: grayscale(20%)`
- Border: `1px solid #e5e7eb`
- Border radius: `8px`
- Max width: `100%`

---

## AI Agents Empty State

### Layout
```
┌────────────────────────────────────────────────────────────┐
│                                                            │
│                     [Illustration]                         │
│                                                            │
│                  Build Your First AI Agent                 │
│                                                            │
│     AI Agents automate customer interactions, qualify      │
│     leads, answer questions, and execute workflows —       │
│     without human intervention.                            │
│                                                            │
│     ─────  How It Works  ─────                            │
│                                                            │
│     1. Choose Tools → Define what your agent can do        │
│     2. Set Behavior → Teach it when and how to respond     │
│     3. Deploy → Connect it to your channels                │
│                                                            │
│     [+ Create Your First Agent]                            │
│                                                            │
│     Not sure where to start?                               │
│     [View Agent Templates →]                               │
│                                                            │
└────────────────────────────────────────────────────────────┘
```

### Specifications

#### Container
- Same as Dashboard: Max width `720px`, centered, padding `64px 32px`

#### Illustration
**Option 1** (Recommended): Abstract agent concept
- Robot/bot icon with connection lines to tools (calendar, database, chat)
- Size: `200px × 160px`
- Colors: `#16a34a` (primary), `#6b7280` (secondary), white background
- Style: Line art or simplified 2.5D

**Option 2**: Flow diagram
- Shows: Customer message → Agent → Actions → Response
- Visual flow with arrows

Margin bottom: `32px`

#### Heading
- Text: `"Build Your First AI Agent"`
- Font size: `28px`
- Weight: `600`
- Color: `#0a0a0a`
- Margin bottom: `16px`

#### Description
- Font size: `16px`
- Color: `#6b7280`
- Line height: `1.6`
- Max width: `560px`
- Margin: `0 auto 40px auto`

#### How It Works Section

**Divider**: Same style as dashboard

**Steps** (Vertical list)

Each step:
```
1. Choose Tools → Define what your agent can do
```

- Number: `24px circle`, background `#f0fdf4`, color `#16a34a`, weight `600`
- Title: `15px`, weight `600`, color `#0a0a0a`
- Arrow: `→`
- Description: `14px`, color `#6b7280`
- Margin between steps: `16px`

#### Primary CTA
- Button: `"+ Create Your First Agent"`
- Background: `#16a34a`
- Color: `white`
- Padding: `12px 24px`
- Border radius: `8px`
- Font size: `15px`
- Weight: `500`
- Height: `48px`
- Margin: `32px 0 24px 0`

#### Secondary CTA
- Text: `"Not sure where to start?"`
- Font size: `14px`
- Color: `#6b7280`
- Margin bottom: `8px`

- Link: `"View Agent Templates →"`
- Font size: `14px`
- Weight: `500`
- Color: `#16a34a`
- Text decoration: `none`
- Hover: `underline`

---

## Inbox Channel Selector Empty State

### Layout
```
┌────────────────────────────────────────────────────────────┐
│                                                            │
│                         💬                                 │
│                                                            │
│                   Select a Channel                         │
│                                                            │
│     Choose a channel from the sidebar to view and          │
│     manage your conversations.                             │
│                                                            │
│     No channels connected yet?                             │
│     [+ Add New Channel]                                    │
│                                                            │
└────────────────────────────────────────────────────────────┘
```

### Specifications

#### Container
- Max width: `480px`
- Margin: `0 auto`
- Padding: `80px 32px`
- Text align: `center`

#### Icon
- Emoji or icon: `💬` or chat bubble icon
- Size: `64px`
- Color: `#d1d5db`
- Margin bottom: `24px`

#### Heading
- Text: `"Select a Channel"`
- Font size: `20px`
- Weight: `600`
- Color: `#374151`
- Margin bottom: `12px`

#### Description
- Font size: `14px`
- Color: `#6b7280`
- Line height: `1.6`
- Margin bottom: `24px`

#### Secondary Text
- Font size: `13px`
- Color: `#9ca3af`
- Margin bottom: `12px`

#### Button
- `"+ Add New Channel"`
- Primary button style (green)
- Padding: `10px 20px`

---

## Conversation Area Empty State

### Layout
```
┌────────────────────────────────────────────────────────────┐
│                                                            │
│                         💬                                 │
│                                                            │
│                 Select a conversation                      │
│                                                            │
│     Choose a chat from the sidebar to start engaging       │
│     with your customers.                                   │
│                                                            │
│     ⌘ + K to search conversations                          │
│                                                            │
└────────────────────────────────────────────────────────────┘
```

### Specifications

#### Container
- Full height of conversation area
- Display: `flex`, justify-center, align-center
- Background: `#f9fafb`

#### Content Box
- Max width: `400px`
- Padding: `32px`
- Text align: `center`

#### Icon
- Size: `56px`
- Color: `#d1d5db`
- Margin bottom: `20px`

#### Heading
- Font size: `18px`
- Weight: `600`
- Color: `#374151`
- Margin bottom: `8px`

#### Description
- Font size: `14px`
- Color: `#6b7280`
- Line height: `1.5`
- Margin bottom: `20px`

#### Keyboard Shortcut Hint
- Background: `#f3f4f6`
- Padding: `8px 12px`
- Border radius: `6px`
- Font size: `13px`
- Color: `#6b7280`
- Font family: `monospace` for ⌘ + K
- Display: `inline-block`

---

## CRM Empty States

### No Leads
```
┌────────────────────────────────────────────────────────────┐
│                                                            │
│                         👤                                 │
│                                                            │
│                   No leads yet                             │
│                                                            │
│     Start capturing leads from your conversations or       │
│     import your existing contact list.                     │
│                                                            │
│     [+ Add Lead]  [Import Contacts]                        │
│                                                            │
└────────────────────────────────────────────────────────────┘
```

Same structure as previous empty states, with two buttons:
- Primary: `"+ Add Lead"`
- Secondary (ghost style): `"Import Contacts"`

---

## Campaigns Empty State

### No Campaigns
```
┌────────────────────────────────────────────────────────────┐
│                                                            │
│                         📢                                 │
│                                                            │
│              Launch Your First Campaign                    │
│                                                            │
│     Broadcast messages to multiple contacts at once.       │
│     Perfect for announcements, offers, and updates.        │
│                                                            │
│     [+ Create Campaign]                                    │
│                                                            │
│     [View Campaign Best Practices →]                       │
│                                                            │
└────────────────────────────────────────────────────────────┘
```

---

## Design Assets Needed

For development handoff, you'll need:

1. **Illustrations** (SVG format preferred):
   - Dashboard hero image (connected channels concept)
   - AI Agents diagram (bot + tools)
   - Each icon (💬, 👤, 📢, etc.) as SVG with proper sizing

2. **Preview Screenshots**:
   - Populated dashboard mockup
   - Optional: Agent builder interface preview

3. **Icon Library**:
   - Consistent icon set (recommend: Heroicons or Lucide)
   - All icons at 20px, 24px, 32px, 48px sizes

---

## Implementation Priority

1. **Immediate** (This week):
   - Conversation area empty state (users see this constantly)
   - Channel selector empty state

2. **Important** (This sprint):
   - Dashboard empty state
   - AI Agents empty state

3. **Polish** (Next sprint):
   - CRM empty states
   - Campaigns empty state
   - Add illustrations/custom graphics
