# Inventory Management System - Design Guidelines

## Design Approach

**Selected System:** Linear-inspired productivity interface with Material Design data components  
**Rationale:** Inventory management demands clarity, speed, and data density. Linear's clean typography and generous spacing combined with Material Design's robust table patterns create an efficient, professional dashboard.

**Core Principles:**
- Information hierarchy through typography, not decoration
- Generous whitespace for reduced cognitive load
- Consistent patterns for predictable interaction
- Data-first design with minimal chrome

## Typography System

**Font Family:** Inter (Google Fonts CDN)

**Hierarchy:**
- Page Titles: 2xl, semibold (600)
- Section Headers: xl, medium (500)
- Card/Panel Titles: lg, medium (500)
- Body Text: base, normal (400)
- Table Headers: sm, medium (500), uppercase tracking-wide
- Table Data: sm, normal (400)
- Helper Text: xs, normal (400)
- Button Text: sm, medium (500)

## Layout System

**Spacing Primitives:** Use Tailwind units of 2, 4, 6, and 8 for consistency
- Micro spacing (within components): 2, 4
- Component spacing: 6, 8
- Section spacing: 8, 12

**Grid Structure:**
- Main container: max-w-7xl mx-auto px-6
- Dashboard uses sidebar + main content layout
- Sidebar: Fixed width 256px (w-64)
- Main content: flex-1 with p-8

## Component Library

### Navigation
**Top Bar:** Full-width header with h-16, flex items-center, px-6
- Logo/Brand: Left-aligned
- Search bar: Center-positioned, max-w-md
- User menu: Right-aligned with avatar

**Sidebar:** Left-aligned vertical navigation
- Navigation items: py-2 px-4, rounded-md
- Icons: 20px (w-5 h-5) from Heroicons
- Active state indicated with subtle background fill
- Section dividers using border-t with my-4

### Data Display
**Product Table:**
- Container: rounded-lg border with overflow-hidden
- Header: Sticky top positioning, subtle background differentiation
- Rows: py-4 px-6, border-b between rows
- Hover state on rows for interactivity
- Action buttons (edit/delete): Right-aligned icon buttons
- Sorting indicators in headers
- Empty state: Centered content with icon and helper text

**Product Cards (Grid View Alternative):**
- Grid: grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6
- Card: rounded-lg border p-6
- Card header with product name + SKU
- Product details in clean vertical stack (gap-2)
- Actions in card footer

**Stats/Metrics Cards:**
- Grid: grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6
- Card structure: p-6 rounded-lg border
- Large number display (3xl, bold) with label below (sm)
- Optional trend indicator

### Forms
**Add/Edit Product Forms:**
- Max-width container: max-w-2xl
- Form groups: space-y-6
- Label: block mb-2, medium weight
- Input fields: Full-width, h-10, px-4, rounded-md, border
- Textarea: h-24 for descriptions
- Select dropdowns: Same styling as inputs
- Required field indicators: Asterisk in label
- Error messages: text-xs below fields
- Form actions: Flex justify-end gap-4, sticky bottom if long forms

### Buttons
**Primary Action:** Solid background, px-6 py-2.5, rounded-md
**Secondary Action:** Border style, same sizing
**Destructive Action:** For delete operations, distinct treatment
**Icon-only Buttons:** Square aspect ratio (w-9 h-9), centered icon

### Alerts & Indicators
**Low Stock Alert:** Inline badge/chip next to quantity
- Rounded-full px-3 py-1 text-xs
- Shows "Low Stock" when quantity < threshold

**Status Badges:** For categories or product status
- Rounded-md px-2.5 py-0.5 text-xs medium

### Modals/Dialogs
**Delete Confirmation:**
- Centered overlay with backdrop
- Modal: max-w-md p-6 rounded-lg
- Title + description + action buttons (Cancel + Delete)

**Add/Edit Modal (Alternative to Full Page):**
- max-w-2xl width
- Scrollable content area if needed
- Sticky header and footer

## Icons
**Library:** Heroicons (CDN)  
**Standard Size:** 20px (w-5 h-5) for UI elements  
**Large Icons:** 24px (w-6 h-6) for empty states

**Icon Usage:**
- Navigation items: Leading icons
- Action buttons: Edit (pencil), Delete (trash), Add (plus)
- Search: Magnifying glass
- Sort indicators: Chevron up/down
- Product categories: Box, tag, or folder icons

## Page Layouts

### Dashboard Home
- Top metrics cards in 4-column grid
- Recent activity or low stock alerts section
- Quick actions area

### Product Listing
- Page header: Title + "Add Product" button (justify-between)
- Search bar and filters row
- View toggle: Table/Grid icons
- Main content area with product table or grid

### Add/Edit Product
- Centered form with max-w-2xl
- Clear section groupings (Basic Info, Pricing, Inventory)
- Bottom action bar with Cancel + Save

## Responsive Behavior
- **Desktop (lg+):** Full sidebar + content layout
- **Tablet (md):** Collapsible sidebar, 2-column grids reduce to 1-2
- **Mobile:** Hidden sidebar (hamburger menu), all grids stack to single column, table scrolls horizontally or converts to cards

## Images
No hero images needed for this utility application. Focus on:
- Product placeholder icons/thumbnails in table/cards (40x40 or 64x64)
- Empty state illustrations (simple line art, centered, ~200px wide)
- User avatar in top navigation (32px circle)

All images should be clean, minimal, and never distract from data.