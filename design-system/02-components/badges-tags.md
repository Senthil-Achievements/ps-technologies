# PS Technologies Design System
## Components: Badges, Tags & Chips

---

## Badge Component

### Overview
Badges are small status indicators that label, categorize, or display counts.

---

## Badge Variants

### 1. Solid Badge
```
 ACTIVE 
```

**Specifications**:
```css
Background: var(--accent-primary)
Color: #FFFFFF
Padding: 4px 10px (Space/4 Space/12)
Border Radius: 6px (Radius/SM)
Font: Label (12px, 500, Uppercase)
Letter Spacing: 0.05em
Display: inline-flex
Align Items: center
Gap: 4px (for icon)
```

**Color Variants**:
```css
Default:  Background: #4F46E5, Color: #FFFFFF
Success:  Background: #22C55E, Color: #FFFFFF
Warning:  Background: #F59E0B, Color: #FFFFFF
Error:    Background: #EF4444, Color: #FFFFFF
Info:     Background: #3B82F6, Color: #FFFFFF
```

---

### 2. Outline Badge
```
┌──────────┐
│  ACTIVE  │
└──────────┘
```

**Specifications**:
```css
Background: transparent
Border: 1.5px solid var(--accent-primary)
Color: var(--accent-primary)
Padding: 3px 9px
Border Radius: 6px
Font: Label (12px, 500, Uppercase)
```

**Color Variants**:
```css
Default:  Border: #4F46E5, Color: #4F46E5
Success:  Border: #22C55E, Color: #22C55E
Warning:  Border: #F59E0B, Color: #F59E0B
Error:    Border: #EF4444, Color: #EF4444
```

---

### 3. Soft Badge
```
 ACTIVE 
```

**Specifications**:
```css
Background: rgba(79, 70, 229, 0.12)
Color: var(--accent-primary)
Padding: 4px 10px
Border Radius: 6px
Font: Label (12px, 500, Uppercase)
```

**Color Variants**:
```css
Default:  Background: rgba(79, 70, 229, 0.12), Color: #4F46E5
Success:  Background: rgba(34, 197, 94, 0.12), Color: #22C55E
Warning:  Background: rgba(245, 158, 11, 0.12), Color: #F59E0B
Error:    Background: rgba(239, 68, 68, 0.12), Color: #EF4444
Info:     Background: rgba(59, 130, 246, 0.12), Color: #3B82F6
```

---

## Badge with Icon
```
 ✓ VERIFIED 
```

**Specifications**:
```css
Icon Size: 12px
Gap: 4px (Space/4)
Icon Color: inherit
```

---

## Badge with Dot
```
 ● Online 
```

**Specifications**:
```css
Dot Size: 6px
Border Radius: 50%
Background: currentColor
Margin Right: 6px
```

---

## Count Badge (Notification)
```
  3  
```

**Specifications**:
```css
Background: #EF4444
Color: #FFFFFF
Padding: 2px 6px
Border Radius: 10px (pill)
Font Size: 11px
Font Weight: 600
Min Width: 18px
Height: 18px
Display: inline-flex
Align Items: center
Justify Content: center

Large (10+):
  Min Width: 22px
  Height: 22px
  Padding: 2px 7px
```

**Positioning** (on avatar/icon):
```css
Position: absolute
Top: -4px
Right: -4px
Border: 2px solid var(--theme-bg-card)
```

---

## Tag Component

### Purpose
Tags are interactive labels for filtering, categorization, or selection.

### Default Tag
```
┌─────────────┐
│  Design  ×  │
└─────────────┘
```

**Specifications**:
```css
Background: var(--bg-soft)
Color: var(--text-secondary)
Padding: 6px 12px (Space/6 Space/12)
Border Radius: 16px (pill-like)
Font: Caption/Medium (14px, 500)
Display: inline-flex
Align Items: center
Gap: 6px
Cursor: pointer
Transition: 0.2s ease

Hover:
  Background: var(--border-subtle)
  Color: var(--text-primary)
  
Remove Button (×):
  Width: 16px
  Height: 16px
  Border Radius: 50%
  Display: flex
  Align Items: center
  Justify Content: center
  Hover Background: rgba(0, 0, 0, 0.1)
```

---

## Chip Component (Selectable)

### Unselected
```
┌──────────┐
│  Filter  │
└──────────┘
```

**Specifications**:
```css
Background: transparent
Border: 1.5px solid var(--border-strong)
Color: var(--text-secondary)
Padding: 8px 16px (Space/8 Space/16)
Border Radius: 20px
Font: Caption/Medium (14px, 500)
Cursor: pointer
Transition: 0.2s ease

Hover:
  Border Color: var(--accent-primary)
  Background: rgba(79, 70, 229, 0.05)
  Color: var(--text-primary)
```

### Selected
```
┌──────────┐
│ ✓ Filter │
└──────────┘
```

**Specifications**:
```css
Background: var(--accent-primary)
Border: 1.5px solid var(--accent-primary)
Color: #FFFFFF
Icon: Checkmark (14px)
```

---

## Status Indicator

### Dot Only
```
● Online
● Away
● Offline
```

**Specifications**:
```css
Display: inline-flex
Align Items: center
Gap: 8px

Dot:
  Width: 8px
  Height: 8px
  Border Radius: 50%
  
Status Colors:
  Online:  #22C55E
  Away:    #F59E0B
  Busy:    #EF4444
  Offline: #94A3B8
```

### With Animation (Pulse)
```css
@keyframes pulse {
  0%, 100% {
    opacity: 1;
    transform: scale(1);
  }
  50% {
    opacity: 0.5;
    transform: scale(1.1);
  }
}

.status-dot.pulse {
  animation: pulse 2s ease-in-out infinite;
}
```

---

## Implementation

### HTML
```html
<!-- Solid Badge -->
<span class="badge badge-solid badge-success">Active</span>

<!-- Outline Badge -->
<span class="badge badge-outline badge-primary">New</span>

<!-- Soft Badge -->
<span class="badge badge-soft badge-warning">Pending</span>

<!-- Badge with Icon -->
<span class="badge badge-solid badge-success">
  <svg class="badge-icon">...</svg>
  Verified
</span>

<!-- Count Badge -->
<div class="relative">
  <button class="icon-button">
    <svg>...</svg>
  </button>
  <span class="badge-count">3</span>
</div>

<!-- Tag -->
<span class="tag">
  Design
  <button class="tag-remove" aria-label="Remove">×</button>
</span>

<!-- Chip (Selectable) -->
<button class="chip" aria-pressed="false">
  Filter
</button>

<button class="chip chip-selected" aria-pressed="true">
  <svg class="chip-icon">✓</svg>
  Filter
</button>

<!-- Status -->
<div class="status">
  <span class="status-dot status-online"></span>
  Online
</div>
```

### CSS
```css
/* Badge Base */
.badge {
  display: inline-flex;
  align-items: center;
  gap: var(--space-4);
  padding: 4px 10px;
  border-radius: var(--radius-sm);
  font-size: 0.75rem;
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  white-space: nowrap;
}

.badge-icon {
  width: 12px;
  height: 12px;
}

/* Solid Badge */
.badge-solid {
  background: var(--accent-primary);
  color: #FFFFFF;
}

.badge-solid.badge-success { background: var(--color-success); }
.badge-solid.badge-warning { background: var(--color-warning); }
.badge-solid.badge-error { background: var(--color-error); }
.badge-solid.badge-info { background: var(--color-info); }

/* Outline Badge */
.badge-outline {
  background: transparent;
  border: 1.5px solid var(--accent-primary);
  color: var(--accent-primary);
  padding: 3px 9px;
}

.badge-outline.badge-success { 
  border-color: var(--color-success);
  color: var(--color-success);
}
.badge-outline.badge-warning { 
  border-color: var(--color-warning);
  color: var(--color-warning);
}
.badge-outline.badge-error { 
  border-color: var(--color-error);
  color: var(--color-error);
}

/* Soft Badge */
.badge-soft {
  background: rgba(79, 70, 229, 0.12);
  color: var(--accent-primary);
}

.badge-soft.badge-success {
  background: rgba(34, 197, 94, 0.12);
  color: var(--color-success);
}
.badge-soft.badge-warning {
  background: rgba(245, 158, 11, 0.12);
  color: var(--color-warning);
}
.badge-soft.badge-error {
  background: rgba(239, 68, 68, 0.12);
  color: var(--color-error);
}

/* Count Badge */
.badge-count {
  position: absolute;
  top: -4px;
  right: -4px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  min-width: 18px;
  height: 18px;
  padding: 2px 6px;
  background: var(--color-error);
  color: #FFFFFF;
  font-size: 11px;
  font-weight: 600;
  border-radius: 10px;
  border: 2px solid var(--theme-bg-card);
}

/* Tag */
.tag {
  display: inline-flex;
  align-items: center;
  gap: var(--space-6);
  padding: 6px 12px;
  background: var(--bg-soft);
  color: var(--text-secondary);
  font-size: 0.875rem;
  font-weight: 500;
  border-radius: 16px;
  cursor: pointer;
  transition: all 0.2s ease;
}

.tag:hover {
  background: var(--border-subtle);
  color: var(--text-primary);
}

.tag-remove {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 16px;
  height: 16px;
  border: none;
  background: transparent;
  cursor: pointer;
  border-radius: 50%;
  transition: background 0.2s ease;
}

.tag-remove:hover {
  background: rgba(0, 0, 0, 0.1);
}

/* Chip */
.chip {
  display: inline-flex;
  align-items: center;
  gap: var(--space-6);
  padding: var(--space-8) var(--space-16);
  background: transparent;
  border: 1.5px solid var(--border-strong);
  color: var(--text-secondary);
  font-size: 0.875rem;
  font-weight: 500;
  border-radius: 20px;
  cursor: pointer;
  transition: all 0.2s ease;
}

.chip:hover {
  border-color: var(--accent-primary);
  background: rgba(79, 70, 229, 0.05);
  color: var(--text-primary);
}

.chip-selected {
  background: var(--accent-primary);
  border-color: var(--accent-primary);
  color: #FFFFFF;
}

.chip-icon {
  width: 14px;
  height: 14px;
}

/* Status */
.status {
  display: inline-flex;
  align-items: center;
  gap: var(--space-8);
  font-size: 0.875rem;
  color: var(--text-secondary);
}

.status-dot {
  width: 8px;
  height: 8px;
  border-radius: 50%;
}

.status-online { background: var(--color-success); }
.status-away { background: var(--color-warning); }
.status-busy { background: var(--color-error); }
.status-offline { background: #94A3B8; }

.status-dot.pulse {
  animation: pulse 2s ease-in-out infinite;
}

@keyframes pulse {
  0%, 100% {
    opacity: 1;
    transform: scale(1);
  }
  50% {
    opacity: 0.5;
    transform: scale(1.1);
  }
}
```

---

## Accessibility

✅ **Color Independence**: Don't rely on color alone
✅ **ARIA Labels**: Descriptive labels for screen readers
✅ **Keyboard Support**: Interactive badges/chips are keyboard accessible
✅ **Focus Indicators**: Clear focus states
✅ **Semantic HTML**: Appropriate elements (span for static, button for interactive)

---

## Usage Guidelines

### Do's
✅ Use badges to highlight status or important info
✅ Keep badge text short (1-2 words)
✅ Use appropriate colors for context
✅ Make remove actions clear on tags
✅ Use chips for filtering or selection

### Don'ts
❌ Don't use badges for long text
❌ Don't over-badge your interface
❌ Don't use too many color variants on one page
❌ Don't make badges look like buttons
❌ Don't forget to handle tag removal

---

**Last Updated**: December 2025  
**Version**: 1.0  
**Maintained by**: PS Technologies Design Team
