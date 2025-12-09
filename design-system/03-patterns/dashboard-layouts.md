# PS Technologies Design System
## Patterns: Dashboard Layouts

---

## Overview
Dashboard patterns provide structured, data-rich interfaces for managing applications, viewing analytics, and accessing core functionality.

---

## Standard Dashboard Layout

### Structure
```
┌─────────────────────────────────────────────────┐
│ [Logo] PS Tech    [Search]    [👤] [🔔]        │  ← Top Nav
├──────┬──────────────────────────────────────────┤
│      │                                          │
│ [🏠] │  Dashboard                               │  ← Sidebar + Main
│ Home │                                          │
│      │  ┌────────┐ ┌────────┐ ┌────────┐      │
│ [📊] │  │Metric 1│ │Metric 2│ │Metric 3│      │  ← Metrics
│ Data │  └────────┘ └────────┘ └────────┘      │
│      │                                          │
│ [⚙️] │  Recent Activity                         │
│ Set  │  ┌──────────────────────────────────┐   │  ← Content
│      │  │                                  │   │
│      │  │         Data Table               │   │
│      │  │                                  │   │
│      │  └──────────────────────────────────┘   │
└──────┴──────────────────────────────────────────┘
```

---

## Layout Specifications

### Top Navigation Bar
```css
Height: 64px
Position: sticky
Top: 0
Z-Index: 20
Background: var(--theme-bg-card)
Border Bottom: 1px solid var(--border-subtle)
Backdrop Filter: blur(12px)
Padding: 0 24px (0 Space/24)

Content Layout:
  Display: grid
  Grid Template Columns: auto 1fr auto
  Align Items: center
  Gap: 24px (Space/24)
```

**Left Section**: Logo + App name
**Center Section**: Global search
**Right Section**: Notifications + User menu

---

### Sidebar Navigation
```css
Width: 240px (expanded) / 64px (collapsed)
Height: 100vh
Position: fixed
Left: 0
Top: 64px
Background: var(--theme-bg-card)
Border Right: 1px solid var(--border-subtle)
Padding: 20px (Space/20)
Overflow Y: auto
Transition: width 0.3s ease
```

**Navigation Items**:
- Icon + Label
- Active state highlighting
- Hover effects
- Badge support (for counts)

**Bottom Actions**:
- Help
- Settings
- User profile

---

### Main Content Area
```css
Margin Left: 240px (with sidebar)
Padding: 32px (Space/32)
Min Height: calc(100vh - 64px)
Background: var(--theme-bg-canvas)

Max Width: 1440px
Margin: 0 auto

@media (max-width: 1024px) {
  Margin Left: 64px (collapsed sidebar)
}

@media (max-width: 768px) {
  Margin Left: 0 (no sidebar)
  Padding: 20px (Space/20)
}
```

---

## Dashboard Components

### 1. Page Header
```
Dashboard
Home / Dashboard
                                    [+ New Project]  [•••]
───────────────────────────────────────────────────────────
```

**Specifications**:
```css
Margin Bottom: 32px (Space/32)

Title:
  Font: H2 (36px, Semi-bold)
  Color: var(--text-primary)
  Margin Bottom: 8px
  
Breadcrumbs:
  Font: Caption (14px)
  Color: var(--text-muted)
  
Actions:
  Display: flex
  Gap: 12px (Space/12)
  Margin Top: 16px
```

---

### 2. Metrics Grid
```
┌───────────────┐  ┌───────────────┐  ┌───────────────┐  ┌───────────────┐
│ [📊]          │  │ [👥]          │  │ [💰]          │  │ [📈]          │
│ Total Users   │  │ Active Users  │  │ Revenue       │  │ Growth        │
│               │  │               │  │               │  │               │
│ 12,845        │  │ 8,234         │  │ $45,231       │  │ +23.5%        │
│ +12.5% ↑      │  │ +5.2% ↑       │  │ +18.2% ↑      │  │ +2.3% ↑       │
└───────────────┘  └───────────────┘  └───────────────┘  └───────────────┘
```

**Grid Layout**:
```css
Display: grid
Grid Template Columns: repeat(auto-fit, minmax(240px, 1fr))
Gap: 24px (Space/24)
Margin Bottom: 32px (Space/32)

@media (max-width: 768px) {
  Grid Template Columns: 1fr
}
```

**Metric Card** (using Card/Metric component):
- Icon with colored background
- Label
- Large value
- Change indicator with trend

---

### 3. Charts Section
```
┌─────────────────────────────────────────────────┐
│ Revenue Overview                           [▼]  │
│ ───────────────────────────────────────────     │
│                                                 │
│         [Line Chart]                            │
│                                                 │
└─────────────────────────────────────────────────┘
```

**Chart Card**:
```css
Background: var(--theme-bg-card)
Border: 1px solid var(--border-subtle)
Border Radius: 12px (Radius/MD)
Padding: 24px (Space/24)
Box Shadow: var(--shadow-soft)
Margin Bottom: 24px (Space/24)

Header:
  Display: flex
  Justify Content: space-between
  Align Items: center
  Margin Bottom: 20px
  
Title:
  Font: H4 (22px, Medium)
```

---

### 4. Data Table Section
```
┌─────────────────────────────────────────────────┐
│ Recent Orders                    [Search] [⚙️]  │
│ ───────────────────────────────────────────     │
│                                                 │
│ ┌─┬────────┬──────────┬─────────┬──────────┐   │
│ │☑│Order ID│Customer  │Amount   │Status    │   │
│ ├─┼────────┼──────────┼─────────┼──────────┤   │
│ │☐│#1234   │John Doe  │$125.00  │COMPLETED │   │
│ │☐│#1235   │Jane S... │$89.50   │PENDING   │   │
│ └─┴────────┴──────────┴─────────┴──────────┘   │
│                                                 │
│ Showing 1-10 of 125   [1] [2] [3] → Next       │
└─────────────────────────────────────────────────┘
```

**Table Card** (using Card + Table components):
- Card header with title and actions
- Filters (chips/dropdowns)
- Data table
- Pagination

---

### 5. Activity Feed
```
┌─────────────────────────────────────────┐
│ Recent Activity                         │
│ ─────────────────────────────────       │
│                                         │
│ [👤] John Doe created a project         │
│      2 hours ago                        │
│                                         │
│ [💰] Payment received - $125.00         │
│      4 hours ago                        │
│                                         │
│ [📄] New document uploaded              │
│      Yesterday at 3:45 PM               │
│                                         │
│ [View All Activity →]                   │
└─────────────────────────────────────────┘
```

**Activity Item**:
```css
Display: flex
Gap: 12px (Space/12)
Padding: 12px 0 (Space/12 0)
Border Bottom: 1px solid var(--border-subtle)

Last Item:
  Border Bottom: none

Avatar/Icon:
  Width: 40px
  Height: 40px
  Flex Shrink: 0
  
Content:
  Flex: 1
  
  Title:
    Font: Body/Medium (16px, 500)
    Color: var(--text-primary)
    
  Time:
    Font: Caption (14px)
    Color: var(--text-muted)
    Margin Top: 4px
```

---

## Dashboard Variants

### 1. Analytics Dashboard
Focus on charts, graphs, and metrics visualization.

**Layout**:
- Full-width metrics at top
- 2-column grid for charts
- Key insights cards

### 2. Management Dashboard
Focus on tables and actionable items.

**Layout**:
- Compact metrics
- Large data tables
- Quick action buttons

### 3. Overview Dashboard
Balanced view with summaries.

**Layout**:
- Metrics row
- Mix of charts and lists
- Recent activity

---

## Responsive Behavior

### Desktop (1024px+)
```
Full sidebar (240px)
Multi-column metrics grid
Side-by-side content sections
```

### Tablet (768px - 1023px)
```
Collapsed sidebar (64px, icons only)
2-column metrics grid
Stacked content sections
```

### Mobile (<768px)
```
Hidden sidebar (hamburger menu)
Single column layout
Simplified metrics
Card-based tables
```

---

## Global Search

### Search Bar (Top Nav)
```
┌──────────────────────────────┐
│ [🔍] Search...          [⌘K] │
└──────────────────────────────┘
```

### Search Results Dropdown
```
┌────────────────────────────────┐
│ Projects                       │
│ → Project Alpha                │
│ → Dashboard Redesign           │
│                                │
│ Users                          │
│ → John Doe                     │
│ → Jane Smith                   │
│                                │
│ [View all results →]           │
└────────────────────────────────┘
```

**Specifications**:
```css
Width: 100%
Max Width: 480px
Background: var(--theme-bg-card)
Border: 1px solid var(--border-subtle)
Border Radius: 12px
Position: absolute
Top: 100%
Margin Top: 8px
Box Shadow: var(--shadow-medium)
Max Height: 480px
Overflow Y: auto

Category:
  Font: Label (12px, Uppercase)
  Color: var(--text-muted)
  Padding: 12px 16px 8px
  
Result Item:
  Padding: 10px 16px
  Display: flex
  Align Items: center
  Gap: 12px
  Cursor: pointer
  
  Hover:
    Background: var(--bg-soft)
```

---

## User Menu (Dropdown)

### Trigger
```
[👤] John Doe ▾
```

### Dropdown Menu
```
┌──────────────────────────┐
│ [👤] John Doe            │
│     john@example.com     │
├──────────────────────────┤
│ [👤] Profile             │
│ [⚙️] Settings            │
│ [📊] Analytics           │
├──────────────────────────┤
│ [❓] Help & Support      │
│ [🌙] Dark Mode    [Toggle]│
├──────────────────────────┤
│ [🚪] Sign Out            │
└──────────────────────────┘
```

---

## Notifications Panel

### Trigger (with Badge)
```
[🔔]
  3   ← Notification count
```

### Panel
```
┌──────────────────────────────────┐
│ Notifications               [×]  │
├──────────────────────────────────┤
│ ● New comment on your post       │
│   2 minutes ago                  │
├──────────────────────────────────┤
│ ● Payment received - $125        │
│   1 hour ago                     │
├──────────────────────────────────┤
│   Task assigned to you           │
│   Yesterday                      │
├──────────────────────────────────┤
│ [View All Notifications]         │
└──────────────────────────────────┘
```

**Specifications**:
```css
Position: absolute
Top: 100%
Right: 0
Width: 360px
Margin Top: 8px
Background: var(--theme-bg-card)
Border: 1px solid var(--border-subtle)
Border Radius: 12px
Box Shadow: var(--shadow-medium)
Max Height: 480px
Overflow Y: auto
```

---

## Empty States

### No Data
```
┌─────────────────────────────────┐
│                                 │
│            [📊]                 │
│                                 │
│       No data available         │
│                                 │
│   Start by creating your first  │
│   project or import data        │
│                                 │
│     [Create Project]            │
│                                 │
└─────────────────────────────────┘
```

### No Results
```
┌─────────────────────────────────┐
│           [🔍]                  │
│                                 │
│    No results found             │
│                                 │
│ Try adjusting your search       │
│ or filter criteria              │
└─────────────────────────────────┘
```

---

## Loading States

### Page Loading
- Show skeleton loaders for metrics
- Skeleton table rows
- Pulsing chart placeholders

### Lazy Loading
- Load more indicator at bottom
- Infinite scroll with loader

---

## Implementation Example

### HTML
```html
<div class="dashboard-layout">
  <!-- Top Nav -->
  <nav class="dashboard-nav">
    <div class="nav-left">
      <img src="logo.svg" alt="PS Technologies" class="nav-logo" />
    </div>
    <div class="nav-center">
      <input type="search" class="search-input" placeholder="Search..." />
    </div>
    <div class="nav-right">
      <button class="icon-button" aria-label="Notifications">
        <svg>🔔</svg>
        <span class="badge-count">3</span>
      </button>
      <button class="user-menu-trigger">
        <img src="avatar.jpg" class="avatar avatar-sm" />
      </button>
    </div>
  </nav>
  
  <!-- Sidebar -->
  <aside class="dashboard-sidebar">
    <nav class="sidebar-nav">
      <a href="/dashboard" class="nav-item active">
        <svg>🏠</svg>
        <span>Home</span>
      </a>
      <a href="/analytics" class="nav-item">
        <svg>📊</svg>
        <span>Analytics</span>
      </a>
      <a href="/settings" class="nav-item">
        <svg>⚙️</svg>
        <span>Settings</span>
      </a>
    </nav>
  </aside>
  
  <!-- Main Content -->
  <main class="dashboard-main">
    <header class="page-header">
      <div>
        <h1 class="page-title">Dashboard</h1>
        <div class="breadcrumbs">Home / Dashboard</div>
      </div>
      <div class="page-actions">
        <button class="btn btn-primary">+ New Project</button>
      </div>
    </header>
    
    <!-- Metrics -->
    <div class="metrics-grid">
      <!-- Metric cards -->
    </div>
    
    <!-- Content Sections -->
    <div class="dashboard-content">
      <!-- Charts, tables, etc. -->
    </div>
  </main>
</div>
```

---

## Accessibility

✅ **Keyboard Navigation**: Full keyboard support
✅ **Focus Management**: Proper focus indicators
✅ **ARIA Labels**: Clear labels for all interactive elements
✅ **Skip Links**: Skip to main content
✅ **Screen Reader**: Proper heading hierarchy
✅ **Live Regions**: Announce updates

---

## Performance

✅ Lazy load charts and heavy components
✅ Virtual scrolling for long lists
✅ Debounce search input
✅ Cache frequently accessed data
✅ Optimize chart rendering

---

**Last Updated**: December 2025  
**Version**: 1.0  
**Maintained by**: PS Technologies Design Team
