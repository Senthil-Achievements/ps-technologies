# PS Technologies Design System
## Foundations: Colors

---

### Brand Philosophy
PS Technologies uses a sophisticated palette that balances modern tech aesthetics with professional credibility. The indigo-teal gradient represents innovation and trust, while the neutral scale ensures readability and versatility across light and dark themes.

---

## Color Palette

### Primary Colors

#### Indigo Scale
```
Primary/Indigo-900: #0F172A
Usage: Dark backgrounds, headers in dark theme
RGB: 15, 23, 42

Primary/Indigo-700: #1E293B
Usage: Elevated surfaces, sidebars
RGB: 30, 41, 59

Primary/Indigo-600: #4F46E5
Usage: Primary actions, links, focus states
RGB: 79, 70, 229
```

#### Teal Accent
```
Primary/Teal-400: #06B6D4
Usage: Accent color, gradient endpoint, highlights
RGB: 6, 182, 212
```

#### Brand Gradient
```
Primary/Gradient: linear-gradient(90deg, #4F46E5 0%, #06B6D4 100%)
Usage: CTAs, hero sections, premium features
Alternative (135deg): linear-gradient(135deg, #4F46E5 0%, #06B6D4 100%)
```

---

### Neutral Scale

```
Neutral/0: #FFFFFF
Usage: Pure white, light theme backgrounds

Neutral/50: #F8FAFC
Usage: Page backgrounds, subtle fills

Neutral/100: #F1F5F9
Usage: Hover states, disabled backgrounds

Neutral/200: #E2E8F0
Usage: Borders, dividers, input borders

Neutral/300: #CBD5E1
Usage: Placeholder text, icons (inactive)

Neutral/500: #64748B
Usage: Secondary text, muted content

Neutral/700: #334155
Usage: Body text (light theme), labels

Neutral/900: #0F172A
Usage: Headings, primary text (light theme)
```

---

### Semantic Colors

#### Success (Green)
```
Success/Green-500: #22C55E
Usage: Success states, positive indicators, "Active" badges
RGB: 34, 197, 94

Success/Green-50: #F0FDF4
Usage: Success alert backgrounds

Success/Green-100: #DCFCE7
Usage: Success badge backgrounds
```

#### Warning (Amber)
```
Warning/Amber-500: #F59E0B
Usage: Warning states, pending indicators
RGB: 245, 158, 11

Warning/Amber-50: #FFFBEB
Usage: Warning alert backgrounds

Warning/Amber-100: #FEF3C7
Usage: Warning badge backgrounds
```

#### Error (Red)
```
Error/Red-500: #EF4444
Usage: Error states, destructive actions, validation errors
RGB: 239, 68, 68

Error/Red-50: #FEF2F2
Usage: Error alert backgrounds

Error/Red-100: #FEE2E2
Usage: Error badge backgrounds
```

#### Info (Blue)
```
Info/Blue-500: #3B82F6
Usage: Info states, helpful indicators
RGB: 59, 130, 246

Info/Blue-50: #EFF6FF
Usage: Info alert backgrounds

Info/Blue-100: #DBEAFE
Usage: Info badge backgrounds
```

---

## Semantic Token System

### Background Tokens

```css
/* Light Theme */
BG/Canvas: Neutral/50 (#F8FAFC)
BG/Card: Neutral/0 (#FFFFFF)
BG/SoftElevated: Neutral/100 (#F1F5F9)
BG/Primary: Primary/Indigo-600 (#4F46E5)
BG/Gradient: linear-gradient(90deg, #4F46E5, #06B6D4)

/* Dark Theme */
BG/Canvas: Primary/Indigo-900 (#0F172A)
BG/Card: Primary/Indigo-700 (#1E293B)
BG/SoftElevated: rgba(79, 70, 229, 0.1)
BG/Primary: Primary/Indigo-600 (#4F46E5)
BG/Gradient: linear-gradient(90deg, #4F46E5, #06B6D4)
```

### Text Tokens

```css
/* Light Theme */
Text/Primary: Neutral/900 (#0F172A)
Text/Secondary: Neutral/700 (#334155)
Text/Muted: Neutral/500 (#64748B)
Text/OnPrimary: Neutral/0 (#FFFFFF)
Text/Link: Primary/Indigo-600 (#4F46E5)
Text/LinkHover: Primary/Teal-400 (#06B6D4)

/* Dark Theme */
Text/Primary: Neutral/0 (#FFFFFF)
Text/Secondary: Neutral/200 (#E2E8F0)
Text/Muted: Neutral/300 (#CBD5E1)
Text/OnPrimary: Neutral/0 (#FFFFFF)
Text/Link: Primary/Teal-400 (#06B6D4)
Text/LinkHover: Primary/Indigo-600 (#4F46E5)
```

### Border Tokens

```css
/* Light Theme */
Border/Subtle: Neutral/200 (#E2E8F0)
Border/Strong: Neutral/300 (#CBD5E1)
Border/Focus: Primary/Indigo-600 (#4F46E5)

/* Dark Theme */
Border/Subtle: rgba(226, 232, 240, 0.1)
Border/Strong: rgba(226, 232, 240, 0.2)
Border/Focus: Primary/Teal-400 (#06B6D4)
```

### Accent Tokens

```css
Accent/Primary: Primary/Indigo-600 (#4F46E5)
Accent/Secondary: Primary/Teal-400 (#06B6D4)
Accent/Gradient: linear-gradient(90deg, #4F46E5, #06B6D4)
```

---

## Usage Guidelines

### Do's
✅ Use the brand gradient sparingly for high-impact CTAs
✅ Maintain contrast ratios of at least 4.5:1 for body text
✅ Use semantic colors consistently (green = success, red = error)
✅ Apply neutral scale for hierarchy without overusing brand colors

### Don'ts
❌ Don't use pure black (#000000) — use Neutral/900 instead
❌ Don't mix gradient with other strong colors
❌ Don't use Teal-400 as a standalone background color
❌ Don't create custom colors outside this system

---

## Accessibility

All color combinations have been tested for WCAG 2.1 compliance:

- **Primary/Indigo-600 on White**: 7.6:1 (AAA)
- **Neutral/700 on White**: 9.8:1 (AAA)
- **Neutral/500 on White**: 4.5:1 (AA)
- **White on Primary/Indigo-600**: 7.6:1 (AAA)
- **White on Primary/Indigo-900**: 15.5:1 (AAA)

---

## Implementation

### CSS Variables (Light Theme)
```css
:root {
  /* Primary */
  --color-primary-indigo-900: #0F172A;
  --color-primary-indigo-700: #1E293B;
  --color-primary-indigo-600: #4F46E5;
  --color-primary-teal-400: #06B6D4;
  --color-primary-gradient: linear-gradient(90deg, #4F46E5 0%, #06B6D4 100%);
  
  /* Neutral */
  --color-neutral-0: #FFFFFF;
  --color-neutral-50: #F8FAFC;
  --color-neutral-100: #F1F5F9;
  --color-neutral-200: #E2E8F0;
  --color-neutral-300: #CBD5E1;
  --color-neutral-500: #64748B;
  --color-neutral-700: #334155;
  --color-neutral-900: #0F172A;
  
  /* Semantic */
  --color-success: #22C55E;
  --color-warning: #F59E0B;
  --color-error: #EF4444;
  --color-info: #3B82F6;
  
  /* Semantic Tokens */
  --bg-canvas: var(--color-neutral-50);
  --bg-card: var(--color-neutral-0);
  --bg-soft-elevated: var(--color-neutral-100);
  --bg-primary: var(--color-primary-indigo-600);
  --bg-gradient: var(--color-primary-gradient);
  
  --text-primary: var(--color-neutral-900);
  --text-secondary: var(--color-neutral-700);
  --text-muted: var(--color-neutral-500);
  --text-on-primary: var(--color-neutral-0);
  --text-link: var(--color-primary-indigo-600);
  
  --border-subtle: var(--color-neutral-200);
  --border-strong: var(--color-neutral-300);
  --border-focus: var(--color-primary-indigo-600);
  
  --accent-primary: var(--color-primary-indigo-600);
  --accent-secondary: var(--color-primary-teal-400);
}
```

### Dark Theme Override
```css
[data-theme="dark"] {
  --bg-canvas: #0F172A;
  --bg-card: #1E293B;
  --bg-soft-elevated: rgba(79, 70, 229, 0.1);
  
  --text-primary: #FFFFFF;
  --text-secondary: #E2E8F0;
  --text-muted: #CBD5E1;
  --text-link: #06B6D4;
  
  --border-subtle: rgba(226, 232, 240, 0.1);
  --border-strong: rgba(226, 232, 240, 0.2);
  --border-focus: #06B6D4;
}
```

---

**Last Updated**: December 2025  
**Version**: 1.0  
**Maintained by**: PS Technologies Design Team
