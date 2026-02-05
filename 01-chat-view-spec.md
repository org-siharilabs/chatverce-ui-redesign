# Chat View Specification

## Current Problem
- Promotional banner blocks entire conversation area
- "Conversation expired" banner obscures message input
- Cannot see message history
- Cannot determine conversation context

## Solution Overview
Remove all promotional content from active conversation area. Show conversation history clearly. Handle expired conversations with clarity and actionable next steps.

---

## Layout Structure

```
┌─────────────────────────────────────────────────────────────┐
│ Conversation Header (64px height)                           │
├─────────────────────────────────────────────────────────────┤
│                                                              │
│                                                              │
│ Message History Area                                         │
│ (flex-grow, scrollable)                                      │
│                                                              │
│                                                              │
├─────────────────────────────────────────────────────────────┤
│ Message Input Area (auto height, min 80px)                  │
└─────────────────────────────────────────────────────────────┘
```

---

## Conversation Header

### Dimensions
- Height: `64px`
- Padding: `0 24px`
- Background: `#ffffff`
- Border bottom: `1px solid #e5e7eb`

### Layout (Flexbox: justify-between, align-center)

#### Left Section
**Avatar + Contact Info**
```
[ V ]  Vicky
       +916207471887
       ● Active now
```

- **Avatar Circle**: 
  - Size: `40px × 40px`
  - Background: `#16a34a`
  - Text: First letter of name, white, 16px, weight 600
  - Border radius: `50%`

- **Contact Name**: 
  - Font size: `16px`
  - Weight: `600`
  - Color: `#0a0a0a`
  - Margin left: `12px`

- **Phone Number**:
  - Font size: `13px`
  - Weight: `400`
  - Color: `#6b7280`
  - Display: Block (below name)

- **Active Status**:
  - Font size: `12px`
  - Color: `#16a34a`
  - Display: Flex with green dot
  - Dot: `6px × 6px`, background `#16a34a`, border-radius `50%`, margin-right `6px`

#### Right Section
**Assignment + Status**

```
Assign to: [Select user ▼]  ● Active now
```

- **"Assign to" label**: 
  - Font size: `13px`
  - Color: `#6b7280`
  - Margin right: `8px`

- **Dropdown**:
  - Min width: `160px`
  - Height: `36px`
  - Border: `1px solid #d1d5db`
  - Border radius: `6px`
  - Padding: `0 12px`
  - Font size: `14px`
  - Background: white with caret icon

- **Active now badge**:
  - Same as left section
  - Margin left: `16px`

---

## Message History Area

### Container
- Background: `#f9fafb`
- Padding: `24px`
- Overflow: `scroll-y`
- Flex grow: `1`

### Message Bubbles

#### Incoming Messages (Customer)
```css
max-width: 70%
align-self: flex-start
background: white
padding: 12px 16px
border-radius: 12px
border-bottom-left-radius: 4px
margin-bottom: 12px
box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05)
```

- **Text**: 
  - Font size: `14px`
  - Line height: `1.5`
  - Color: `#0a0a0a`

- **Timestamp**:
  - Font size: `11px`
  - Color: `#9ca3af`
  - Margin top: `6px`
  - Display: `block`

#### Outgoing Messages (Agent)
```css
max-width: 70%
align-self: flex-end
background: #16a34a
padding: 12px 16px
border-radius: 12px
border-bottom-right-radius: 4px
margin-bottom: 12px
color: white
```

- **Text**: 
  - Font size: `14px`
  - Line height: `1.5`
  - Color: `white`

- **Timestamp**:
  - Font size: `11px`
  - Color: `rgba(255, 255, 255, 0.8)`
  - Margin top: `6px`
  - Display: `block`

### System Messages (e.g., "Conversation expired")
```css
align-self: center
background: #fef3c7
padding: 10px 16px
border-radius: 8px
margin: 16px 0
max-width: 80%
text-align: center
```

- **Text**: 
  - Font size: `13px`
  - Color: `#92400e`
  - Line height: `1.4`

---

## Message Input Area

### Container
- Background: `#ffffff`
- Border top: `1px solid #e5e7eb`
- Padding: `16px 24px`
- Min height: `80px`

### Active State (Can Send Messages)

#### Layout
```
┌──────────────────────────────────────────────────┬──────┐
│ [Type your message...]                           │ Send │
│                                                  │      │
└──────────────────────────────────────────────────┴──────┘
  [📎 Attach]  [😊 Emoji]
```

- **Input Field**:
  - Multi-line textarea
  - Min height: `40px`
  - Max height: `120px` (then scroll)
  - Border: `1px solid #d1d5db`
  - Border radius: `8px`
  - Padding: `10px 12px`
  - Font size: `14px`
  - Placeholder: `"Type your message..."`
  - Placeholder color: `#9ca3af`

- **Send Button**:
  - Position: Absolute right `16px`, bottom `16px`
  - Width: `72px`
  - Height: `36px`
  - Background: `#16a34a`
  - Color: `white`
  - Border radius: `6px`
  - Font size: `14px`
  - Font weight: `500`

- **Attachment/Emoji Buttons**:
  - Display: `flex`, margin-top `8px`
  - Each button: `36px × 36px`, transparent background
  - Icon: `#6b7280`, size `20px`
  - Hover: Background `#f3f4f6`
  - Margin right: `8px`

### Expired State (Cannot Send Messages)

#### Layout
```
┌────────────────────────────────────────────────────────────┐
│ ⚠️  This conversation expired 2 hours ago                  │
│                                                            │
│ WhatsApp allows responses within 24 hours of the last     │
│ customer message. You can:                                │
│                                                            │
│ [Send Template Message]  [Wait for Customer Reply]        │
└────────────────────────────────────────────────────────────┘
```

- **Container**:
  - Background: `#fef3c7` (warning yellow tint)
  - Border: `1px solid #fde68a`
  - Border radius: `8px`
  - Padding: `20px 24px`

- **Icon + Heading**:
  - Font size: `15px`
  - Weight: `600`
  - Color: `#92400e`
  - Margin bottom: `8px`

- **Explanation Text**:
  - Font size: `13px`
  - Color: `#78350f`
  - Line height: `1.5`
  - Margin bottom: `16px`

- **Action Buttons**:
  - Display: `flex`, gap `12px`
  - Primary button: `"Send Template Message"`
    - Background: `#16a34a`
    - Color: `white`
    - Padding: `10px 16px`
    - Border radius: `6px`
  - Secondary button: `"Wait for Customer Reply"`
    - Background: `transparent`
    - Border: `1px solid #d1d5db`
    - Color: `#374151`
    - Padding: `10px 16px`
    - Border radius: `6px`

---

## Behavior Rules

1. **On page load**: Load last 50 messages, scroll to bottom
2. **New message arrives**: Append to bottom, auto-scroll if user is within 100px of bottom
3. **User scrolls up**: Disable auto-scroll, show "New messages ↓" badge
4. **Send button**: Disabled (grey) until text length > 0
5. **Expired state**: Check conversation timestamp vs current time
6. **Template button click**: Open template selector modal (separate spec)

---

## Removed Elements

### ❌ Delete These
1. All promotional banners (AI Agents marketing image)
2. Full-screen "Conversation expired" overlay
3. ChatVerce branding in chat area
4. Any "Free Trial" or upsell messaging in active conversations

### ✅ Keep These Elsewhere
- AI Agents promotion → Dashboard empty state or dedicated onboarding flow
- Free trial messaging → Settings page or top-bar notification
