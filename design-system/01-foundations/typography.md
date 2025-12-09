# PS Technologies Design System
## Foundations: Typography

---

### Philosophy
Typography for PS Technologies prioritizes clarity, readability, and modern professionalism. We use system fonts for performance and familiarity, with carefully calibrated scales that work across marketing content, dashboards, and documentation.

---

## Font Stack

### Primary Font
```css
font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', 
             'Roboto', 'Helvetica Neue', Arial, sans-serif;
```

**Inter** is our primary typeface:
- Clean, geometric sans-serif
- Excellent readability at all sizes
- Designed specifically for screens
- Available via Google Fonts or self-hosted

**Fallback Stack**: System fonts ensure instant rendering if Inter doesn't load.

### Monospace Font (Code)
```css
font-family: 'SF Mono', 'Monaco', 'Cascadia Code', 'Consolas', 
             'Courier New', monospace;
```

---

## Type Scale

### Display Styles

#### Display
```
Font Size: 56px (3.5rem)
Line Height: 64px (1.14)
Font Weight: 600 (Semi-bold)
Letter Spacing: -0.02em

Usage: Hero headlines, major landing page headers
Token: Text/Display
```

#### H1 – Heading 1
```
Font Size: 48px (3rem)
Line Height: 56px (1.17)
Font Weight: 600 (Semi-bold)
Letter Spacing: -0.02em

Usage: Page titles, primary headlines
Token: Text/H1
```

#### H2 – Heading 2
```
Font Size: 36px (2.25rem)
Line Height: 44px (1.22)
Font Weight: 600 (Semi-bold)
Letter Spacing: -0.01em

Usage: Section headers, feature titles
Token: Text/H2
```

#### H3 – Heading 3
```
Font Size: 28px (1.75rem)
Line Height: 36px (1.29)
Font Weight: 500 (Medium)
Letter Spacing: -0.01em

Usage: Subsection headers, card titles
Token: Text/H3
```

#### H4 – Heading 4
```
Font Size: 22px (1.375rem)
Line Height: 30px (1.36)
Font Weight: 500 (Medium)
Letter Spacing: -0.005em

Usage: Component headers, modal titles
Token: Text/H4
```

### Body Styles

#### Body Large / Regular
```
Font Size: 18px (1.125rem)
Line Height: 28px (1.56)
Font Weight: 400 (Regular)
Letter Spacing: 0

Usage: Large body text, lead paragraphs
Token: Text/BodyLarge
```

#### Body / Regular
```
Font Size: 16px (1rem)
Line Height: 24px (1.5)
Font Weight: 400 (Regular)
Letter Spacing: 0

Usage: Standard body text, descriptions
Token: Text/Body
```

#### Body / Medium
```
Font Size: 16px (1rem)
Line Height: 24px (1.5)
Font Weight: 500 (Medium)
Letter Spacing: 0

Usage: Emphasized body text, button labels, table headers
Token: Text/BodyMedium
```

#### Body / Semi-bold
```
Font Size: 16px (1rem)
Line Height: 24px (1.5)
Font Weight: 600 (Semi-bold)
Letter Spacing: 0

Usage: Strong emphasis, active navigation items
Token: Text/BodySemibold
```

### Small Styles

#### Caption
```
Font Size: 14px (0.875rem)
Line Height: 20px (1.43)
Font Weight: 400 (Regular)
Letter Spacing: 0

Usage: Helper text, timestamps, metadata
Token: Text/Caption
```

#### Caption / Medium
```
Font Size: 14px (0.875rem)
Line Height: 20px (1.43)
Font Weight: 500 (Medium)
Letter Spacing: 0

Usage: Form labels, badge text, small button labels
Token: Text/CaptionMedium
```

#### Label (Tiny)
```
Font Size: 12px (0.75rem)
Line Height: 16px (1.33)
Font Weight: 500 (Medium)
Letter Spacing: 0.02em
Text Transform: Uppercase

Usage: Overlines, category tags, tiny labels
Token: Text/Label
```

### Code / Monospace

#### Code Inline
```
Font Size: 14px (0.875rem)
Line Height: 20px (1.43)
Font Weight: 400 (Regular)
Font Family: Monospace

Usage: Inline code, API references
Token: Text/CodeInline
```

#### Code Block
```
Font Size: 14px (0.875rem)
Line Height: 22px (1.57)
Font Weight: 400 (Regular)
Font Family: Monospace

Usage: Code snippets, terminal output
Token: Text/CodeBlock
```

---

## Typography Hierarchy

### Marketing Pages
```
Hero Headline:     Display (56px/Semi-bold)
Hero Subtitle:     Body Large (18px/Regular)
Section Header:    H2 (36px/Semi-bold)
Feature Title:     H3 (28px/Medium)
Body Text:         Body (16px/Regular)
CTA Button:        Body Medium (16px/Medium)
```

### Dashboard / App
```
Page Title:        H2 (36px/Semi-bold)
Section Header:    H3 (28px/Medium)
Card Title:        H4 (22px/Medium)
Body Text:         Body (16px/Regular)
Table Header:      Body Medium (16px/Medium)
Table Cell:        Body (16px/Regular)
Metadata:          Caption (14px/Regular)
```

### Forms / Modals
```
Modal Title:       H3 (28px/Medium)
Field Label:       Caption Medium (14px/Medium)
Input Text:        Body (16px/Regular)
Helper Text:       Caption (14px/Regular)
Button Label:      Body Medium (16px/Medium)
```

---

## Text Color Usage

### Light Theme
```css
Headings (H1-H4):      Text/Primary (Neutral/900)
Body Text:             Text/Secondary (Neutral/700)
Muted/Helper Text:     Text/Muted (Neutral/500)
Links:                 Text/Link (Indigo-600)
Text on Primary:       Text/OnPrimary (White)
```

### Dark Theme
```css
Headings (H1-H4):      Text/Primary (Neutral/0)
Body Text:             Text/Secondary (Neutral/200)
Muted/Helper Text:     Text/Muted (Neutral/300)
Links:                 Text/Link (Teal-400)
Text on Primary:       Text/OnPrimary (White)
```

---

## Usage Guidelines

### Do's
✅ Use Display style only once per page (hero sections)
✅ Maintain proper hierarchy (H1 → H2 → H3, no skipping)
✅ Use Medium weight for emphasis, not bold
✅ Keep line length between 50-75 characters for readability
✅ Use Caption for secondary information

### Don'ts
❌ Don't use multiple Display headings on one page
❌ Don't use weights below 400 or above 600
❌ Don't manually adjust letter spacing beyond defined tokens
❌ Don't use font sizes outside the scale
❌ Don't use all-caps except for Label style

---

## Responsive Typography

### Desktop (1024px+)
Use full type scale as defined above.

### Tablet (768px - 1023px)
```
Display:  48px → 42px
H1:       48px → 36px
H2:       36px → 28px
H3:       28px → 24px
H4:       22px → 20px
Body:     16px (unchanged)
```

### Mobile (< 768px)
```
Display:  42px → 36px
H1:       36px → 28px
H2:       28px → 24px
H3:       24px → 20px
H4:       20px → 18px
Body:     16px (unchanged)
Caption:  14px → 13px
```

---

## Implementation

### CSS Text Styles
```css
/* Display & Headings */
.text-display {
  font-size: 3.5rem;
  line-height: 1.14;
  font-weight: 600;
  letter-spacing: -0.02em;
}

.text-h1 {
  font-size: 3rem;
  line-height: 1.17;
  font-weight: 600;
  letter-spacing: -0.02em;
}

.text-h2 {
  font-size: 2.25rem;
  line-height: 1.22;
  font-weight: 600;
  letter-spacing: -0.01em;
}

.text-h3 {
  font-size: 1.75rem;
  line-height: 1.29;
  font-weight: 500;
  letter-spacing: -0.01em;
}

.text-h4 {
  font-size: 1.375rem;
  line-height: 1.36;
  font-weight: 500;
  letter-spacing: -0.005em;
}

/* Body Styles */
.text-body-large {
  font-size: 1.125rem;
  line-height: 1.56;
  font-weight: 400;
}

.text-body {
  font-size: 1rem;
  line-height: 1.5;
  font-weight: 400;
}

.text-body-medium {
  font-size: 1rem;
  line-height: 1.5;
  font-weight: 500;
}

.text-body-semibold {
  font-size: 1rem;
  line-height: 1.5;
  font-weight: 600;
}

/* Small Styles */
.text-caption {
  font-size: 0.875rem;
  line-height: 1.43;
  font-weight: 400;
}

.text-caption-medium {
  font-size: 0.875rem;
  line-height: 1.43;
  font-weight: 500;
}

.text-label {
  font-size: 0.75rem;
  line-height: 1.33;
  font-weight: 500;
  letter-spacing: 0.02em;
  text-transform: uppercase;
}

/* Code */
.text-code-inline {
  font-family: 'SF Mono', Monaco, 'Cascadia Code', Consolas, monospace;
  font-size: 0.875rem;
  line-height: 1.43;
  font-weight: 400;
}

.text-code-block {
  font-family: 'SF Mono', Monaco, 'Cascadia Code', Consolas, monospace;
  font-size: 0.875rem;
  line-height: 1.57;
  font-weight: 400;
}
```

### CSS Variables
```css
:root {
  /* Font Families */
  --font-primary: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', 
                  'Roboto', 'Helvetica Neue', Arial, sans-serif;
  --font-mono: 'SF Mono', Monaco, 'Cascadia Code', Consolas, 
               'Courier New', monospace;
  
  /* Font Sizes */
  --font-size-display: 3.5rem;
  --font-size-h1: 3rem;
  --font-size-h2: 2.25rem;
  --font-size-h3: 1.75rem;
  --font-size-h4: 1.375rem;
  --font-size-body-large: 1.125rem;
  --font-size-body: 1rem;
  --font-size-caption: 0.875rem;
  --font-size-label: 0.75rem;
  
  /* Font Weights */
  --font-weight-regular: 400;
  --font-weight-medium: 500;
  --font-weight-semibold: 600;
  
  /* Line Heights */
  --line-height-tight: 1.2;
  --line-height-normal: 1.5;
  --line-height-relaxed: 1.6;
}
```

### Tailwind Configuration
```javascript
module.exports = {
  theme: {
    fontFamily: {
      sans: ['Inter', '-apple-system', 'BlinkMacSystemFont', 'Segoe UI', 
             'Roboto', 'Helvetica Neue', 'Arial', 'sans-serif'],
      mono: ['SF Mono', 'Monaco', 'Cascadia Code', 'Consolas', 
             'Courier New', 'monospace'],
    },
    fontSize: {
      'display': ['3.5rem', { lineHeight: '1.14', letterSpacing: '-0.02em', fontWeight: '600' }],
      'h1': ['3rem', { lineHeight: '1.17', letterSpacing: '-0.02em', fontWeight: '600' }],
      'h2': ['2.25rem', { lineHeight: '1.22', letterSpacing: '-0.01em', fontWeight: '600' }],
      'h3': ['1.75rem', { lineHeight: '1.29', letterSpacing: '-0.01em', fontWeight: '500' }],
      'h4': ['1.375rem', { lineHeight: '1.36', letterSpacing: '-0.005em', fontWeight: '500' }],
      'body-large': ['1.125rem', { lineHeight: '1.56' }],
      'body': ['1rem', { lineHeight: '1.5' }],
      'caption': ['0.875rem', { lineHeight: '1.43' }],
      'label': ['0.75rem', { lineHeight: '1.33', letterSpacing: '0.02em' }],
    },
  },
}
```

---

## Accessibility

- **Minimum font size**: 14px (0.875rem) for body text
- **Line height**: Minimum 1.5 for body text ensures readability
- **Contrast ratios**: All text meets WCAG AA standards
- **Responsive scaling**: Text remains readable on all device sizes
- **Font loading**: System fonts ensure content is never invisible

---

**Last Updated**: December 2025  
**Version**: 1.0  
**Maintained by**: PS Technologies Design Team
