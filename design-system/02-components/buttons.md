# PS Technologies Design System
## Components: Buttons

---

### Overview
Buttons are primary interactive elements that trigger actions. They come in multiple variants to establish clear visual hierarchy and guide users toward important actions.

---

## Component Anatomy

```
┌──────────────────────────────────┐
│  [Icon]  Label Text  [Icon]      │
└──────────────────────────────────┘
   ↑         ↑           ↑
   Leading   Content     Trailing
   Icon      (Required)  Icon
```

**Required Elements:**
- Label text (or icon for IconOnly variant)
- Background or border (based on variant)

**Optional Elements:**
- Leading icon
- Trailing icon
- Loading spinner

---

## Variants

### 1. Primary Button
**Purpose**: Main call-to-action, highest emphasis

#### Default State
```css
Background: linear-gradient(90deg, #4F46E5, #06B6D4)
Text Color: #FFFFFF
Border Radius: 9999px (pill)
Font: Body/Medium (16px, 500 weight)
Shadow: None
```

#### Hover State
```css
Box Shadow: 0px 0px 0px 3px rgba(79, 70, 229, 0.12),
            0px 4px 12px rgba(79, 70, 229, 0.25)
Transform: translateY(-1px)
Transition: 0.2s ease
```

#### Pressed/Active State
```css
Transform: translateY(0px)
Box Shadow: inset 0px 2px 4px rgba(0, 0, 0, 0.15)
```

#### Focus State
```css
Outline: 2px solid #4F46E5
Outline Offset: 2px
```

#### Disabled State
```css
Background: #F1F5F9 (Neutral/100)
Text Color: #CBD5E1 (Neutral/300)
Cursor: not-allowed
Opacity: 0.6
```

---

### 2. Secondary Button
**Purpose**: Supporting actions, medium emphasis

#### Default State
```css
Background: transparent
Text Color: #4F46E5 (Indigo-600)
Border: 2px solid #4F46E5
Border Radius: 9999px (pill)
Font: Body/Medium (16px, 500 weight)
```

#### Dark Theme
```css
Text Color: #06B6D4
Border: 2px solid #06B6D4
```

#### Hover State
```css
Background: rgba(79, 70, 229, 0.08)
Box Shadow: 0px 0px 0px 3px rgba(79, 70, 229, 0.08)
```

#### Disabled State
```css
Border Color: #E2E8F0
Text Color: #CBD5E1
```

---

### 3. Tertiary Button
**Purpose**: Low-emphasis actions

#### Default State
```css
Background: #F8FAFC (Neutral/50)
Text Color: #334155 (Neutral/700)
Border: none
Border Radius: 12px
Font: Body/Medium
```

#### Dark Theme
```css
Background: rgba(226, 232, 240, 0.05)
Text Color: #E2E8F0
```

#### Hover State
```css
Background: #E2E8F0 (Light) / rgba(226, 232, 240, 0.1) (Dark)
```

---

### 4. Ghost Button
**Purpose**: Minimal visual weight, inline actions

#### Default State
```css
Background: transparent
Text Color: #4F46E5 (Indigo-600)
Border: none
Border Radius: 8px
Font: Body/Medium
Padding: reduced (8px 12px)
```

#### Hover State
```css
Background: rgba(79, 70, 229, 0.08)
```

---

### 5. Destructive Button
**Purpose**: Dangerous/delete actions

#### Default State
```css
Background: #EF4444 (Error/Red-500)
Text Color: #FFFFFF
Border Radius: 9999px (pill)
Font: Body/Medium
```

#### Hover State
```css
Background: #DC2626 (darker red)
Box Shadow: 0px 0px 0px 3px rgba(239, 68, 68, 0.12),
            0px 4px 12px rgba(239, 68, 68, 0.25)
```

#### Outline Version
```css
Background: transparent
Text Color: #EF4444
Border: 2px solid #EF4444
```

---

## Sizes

### Large
```css
Padding: 16px 32px (Space/16 Space/32)
Font Size: 16px (Body/Medium)
Line Height: 24px
Min Height: 56px
Icon Size: 20px
Gap (Icon + Text): 10px
```

**Use Cases**: Hero CTAs, primary landing page actions

---

### Medium (Default)
```css
Padding: 12px 24px (Space/12 Space/24)
Font Size: 16px (Body/Medium)
Line Height: 24px
Min Height: 48px
Icon Size: 18px
Gap (Icon + Text): 8px
```

**Use Cases**: Forms, modals, standard page actions

---

### Small
```css
Padding: 8px 16px (Space/8 Space/16)
Font Size: 14px (Caption/Medium)
Line Height: 20px
Min Height: 36px
Icon Size: 16px
Gap (Icon + Text): 6px
```

**Use Cases**: Table actions, compact UIs, secondary actions

---

## Icon Configurations

### Icon Left
```
┌─────────────────────┐
│ [Icon] Label        │
└─────────────────────┘
```

**Usage**: Actions with iconic representation (Save, Download, Add)

---

### Icon Right
```
┌─────────────────────┐
│ Label [Icon]        │
└─────────────────────┘
```

**Usage**: Navigation (Next, Forward), external links

---

### Icon Only
```
┌──────┐
│ Icon │
└──────┘
```

**Sizing**:
- Large: 48px × 48px (icon: 24px)
- Medium: 40px × 40px (icon: 20px)
- Small: 32px × 32px (icon: 16px)

**Usage**: Toolbars, icon buttons, compact actions
**Accessibility**: MUST include aria-label

---

## Special States

### Loading State
```
┌─────────────────────────┐
│ [Spinner] Loading...    │
└─────────────────────────┘
```

**Implementation**:
- Replace icon/text with spinner
- Disable interaction
- Optional loading text
- Spinner color matches text color

```css
.button-loading {
  pointer-events: none;
  cursor: wait;
}
```

---

### With Badge
```
┌──────────────────────┐
│ Label      [Badge: 3]│
└──────────────────────┘
```

**Usage**: Notification indicators, counts

---

## Component Naming Convention

```
Button / Primary / Large / Default
Button / Primary / Large / Hover
Button / Primary / Large / Focus
Button / Primary / Large / Disabled

Button / Secondary / Medium / Default
Button / Secondary / Medium / Hover

Button / IconOnly / Small / Default

Button / Destructive / Medium / Default
```

---

## Implementation

### HTML Structure
```html
<!-- Primary Button -->
<button class="btn btn-primary btn-lg">
  Get Started
</button>

<!-- With Icon Left -->
<button class="btn btn-primary btn-md">
  <svg class="btn-icon-left">...</svg>
  Save Changes
</button>

<!-- Icon Only -->
<button class="btn btn-ghost btn-icon-only" aria-label="Close">
  <svg>...</svg>
</button>
```

### CSS Classes
```css
/* Base Button */
.btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: var(--space-8);
  font-family: var(--font-primary);
  font-weight: 500;
  text-align: center;
  white-space: nowrap;
  user-select: none;
  cursor: pointer;
  transition: all 0.2s ease-in-out;
  border: none;
  outline: none;
}

.btn:focus-visible {
  outline: 2px solid var(--border-focus);
  outline-offset: 2px;
}

/* Variants */
.btn-primary {
  background: linear-gradient(90deg, #4F46E5 0%, #06B6D4 100%);
  color: #FFFFFF;
  border-radius: var(--radius-full);
}

.btn-primary:hover {
  box-shadow: 0px 0px 0px 3px rgba(79, 70, 229, 0.12),
              0px 4px 12px rgba(79, 70, 229, 0.25);
  transform: translateY(-1px);
}

.btn-primary:active {
  transform: translateY(0);
  box-shadow: inset 0px 2px 4px rgba(0, 0, 0, 0.15);
}

.btn-secondary {
  background: transparent;
  color: var(--accent-primary);
  border: 2px solid var(--accent-primary);
  border-radius: var(--radius-full);
}

.btn-secondary:hover {
  background: rgba(79, 70, 229, 0.08);
}

.btn-ghost {
  background: transparent;
  color: var(--accent-primary);
  border-radius: var(--radius-sm);
}

.btn-ghost:hover {
  background: rgba(79, 70, 229, 0.08);
}

.btn-destructive {
  background: #EF4444;
  color: #FFFFFF;
  border-radius: var(--radius-full);
}

.btn-destructive:hover {
  background: #DC2626;
  box-shadow: 0px 0px 0px 3px rgba(239, 68, 68, 0.12),
              0px 4px 12px rgba(239, 68, 68, 0.25);
}

/* Sizes */
.btn-lg {
  padding: var(--space-16) var(--space-32);
  font-size: 1rem;
  line-height: 1.5;
  min-height: 56px;
}

.btn-md {
  padding: var(--space-12) var(--space-24);
  font-size: 1rem;
  line-height: 1.5;
  min-height: 48px;
}

.btn-sm {
  padding: var(--space-8) var(--space-16);
  font-size: 0.875rem;
  line-height: 1.43;
  min-height: 36px;
}

.btn-icon-only {
  padding: var(--space-8);
  aspect-ratio: 1;
}

/* Disabled State */
.btn:disabled {
  opacity: 0.6;
  cursor: not-allowed;
  pointer-events: none;
}

.btn-primary:disabled {
  background: var(--bg-disabled);
  color: var(--text-muted);
}

/* Loading State */
.btn-loading {
  pointer-events: none;
  cursor: wait;
  position: relative;
}

.btn-loading::before {
  content: '';
  position: absolute;
  width: 16px;
  height: 16px;
  border: 2px solid currentColor;
  border-top-color: transparent;
  border-radius: 50%;
  animation: spin 0.6s linear infinite;
}

@keyframes spin {
  to { transform: rotate(360deg); }
}
```

### React Component
```typescript
import React from 'react';

interface ButtonProps {
  variant?: 'primary' | 'secondary' | 'tertiary' | 'ghost' | 'destructive';
  size?: 'small' | 'medium' | 'large';
  iconLeft?: React.ReactNode;
  iconRight?: React.ReactNode;
  iconOnly?: boolean;
  loading?: boolean;
  disabled?: boolean;
  children: React.ReactNode;
  onClick?: () => void;
  type?: 'button' | 'submit' | 'reset';
  ariaLabel?: string;
}

export const Button: React.FC<ButtonProps> = ({
  variant = 'primary',
  size = 'medium',
  iconLeft,
  iconRight,
  iconOnly = false,
  loading = false,
  disabled = false,
  children,
  onClick,
  type = 'button',
  ariaLabel,
}) => {
  const classes = [
    'btn',
    `btn-${variant}`,
    `btn-${size === 'small' ? 'sm' : size === 'large' ? 'lg' : 'md'}`,
    iconOnly && 'btn-icon-only',
    loading && 'btn-loading',
  ].filter(Boolean).join(' ');

  return (
    <button
      className={classes}
      onClick={onClick}
      disabled={disabled || loading}
      type={type}
      aria-label={ariaLabel || (iconOnly ? 'Button' : undefined)}
    >
      {!loading && iconLeft && <span className="btn-icon-left">{iconLeft}</span>}
      {!loading && !iconOnly && children}
      {!loading && iconRight && <span className="btn-icon-right">{iconRight}</span>}
      {loading && <span>Loading...</span>}
    </button>
  );
};
```

---

## Accessibility

✅ **Keyboard Support**: Full Tab/Enter/Space support
✅ **Focus Indicators**: Clear focus rings (2px)
✅ **ARIA Labels**: Required for icon-only buttons
✅ **Disabled State**: Properly communicated to screen readers
✅ **Color Contrast**: All variants meet WCAG AA (4.5:1)
✅ **Touch Targets**: Minimum 44px (iOS) / 48px (Material)

---

## Usage Guidelines

### Do's
✅ Use Primary for the main action on each page/section
✅ Limit to one Primary button per screen area
✅ Use Secondary for alternative actions
✅ Provide clear, action-oriented labels ("Save Changes" not "Submit")
✅ Use loading states for async actions

### Don'ts
❌ Don't use multiple Primary buttons competing for attention
❌ Don't rely on color alone to convey meaning
❌ Don't create buttons smaller than 32px height
❌ Don't use vague labels like "Click Here" or "OK"
❌ Don't disable buttons without explanation

---

**Last Updated**: December 2025  
**Version**: 1.0  
**Maintained by**: PS Technologies Design Team
