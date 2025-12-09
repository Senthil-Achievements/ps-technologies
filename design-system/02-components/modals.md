# PS Technologies Design System
## Components: Modals & Overlays

---

## Modal Component

### Anatomy
```
        [Backdrop - Dark overlay]
        
        ┌─────────────────────────────┐
        │ Title               [×]     │
        ├─────────────────────────────┤
        │                             │
        │ Modal body content goes     │
        │ here with description and   │
        │ any form fields...          │
        │                             │
        ├─────────────────────────────┤
        │ [Cancel]   [Primary Action] │
        └─────────────────────────────┘
```

---

## Modal Specifications

### Backdrop
```css
Position: fixed
Top: 0, Left: 0, Right: 0, Bottom: 0
Background: rgba(15, 23, 42, 0.6)
Backdrop Filter: blur(4px)
Z-Index: 40
Display: flex
Align Items: center
Justify Content: center
Padding: 20px (Space/20)
Animation: fade-in 0.2s ease
```

### Modal Container
```css
Background: var(--theme-bg-card)
Border Radius: 16px (Radius/LG)
Box Shadow: var(--shadow-large)
Max Width: see size variants
Width: 100%
Max Height: calc(100vh - 40px)
Display: flex
Flex Direction: column
Animation: slide-up 0.3s ease
Position: relative
```

---

## Size Variants

### Small
```css
Max Width: 400px
Padding: 24px (Space/24)

Use Cases:
- Simple confirmations
- Quick forms
- Alerts with actions
```

### Medium (Default)
```css
Max Width: 560px
Padding: 32px (Space/32)

Use Cases:
- Standard forms
- Content previews
- Detailed confirmations
```

### Large
```css
Max Width: 800px
Padding: 40px (Space/40)

Use Cases:
- Complex forms
- Rich content
- Data tables
```

### Full Screen (Mobile)
```css
@media (max-width: 768px) {
  Max Width: 100%
  Height: 100vh
  Border Radius: 0
  Margin: 0
}
```

---

## Modal Header
```css
Display: flex
Align Items: flex-start
Justify Content: space-between
Margin Bottom: 24px (Space/24)

Title:
  Font: H3 (28px, Medium)
  Color: var(--text-primary)
  Flex: 1
  Padding Right: 20px
  
Subtitle (optional):
  Font: Body (16px)
  Color: var(--text-secondary)
  Margin Top: 8px
  
Close Button:
  Width: 32px
  Height: 32px
  Border Radius: 8px
  Background: transparent
  Color: var(--text-muted)
  Display: flex
  Align Items: center
  Justify Content: center
  Cursor: pointer
  Transition: 0.2s ease
  
  Hover:
    Background: var(--bg-soft)
    Color: var(--text-primary)
```

---

## Modal Body
```css
Flex: 1
Overflow Y: auto
Margin Bottom: 24px (Space/24)
Color: var(--text-secondary)
Line Height: 1.6

/* Custom Scrollbar */
Scrollbar Width: thin
Scrollbar Color: var(--border-strong) transparent

::-webkit-scrollbar {
  width: 8px
}

::-webkit-scrollbar-thumb {
  background: var(--border-strong)
  border-radius: 4px
}
```

---

## Modal Footer
```css
Display: flex
Align Items: center
Justify Content: flex-end
Gap: 12px (Space/12)
Padding Top: 24px (Space/24)
Border Top: 1px solid var(--border-subtle)

/* On mobile, stack buttons */
@media (max-width: 480px) {
  Flex Direction: column-reverse
  
  Button {
    Width: 100%
  }
}
```

---

## Modal Variants

### 1. Confirmation Modal
```
┌─────────────────────────────┐
│ Delete Account?       [×]   │
├─────────────────────────────┤
│                             │
│ This action cannot be       │
│ undone. All your data will  │
│ be permanently deleted.     │
│                             │
├─────────────────────────────┤
│ [Cancel]   [Delete Account] │
└─────────────────────────────┘
```

**Specifications**:
- Size: Small
- Destructive action button (red)
- Clear, direct copy
- Icon optional (warning icon)

---

### 2. Form Modal
```
┌─────────────────────────────┐
│ Add Team Member       [×]   │
├─────────────────────────────┤
│                             │
│ Name                        │
│ [_______________________]   │
│                             │
│ Email                       │
│ [_______________________]   │
│                             │
│ Role                        │
│ [Dropdown ▼]                │
│                             │
├─────────────────────────────┤
│ [Cancel]   [Add Member]     │
└─────────────────────────────┘
```

**Specifications**:
- Size: Medium
- Form fields with proper spacing
- Validation states
- Loading state on submit

---

### 3. Waitlist Modal
```
┌─────────────────────────────┐
│ Join the Waitlist     [×]   │
├─────────────────────────────┤
│                             │
│ Get early access to PS      │
│ Technologies platform       │
│                             │
│ Email Address *             │
│ [_______________________]   │
│                             │
│ Company Name (Optional)     │
│ [_______________________]   │
│                             │
│ □ I agree to receive        │
│   product updates           │
│                             │
├─────────────────────────────┤
│ [Cancel]   [Join Waitlist]  │
└─────────────────────────────┘
```

**Specifications**:
- Size: Small-Medium
- Compelling headline
- Minimal fields
- Checkbox for consent
- Gradient CTA button

---

### 4. Content Modal
```
┌─────────────────────────────┐
│ Feature Preview       [×]   │
├─────────────────────────────┤
│                             │
│ [Image/Video Preview]       │
│                             │
│ Rich content with text,     │
│ images, and detailed        │
│ descriptions...             │
│                             │
│ (scrollable content)        │
│                             │
├─────────────────────────────┤
│              [Got it]       │
└─────────────────────────────┘
```

**Specifications**:
- Size: Large
- Rich media support
- Scrollable body
- Single action button

---

## Drawer Component

### Side Drawer (Alternative to Modal)
```
┌─────────────────────┐
│ [×] Title           │
│ ─────────────       │
│                     │
│ Content slides      │
│ in from right       │
│ or left...          │
│                     │
│                     │
│ [Footer Actions]    │
└─────────────────────┘
```

**Specifications**:
```css
Position: fixed
Top: 0, Bottom: 0
Right: 0 (or Left: 0)
Width: 400px (Mobile: 100%)
Background: var(--theme-bg-card)
Box Shadow: -4px 0 24px rgba(0, 0, 0, 0.1)
Z-Index: 40
Transform: translateX(100%) (hidden)
         translateX(0) (visible)
Transition: transform 0.3s ease
Overflow Y: auto
```

---

## Implementation

### HTML
```html
<!-- Modal -->
<div class="modal-backdrop" id="modal" role="dialog" aria-modal="true" aria-labelledby="modal-title">
  <div class="modal modal-md">
    <div class="modal-header">
      <div>
        <h2 class="modal-title" id="modal-title">Modal Title</h2>
        <p class="modal-subtitle">Optional subtitle</p>
      </div>
      <button class="modal-close" aria-label="Close">
        <svg>×</svg>
      </button>
    </div>
    
    <div class="modal-body">
      <p>Modal content goes here...</p>
    </div>
    
    <div class="modal-footer">
      <button class="btn btn-secondary">Cancel</button>
      <button class="btn btn-primary">Confirm</button>
    </div>
  </div>
</div>
```

### CSS
```css
/* Backdrop */
.modal-backdrop {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(15, 23, 42, 0.6);
  backdrop-filter: blur(4px);
  z-index: 40;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: var(--space-20);
  animation: fade-in 0.2s ease;
  cursor: pointer;
}

@keyframes fade-in {
  from { opacity: 0; }
  to { opacity: 1; }
}

/* Modal */
.modal {
  background: var(--theme-bg-card);
  border-radius: var(--radius-lg);
  box-shadow: var(--shadow-large);
  max-height: calc(100vh - 40px);
  width: 100%;
  display: flex;
  flex-direction: column;
  animation: slide-up 0.3s ease;
  cursor: default;
  position: relative;
}

@keyframes slide-up {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.modal-sm { max-width: 400px; padding: var(--space-24); }
.modal-md { max-width: 560px; padding: var(--space-32); }
.modal-lg { max-width: 800px; padding: var(--space-40); }

/* Header */
.modal-header {
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  margin-bottom: var(--space-24);
}

.modal-title {
  font-size: 1.75rem;
  font-weight: 500;
  color: var(--text-primary);
  margin: 0;
  padding-right: var(--space-20);
}

.modal-subtitle {
  font-size: 1rem;
  color: var(--text-secondary);
  margin-top: var(--space-8);
}

.modal-close {
  width: 32px;
  height: 32px;
  border-radius: var(--radius-sm);
  background: transparent;
  border: none;
  color: var(--text-muted);
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: all 0.2s ease;
  flex-shrink: 0;
}

.modal-close:hover {
  background: var(--bg-soft);
  color: var(--text-primary);
}

/* Body */
.modal-body {
  flex: 1;
  overflow-y: auto;
  margin-bottom: var(--space-24);
  color: var(--text-secondary);
  line-height: 1.6;
}

.modal-body::-webkit-scrollbar {
  width: 8px;
}

.modal-body::-webkit-scrollbar-thumb {
  background: var(--border-strong);
  border-radius: 4px;
}

/* Footer */
.modal-footer {
  display: flex;
  align-items: center;
  justify-content: flex-end;
  gap: var(--space-12);
  padding-top: var(--space-24);
  border-top: 1px solid var(--border-subtle);
}

@media (max-width: 480px) {
  .modal-footer {
    flex-direction: column-reverse;
  }
  
  .modal-footer .btn {
    width: 100%;
  }
}

/* Drawer */
.drawer {
  position: fixed;
  top: 0;
  bottom: 0;
  right: 0;
  width: 400px;
  background: var(--theme-bg-card);
  box-shadow: -4px 0 24px rgba(0, 0, 0, 0.1);
  z-index: 40;
  transform: translateX(100%);
  transition: transform 0.3s ease;
  overflow-y: auto;
  padding: var(--space-32);
}

.drawer.open {
  transform: translateX(0);
}

@media (max-width: 768px) {
  .drawer {
    width: 100%;
  }
}
```

### JavaScript
```javascript
// Modal Management
class Modal {
  constructor(modalId) {
    this.modal = document.getElementById(modalId);
    this.backdrop = this.modal;
    
    // Close on backdrop click
    this.backdrop.addEventListener('click', (e) => {
      if (e.target === this.backdrop) {
        this.close();
      }
    });
    
    // Close on Escape key
    document.addEventListener('keydown', (e) => {
      if (e.key === 'Escape' && this.isOpen()) {
        this.close();
      }
    });
  }
  
  open() {
    this.modal.style.display = 'flex';
    document.body.style.overflow = 'hidden';
    this.modal.querySelector('.modal-close')?.focus();
  }
  
  close() {
    this.modal.style.display = 'none';
    document.body.style.overflow = '';
  }
  
  isOpen() {
    return this.modal.style.display === 'flex';
  }
}

// Usage
const myModal = new Modal('modal');
document.getElementById('openModal').addEventListener('click', () => myModal.open());
```

---

## Accessibility

✅ **Focus Trap**: Keep focus within modal
✅ **Escape Key**: Close on Escape
✅ **ARIA Attributes**: role="dialog", aria-modal="true"
✅ **Focus Management**: Return focus to trigger on close
✅ **Backdrop Click**: Close on backdrop click
✅ **Screen Reader**: Clear labels and structure

---

## Usage Guidelines

### Do's
✅ Use modals for focused tasks
✅ Provide clear close affordances
✅ Keep content concise
✅ Disable background scrolling
✅ Use appropriate size for content

### Don'ts
❌ Don't nest modals
❌ Don't use for complex workflows
❌ Don't auto-open without user action
❌ Don't hide close button
❌ Don't block progress indefinitely

---

**Last Updated**: December 2025  
**Version**: 1.0  
**Maintained by**: PS Technologies Design Team
