# PS Technologies Design System
## Components: Navigation

---

## Top Navigation Bar

### Anatomy (Marketing Site)
```
┌──────────────────────────────────────────────────────────┐
│ [Logo]  Home  Product  Pricing  Resources  [Get Started] │
└──────────────────────────────────────────────────────────┘
```

### Specifications
```css
Height: 64px (Space/64)
Background: var(--theme-bg-card) with backdrop blur
Border Bottom: 1px solid var(--border-subtle)
Padding: 0 40px (0 Space/40)
Position: sticky
Top: 0
Z-Index: 20
Backdrop Filter: blur(12px) saturate(180%)
Box Shadow: none (adds shadow on scroll)
```

### Logo Area
```css
Height: 32px
Display: flex
Align Items: center
Gap: 12px
Font Weight: 600
Font Size: 18px
Color: var(--text-primary)
```

### Nav Items
```css
Display: flex
Gap: 32px (Space/32)
Align Items: center

Link:
  Font: Body/Medium (16px, 500)
  Color: var(--text-secondary)
  Padding: 8px 12px
  Border Radius: 8px
  Transition: 0.2s ease
  
Link Hover:
  Color: var(--text-primary)
  Background: var(--bg-soft)
  
Link Active:
  Color: var(--accent-primary)
  Background: rgba(79, 70, 229, 0.08)
```

### CTA Button
```css
Variant: Primary
Size: Medium
Margin Left: auto
```

### Sticky/Scrolled State
```css
Box Shadow: var(--shadow-soft)
Background: rgba(255, 255, 255, 0.9) (light)
            rgba(30, 41, 59, 0.9) (dark)
```

---

## Mobile Navigation

### Hamburger Menu
```
┌────────────────────────┐
│ [Logo]           [≡]   │
└────────────────────────┘
```

### Menu Open
```
┌────────────────────────┐
│ [Logo]           [×]   │
├────────────────────────┤
│                        │
│ Home                   │
│ Product                │
│ Pricing                │
│ Resources              │
│                        │
│ [Get Started]          │
│                        │
└────────────────────────┘
```

**Specifications**:
```css
Mobile Menu:
  Position: fixed
  Top: 64px
  Left: 0, Right: 0, Bottom: 0
  Background: var(--theme-bg-card)
  Padding: 24px (Space/24)
  Z-Index: 30
  
  Animation: Slide down from top
  
  Links:
    Display: block
    Padding: 16px (Space/16)
    Font Size: 18px
    Border Bottom: 1px solid var(--border-subtle)
```

---

## Sidebar Navigation (Dashboard)

### Anatomy
```
┌──────────────┐
│ [Logo]       │
│              │
│ [🏠] Home    │
│ [📊] Metrics │
│ [⚙️] Settings│
│              │
│ ─────────    │
│              │
│ [❓] Help    │
│ [👤] Profile │
└──────────────┘
```

### Specifications
```css
Width: 240px (expanded) / 64px (collapsed)
Height: 100vh
Position: fixed
Left: 0
Top: 0
Background: var(--theme-bg-card)
Border Right: 1px solid var(--border-subtle)
Padding: 20px (Space/20)
Z-Index: 10
Transition: width 0.3s ease
```

### Nav Item
```css
Display: flex
Align Items: center
Gap: 12px (Space/12)
Padding: 12px 16px (Space/12 Space/16)
Border Radius: 8px (Radius/SM)
Font: Body/Medium (16px, 500)
Color: var(--text-secondary)
Transition: 0.2s ease
Margin Bottom: 4px (Space/4)

Icon:
  Size: 20px
  Color: inherit
  
Text:
  Display: none when collapsed
  
Hover:
  Background: var(--bg-soft)
  Color: var(--text-primary)
  
Active:
  Background: rgba(79, 70, 229, 0.12)
  Color: var(--accent-primary)
  Border Left: 3px solid var(--accent-primary)
```

### Collapse Toggle
```css
Position: absolute
Top: 20px
Right: -12px
Width: 24px
Height: 24px
Background: var(--theme-bg-card)
Border: 1px solid var(--border-subtle)
Border Radius: 50%
Display: flex
Align Items: center
Justify Content: center
Cursor: pointer
Z-Index: 11
```

---

## Breadcrumbs

### Basic
```
Home / Products / Category / Item Name
```

### Specifications
```css
Display: flex
Align Items: center
Gap: 8px (Space/8)
Font: Caption/Medium (14px, 500)
Color: var(--text-muted)
Margin Bottom: 20px (Space/20)

Link:
  Color: var(--text-muted)
  
Link Hover:
  Color: var(--accent-primary)
  Text Decoration: underline
  
Current (Last item):
  Color: var(--text-primary)
  Font Weight: 500
  
Separator:
  Content: "/"
  Color: var(--border-strong)
  User Select: none
```

### With Icons
```
[🏠] Home / [📁] Products / Item
```

---

## Tabs

### Variant 1: Underline Tabs
```
──────────────────────────────────
  Tab 1     Tab 2     Tab 3
  ━━━━━
```

**Specifications**:
```css
Display: flex
Gap: 32px (Space/32)
Border Bottom: 1px solid var(--border-subtle)

Tab:
  Padding: 12px 0 (Space/12 0)
  Font: Body/Medium (16px, 500)
  Color: var(--text-muted)
  Position: relative
  Cursor: pointer
  Transition: 0.2s ease
  
  Border Bottom: 2px solid transparent
  Margin Bottom: -1px
  
Tab Hover:
  Color: var(--text-primary)
  
Tab Active:
  Color: var(--accent-primary)
  Border Bottom: 2px solid var(--accent-primary)
```

### Variant 2: Pill Tabs
```
┌────────┐  ┌────────┐  ┌────────┐
│  Tab 1 │  │  Tab 2 │  │  Tab 3 │
└────────┘  └────────┘  └────────┘
   ▓▓▓▓
```

**Specifications**:
```css
Display: inline-flex
Background: var(--bg-soft)
Padding: 4px (Space/4)
Border Radius: 10px (Radius/MD)
Gap: 4px (Space/4)

Tab:
  Padding: 8px 16px (Space/8 Space/16)
  Font: Body/Medium (16px, 500)
  Color: var(--text-secondary)
  Background: transparent
  Border Radius: 8px (Radius/SM)
  Cursor: pointer
  Transition: 0.2s ease
  
Tab Active:
  Background: var(--theme-bg-card)
  Color: var(--text-primary)
  Box Shadow: var(--shadow-soft)
```

---

## Pagination

### Standard
```
← Previous   1  2  [3]  4  5   Next →
```

**Specifications**:
```css
Display: flex
Align Items: center
Gap: 8px (Space/8)
Font: Body/Medium (16px, 500)

Page Button:
  Width: 40px
  Height: 40px
  Display: flex
  Align Items: center
  Justify Content: center
  Border Radius: 8px (Radius/SM)
  Color: var(--text-secondary)
  Background: transparent
  Cursor: pointer
  
Page Hover:
  Background: var(--bg-soft)
  Color: var(--text-primary)
  
Page Active:
  Background: var(--accent-primary)
  Color: white
  
Prev/Next Button:
  Padding: 8px 16px (Space/8 Space/16)
  Gap: 8px
  
Disabled:
  Opacity: 0.4
  Cursor: not-allowed
```

### With Page Info
```
Showing 1-10 of 100 items

← Previous   1  2  [3]  4  5   Next →
```

---

## Implementation

### HTML - Top Nav
```html
<nav class="top-nav" id="topNav">
  <div class="nav-container">
    <a href="/" class="nav-logo">
      <img src="logo.svg" alt="PS Technologies" />
      PS Technologies
    </a>
    
    <ul class="nav-links">
      <li><a href="/" class="nav-link active">Home</a></li>
      <li><a href="/product" class="nav-link">Product</a></li>
      <li><a href="/pricing" class="nav-link">Pricing</a></li>
      <li><a href="/resources" class="nav-link">Resources</a></li>
    </ul>
    
    <button class="btn btn-primary">Get Started</button>
    
    <button class="mobile-menu-toggle" aria-label="Menu">
      <span class="hamburger"></span>
    </button>
  </div>
</nav>
```

### CSS - Top Nav
```css
.top-nav {
  position: sticky;
  top: 0;
  z-index: 20;
  height: 64px;
  background: var(--theme-bg-card);
  border-bottom: 1px solid var(--border-subtle);
  backdrop-filter: blur(12px) saturate(180%);
  transition: box-shadow 0.2s ease;
}

.top-nav.scrolled {
  box-shadow: var(--shadow-soft);
}

.nav-container {
  max-width: var(--container-2xl);
  margin: 0 auto;
  padding: 0 var(--space-40);
  height: 100%;
  display: flex;
  align-items: center;
  gap: var(--space-32);
}

.nav-logo {
  display: flex;
  align-items: center;
  gap: var(--space-12);
  font-weight: 600;
  font-size: 1.125rem;
  color: var(--text-primary);
  text-decoration: none;
}

.nav-links {
  display: flex;
  gap: var(--space-32);
  list-style: none;
  margin: 0;
  padding: 0;
}

.nav-link {
  padding: var(--space-8) var(--space-12);
  font-size: 1rem;
  font-weight: 500;
  color: var(--text-secondary);
  text-decoration: none;
  border-radius: var(--radius-sm);
  transition: all 0.2s ease;
}

.nav-link:hover {
  color: var(--text-primary);
  background: var(--bg-soft);
}

.nav-link.active {
  color: var(--accent-primary);
  background: rgba(79, 70, 229, 0.08);
}

.mobile-menu-toggle {
  display: none;
  margin-left: auto;
}

@media (max-width: 768px) {
  .nav-links {
    display: none;
  }
  
  .mobile-menu-toggle {
    display: block;
  }
}
```

### JavaScript - Sticky Nav
```javascript
const topNav = document.getElementById('topNav');

window.addEventListener('scroll', () => {
  if (window.scrollY > 10) {
    topNav.classList.add('scrolled');
  } else {
    topNav.classList.remove('scrolled');
  }
});
```

---

## Accessibility

✅ **Keyboard Navigation**: Full Tab support
✅ **ARIA Labels**: Clear labels for all interactive elements
✅ **Focus Indicators**: Visible focus states
✅ **Skip Links**: "Skip to main content" link
✅ **Semantic HTML**: Proper nav, ul, li structure
✅ **Mobile Menu**: Keyboard accessible

---

## Usage Guidelines

### Do's
✅ Keep navigation simple and scannable
✅ Highlight current page/section
✅ Use consistent navigation across site
✅ Provide clear visual hierarchy
✅ Make CTAs stand out

### Don'ts
❌ Don't hide critical nav items in dropdowns
❌ Don't use more than 7 top-level items
❌ Don't forget mobile navigation
❌ Don't remove focus indicators
❌ Don't use vague labels like "Miscellaneous"

---

**Last Updated**: December 2025  
**Version**: 1.0  
**Maintained by**: PS Technologies Design Team
