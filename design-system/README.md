# PS Technologies Design System
**Version 1.0** • December 2025

---

## 🎯 Overview

This is a comprehensive, production-ready design system for PS Technologies - a B2B AI SaaS platform. The system provides foundations, components, and patterns for building consistent, accessible, and beautiful experiences across:

- **Marketing Website** - Landing pages, product pages, pricing
- **Dashboard/Web App** - Application interfaces, data visualizations
- **Authentication Flows** - Sign in, registration, password reset
- **Waitlist & Onboarding** - User acquisition funnels
- **Internal Tools** - Admin panels, management interfaces

---

## 📚 Documentation Structure

### 01 - Foundations
Core design tokens that form the building blocks of the system.

| File | Description |
|------|-------------|
| **[colors.md](01-foundations/colors.md)** | Color palette, semantic tokens, light/dark themes, gradients, accessibility guidelines |
| **[typography.md](01-foundations/typography.md)** | Type scale, font families, responsive typography, CSS classes |
| **[spacing-layout.md](01-foundations/spacing-layout.md)** | 8-point spacing system, radius scale, grid system, containers, z-index |
| **[effects.md](01-foundations/effects.md)** | Shadows, glows, focus rings, dark theme adjustments |
| **[themes.md](01-foundations/themes.md)** | Light/dark theme specifications, token system, theme switching implementation |

**Key Concepts**:
- **Brand Colors**: Indigo-Teal gradient (`#4F46E5` → `#06B6D4`)
- **Typography**: Inter font family with 9 type scales
- **Spacing**: 8-point system (2px to 128px)
- **Themes**: Full light/dark mode support

---

### 02 - Components
Reusable UI components with variants, states, and implementation code.

| Component | Description |
|-----------|-------------|
| **[buttons.md](02-components/buttons.md)** | 5 variants (Primary, Secondary, Tertiary, Ghost, Destructive), 3 sizes, icon configurations |
| **[inputs-forms.md](02-components/inputs-forms.md)** | Text inputs, textarea, password, select, checkbox, radio, toggle, search, file upload |
| **[cards.md](02-components/cards.md)** | 5 card variants (Base, Metric, Feature, List Item, Pricing) |
| **[navigation.md](02-components/navigation.md)** | Top nav, mobile nav, sidebar, breadcrumbs, tabs, pagination |
| **[badges-tags.md](02-components/badges-tags.md)** | Badge variants (Solid, Outline, Soft), tags, chips, status indicators |
| **[modals.md](02-components/modals.md)** | Modal sizes and variants, drawer component, focus management |
| **[toasts-alerts.md](02-components/toasts-alerts.md)** | Toast notifications (4 semantic types), inline alerts, ToastManager |
| **[tables-data.md](02-components/tables-data.md)** | Data tables, selectable rows, pagination, avatars, skeleton loaders |

**Each Component Includes**:
- Visual ASCII diagrams
- Complete specifications (sizes, colors, spacing)
- All states (default, hover, focus, disabled, error, success)
- HTML + CSS implementation
- React component examples
- Accessibility guidelines
- Usage best practices

---

### 03 - Patterns
High-level patterns showing how components combine into complete interfaces.

| Pattern | Description |
|---------|-------------|
| **[auth-pages.md](03-patterns/auth-pages.md)** | Sign in, create account, password reset, 2FA, email verification, social sign-in |
| **[dashboard-layouts.md](03-patterns/dashboard-layouts.md)** | Dashboard structure, metrics grid, charts, tables, activity feed, search, notifications |
| **[marketing-pages.md](03-patterns/marketing-pages.md)** | Hero sections, features, pricing, testimonials, CTA, FAQ, footer |

---

## 🚀 Quick Start

### For Developers

**1. Set up CSS Variables**
```html
<link rel="stylesheet" href="design-system/variables.css">
```

**2. Use Foundation Tokens**
```css
.my-component {
  background: var(--theme-bg-card);
  color: var(--theme-text-primary);
  padding: var(--space-16);
  border-radius: var(--radius-md);
  box-shadow: var(--shadow-soft);
}
```

**3. Build Components**
Refer to component documentation for complete HTML/CSS implementation. Each component file includes copy-paste ready code.

**4. Implement Themes**
```javascript
// Theme switching
document.documentElement.setAttribute('data-theme', 'dark');
localStorage.setItem('theme', 'dark');
```

See `01-foundations/themes.md` for complete theme implementation.

---

### For Designers (Figma)

**Component Naming Convention**:
```
Category / Variant / Size / State

Examples:
- Button / Primary / Large / Default
- Button / Primary / Large / Hover
- Button / Secondary / Medium / Disabled
- Input / Text / Default / Empty
- Input / Text / Default / Filled
- Input / Text / Error / Filled
- Card / Metric / Default
- Card / Pricing / Popular
```

**Layer Structure**:
```
Component
├─ Background
├─ Border
├─ Content
│  ├─ Icon (if applicable)
│  ├─ Text
│  └─ Badge (if applicable)
└─ States (variants)
```

---

## 🎨 Core Design Tokens

### Colors
```css
/* Primary Brand */
--indigo-600: #4F46E5;
--teal-400: #06B6D4;
--accent-gradient: linear-gradient(90deg, #4F46E5 0%, #06B6D4 100%);

/* Semantic */
--color-success: #22C55E;
--color-warning: #F59E0B;
--color-error: #EF4444;
--color-info: #3B82F6;

/* Theme Tokens (switch based on light/dark) */
--theme-bg-canvas: /* #FFFFFF in light, #0F172A in dark */
--theme-text-primary: /* #0F172A in light, #FFFFFF in dark */
```

### Typography Scale
```css
--font-display: 56px / 1.14 / 600
--font-h1: 48px / 1.2 / 600
--font-h2: 36px / 1.3 / 600
--font-h3: 28px / 1.35 / 600
--font-h4: 22px / 1.4 / 500
--font-body: 16px / 1.6 / 400
--font-caption: 14px / 1.5 / 400
--font-label: 12px / 1.5 / 500
```

### Spacing (8-point system)
```css
--space-2: 2px    --space-40: 40px
--space-4: 4px    --space-48: 48px
--space-8: 8px    --space-56: 56px
--space-12: 12px  --space-64: 64px
--space-16: 16px  --space-80: 80px
--space-20: 20px  --space-96: 96px
--space-24: 24px  --space-128: 128px
--space-32: 32px
```

### Border Radius
```css
--radius-xs: 4px
--radius-sm: 8px
--radius-md: 12px
--radius-lg: 16px
--radius-xl: 20px
--radius-2xl: 24px
--radius-full: 9999px
```

### Shadows
```css
--shadow-soft: 0 2px 8px rgba(15, 23, 42, 0.08)
--shadow-medium: 0 4px 16px rgba(15, 23, 42, 0.12)
--shadow-large: 0 8px 24px rgba(15, 23, 42, 0.16)
--shadow-xl: 0 16px 48px rgba(15, 23, 42, 0.24)
```

---

## 🏗️ Usage Examples

### Building a Button
```html
<button class="btn btn-primary btn-large">
  <svg class="btn-icon">...</svg>
  <span>Get Started</span>
</button>
```
```css
.btn {
  display: inline-flex;
  align-items: center;
  gap: var(--space-8);
  padding: var(--space-12) var(--space-24);
  border-radius: var(--radius-md);
  font: var(--font-body-medium);
  transition: all 0.2s;
}

.btn-primary {
  background: var(--accent-gradient);
  color: #FFFFFF;
}

.btn-large {
  padding: var(--space-16) var(--space-32);
  font-size: 18px;
}
```

### Building a Card
```html
<div class="card">
  <div class="card-header">
    <h3>Card Title</h3>
    <span class="badge badge-soft-success">Active</span>
  </div>
  <div class="card-body">
    <p>Card content goes here...</p>
  </div>
  <div class="card-footer">
    <button class="btn btn-secondary">Action</button>
  </div>
</div>
```
```css
.card {
  background: var(--theme-bg-card);
  border: 1px solid var(--theme-border-subtle);
  border-radius: var(--radius-lg);
  box-shadow: var(--shadow-soft);
}

.card-header {
  display: flex;
  justify-content: space-between;
  padding: var(--space-24);
  border-bottom: 1px solid var(--theme-border-subtle);
}
```

### Building a Dashboard Layout
```html
<div class="dashboard">
  <nav class="top-nav">...</nav>
  <aside class="sidebar">...</aside>
  <main class="main-content">
    <div class="metrics-grid">
      <div class="card card-metric">...</div>
      <div class="card card-metric">...</div>
      <div class="card card-metric">...</div>
    </div>
  </main>
</div>
```

See pattern documentation for complete implementations.

---

## ♿ Accessibility Standards

All components meet **WCAG 2.1 Level AA** standards:

✅ **Color Contrast**: Minimum 4.5:1 for text, 3:1 for large text  
✅ **Keyboard Navigation**: All interactive elements accessible via keyboard  
✅ **Focus Indicators**: Visible focus rings on all focusable elements  
✅ **Screen Readers**: Proper ARIA labels and semantic HTML  
✅ **Motion**: Respects `prefers-reduced-motion`  
✅ **Responsive**: Works on all screen sizes

---

## 🌗 Theme Implementation

The design system supports light and dark themes using CSS custom properties.

**Set Theme**:
```javascript
// JavaScript
function setTheme(theme) {
  document.documentElement.setAttribute('data-theme', theme);
  localStorage.setItem('theme', theme);
}

// On page load
const savedTheme = localStorage.getItem('theme') || 
  (window.matchMedia('(prefers-color-scheme: dark)').matches ? 'dark' : 'light');
setTheme(savedTheme);
```

**CSS Variables**:
```css
:root {
  --theme-bg-canvas: #FFFFFF;
  --theme-text-primary: #0F172A;
}

[data-theme="dark"] {
  --theme-bg-canvas: #0F172A;
  --theme-text-primary: #FFFFFF;
}
```

See `01-foundations/themes.md` for complete implementation.

---

## 📱 Responsive Design

### Breakpoints
```css
/* Mobile First */
--breakpoint-sm: 640px   /* Small tablets */
--breakpoint-md: 768px   /* Tablets */
--breakpoint-lg: 1024px  /* Small laptops */
--breakpoint-xl: 1280px  /* Desktops */
--breakpoint-2xl: 1536px /* Large screens */
```

### Mobile Considerations
- Touch targets minimum 44x44px
- Stack layouts vertically on mobile
- Simplified navigation (hamburger menu)
- Larger font sizes for readability
- Reduced spacing on smaller screens

---

## 🧪 Testing Checklist

Before deploying components:

- [ ] Test in light and dark themes
- [ ] Test on mobile, tablet, desktop sizes
- [ ] Test keyboard navigation (Tab, Enter, Escape)
- [ ] Test with screen reader
- [ ] Verify color contrast ratios
- [ ] Test all interactive states (hover, focus, active, disabled)
- [ ] Validate HTML semantics
- [ ] Check loading and error states
- [ ] Test with reduced motion preference
- [ ] Cross-browser testing (Chrome, Firefox, Safari, Edge)

---

## 🔄 Version History

**v1.0 - December 2025**
- Initial release
- Complete foundation tokens (colors, typography, spacing, effects, themes)
- 8 core component categories
- 3 high-level pattern categories
- Full light/dark theme support
- Accessibility compliance (WCAG 2.1 AA)

---

## 🤝 Contributing

When adding new components or patterns:

1. Follow existing documentation structure
2. Include ASCII visual diagrams
3. Provide complete specifications (CSS values)
4. Document all states and variants
5. Include implementation code (HTML, CSS, JavaScript)
6. Add accessibility guidelines
7. Include usage examples and best practices
8. Test across themes and screen sizes

---

## 📞 Support

For questions or feedback about the design system:
- **Email**: design@pstechnologies.com
- **Slack**: #design-system
- **Documentation Issues**: GitHub Issues

---

## 📄 License

© 2025 PS Technologies. All rights reserved.

This design system is proprietary and confidential. Unauthorized use, reproduction, or distribution is prohibited.

---

**Built with ❤️ by the PS Technologies Design Team**
