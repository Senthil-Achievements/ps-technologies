# PS Technologies Design System
## Components: Cards

---

### Overview
Cards are flexible containers that group related content and actions. They serve as primary building blocks for dashboards, marketing features, and content organization.

---

## Base Card

### Anatomy
```
┌─────────────────────────────────┐
│ [Icon] Title              [Menu]│  ← Header
│ ─────────────────────────────── │
│                                 │
│ Body content goes here with     │  ← Body
│ description text and details    │
│                                 │
│ ─────────────────────────────── │
│ [Button]        Footer info     │  ← Footer
└─────────────────────────────────┘
```

### Default Specifications
```css
Background: var(--theme-bg-card)
Border: 1px solid var(--border-subtle)
Border Radius: 12px (Radius/MD)
Box Shadow: var(--shadow-soft)
Padding: 20px-24px (Space/20-24)
```

### Component: Card / Base
```css
Background: #FFFFFF (Light) / #1E293B (Dark)
Border Radius: 12px
Box Shadow: 0px 1px 2px rgba(15, 23, 42, 0.05),
            0px 1px 3px rgba(15, 23, 42, 0.10)
Padding: 24px (Space/24)
Gap (Internal): 16px (Space/16)
```

### Hover State (Interactive)
```css
Box Shadow: var(--shadow-medium)
Transform: translateY(-2px)
Transition: all 0.2s ease
Border Color: var(--border-strong)
```

---

## Card Variants

### 1. Card / Metric
**Use Case**: Dashboard statistics, KPIs

```
┌─────────────────────────────────┐
│ [📊] Total Revenue              │
│                                 │
│ $45,231.89                      │
│ +20.1% from last month          │
└─────────────────────────────────┘
```

**Specifications**:
```css
Padding: 20px (Space/20)
Icon Size: 20px
Icon Color: var(--accent-primary)

Title:
  Font: Caption/Medium (14px, 500)
  Color: var(--text-muted)
  
Value:
  Font: H3 (28px, Medium)
  Color: var(--text-primary)
  Margin Top: 8px
  
Change Indicator:
  Font: Caption (14px)
  Color: #22C55E (positive) / #EF4444 (negative)
  Margin Top: 4px
  Icon: Up/Down arrow
```

### 2. Card / Feature
**Use Case**: Marketing features, service descriptions

```
┌─────────────────────────────────┐
│           [🚀]                  │
│                                 │
│   Lightning Fast Performance    │
│                                 │
│   Optimized for speed with      │
│   cutting-edge technology       │
│                                 │
│   [Learn More →]                │
└─────────────────────────────────┘
```

**Specifications**:
```css
Padding: 32px (Space/32)
Text Align: center
Icon Size: 48px
Icon Background: Soft gradient circle

Title:
  Font: H4 (22px, Medium)
  Margin Top: 16px
  
Description:
  Font: Body (16px, Regular)
  Color: var(--text-secondary)
  Margin Top: 12px
  Max Width: 320px
  
Action:
  Margin Top: 20px
```

### 3. Card / List Item
**Use Case**: List views, search results

```
┌─────────────────────────────────┐
│ [Avatar] John Doe               │
│          john@example.com       │
│          Last seen 2h ago   [•••]│
└─────────────────────────────────┘
```

**Specifications**:
```css
Padding: 16px (Space/16)
Display: flex
Align Items: center
Gap: 12px

Avatar: 40px circular

Content:
  Flex: 1
  
  Title:
    Font: Body/Medium (16px, 500)
    
  Subtitle:
    Font: Caption (14px)
    Color: var(--text-muted)
    Margin Top: 2px
    
Actions:
  Icon Button (Ghost)
```

### 4. Card / Pricing
**Use Case**: Pricing tiers

```
┌─────────────────────────────────┐
│          STARTER                │
│                                 │
│         $29/month               │
│                                 │
│ ✓ 10 Projects                   │
│ ✓ 100 GB Storage                │
│ ✓ Email Support                 │
│ ✗ Priority Support              │
│                                 │
│ [Get Started]                   │
└─────────────────────────────────┘
```

**Specifications**:
```css
Padding: 32px (Space/32)
Border: 2px solid var(--border-subtle)

Popular/Highlight:
  Border: 2px solid var(--accent-primary)
  Position: relative
  
  Badge "Popular":
    Position: absolute
    Top: -12px
    Background: var(--accent-gradient)
    
Plan Name:
  Font: Label (12px, Uppercase)
  Color: var(--text-muted)
  Letter Spacing: 0.05em
  
Price:
  Font: H2 (36px, Semi-bold)
  Margin: 16px 0
  
Features List:
  Gap: 12px
  Margin: 24px 0
  
  Feature Item:
    Font: Body (16px)
    Display: flex
    Align Items: center
    Gap: 10px
    
    Icon: 16px checkmark (green) or X (muted)
    
CTA Button:
  Margin Top: 24px
  Full Width
```

### 5. Card / Article/Blog
**Use Case**: Blog posts, articles

```
┌─────────────────────────────────┐
│ [Featured Image]                │
│                                 │
│ Product Updates                 │
│                                 │
│ Introducing AI-Powered Features │
│                                 │
│ Discover how our new AI tools   │
│ can help you work faster...     │
│                                 │
│ [Avatar] Jane Doe   •  Dec 9    │
└─────────────────────────────────┘
```

**Specifications**:
```css
Padding: 0 (Image full-bleed at top)
Content Padding: 20px (Space/20)

Image:
  Aspect Ratio: 16:9
  Border Radius: 12px 12px 0 0
  Object Fit: cover
  
Category Badge:
  Position: absolute
  Top: 16px, Left: 16px
  
Title:
  Font: H4 (22px, Medium)
  Margin Top: 16px
  
Excerpt:
  Font: Body (16px)
  Color: var(--text-secondary)
  Margin Top: 8px
  Line Clamp: 2
  
Meta:
  Display: flex
  Align Items: center
  Gap: 12px
  Margin Top: 16px
  Font: Caption (14px)
  Color: var(--text-muted)
```

---

## Special States

### Loading State
```
┌─────────────────────────────────┐
│ ▓▓▓▓▓▓▓▓▓░░░░░░░░░░░░░░         │  ← Skeleton title
│                                 │
│ ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓░░░░░           │  ← Skeleton line
│ ▓▓▓▓▓▓▓▓▓▓▓▓░░░░░░░░             │  ← Skeleton line
│                                 │
│ ▓▓▓▓▓░░░░░░░                    │  ← Skeleton footer
└─────────────────────────────────┘
```

**Implementation**: Pulsing gradient animation

### Empty State
```
┌─────────────────────────────────┐
│                                 │
│          [📭]                   │
│                                 │
│      No items found             │
│                                 │
│  Start by creating your first   │
│  project or contact support     │
│                                 │
│      [Create Project]           │
│                                 │
└─────────────────────────────────┘
```

---

## Card Actions

### Action Menu (3-dot)
```
┌─────────────────────────────────┐
│ Title                      [•••]│  ← Menu trigger
└─────────────────────────────────┘
```

**Dropdown Menu**:
```
┌──────────────────┐
│ Edit             │
│ Duplicate        │
│ ──────────       │
│ Delete           │  ← Destructive, red text
└──────────────────┘
```

### Expandable Card
```
┌─────────────────────────────────┐
│ Collapsed Title            [˅]  │
└─────────────────────────────────┘

(When expanded)
┌─────────────────────────────────┐
│ Expanded Title             [˄]  │
│ ─────────────────────────────── │
│                                 │
│ Additional content shown here   │
│                                 │
└─────────────────────────────────┘
```

---

## Card Layouts

### Grid Layout
```css
Display: grid
Grid Template Columns: repeat(auto-fill, minmax(320px, 1fr))
Gap: 24px (Space/24)

/* Responsive */
Mobile: 1 column
Tablet: 2 columns
Desktop: 3-4 columns
```

### Masonry Layout
```css
Display: grid
Grid Template Rows: masonry (if supported)
Or use CSS columns
```

---

## Implementation

### HTML
```html
<!-- Base Card -->
<div class="card">
  <div class="card-header">
    <h3 class="card-title">Card Title</h3>
    <button class="card-menu" aria-label="Menu">•••</button>
  </div>
  <div class="card-body">
    <p>Card content goes here...</p>
  </div>
  <div class="card-footer">
    <button class="btn btn-primary">Action</button>
  </div>
</div>

<!-- Metric Card -->
<div class="card card-metric">
  <div class="card-metric-icon">📊</div>
  <div class="card-metric-label">Total Revenue</div>
  <div class="card-metric-value">$45,231.89</div>
  <div class="card-metric-change positive">
    <span class="icon">↑</span>
    <span>+20.1%</span>
  </div>
</div>
```

### CSS
```css
/* Base Card */
.card {
  background: var(--theme-bg-card);
  border: 1px solid var(--border-subtle);
  border-radius: var(--radius-md);
  box-shadow: var(--shadow-soft);
  padding: var(--space-24);
  display: flex;
  flex-direction: column;
  gap: var(--space-16);
  transition: all 0.2s ease;
}

.card:hover.card-interactive {
  box-shadow: var(--shadow-medium);
  transform: translateY(-2px);
  border-color: var(--border-strong);
}

/* Card Header */
.card-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: var(--space-12);
}

.card-title {
  font-size: 1.375rem;
  font-weight: 500;
  color: var(--text-primary);
  margin: 0;
}

/* Card Body */
.card-body {
  flex: 1;
  color: var(--text-secondary);
}

/* Card Footer */
.card-footer {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding-top: var(--space-16);
  border-top: 1px solid var(--border-subtle);
}

/* Metric Card */
.card-metric {
  padding: var(--space-20);
}

.card-metric-icon {
  font-size: 20px;
  margin-bottom: var(--space-8);
}

.card-metric-label {
  font-size: 0.875rem;
  font-weight: 500;
  color: var(--text-muted);
  text-transform: uppercase;
  letter-spacing: 0.05em;
}

.card-metric-value {
  font-size: 1.75rem;
  font-weight: 500;
  color: var(--text-primary);
  margin-top: var(--space-8);
}

.card-metric-change {
  display: flex;
  align-items: center;
  gap: var(--space-4);
  font-size: 0.875rem;
  margin-top: var(--space-4);
}

.card-metric-change.positive {
  color: var(--color-success);
}

.card-metric-change.negative {
  color: var(--color-error);
}

/* Loading Skeleton */
.card-skeleton .skeleton {
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
```

### React Component
```typescript
import React from 'react';

interface CardProps {
  variant?: 'base' | 'metric' | 'feature' | 'list' | 'pricing';
  interactive?: boolean;
  children: React.ReactNode;
  className?: string;
}

export const Card: React.FC<CardProps> = ({
  variant = 'base',
  interactive = false,
  children,
  className = '',
}) => {
  const classes = [
    'card',
    `card-${variant}`,
    interactive && 'card-interactive',
    className
  ].filter(Boolean).join(' ');

  return (
    <div className={classes}>
      {children}
    </div>
  );
};

export const CardHeader: React.FC<{ children: React.ReactNode }> = ({ children }) => (
  <div className="card-header">{children}</div>
);

export const CardBody: React.FC<{ children: React.ReactNode }> = ({ children }) => (
  <div className="card-body">{children}</div>
);

export const CardFooter: React.FC<{ children: React.ReactNode }> = ({ children }) => (
  <div className="card-footer">{children}</div>
);
```

---

## Accessibility

✅ **Semantic HTML**: Use appropriate heading levels
✅ **Focus Management**: Interactive cards are keyboard accessible
✅ **ARIA Labels**: Menu buttons have clear labels
✅ **Color Contrast**: All text meets WCAG standards
✅ **Touch Targets**: Minimum 44×44px for interactive elements

---

## Usage Guidelines

### Do's
✅ Use cards to group related content
✅ Maintain consistent padding across card types
✅ Add hover effects for interactive cards
✅ Keep card content scannable
✅ Use shadows to create depth hierarchy

### Don'ts
❌ Don't nest cards within cards
❌ Don't overcrowd cards with too much information
❌ Don't use cards for single lines of text
❌ Don't create cards wider than 600px for readability
❌ Don't forget empty states

---

**Last Updated**: December 2025  
**Version**: 1.0  
**Maintained by**: PS Technologies Design Team
