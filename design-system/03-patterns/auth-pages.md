# PS Technologies Design System
## Patterns: Authentication Pages

---

## Overview
Authentication patterns provide consistent, secure, and user-friendly experiences for sign-in, registration, and password management.

---

## Layout Structure

### Standard Auth Layout
```
┌──────────────────────────────────────────┐
│                                          │
│  [Logo]                                  │  ← Left: Form
│                                          │
│  ┌────────────────────┐                  │
│  │                    │     [Image/      │  ← Right: Visual
│  │   Auth Form        │    Illustration] │
│  │                    │                  │
│  └────────────────────┘                  │
│                                          │
└──────────────────────────────────────────┘
```

**Specifications**:
```css
Layout: 2-column grid (Desktop)
        Single column (Mobile)

Left Column:
  Max Width: 480px
  Padding: 40px (Space/40)
  Background: var(--theme-bg-canvas)
  
Right Column:
  Background: var(--bg-gradient) or image
  Min Height: 100vh
  Display: flex
  Align Items: center
  Justify Content: center
```

---

## Sign In Page

### Layout
```
┌────────────────────────────────────────┐
│ [Logo] PS Technologies                 │
│                                        │
│ Welcome back                           │
│ Sign in to your account                │
│                                        │
│ Email Address                          │
│ [___________________________]          │
│                                        │
│ Password                               │
│ [___________________________] [👁]     │
│                                        │
│ □ Remember me      Forgot password?    │
│                                        │
│ [Sign In]                              │
│                                        │
│ ─────────── OR ───────────             │
│                                        │
│ [Continue with Google]                 │
│ [Continue with GitHub]                 │
│                                        │
│ Don't have an account? Sign up         │
└────────────────────────────────────────┘
```

### Components Used
- Logo (32px height)
- H2 heading ("Welcome back")
- Body text (description)
- Text inputs (Email, Password)
- Checkbox (Remember me)
- Link (Forgot password)
- Primary button (Sign In)
- Divider with text
- Secondary buttons (Social sign-in)
- Text link (Sign up)

### Specifications
```css
Container:
  Max Width: 400px
  Padding: 40px (Space/40)
  
Heading:
  Margin Bottom: 8px
  
Description:
  Margin Bottom: 32px
  
Form Fields:
  Gap: 20px (Space/20)
  
Actions Row:
  Display: flex
  Justify Content: space-between
  Align Items: center
  Margin: 16px 0 24px
  
Divider:
  Margin: 24px 0
  
Social Buttons:
  Gap: 12px (Space/12)
  
Footer Link:
  Text Align: center
  Margin Top: 24px
```

---

## Create Account Page

### Layout
```
┌────────────────────────────────────────┐
│ [Logo] PS Technologies                 │
│                                        │
│ Create your account                    │
│ Start your 14-day free trial           │
│                                        │
│ Full Name                              │
│ [___________________________]          │
│                                        │
│ Email Address                          │
│ [___________________________]          │
│                                        │
│ Password                               │
│ [___________________________] [👁]     │
│ [==============          ] Weak        │
│ • At least 8 characters                │
│ • One uppercase letter                 │
│ • One number                           │
│                                        │
│ □ I agree to the Terms and Privacy     │
│                                        │
│ [Create Account]                       │
│                                        │
│ ─────────── OR ───────────             │
│                                        │
│ [Continue with Google]                 │
│ [Continue with GitHub]                 │
│                                        │
│ Already have an account? Sign in       │
└────────────────────────────────────────┘
```

### Specifications
```css
Password Strength Indicator:
  Display: block
  Margin Top: 8px
  Height: 4px
  Border Radius: 2px
  Background: var(--bg-soft)
  
  Progress:
    Height: 100%
    Border Radius: inherit
    Transition: width 0.3s, background 0.3s
    
Requirements List:
  Font: Caption (14px)
  Color: var(--text-muted)
  Margin Top: 12px
  Line Height: 1.8
  
  Valid Item:
    Color: var(--color-success)
    Icon: ✓
```

---

## Reset Password Page

### Step 1: Request Reset
```
┌────────────────────────────────────────┐
│ [Logo] PS Technologies                 │
│                                        │
│ Forgot your password?                  │
│ No worries, we'll send you reset      │
│ instructions.                          │
│                                        │
│ Email Address                          │
│ [___________________________]          │
│                                        │
│ [Send Reset Link]                      │
│                                        │
│ ← Back to Sign In                      │
└────────────────────────────────────────┘
```

### Step 2: Check Email
```
┌────────────────────────────────────────┐
│ [Logo] PS Technologies                 │
│                                        │
│ [✉️]                                   │
│                                        │
│ Check your email                       │
│ We sent a password reset link to       │
│ john@example.com                       │
│                                        │
│ [Open Email App]                       │
│                                        │
│ Didn't receive the email?              │
│ Click to resend                        │
└────────────────────────────────────────┘
```

### Step 3: Set New Password
```
┌────────────────────────────────────────┐
│ [Logo] PS Technologies                 │
│                                        │
│ Set new password                       │
│ Create a strong password for your      │
│ account.                               │
│                                        │
│ New Password                           │
│ [___________________________] [👁]     │
│                                        │
│ Confirm Password                       │
│ [___________________________] [👁]     │
│                                        │
│ [Reset Password]                       │
└────────────────────────────────────────┘
```

---

## Email Verification Page

```
┌────────────────────────────────────────┐
│ [Logo] PS Technologies                 │
│                                        │
│ [✉️]                                   │
│                                        │
│ Verify your email                      │
│ We sent a verification email to        │
│ john@example.com                       │
│                                        │
│ Please click the link in the email     │
│ to verify your account.                │
│                                        │
│ [Open Email App]                       │
│                                        │
│ Didn't receive the email?              │
│ [Resend Verification Email]            │
└────────────────────────────────────────┘
```

---

## Two-Factor Authentication

```
┌────────────────────────────────────────┐
│ [Logo] PS Technologies                 │
│                                        │
│ Two-factor authentication              │
│ Enter the 6-digit code from your      │
│ authenticator app                      │
│                                        │
│ [_] [_] [_] [_] [_] [_]               │
│                                        │
│ [Verify Code]                          │
│                                        │
│ Having trouble?                        │
│ Use backup code                        │
│                                        │
│ ← Back to Sign In                      │
└────────────────────────────────────────┘
```

**Code Input Specifications**:
```css
Display: flex
Gap: 12px (Space/12)
Justify Content: center

Input Box:
  Width: 48px
  Height: 56px
  Text Align: center
  Font Size: 24px
  Font Weight: 500
  Border: 2px solid var(--border-subtle)
  Border Radius: 12px
  
  Focus:
    Border Color: var(--accent-primary)
    Box Shadow: var(--focus-ring)
    
Auto-advance: Focus next input on digit entry
```

---

## Social Sign-In Buttons

### Google
```
┌────────────────────────────────────┐
│ [G] Continue with Google           │
└────────────────────────────────────┘
```

### GitHub
```
┌────────────────────────────────────┐
│ [GitHub] Continue with GitHub      │
└────────────────────────────────────┘
```

**Specifications**:
```css
Width: 100%
Padding: 12px 24px (Space/12 Space/24)
Background: var(--theme-bg-card)
Border: 2px solid var(--border-strong)
Border Radius: 12px (Radius/MD)
Font: Body/Medium (16px, 500)
Color: var(--text-primary)
Display: flex
Align Items: center
Justify Content: center
Gap: 12px

Icon:
  Width: 20px
  Height: 20px
  
Hover:
  Border Color: var(--accent-primary)
  Background: var(--bg-soft)
```

---

## Error Handling

### Inline Errors
```
Email Address
[john@invalid]  ✗
Invalid email format
```

### Alert Messages
```
┌────────────────────────────────────────┐
│ [!] Error signing in                   │
│ Invalid email or password. Please try  │
│ again.                                 │
└────────────────────────────────────────┘
```

---

## Loading States

### Button Loading
```
[⟳ Signing in...]  ← Disabled state
```

### Form Submission
- Disable all inputs
- Show loading state on button
- Prevent multiple submissions

---

## Responsive Behavior

### Mobile (<768px)
```css
Layout:
  Single column
  Full height
  
Visual/Illustration:
  Hidden or minimal
  
Container:
  Padding: 20px (Space/20)
  
Buttons:
  Full width
  
Social Buttons:
  Stack vertically
```

---

## Implementation Example

### HTML - Sign In
```html
<div class="auth-layout">
  <div class="auth-form-container">
    <a href="/" class="auth-logo">
      <img src="logo.svg" alt="PS Technologies" />
    </a>
    
    <div class="auth-header">
      <h2 class="auth-title">Welcome back</h2>
      <p class="auth-description">Sign in to your account</p>
    </div>
    
    <form class="auth-form" onsubmit="handleSignIn(event)">
      <div class="form-group">
        <label class="form-label">Email Address</label>
        <input type="email" class="form-input" required />
      </div>
      
      <div class="form-group">
        <label class="form-label">Password</label>
        <input type="password" class="form-input" required />
      </div>
      
      <div class="auth-actions">
        <label class="checkbox-label">
          <input type="checkbox" />
          Remember me
        </label>
        <a href="/forgot-password" class="link">Forgot password?</a>
      </div>
      
      <button type="submit" class="btn btn-primary btn-lg">
        Sign In
      </button>
      
      <div class="divider">
        <span>OR</span>
      </div>
      
      <button type="button" class="btn-social">
        <img src="google-icon.svg" />
        Continue with Google
      </button>
      
      <button type="button" class="btn-social">
        <img src="github-icon.svg" />
        Continue with GitHub
      </button>
    </form>
    
    <p class="auth-footer">
      Don't have an account? <a href="/signup" class="link">Sign up</a>
    </p>
  </div>
  
  <div class="auth-visual">
    <!-- Illustration or background gradient -->
  </div>
</div>
```

---

## Accessibility

✅ **Form Labels**: All inputs have associated labels
✅ **Error Messages**: Linked via aria-describedby
✅ **Focus Management**: Logical tab order
✅ **Password Toggle**: Keyboard accessible
✅ **Loading States**: Communicated to screen readers
✅ **ARIA Labels**: Clear button purposes

---

## Security Best Practices

✅ Use HTTPS for all auth pages
✅ Implement rate limiting
✅ Show password strength indicator
✅ Support two-factor authentication
✅ Never expose password in errors
✅ Use secure session management
✅ Implement CSRF protection

---

**Last Updated**: December 2025  
**Version**: 1.0  
**Maintained by**: PS Technologies Design Team
