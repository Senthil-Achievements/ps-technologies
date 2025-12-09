# PS Technologies Design System
## Components: Tables & Data Display

---

## Table Component

### Basic Table Structure
```
┌──────────┬──────────┬──────────┬──────────┐
│ Name ▴   │ Email    │ Role     │ Actions  │  ← Header
├──────────┼──────────┼──────────┼──────────┤
│ John Doe │ john@... │ Admin    │ •••      │
│ Jane Sm...│ jane@... │ Editor   │ •••      │
│ Mike J...│ mike@... │ Viewer   │ •••      │
└──────────┴──────────┴──────────┴──────────┘
```

---

## Table Specifications

### Table Container
```css
Background: var(--theme-bg-card)
Border: 1px solid var(--border-subtle)
Border Radius: 12px (Radius/MD)
Overflow: hidden
```

### Table Header
```css
Background: var(--bg-soft)
Border Bottom: 1px solid var(--border-subtle)
Font: Caption/Medium (14px, 500)
Color: var(--text-muted)
Text Transform: Uppercase
Letter Spacing: 0.05em
Padding: 12px 16px (Space/12 Space/16)
```

### Table Row
```css
Border Bottom: 1px solid var(--border-subtle)
Padding: 16px (Space/16)
Transition: background 0.2s ease

Last Row:
  Border Bottom: none
  
Hover:
  Background: var(--bg-soft)
  
Selected:
  Background: rgba(79, 70, 229, 0.08)
  Border Left: 3px solid var(--accent-primary)
```

### Table Cell
```css
Padding: 16px (Space/16)
Font: Body (16px, Regular)
Color: var(--text-secondary)
Vertical Align: middle
```

### Sortable Column Header
```css
Cursor: pointer
Display: flex
Align Items: center
Gap: 6px

Sort Icon:
  Width: 14px
  Height: 14px
  Opacity: 0.4
  
Active Sort:
  Opacity: 1
  Color: var(--accent-primary)
```

---

## Table Variants

### 1. Basic Table
Simple data display with headers and rows.

### 2. Selectable Table
```
┌─┬──────────┬──────────┬──────────┬──────────┐
│☑│ Name     │ Email    │ Role     │ Actions  │
├─┼──────────┼──────────┼──────────┼──────────┤
│☐│ John Doe │ john@... │ Admin    │ •••      │
│☑│ Jane Sm..│ jane@... │ Editor   │ •••      │
│☐│ Mike J...│ mike@... │ Viewer   │ •••      │
└─┴──────────┴──────────┴──────────┴──────────┘
```

**Checkbox Column**:
- Width: 48px
- Center aligned
- Header checkbox selects all

### 3. Expandable Rows
```
┌──────────┬──────────┬──────────┬──────────┐
│▼ Project │ Status   │ Due Date │ Actions  │
├──────────┴──────────┴──────────┴──────────┤
│  Expanded details shown here...            │
│  Can include nested content, images, etc.  │
├──────────┬──────────┬──────────┬──────────┤
│▸ Project │ Status   │ Due Date │ Actions  │
└──────────┴──────────┴──────────┴──────────┘
```

### 4. With Status Badges
```
┌──────────┬──────────┬──────────┬──────────┐
│ Name     │ Status   │ Progress │ Actions  │
├──────────┼──────────┼──────────┼──────────┤
│ Task 1   │ ACTIVE   │ ████░░░  │ •••      │
│ Task 2   │ PENDING  │ ██░░░░░  │ •••      │
└──────────┴──────────┴──────────┴──────────┘
```

---

## Pagination
```
Showing 1-10 of 45 items

← Previous   1  2  [3]  4  5   Next →
```

**Specifications**:
```css
Display: flex
Align Items: center
Justify Content: space-between
Padding: 16px (Space/16)
Border Top: 1px solid var(--border-subtle)
Background: var(--bg-soft)
```

---

## Empty State
```
┌──────────────────────────────────────────┐
│                                          │
│               [📋]                       │
│                                          │
│           No data found                  │
│                                          │
│   Try adjusting your filters or         │
│   create your first entry                │
│                                          │
│         [Create Entry]                   │
│                                          │
└──────────────────────────────────────────┘
```

---

## Loading State
```
┌──────────────────────────────────────────┐
│ Name     │ Email    │ Role     │ Actions  │
├──────────┼──────────┼──────────┼──────────┤
│ ▓▓▓▓▓▓▓  │ ▓▓▓▓▓▓▓  │ ▓▓▓▓▓▓  │  ▓▓▓     │
│ ▓▓▓▓▓    │ ▓▓▓▓▓▓▓  │ ▓▓▓▓    │  ▓▓▓     │
│ ▓▓▓▓▓▓   │ ▓▓▓▓▓    │ ▓▓▓▓▓   │  ▓▓▓     │
└──────────┴──────────┴──────────┴──────────┘
```

Skeleton loaders with pulsing animation.

---

## Responsive Behavior

### Mobile (< 768px)
Convert table to card-based layout:

```
┌─────────────────────────────┐
│ John Doe              •••   │
│ john@example.com            │
│ Role: Admin                 │
└─────────────────────────────┘
┌─────────────────────────────┐
│ Jane Smith            •••   │
│ jane@example.com            │
│ Role: Editor                │
└─────────────────────────────┘
```

---

## Avatar Component

### Sizes
```
Small:   32px × 32px
Medium:  40px × 40px
Large:   48px × 48px
XL:      64px × 64px
```

### With Image
```css
Border Radius: 50%
Object Fit: cover
Display: block
```

### With Initials
```css
Background: var(--accent-gradient)
Color: #FFFFFF
Display: flex
Align Items: center
Justify Content: center
Font Weight: 500
Font Size: 14px (Medium), 16px (Large)
```

### With Status Indicator
```
Position: absolute
Bottom: 0
Right: 0
Width: 10px (Small), 12px (Medium), 14px (Large)
Height: same as width
Border: 2px solid var(--theme-bg-card)
Border Radius: 50%
Background: #22C55E (online), #94A3B8 (offline)
```

---

## Skeleton Loaders

### Usage
Show during data loading to maintain layout stability.

### Types

**Text Skeleton**:
```css
Height: 1em
Background: var(--bg-soft)
Border Radius: 4px
Animation: pulse 1.5s ease-in-out infinite
```

**Circle Skeleton** (Avatar):
```css
Width: 40px
Height: 40px
Border Radius: 50%
```

**Card Skeleton**:
Full card structure with placeholder elements

---

## Implementation

### HTML - Table
```html
<div class="table-container">
  <table class="table">
    <thead>
      <tr>
        <th class="table-header sortable">
          Name
          <svg class="sort-icon">▴</svg>
        </th>
        <th class="table-header">Email</th>
        <th class="table-header">Role</th>
        <th class="table-header">Actions</th>
      </tr>
    </thead>
    <tbody>
      <tr class="table-row">
        <td class="table-cell">John Doe</td>
        <td class="table-cell">john@example.com</td>
        <td class="table-cell">
          <span class="badge badge-solid badge-success">Admin</span>
        </td>
        <td class="table-cell">
          <button class="btn btn-ghost btn-sm">Edit</button>
        </td>
      </tr>
    </tbody>
  </table>
  
  <div class="table-pagination">
    <span>Showing 1-10 of 45 items</span>
    <div class="pagination">
      <!-- Pagination controls -->
    </div>
  </div>
</div>
```

### CSS
```css
.table-container {
  background: var(--theme-bg-card);
  border: 1px solid var(--border-subtle);
  border-radius: var(--radius-md);
  overflow: hidden;
}

.table {
  width: 100%;
  border-collapse: collapse;
}

.table-header {
  background: var(--bg-soft);
  border-bottom: 1px solid var(--border-subtle);
  padding: var(--space-12) var(--space-16);
  text-align: left;
  font-size: 0.875rem;
  font-weight: 500;
  color: var(--text-muted);
  text-transform: uppercase;
  letter-spacing: 0.05em;
}

.table-header.sortable {
  cursor: pointer;
  user-select: none;
}

.table-header.sortable:hover {
  background: var(--border-subtle);
}

.table-row {
  border-bottom: 1px solid var(--border-subtle);
  transition: background 0.2s ease;
}

.table-row:last-child {
  border-bottom: none;
}

.table-row:hover {
  background: var(--bg-soft);
}

.table-row.selected {
  background: rgba(79, 70, 229, 0.08);
  border-left: 3px solid var(--accent-primary);
}

.table-cell {
  padding: var(--space-16);
  font-size: 1rem;
  color: var(--text-secondary);
  vertical-align: middle;
}

.table-pagination {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: var(--space-16);
  border-top: 1px solid var(--border-subtle);
  background: var(--bg-soft);
  font-size: 0.875rem;
  color: var(--text-muted);
}

/* Avatar */
.avatar {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
  overflow: hidden;
  flex-shrink: 0;
  position: relative;
}

.avatar-sm { width: 32px; height: 32px; font-size: 14px; }
.avatar-md { width: 40px; height: 40px; font-size: 16px; }
.avatar-lg { width: 48px; height: 48px; font-size: 18px; }
.avatar-xl { width: 64px; height: 64px; font-size: 24px; }

.avatar-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.avatar-initials {
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  background: var(--accent-gradient);
  color: #FFFFFF;
  font-weight: 500;
}

.avatar-status {
  position: absolute;
  bottom: 0;
  right: 0;
  width: 12px;
  height: 12px;
  border: 2px solid var(--theme-bg-card);
  border-radius: 50%;
}

.avatar-status.online { background: var(--color-success); }
.avatar-status.offline { background: #94A3B8; }

/* Skeleton */
.skeleton {
  background: linear-gradient(
    90deg,
    var(--bg-soft) 0%,
    var(--border-subtle) 50%,
    var(--bg-soft) 100%
  );
  background-size: 200% 100%;
  animation: skeleton-loading 1.5s ease-in-out infinite;
  border-radius: var(--radius-sm);
}

@keyframes skeleton-loading {
  0% { background-position: 200% 0; }
  100% { background-position: -200% 0; }
}

.skeleton-text {
  height: 1em;
  width: 100%;
}

.skeleton-circle {
  border-radius: 50%;
}
```

---

## Accessibility

✅ **Semantic HTML**: Use `<table>`, `<thead>`, `<tbody>`, `<tr>`, `<th>`, `<td>`
✅ **Sort Announcements**: Screen reader announcements for sorting
✅ **Keyboard Navigation**: Full keyboard support for interactive elements
✅ **ARIA Labels**: Clear labels for actions
✅ **Caption**: Use `<caption>` for table description

---

## Usage Guidelines

### Do's
✅ Use tables for tabular data only
✅ Make columns sortable when relevant
✅ Provide clear column headers
✅ Show loading states
✅ Handle empty states gracefully

### Don'ts
❌ Don't use tables for layout
❌ Don't hide important data on mobile
❌ Don't forget zebra striping or hover states
❌ Don't make tables too wide
❌ Don't skip pagination for large datasets

---

**Last Updated**: December 2025  
**Version**: 1.0  
**Maintained by**: PS Technologies Design Team
