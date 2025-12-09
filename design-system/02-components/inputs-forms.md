# PS Technologies Design System
## Components: Input Fields & Forms

---

### Overview
Form inputs are critical for data collection and user interaction. They must be accessible, clear, and provide helpful feedback.

---

## Text Input

### Anatomy
```
┌─────────────────────────────────────┐
│ Label *                             │  ← Label (required)
│ ┌─────────────────────────────────┐ │
│ │ Placeholder text...       [Icon]│ │  ← Input field
│ └─────────────────────────────────┘ │
│ Helper text or error message        │  ← Helper/Error text
└─────────────────────────────────────┘
```

### Default State
```css
Background: var(--theme-bg-input) (#FFFFFF / #1E293B)
Border: 1px solid var(--border-subtle)
Border Radius: 12px (Radius/MD)
Padding: 12px 16px (Space/12 Space/16)
Font: Body (16px, Regular)
Text Color: var(--text-primary)
Min Height: 48px
```

### Focus State
```css
Border: 2px solid var(--border-focus)
Box Shadow: 0px 0px 0px 3px rgba(79, 70, 229, 0.12)
Outline: none
```

### Error State
```css
Border: 2px solid #EF4444
Box Shadow: 0px 0px 0px 3px rgba(239, 68, 68, 0.12)
Text Color: #EF4444 (for error message)
Icon: Error icon in red
```

### Disabled State
```css
Background: var(--bg-disabled)
Border: 1px solid var(--border-subtle)
Text Color: var(--text-muted)
Cursor: not-allowed
Opacity: 0.6
```

### Success State
```css
Border: 2px solid #22C55E
Box Shadow: 0px 0px 0px 3px rgba(34, 197, 94, 0.12)
Icon: Checkmark in green
```

---

## Label
```css
Font: Caption/Medium (14px, 500 weight)
Color: var(--text-secondary)
Margin Bottom: 8px (Space/8)
Display: Required indicator (*) in red
```

---

## Helper Text
```css
Font: Caption (14px, Regular)
Color: var(--text-muted)
Margin Top: 4px (Space/4)
```

---

## Placeholder
```css
Color: var(--text-placeholder)
Font Style: Regular
Opacity: 1 (don't rely on browser default)
```

---

## Text Input Variants

### Standard Text Input
```html
<div class="form-group">
  <label for="email" class="form-label">
    Email Address <span class="required">*</span>
  </label>
  <input 
    type="email" 
    id="email"
    class="form-input" 
    placeholder="you@company.com"
    required
  />
  <p class="form-helper">We'll never share your email.</p>
</div>
```

### With Icon (Leading)
```
┌─────────────────────────────────┐
│ [🔍] Search...                  │
└─────────────────────────────────┘
```

**Padding**: Add 12px left padding for icon space
**Icon Size**: 18px, positioned 16px from left

### With Icon (Trailing)
```
┌─────────────────────────────────┐
│ Password                    [👁]│
└─────────────────────────────────┘
```

**Use Cases**: Password visibility toggle, clear button, validation icon

### With Prefix/Suffix
```
┌─────────────────────────────────┐
│ https:// | yoursite.com         │
└─────────────────────────────────┘

┌─────────────────────────────────┐
│ 1,234           | USD            │
└─────────────────────────────────┘
```

---

## Textarea

### Specifications
```css
Min Height: 96px (6 rows)
Max Height: 320px (with scrollbar)
Resize: vertical
Padding: 12px 16px
Line Height: 24px
Border Radius: 12px
```

### Character Count
```
┌─────────────────────────────────┐
│ Your message here...            │
│                                 │
│                                 │
└─────────────────────────────────┘
120 / 500 characters
```

---

## Password Input

### Default
```
┌─────────────────────────────────┐
│ ••••••••••                  [👁]│
└─────────────────────────────────┘
```

### Strength Indicator
```
┌─────────────────────────────────┐
│ mypassword123               [👁]│
└─────────────────────────────────┘
[==============              ] Weak

Password must contain:
✓ At least 8 characters
✗ One uppercase letter
✓ One number
✗ One special character
```

**Strength Colors**:
- Weak: #EF4444 (Red)
- Fair: #F59E0B (Amber)
- Good: #3B82F6 (Blue)
- Strong: #22C55E (Green)

---

## Select / Dropdown

### Closed State
```
┌─────────────────────────────────┐
│ Select option...            [▼] │
└─────────────────────────────────┘
```

### Open State
```
┌─────────────────────────────────┐
│ Select option...            [▲] │
└─────────────────────────────────┘
┌─────────────────────────────────┐
│ Option 1                        │  ← Hover highlight
│ Option 2                        │
│ Option 3                        │
│ Option 4                        │
└─────────────────────────────────┘
```

**Dropdown Panel**:
```css
Background: var(--theme-bg-card)
Border: 1px solid var(--border-subtle)
Border Radius: 12px
Box Shadow: var(--shadow-medium)
Max Height: 300px (scrollable)
Padding: 4px
```

**Option**:
```css
Padding: 10px 12px
Border Radius: 8px
Hover Background: var(--bg-soft)
Selected Background: var(--accent-primary) with white text
```

---

## Checkbox

### Unchecked
```
☐ Remember me
```

```css
Size: 20px × 20px
Border: 2px solid var(--border-strong)
Border Radius: 4px (Radius/XS)
Background: transparent
```

### Checked
```
☑ Remember me
```

```css
Background: var(--accent-primary)
Border: 2px solid var(--accent-primary)
Checkmark: White, 14px
```

### Indeterminate
```
☑ Select all (2 of 5 selected)
```

**Icon**: Horizontal line instead of checkmark

### Disabled
```css
Opacity: 0.5
Cursor: not-allowed
Background: var(--bg-disabled)
```

---

## Radio Button

### Unselected
```
○ Option 1
```

```css
Size: 20px × 20px
Border: 2px solid var(--border-strong)
Border Radius: 50%
Background: transparent
```

### Selected
```
◉ Option 2
```

```css
Border: 2px solid var(--accent-primary)
Inner Circle: 10px, Background: var(--accent-primary)
```

---

## Toggle / Switch

### Off State
```
[ O     ]  Enable notifications
```

```css
Width: 44px
Height: 24px
Background: var(--border-strong)
Border Radius: 12px (pill)
Thumb: 18px circle, positioned left
```

### On State
```
[     O ]  Enable notifications
```

```css
Background: var(--accent-primary)
Thumb: positioned right
Transition: 0.2s ease
```

---

## Search Input

```
┌─────────────────────────────────┐
│ [🔍] Search...              [⌘K]│
└─────────────────────────────────┘
```

**Features**:
- Leading search icon
- Trailing keyboard shortcut badge
- Auto-focus on keyboard shortcut
- Clear button when text entered

---

## File Upload

### Default
```
┌─────────────────────────────────┐
│                                 │
│        [📄]                     │
│   Drop files here or click      │
│        to browse                │
│                                 │
│   Accepted: .pdf, .doc, .jpg    │
│   Max size: 10MB                │
└─────────────────────────────────┘
```

### Drag Active
```css
Border: 2px dashed var(--accent-primary)
Background: rgba(79, 70, 229, 0.05)
```

### File Selected
```
┌─────────────────────────────────┐
│ [📄] document.pdf        [×]    │
│      2.4 MB                     │
└─────────────────────────────────┘
```

---

## Date Picker

### Input
```
┌─────────────────────────────────┐
│ 12/09/2025                  [📅]│
└─────────────────────────────────┘
```

### Calendar Popup
```
    December 2025        [< >]
┌─────────────────────────────────┐
│ Su Mo Tu We Th Fr Sa            │
│  1  2  3  4  5  6  7            │
│  8  9 10 11 12 13 14            │
│ 15 16 17 18 19 20 21            │
│ 22 23 24 25 26 27 28            │
│ 29 30 31                        │
└─────────────────────────────────┘
```

**Selected Date**: Highlighted with primary color
**Today**: Subtle border
**Disabled Dates**: Muted, not clickable

---

## Form Layout Patterns

### Stacked (Default)
```
┌─────────────────────────────────┐
│ First Name                      │
│ [_________________________]     │
│                                 │
│ Last Name                       │
│ [_________________________]     │
│                                 │
│ Email                           │
│ [_________________________]     │
└─────────────────────────────────┘
```

**Gap Between Fields**: 20px (Space/20)

### Two-Column
```
┌─────────────────┬───────────────┐
│ First Name      │ Last Name     │
│ [____________]  │ [___________] │
│                 │               │
│ Email                           │
│ [____________________________]  │
└─────────────────────────────────┘
```

### Inline Form (Compact)
```
[Email: __________] [Subscribe]
```

**Use Cases**: Newsletter signups, search bars

---

## Implementation

### CSS
```css
/* Form Group */
.form-group {
  display: flex;
  flex-direction: column;
  gap: var(--space-8);
  margin-bottom: var(--space-20);
}

/* Label */
.form-label {
  font-size: 0.875rem;
  font-weight: 500;
  color: var(--text-secondary);
}

.form-label .required {
  color: var(--color-error);
  margin-left: 2px;
}

/* Input */
.form-input {
  width: 100%;
  padding: var(--space-12) var(--space-16);
  font-size: 1rem;
  line-height: 1.5;
  color: var(--text-primary);
  background: var(--theme-bg-input);
  border: 1px solid var(--border-subtle);
  border-radius: var(--radius-md);
  min-height: 48px;
  transition: all 0.2s ease;
}

.form-input:focus {
  outline: none;
  border: 2px solid var(--border-focus);
  box-shadow: 0px 0px 0px 3px rgba(79, 70, 229, 0.12);
}

.form-input:disabled {
  background: var(--bg-disabled);
  cursor: not-allowed;
  opacity: 0.6;
}

.form-input.error {
  border: 2px solid var(--color-error);
  box-shadow: 0px 0px 0px 3px rgba(239, 68, 68, 0.12);
}

/* Helper Text */
.form-helper {
  font-size: 0.875rem;
  color: var(--text-muted);
  margin-top: var(--space-4);
}

.form-error {
  font-size: 0.875rem;
  color: var(--color-error);
  margin-top: var(--space-4);
}

/* Textarea */
.form-textarea {
  min-height: 96px;
  resize: vertical;
  font-family: inherit;
}

/* Select */
.form-select {
  appearance: none;
  background-image: url("data:image/svg+xml,..."); /* Chevron icon */
  background-repeat: no-repeat;
  background-position: right 16px center;
  padding-right: 48px;
}

/* Checkbox */
.form-checkbox {
  width: 20px;
  height: 20px;
  border: 2px solid var(--border-strong);
  border-radius: var(--radius-xs);
  cursor: pointer;
}

.form-checkbox:checked {
  background: var(--accent-primary);
  border-color: var(--accent-primary);
}

/* Toggle */
.form-toggle {
  position: relative;
  width: 44px;
  height: 24px;
  background: var(--border-strong);
  border-radius: 12px;
  cursor: pointer;
  transition: background 0.2s;
}

.form-toggle::after {
  content: '';
  position: absolute;
  top: 3px;
  left: 3px;
  width: 18px;
  height: 18px;
  background: white;
  border-radius: 50%;
  transition: transform 0.2s;
}

.form-toggle:checked {
  background: var(--accent-primary);
}

.form-toggle:checked::after {
  transform: translateX(20px);
}
```

---

## Accessibility

✅ **Labels**: Every input has associated label
✅ **Required Indicators**: Visual and aria-required
✅ **Error Messages**: Linked via aria-describedby
✅ **Focus Management**: Clear focus indicators
✅ **Keyboard Navigation**: Full Tab/Arrow support
✅ **Screen Reader Support**: Proper ARIA labels

---

## Usage Guidelines

### Do's
✅ Always provide labels for inputs
✅ Show validation feedback inline
✅ Use placeholder as example, not instruction
✅ Group related fields together
✅ Provide clear error messages

### Don'ts
❌ Don't use placeholder as label
❌ Don't validate until user leaves field (on blur)
❌ Don't disable submit button without explanation
❌ Don't use vague error messages
❌ Don't hide password requirements

---

**Last Updated**: December 2025  
**Version**: 1.0  
**Maintained by**: PS Technologies Design Team
