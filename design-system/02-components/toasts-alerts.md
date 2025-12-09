# PS Technologies Design System
## Components: Toasts & Alerts

---

## Toast Component (Notifications)

### Overview
Toasts provide brief, auto-dismissing feedback about an operation. They appear temporarily and don't require user interaction.

---

## Toast Anatomy
```
┌────────────────────────────────────┐
│ [Icon] Title              [×]      │
│        Optional description text   │
└────────────────────────────────────┘
```

---

## Toast Specifications

### Base Toast
```css
Min Width: 320px
Max Width: 420px
Background: var(--theme-bg-card)
Border: 1px solid var(--border-subtle)
Border Radius: 12px (Radius/MD)
Box Shadow: var(--shadow-large)
Padding: 16px (Space/16)
Display: flex
Gap: 12px (Space/12)
Position: fixed
Top: 20px
Right: 20px
Z-Index: 50
Animation: slide-in-right 0.3s ease
```

### Toast Container (Stack)
```css
Position: fixed
Top: 20px
Right: 20px
Display: flex
Flex Direction: column
Gap: 12px (Space/12)
Z-Index: 50
Max Width: 420px
```

---

## Toast Variants

### 1. Success Toast
```
┌────────────────────────────────────┐
│ [✓] Changes saved successfully  [×]│
│     Your profile has been updated  │
└────────────────────────────────────┘
```

**Specifications**:
```css
Border Left: 3px solid #22C55E

Icon:
  Size: 20px
  Color: #22C55E
  Background: rgba(34, 197, 94, 0.12)
  Padding: 8px
  Border Radius: 8px
```

---

### 2. Error Toast
```
┌────────────────────────────────────┐
│ [!] Error saving changes        [×]│
│     Please check your connection   │
└────────────────────────────────────┘
```

**Specifications**:
```css
Border Left: 3px solid #EF4444

Icon:
  Size: 20px
  Color: #EF4444
  Background: rgba(239, 68, 68, 0.12)
```

---

### 3. Warning Toast
```
┌────────────────────────────────────┐
│ [⚠] Storage almost full         [×]│
│     You have 10% space remaining   │
└────────────────────────────────────┘
```

**Specifications**:
```css
Border Left: 3px solid #F59E0B

Icon:
  Color: #F59E0B
  Background: rgba(245, 158, 11, 0.12)
```

---

### 4. Info Toast
```
┌────────────────────────────────────┐
│ [ℹ] New feature available       [×]│
│     Check out our AI tools         │
└────────────────────────────────────┘
```

**Specifications**:
```css
Border Left: 3px solid #3B82F6

Icon:
  Color: #3B82F6
  Background: rgba(59, 130, 246, 0.12)
```

---

### 5. Loading Toast
```
┌────────────────────────────────────┐
│ [⟳] Processing...                 │
│     Please wait...                 │
└────────────────────────────────────┘
```

**Specifications**:
```css
No close button
Spinner animation on icon
Stays until dismissed programmatically
```

---

## Toast Content

### Title
```css
Font: Body/Medium (16px, 500)
Color: var(--text-primary)
Margin Bottom: 2px (if description exists)
```

### Description
```css
Font: Caption (14px, Regular)
Color: var(--text-muted)
Line Height: 1.5
```

### Close Button
```css
Width: 24px
Height: 24px
Border Radius: 6px
Background: transparent
Color: var(--text-muted)
Cursor: pointer
Align Self: flex-start
Flex Shrink: 0

Hover:
  Background: var(--bg-soft)
  Color: var(--text-primary)
```

---

## Toast with Action
```
┌────────────────────────────────────┐
│ [✓] File uploaded               [×]│
│     document.pdf (2.4 MB)          │
│     [View File]                    │
└────────────────────────────────────┘
```

**Action Button**:
```css
Margin Top: 12px
Variant: Ghost or Secondary
Size: Small
```

---

## Progress Toast
```
┌────────────────────────────────────┐
│ [↑] Uploading file...           [×]│
│     [████████░░░░░░░░] 45%        │
└────────────────────────────────────┘
```

**Progress Bar**:
```css
Width: 100%
Height: 4px
Background: var(--bg-soft)
Border Radius: 2px
Margin Top: 8px

Fill:
  Background: var(--accent-primary)
  Height: 100%
  Border Radius: inherit
  Transition: width 0.3s ease
```

---

## Alert Component (Inline)

### Overview
Alerts are persistent notifications embedded in page content, requiring explicit dismissal or acknowledgment.

---

## Alert Variants

### Success Alert
```
┌────────────────────────────────────────┐
│ [✓] Success!                       [×] │
│                                        │
│ Your account has been created          │
│ successfully. Check your email to      │
│ verify your account.                   │
└────────────────────────────────────────┘
```

**Specifications**:
```css
Background: rgba(34, 197, 94, 0.08)
Border: 1px solid rgba(34, 197, 94, 0.3)
Border Radius: 12px
Padding: 16px 20px (Space/16 Space/20)

Icon:
  Color: #22C55E
  Size: 24px
  
Title:
  Font: Body/Semi-bold (16px, 600)
  Color: #22C55E
  
Body:
  Font: Body (16px, Regular)
  Color: var(--text-secondary)
  Margin Top: 8px
```

---

### Error Alert
```
┌────────────────────────────────────────┐
│ [!] Error                          [×] │
│                                        │
│ Failed to process payment. Please      │
│ check your card details and try again. │
│                                        │
│ [Retry Payment]                        │
└────────────────────────────────────────┘
```

**Specifications**:
```css
Background: rgba(239, 68, 68, 0.08)
Border: 1px solid rgba(239, 68, 68, 0.3)
Icon Color: #EF4444
Title Color: #EF4444
```

---

### Warning Alert
```
┌────────────────────────────────────────┐
│ [⚠] Warning                        [×] │
│                                        │
│ Your trial expires in 3 days. Upgrade  │
│ now to keep access to premium features.│
│                                        │
│ [Upgrade Now]                          │
└────────────────────────────────────────┘
```

**Specifications**:
```css
Background: rgba(245, 158, 11, 0.08)
Border: 1px solid rgba(245, 158, 11, 0.3)
Icon Color: #F59E0B
Title Color: #F59E0B
```

---

### Info Alert
```
┌────────────────────────────────────────┐
│ [ℹ] Information                    [×] │
│                                        │
│ We've updated our privacy policy.      │
│ Review the changes to stay informed.   │
│                                        │
│ [Learn More]                           │
└────────────────────────────────────────┘
```

**Specifications**:
```css
Background: rgba(59, 130, 246, 0.08)
Border: 1px solid rgba(59, 130, 246, 0.3)
Icon Color: #3B82F6
Title Color: #3B82F6
```

---

## Implementation

### HTML - Toast
```html
<div class="toast toast-success" role="alert">
  <div class="toast-icon">
    <svg>✓</svg>
  </div>
  <div class="toast-content">
    <div class="toast-title">Changes saved successfully</div>
    <div class="toast-description">Your profile has been updated</div>
  </div>
  <button class="toast-close" aria-label="Close">
    <svg>×</svg>
  </button>
</div>
```

### HTML - Alert
```html
<div class="alert alert-warning" role="alert">
  <div class="alert-icon">
    <svg>⚠</svg>
  </div>
  <div class="alert-content">
    <div class="alert-title">Warning</div>
    <div class="alert-body">
      Your trial expires in 3 days. Upgrade now to keep access.
    </div>
    <button class="btn btn-primary btn-sm">Upgrade Now</button>
  </div>
  <button class="alert-close" aria-label="Close">
    <svg>×</svg>
  </button>
</div>
```

### CSS
```css
/* Toast */
.toast {
  min-width: 320px;
  max-width: 420px;
  background: var(--theme-bg-card);
  border: 1px solid var(--border-subtle);
  border-radius: var(--radius-md);
  box-shadow: var(--shadow-large);
  padding: var(--space-16);
  display: flex;
  gap: var(--space-12);
  animation: slide-in-right 0.3s ease;
}

.toast-success { border-left: 3px solid var(--color-success); }
.toast-error { border-left: 3px solid var(--color-error); }
.toast-warning { border-left: 3px solid var(--color-warning); }
.toast-info { border-left: 3px solid var(--color-info); }

@keyframes slide-in-right {
  from {
    opacity: 0;
    transform: translateX(100%);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

.toast-icon {
  width: 36px;
  height: 36px;
  border-radius: var(--radius-sm);
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
}

.toast-success .toast-icon {
  background: rgba(34, 197, 94, 0.12);
  color: var(--color-success);
}

.toast-error .toast-icon {
  background: rgba(239, 68, 68, 0.12);
  color: var(--color-error);
}

.toast-content {
  flex: 1;
  min-width: 0;
}

.toast-title {
  font-size: 1rem;
  font-weight: 500;
  color: var(--text-primary);
  margin-bottom: 2px;
}

.toast-description {
  font-size: 0.875rem;
  color: var(--text-muted);
  line-height: 1.5;
}

.toast-close {
  width: 24px;
  height: 24px;
  border-radius: 6px;
  background: transparent;
  border: none;
  color: var(--text-muted);
  cursor: pointer;
  flex-shrink: 0;
  align-self: flex-start;
  transition: all 0.2s ease;
}

.toast-close:hover {
  background: var(--bg-soft);
  color: var(--text-primary);
}

/* Toast Container */
.toast-container {
  position: fixed;
  top: 20px;
  right: 20px;
  display: flex;
  flex-direction: column;
  gap: var(--space-12);
  z-index: 50;
  max-width: 420px;
}

/* Alert */
.alert {
  display: flex;
  gap: var(--space-16);
  padding: var(--space-16) var(--space-20);
  border-radius: var(--radius-md);
  border: 1px solid;
  position: relative;
}

.alert-success {
  background: rgba(34, 197, 94, 0.08);
  border-color: rgba(34, 197, 94, 0.3);
}

.alert-error {
  background: rgba(239, 68, 68, 0.08);
  border-color: rgba(239, 68, 68, 0.3);
}

.alert-warning {
  background: rgba(245, 158, 11, 0.08);
  border-color: rgba(245, 158, 11, 0.3);
}

.alert-info {
  background: rgba(59, 130, 246, 0.08);
  border-color: rgba(59, 130, 246, 0.3);
}

.alert-icon {
  width: 24px;
  height: 24px;
  flex-shrink: 0;
}

.alert-success .alert-icon { color: var(--color-success); }
.alert-error .alert-icon { color: var(--color-error); }
.alert-warning .alert-icon { color: var(--color-warning); }
.alert-info .alert-icon { color: var(--color-info); }

.alert-content {
  flex: 1;
}

.alert-title {
  font-size: 1rem;
  font-weight: 600;
  margin-bottom: var(--space-8);
}

.alert-success .alert-title { color: var(--color-success); }
.alert-error .alert-title { color: var(--color-error); }
.alert-warning .alert-title { color: var(--color-warning); }
.alert-info .alert-title { color: var(--color-info); }

.alert-body {
  font-size: 1rem;
  color: var(--text-secondary);
  line-height: 1.6;
}

.alert-close {
  position: absolute;
  top: 16px;
  right: 16px;
  width: 24px;
  height: 24px;
  border: none;
  background: transparent;
  color: var(--text-muted);
  cursor: pointer;
  border-radius: 6px;
  transition: all 0.2s ease;
}

.alert-close:hover {
  background: rgba(0, 0, 0, 0.05);
  color: var(--text-primary);
}
```

### JavaScript - Toast Manager
```javascript
class ToastManager {
  constructor() {
    this.container = this.createContainer();
  }
  
  createContainer() {
    let container = document.querySelector('.toast-container');
    if (!container) {
      container = document.createElement('div');
      container.className = 'toast-container';
      document.body.appendChild(container);
    }
    return container;
  }
  
  show(type, title, description, duration = 5000) {
    const toast = document.createElement('div');
    toast.className = `toast toast-${type}`;
    toast.setAttribute('role', 'alert');
    
    const icons = {
      success: '✓',
      error: '!',
      warning: '⚠',
      info: 'ℹ'
    };
    
    toast.innerHTML = `
      <div class="toast-icon">
        <svg>${icons[type]}</svg>
      </div>
      <div class="toast-content">
        <div class="toast-title">${title}</div>
        ${description ? `<div class="toast-description">${description}</div>` : ''}
      </div>
      <button class="toast-close" aria-label="Close">×</button>
    `;
    
    this.container.appendChild(toast);
    
    // Close button handler
    toast.querySelector('.toast-close').addEventListener('click', () => {
      this.remove(toast);
    });
    
    // Auto-dismiss
    if (duration > 0) {
      setTimeout(() => this.remove(toast), duration);
    }
    
    return toast;
  }
  
  remove(toast) {
    toast.style.animation = 'slide-out-right 0.3s ease';
    setTimeout(() => toast.remove(), 300);
  }
}

// Usage
const toasts = new ToastManager();
toasts.show('success', 'Saved!', 'Your changes have been saved');
toasts.show('error', 'Error', 'Something went wrong');
```

---

## Timing & Behavior

### Auto-Dismiss Duration
```
Success: 4-5 seconds
Info: 5-6 seconds
Warning: 7-8 seconds (more time to read)
Error: No auto-dismiss or 10+ seconds
Loading: No auto-dismiss (dismiss programmatically)
```

### Stacking
- Maximum 3 toasts visible at once
- Older toasts dismissed first
- New toasts appear at top

---

## Accessibility

✅ **ARIA Role**: role="alert" for announcements
✅ **Live Region**: Screen readers announce toasts
✅ **Keyboard**: Close button is keyboard accessible
✅ **Focus Management**: Don't steal focus from main content
✅ **Color Independence**: Use icons, not just color

---

## Usage Guidelines

### Do's
✅ Use toasts for brief, non-critical feedback
✅ Keep messages concise and clear
✅ Use appropriate semantic types
✅ Provide actions when relevant
✅ Auto-dismiss non-errors

### Don'ts
❌ Don't use toasts for critical errors
❌ Don't stack too many toasts
❌ Don't auto-dismiss error messages quickly
❌ Don't include complex interactions in toasts
❌ Don't use toasts for lengthy content

---

**Last Updated**: December 2025  
**Version**: 1.0  
**Maintained by**: PS Technologies Design Team
