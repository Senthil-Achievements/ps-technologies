# PS Technologies Design System
## Foundations: Spacing & Layout

---

### Philosophy
PS Technologies uses an 8-point spacing system that creates visual rhythm and consistency across all interfaces. This system ensures harmonious layouts that scale predictably across different screen sizes.

---

## Spacing Scale

### Base Unit
**Base**: 8px (0.5rem)

All spacing values are multiples or fractions of this base unit, creating a cohesive visual rhythm.

### Spacing Tokens

```
Space/2:   2px   (0.125rem)  // Hairline spacing
Space/4:   4px   (0.25rem)   // Minimal spacing
Space/8:   8px   (0.5rem)    // Extra small
Space/12:  12px  (0.75rem)   // Small
Space/16:  16px  (1rem)      // Medium
Space/20:  20px  (1.25rem)   // Default
Space/24:  24px  (1.5rem)    // Large
Space/32:  32px  (2rem)      // Extra large
Space/40:  40px  (2.5rem)    // 2X large
Space/48:  48px  (3rem)      // 3X large
Space/56:  56px  (3.5rem)    // 4X large
Space/64:  64px  (4rem)      // 5X large
Space/80:  80px  (5rem)      // Section spacing
Space/96:  96px  (6rem)      // Large section spacing
Space/128: 128px (8rem)      // Hero spacing
```

---

## Usage Guidelines

### Component Internal Spacing

#### Buttons
```
Padding (Small):     8px 16px (Space/8 Space/16)
Padding (Medium):    12px 24px (Space/12 Space/24)
Padding (Large):     16px 32px (Space/16 Space/32)
Gap (Icon + Text):   8px (Space/8)
```

#### Input Fields
```
Padding:             12px 16px (Space/12 Space/16)
Gap (Label + Input): 8px (Space/8)
Gap (Input + Helper):4px (Space/4)
```

#### Cards
```
Padding (Small):     16px (Space/16)
Padding (Medium):    20px (Space/20)
Padding (Large):     24px (Space/24)
Gap (Title + Body):  12px (Space/12)
Gap (Body + Footer): 16px (Space/16)
```

#### Modal/Dialog
```
Padding:             24px (Space/24)
Gap (Title + Body):  16px (Space/16)
Gap (Body + Footer): 24px (Space/24)
```

### Layout Spacing

#### Section Spacing
```
Between sections (Desktop):  80px-96px (Space/80-96)
Between sections (Mobile):   56px-64px (Space/56-64)
```

#### Component Stacking
```
Tight grouping:      8px (Space/8)
Related items:       16px (Space/16)
Separate sections:   32px (Space/32)
Major sections:      48px-64px (Space/48-64)
```

#### Grid/Column Gaps
```
Dense grid:          16px (Space/16)
Standard grid:       24px (Space/24)
Loose grid:          32px (Space/32)
```

---

## Border Radius

### Radius Scale

```
Radius/XS:   4px   (0.25rem)  // Subtle rounding
Radius/SM:   8px   (0.5rem)   // Small components
Radius/MD:   12px  (0.75rem)  // Default components
Radius/LG:   16px  (1rem)     // Large cards, modals
Radius/XL:   20px  (1.25rem)  // Hero sections
Radius/2XL:  24px  (1.5rem)   // Extra large elements
Radius/Full: 9999px            // Pills, circular elements
```

### Component Radius Map

```
Buttons:              Radius/Full (9999px) for pill style
                      Radius/MD (12px) for standard
Input Fields:         Radius/MD (12px)
Cards:                Radius/MD (12px)
Modals:               Radius/LG (16px)
Badges/Tags:          Radius/SM (8px)
Avatars:              Radius/Full (9999px)
Tooltips:             Radius/SM (8px)
Dropdown Menus:       Radius/MD (12px)
Large Hero Cards:     Radius/XL (20px)
Code Blocks:          Radius/SM (8px)
Images/Thumbnails:    Radius/MD (12px)
```

---

## Container Sizes

### Max Width Constraints

```
Container/XS:   448px  (28rem)   // Narrow forms
Container/SM:   640px  (40rem)   // Standard forms, modals
Container/MD:   768px  (48rem)   // Content articles
Container/LG:   1024px (64rem)   // Standard page content
Container/XL:   1280px (80rem)   // Wide layouts
Container/2XL:  1536px (96rem)   // Extra wide dashboards
Container/Full: 100%              // Full bleed
```

### Usage
```
Marketing Hero:       Container/2XL (1536px)
Marketing Content:    Container/LG (1024px)
Dashboard:            Container/Full with padding
Auth Forms:           Container/XS (448px)
Settings Pages:       Container/MD (768px)
Data Tables:          Container/XL (1280px)
```

---

## Grid System

### 12-Column Grid

```css
Grid Columns:         12
Column Gap (Desktop): 24px (Space/24)
Column Gap (Tablet):  20px (Space/20)
Column Gap (Mobile):  16px (Space/16)
```

### Breakpoints
```
Mobile:     < 768px
Tablet:     768px - 1023px
Desktop:    1024px - 1439px
Wide:       ≥ 1440px
```

### Common Layouts

#### Two-Column (Desktop)
```
Sidebar + Content:    3 cols + 9 cols
Content + Aside:      8 cols + 4 cols
Split Equal:          6 cols + 6 cols
```

#### Three-Column
```
Equal:                4 cols + 4 cols + 4 cols
Feature Cards:        4 cols each
```

#### Four-Column
```
Pricing/Features:     3 cols each
```

---

## Responsive Padding

### Page/Section Padding

```css
/* Desktop (1024px+) */
Horizontal Padding:   40px-64px (Space/40-64)
Vertical Padding:     64px-96px (Space/64-96)

/* Tablet (768px-1023px) */
Horizontal Padding:   32px (Space/32)
Vertical Padding:     48px-64px (Space/48-64)

/* Mobile (<768px) */
Horizontal Padding:   16px-20px (Space/16-20)
Vertical Padding:     40px-48px (Space/40-48)
```

---

## Elevation & Depth

While shadows are covered separately, spacing contributes to depth through:

### Z-Index Scale
```
z-0:     0      // Base layer
z-10:    10     // Dropdowns, popovers
z-20:    20     // Sticky headers
z-30:    30     // Modals backdrop
z-40:    40     // Modal content
z-50:    50     // Toasts, notifications
z-max:   9999   // Extreme overlays
```

---

## Implementation

### CSS Variables
```css
:root {
  /* Spacing Scale */
  --space-2: 0.125rem;   /* 2px */
  --space-4: 0.25rem;    /* 4px */
  --space-8: 0.5rem;     /* 8px */
  --space-12: 0.75rem;   /* 12px */
  --space-16: 1rem;      /* 16px */
  --space-20: 1.25rem;   /* 20px */
  --space-24: 1.5rem;    /* 24px */
  --space-32: 2rem;      /* 32px */
  --space-40: 2.5rem;    /* 40px */
  --space-48: 3rem;      /* 48px */
  --space-56: 3.5rem;    /* 56px */
  --space-64: 4rem;      /* 64px */
  --space-80: 5rem;      /* 80px */
  --space-96: 6rem;      /* 96px */
  --space-128: 8rem;     /* 128px */
  
  /* Radius Scale */
  --radius-xs: 0.25rem;  /* 4px */
  --radius-sm: 0.5rem;   /* 8px */
  --radius-md: 0.75rem;  /* 12px */
  --radius-lg: 1rem;     /* 16px */
  --radius-xl: 1.25rem;  /* 20px */
  --radius-2xl: 1.5rem;  /* 24px */
  --radius-full: 9999px;
  
  /* Container Sizes */
  --container-xs: 28rem;   /* 448px */
  --container-sm: 40rem;   /* 640px */
  --container-md: 48rem;   /* 768px */
  --container-lg: 64rem;   /* 1024px */
  --container-xl: 80rem;   /* 1280px */
  --container-2xl: 96rem;  /* 1536px */
}
```

### Utility Classes
```css
/* Spacing Utilities */
.p-2 { padding: var(--space-2); }
.p-4 { padding: var(--space-4); }
.p-8 { padding: var(--space-8); }
.p-12 { padding: var(--space-12); }
.p-16 { padding: var(--space-16); }
.p-20 { padding: var(--space-20); }
.p-24 { padding: var(--space-24); }
.p-32 { padding: var(--space-32); }
.p-40 { padding: var(--space-40); }
.p-48 { padding: var(--space-48); }
.p-64 { padding: var(--space-64); }

/* Margin Utilities */
.m-2 { margin: var(--space-2); }
.m-4 { margin: var(--space-4); }
.m-8 { margin: var(--space-8); }
.m-12 { margin: var(--space-12); }
.m-16 { margin: var(--space-16); }
.m-20 { margin: var(--space-20); }
.m-24 { margin: var(--space-24); }
.m-32 { margin: var(--space-32); }

/* Gap Utilities */
.gap-2 { gap: var(--space-2); }
.gap-4 { gap: var(--space-4); }
.gap-8 { gap: var(--space-8); }
.gap-12 { gap: var(--space-12); }
.gap-16 { gap: var(--space-16); }
.gap-20 { gap: var(--space-20); }
.gap-24 { gap: var(--space-24); }
.gap-32 { gap: var(--space-32); }

/* Radius Utilities */
.rounded-xs { border-radius: var(--radius-xs); }
.rounded-sm { border-radius: var(--radius-sm); }
.rounded-md { border-radius: var(--radius-md); }
.rounded-lg { border-radius: var(--radius-lg); }
.rounded-xl { border-radius: var(--radius-xl); }
.rounded-2xl { border-radius: var(--radius-2xl); }
.rounded-full { border-radius: var(--radius-full); }
```

### Tailwind Configuration
```javascript
module.exports = {
  theme: {
    spacing: {
      '2': '0.125rem',
      '4': '0.25rem',
      '8': '0.5rem',
      '12': '0.75rem',
      '16': '1rem',
      '20': '1.25rem',
      '24': '1.5rem',
      '32': '2rem',
      '40': '2.5rem',
      '48': '3rem',
      '56': '3.5rem',
      '64': '4rem',
      '80': '5rem',
      '96': '6rem',
      '128': '8rem',
    },
    borderRadius: {
      'xs': '0.25rem',
      'sm': '0.5rem',
      'md': '0.75rem',
      'lg': '1rem',
      'xl': '1.25rem',
      '2xl': '1.5rem',
      'full': '9999px',
    },
    maxWidth: {
      'xs': '28rem',
      'sm': '40rem',
      'md': '48rem',
      'lg': '64rem',
      'xl': '80rem',
      '2xl': '96rem',
    },
  },
}
```

---

## Usage Guidelines

### Do's
✅ Use spacing tokens consistently — never arbitrary values
✅ Maintain 8px multiples for all spacing
✅ Use larger spacing for section breaks, smaller for related items
✅ Apply consistent padding to all sides of containers
✅ Use border radius consistently per component type

### Don'ts
❌ Don't use spacing values outside the defined scale
❌ Don't mix different spacing systems
❌ Don't use inconsistent border radius on the same component
❌ Don't create visual clutter with too little spacing
❌ Don't over-space related elements

---

**Last Updated**: December 2025  
**Version**: 1.0  
**Maintained by**: PS Technologies Design Team
