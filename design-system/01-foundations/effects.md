# PS Technologies Design System
## Foundations: Effects (Shadows & Glows)

---

### Philosophy
Effects in the PS Technologies design system provide subtle depth and hierarchy without overwhelming the clean, minimal aesthetic. Shadows and glows are used sparingly to elevate important elements and create visual separation.

---

## Shadow System

### Shadow Scale

#### Shadow/None
```css
box-shadow: none;

Usage: Flat elements, cards in dark theme
```

#### Shadow/Soft
```css
box-shadow: 0px 1px 2px rgba(15, 23, 42, 0.05),
            0px 1px 3px rgba(15, 23, 42, 0.10);

Usage: Cards, buttons (default state), dropdown triggers
Token: shadow-soft
```

#### Shadow/Medium
```css
box-shadow: 0px 4px 6px rgba(15, 23, 42, 0.05),
            0px 10px 15px rgba(15, 23, 42, 0.10);

Usage: Dropdowns, popovers, elevated cards
Token: shadow-medium
```

#### Shadow/Large
```css
box-shadow: 0px 10px 15px rgba(15, 23, 42, 0.05),
            0px 20px 25px rgba(15, 23, 42, 0.10);

Usage: Modals, dialog boxes, major overlays
Token: shadow-large
```

#### Shadow/XL
```css
box-shadow: 0px 20px 25px rgba(15, 23, 42, 0.05),
            0px 25px 50px rgba(15, 23, 42, 0.15);

Usage: High-elevation modals, drawer panels
Token: shadow-xl
```

---

## Glow Effects

### Primary Glow
```css
box-shadow: 0px 0px 0px 3px rgba(79, 70, 229, 0.12),
            0px 4px 12px rgba(79, 70, 229, 0.25);

Usage: Primary button hover, focus states
Token: glow-primary
Color: Based on Primary/Indigo-600
```

### Secondary Glow (Teal)
```css
box-shadow: 0px 0px 0px 3px rgba(6, 182, 212, 0.12),
            0px 4px 12px rgba(6, 182, 212, 0.25);

Usage: Accent elements, secondary CTAs hover
Token: glow-secondary
Color: Based on Primary/Teal-400
```

### Success Glow
```css
box-shadow: 0px 0px 0px 3px rgba(34, 197, 94, 0.12),
            0px 4px 12px rgba(34, 197, 94, 0.20);

Usage: Success notifications, positive actions
Token: glow-success
Color: Based on Success/Green-500
```

### Error Glow
```css
box-shadow: 0px 0px 0px 3px rgba(239, 68, 68, 0.12),
            0px 4px 12px rgba(239, 68, 68, 0.20);

Usage: Error states, destructive actions
Token: glow-error
Color: Based on Error/Red-500
```

---

## Focus Rings

### Default Focus Ring
```css
outline: 2px solid #4F46E5;
outline-offset: 2px;

Usage: Keyboard navigation, accessibility
Token: focus-ring-primary
```

### Focus Ring (Dark Theme)
```css
outline: 2px solid #06B6D4;
outline-offset: 2px;

Usage: Keyboard navigation in dark theme
Token: focus-ring-dark
```

### Input Focus
```css
box-shadow: 0px 0px 0px 3px rgba(79, 70, 229, 0.12);
border-color: #4F46E5;

Usage: Text inputs, textareas, selects on focus
Token: focus-input
```

---

## Inner Shadows

### Inset/Subtle
```css
box-shadow: inset 0px 1px 2px rgba(15, 23, 42, 0.08);

Usage: Pressed button states, recessed inputs
Token: shadow-inset
```

### Inset/Strong
```css
box-shadow: inset 0px 2px 4px rgba(15, 23, 42, 0.12);

Usage: Disabled inputs, sunken elements
Token: shadow-inset-strong
```

---

## Component Shadow Map

### Buttons
```
Default State:      Shadow/Soft or None
Hover State:        Glow/Primary (for primary buttons)
Pressed State:      Shadow/Inset
Disabled State:     None
```

### Cards
```
Static Card:        Shadow/Soft
Hover Card:         Shadow/Medium (if interactive)
Elevated Card:      Shadow/Medium
Dragging Card:      Shadow/Large
```

### Inputs & Forms
```
Default State:      Shadow/None + Border
Focus State:        Focus/Input (ring + border change)
Error State:        Glow/Error (red ring)
Disabled State:     Shadow/Inset/Subtle
```

### Dropdowns & Menus
```
Dropdown Menu:      Shadow/Medium
Context Menu:       Shadow/Medium
Tooltip:            Shadow/Soft
```

### Modals & Overlays
```
Modal Dialog:       Shadow/Large
Drawer Panel:       Shadow/XL
Backdrop:           None (uses opacity instead)
```

### Navigation
```
Top Nav (Sticky):   Shadow/Soft (when scrolled)
Sidebar:            Shadow/None or Soft (depending on theme)
```

---

## Dark Theme Adjustments

In dark theme, shadows need to be more subtle to avoid visual harshness:

```css
[data-theme="dark"] {
  /* Reduce shadow intensity */
  --shadow-soft: 0px 1px 2px rgba(0, 0, 0, 0.2),
                 0px 1px 3px rgba(0, 0, 0, 0.3);
  
  --shadow-medium: 0px 4px 6px rgba(0, 0, 0, 0.2),
                   0px 10px 15px rgba(0, 0, 0, 0.3);
  
  --shadow-large: 0px 10px 15px rgba(0, 0, 0, 0.3),
                  0px 20px 25px rgba(0, 0, 0, 0.4);
  
  /* Use lighter glows */
  --glow-primary: 0px 0px 0px 3px rgba(6, 182, 212, 0.20),
                  0px 4px 12px rgba(6, 182, 212, 0.35);
}
```

---

## Elevation Layers

Elevation hierarchy using shadows:

```
Level 0 (Base):        Shadow/None
Level 1 (Raised):      Shadow/Soft
Level 2 (Elevated):    Shadow/Medium
Level 3 (Floating):    Shadow/Large
Level 4 (Modal):       Shadow/XL
Level 5 (Toast):       Shadow/Large + High z-index
```

---

## Implementation

### CSS Variables
```css
:root {
  /* Shadow Scale */
  --shadow-soft: 0px 1px 2px rgba(15, 23, 42, 0.05),
                 0px 1px 3px rgba(15, 23, 42, 0.10);
  
  --shadow-medium: 0px 4px 6px rgba(15, 23, 42, 0.05),
                   0px 10px 15px rgba(15, 23, 42, 0.10);
  
  --shadow-large: 0px 10px 15px rgba(15, 23, 42, 0.05),
                  0px 20px 25px rgba(15, 23, 42, 0.10);
  
  --shadow-xl: 0px 20px 25px rgba(15, 23, 42, 0.05),
               0px 25px 50px rgba(15, 23, 42, 0.15);
  
  /* Inset Shadows */
  --shadow-inset: inset 0px 1px 2px rgba(15, 23, 42, 0.08);
  --shadow-inset-strong: inset 0px 2px 4px rgba(15, 23, 42, 0.12);
  
  /* Glow Effects */
  --glow-primary: 0px 0px 0px 3px rgba(79, 70, 229, 0.12),
                  0px 4px 12px rgba(79, 70, 229, 0.25);
  
  --glow-secondary: 0px 0px 0px 3px rgba(6, 182, 212, 0.12),
                    0px 4px 12px rgba(6, 182, 212, 0.25);
  
  --glow-success: 0px 0px 0px 3px rgba(34, 197, 94, 0.12),
                  0px 4px 12px rgba(34, 197, 94, 0.20);
  
  --glow-error: 0px 0px 0px 3px rgba(239, 68, 68, 0.12),
                0px 4px 12px rgba(239, 68, 68, 0.20);
  
  /* Focus Rings */
  --focus-ring: 0px 0px 0px 3px rgba(79, 70, 229, 0.12);
  --focus-ring-color: #4F46E5;
  --focus-ring-offset: 2px;
}

/* Dark Theme Overrides */
[data-theme="dark"] {
  --shadow-soft: 0px 1px 2px rgba(0, 0, 0, 0.2),
                 0px 1px 3px rgba(0, 0, 0, 0.3);
  
  --shadow-medium: 0px 4px 6px rgba(0, 0, 0, 0.2),
                   0px 10px 15px rgba(0, 0, 0, 0.3);
  
  --shadow-large: 0px 10px 15px rgba(0, 0, 0, 0.3),
                  0px 20px 25px rgba(0, 0, 0, 0.4);
  
  --shadow-xl: 0px 20px 25px rgba(0, 0, 0, 0.3),
               0px 25px 50px rgba(0, 0, 0, 0.5);
  
  --glow-primary: 0px 0px 0px 3px rgba(6, 182, 212, 0.20),
                  0px 4px 12px rgba(6, 182, 212, 0.35);
  
  --focus-ring-color: #06B6D4;
}
```

### Utility Classes
```css
/* Shadow Utilities */
.shadow-none { box-shadow: none; }
.shadow-soft { box-shadow: var(--shadow-soft); }
.shadow-medium { box-shadow: var(--shadow-medium); }
.shadow-large { box-shadow: var(--shadow-large); }
.shadow-xl { box-shadow: var(--shadow-xl); }
.shadow-inset { box-shadow: var(--shadow-inset); }

/* Glow Utilities */
.glow-primary { box-shadow: var(--glow-primary); }
.glow-secondary { box-shadow: var(--glow-secondary); }
.glow-success { box-shadow: var(--glow-success); }
.glow-error { box-shadow: var(--glow-error); }

/* Focus Ring */
.focus-ring {
  outline: 2px solid var(--focus-ring-color);
  outline-offset: var(--focus-ring-offset);
}

.focus-ring-input {
  box-shadow: var(--focus-ring);
  border-color: var(--focus-ring-color);
}
```

### Tailwind Configuration
```javascript
module.exports = {
  theme: {
    extend: {
      boxShadow: {
        'soft': '0px 1px 2px rgba(15, 23, 42, 0.05), 0px 1px 3px rgba(15, 23, 42, 0.10)',
        'medium': '0px 4px 6px rgba(15, 23, 42, 0.05), 0px 10px 15px rgba(15, 23, 42, 0.10)',
        'large': '0px 10px 15px rgba(15, 23, 42, 0.05), 0px 20px 25px rgba(15, 23, 42, 0.10)',
        'xl': '0px 20px 25px rgba(15, 23, 42, 0.05), 0px 25px 50px rgba(15, 23, 42, 0.15)',
        'inset': 'inset 0px 1px 2px rgba(15, 23, 42, 0.08)',
        'glow-primary': '0px 0px 0px 3px rgba(79, 70, 229, 0.12), 0px 4px 12px rgba(79, 70, 229, 0.25)',
        'glow-secondary': '0px 0px 0px 3px rgba(6, 182, 212, 0.12), 0px 4px 12px rgba(6, 182, 212, 0.25)',
        'glow-success': '0px 0px 0px 3px rgba(34, 197, 94, 0.12), 0px 4px 12px rgba(34, 197, 94, 0.20)',
        'glow-error': '0px 0px 0px 3px rgba(239, 68, 68, 0.12), 0px 4px 12px rgba(239, 68, 68, 0.20)',
      },
    },
  },
}
```

---

## Usage Guidelines

### Do's
✅ Use shadows to create clear visual hierarchy
✅ Apply subtle shadows in dark theme
✅ Use glow effects sparingly for emphasis
✅ Ensure focus rings are always visible for accessibility
✅ Increase shadow on hover for interactive elements

### Don'ts
❌ Don't stack multiple shadow effects unnecessarily
❌ Don't use heavy shadows in dark theme
❌ Don't use glows on every element
❌ Don't remove focus indicators
❌ Don't use shadows as the only indicator of interactivity

---

## Animation & Transitions

Effects should transition smoothly:

```css
.interactive-element {
  transition: box-shadow 0.2s ease-in-out;
}

.interactive-element:hover {
  box-shadow: var(--shadow-medium);
}

.button-primary:hover {
  box-shadow: var(--glow-primary);
}
```

---

## Accessibility Considerations

- **Focus indicators**: Always visible, meet WCAG contrast requirements
- **Shadow reliance**: Never use shadows as the only visual indicator
- **Reduced motion**: Respect `prefers-reduced-motion` for shadow transitions
- **Color independence**: Ensure UI works without shadows (for high contrast modes)

---

**Last Updated**: December 2025  
**Version**: 1.0  
**Maintained by**: PS Technologies Design Team
