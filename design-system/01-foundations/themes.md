# PS Technologies Design System
## Foundations: Themes (Light + Dark)

---

### Philosophy
PS Technologies supports both light and dark themes to accommodate user preferences and different usage contexts. The themes maintain consistent brand identity while optimizing for readability and reduced eye strain.

---

## Theme Overview

### Light Theme
- **Primary Use**: Default theme, marketing pages, professional contexts
- **Background**: Light neutrals (whites and off-whites)
- **Text**: Dark neutrals for maximum contrast
- **Accent**: Indigo primary color
- **Mood**: Clean, professional, approachable

### Dark Theme
- **Primary Use**: Dashboard, late-night work, developer tools
- **Background**: Deep indigo/charcoal
- **Text**: Light neutrals
- **Accent**: Teal-shifted palette
- **Mood**: Modern, focused, reduced eye strain

---

## Light Theme Specification

### Background Colors
```css
Canvas (Body):           #F8FAFC (Neutral/50)
Card:                    #FFFFFF (Neutral/0)
Elevated/Modal:          #FFFFFF (Neutral/0)
Soft Elevated:           #F1F5F9 (Neutral/100)
Input Background:        #FFFFFF (Neutral/0)
Disabled Background:     #F1F5F9 (Neutral/100)
Code Block Background:   #F8FAFC (Neutral/50)
```

### Text Colors
```css
Primary (Headings):      #0F172A (Neutral/900)
Secondary (Body):        #334155 (Neutral/700)
Muted (Helper):          #64748B (Neutral/500)
Placeholder:             #CBD5E1 (Neutral/300)
On Primary:              #FFFFFF (Neutral/0)
Link:                    #4F46E5 (Primary/Indigo-600)
Link Hover:              #06B6D4 (Primary/Teal-400)
```

### Border Colors
```css
Subtle:                  #E2E8F0 (Neutral/200)
Strong:                  #CBD5E1 (Neutral/300)
Focus:                   #4F46E5 (Primary/Indigo-600)
Error:                   #EF4444 (Error/Red-500)
```

### Interactive Colors
```css
Primary Button BG:       linear-gradient(90deg, #4F46E5, #06B6D4)
Primary Button Text:     #FFFFFF
Secondary Button BG:     transparent
Secondary Button Border: #4F46E5
Secondary Button Text:   #4F46E5
Hover State:             Add Shadow/Glow
Active State:            Darken 10%
Disabled State:          #F1F5F9 (Neutral/100)
```

### Component Backgrounds
```css
Card:                    #FFFFFF + Shadow/Soft
Modal:                   #FFFFFF + Shadow/Large
Dropdown:                #FFFFFF + Shadow/Medium
Tooltip:                 #0F172A (Dark) with white text
Badge Solid:             #4F46E5 (Primary)
Badge Outline:           transparent
Badge Soft:              #EEF2FF (light indigo tint)
```

---

## Dark Theme Specification

### Background Colors
```css
Canvas (Body):           #0F172A (Primary/Indigo-900)
Card:                    #1E293B (Primary/Indigo-700)
Elevated/Modal:          #1E293B (Primary/Indigo-700)
Soft Elevated:           rgba(79, 70, 229, 0.1)
Input Background:        #1E293B (Primary/Indigo-700)
Disabled Background:     rgba(255, 255, 255, 0.05)
Code Block Background:   #0F172A (Primary/Indigo-900)
```

### Text Colors
```css
Primary (Headings):      #FFFFFF (Neutral/0)
Secondary (Body):        #E2E8F0 (Neutral/200)
Muted (Helper):          #CBD5E1 (Neutral/300)
Placeholder:             #64748B (Neutral/500)
On Primary:              #FFFFFF (Neutral/0)
Link:                    #06B6D4 (Primary/Teal-400)
Link Hover:              #4F46E5 (Primary/Indigo-600)
```

### Border Colors
```css
Subtle:                  rgba(226, 232, 240, 0.1)
Strong:                  rgba(226, 232, 240, 0.2)
Focus:                   #06B6D4 (Primary/Teal-400)
Error:                   #EF4444 (Error/Red-500)
```

### Interactive Colors
```css
Primary Button BG:       linear-gradient(90deg, #4F46E5, #06B6D4)
Primary Button Text:     #FFFFFF
Secondary Button BG:     transparent
Secondary Button Border: #06B6D4
Secondary Button Text:   #06B6D4
Hover State:             Add Glow/Secondary
Active State:            Lighten 10%
Disabled State:          rgba(255, 255, 255, 0.05)
```

### Component Backgrounds
```css
Card:                    #1E293B + Shadow/Soft (subtle)
Modal:                   #1E293B + Shadow/Large
Dropdown:                #1E293B + Shadow/Medium
Tooltip:                 #334155 with white text
Badge Solid:             #06B6D4 (Teal)
Badge Outline:           transparent
Badge Soft:              rgba(6, 182, 212, 0.15)
```

---

## Theme Comparison Table

| Element                | Light Theme           | Dark Theme            |
|------------------------|-----------------------|-----------------------|
| **Body Background**    | #F8FAFC              | #0F172A              |
| **Card Background**    | #FFFFFF              | #1E293B              |
| **Primary Text**       | #0F172A              | #FFFFFF              |
| **Secondary Text**     | #334155              | #E2E8F0              |
| **Muted Text**         | #64748B              | #CBD5E1              |
| **Border Subtle**      | #E2E8F0              | rgba(226,232,240,0.1)|
| **Link Color**         | #4F46E5              | #06B6D4              |
| **Focus Ring**         | #4F46E5              | #06B6D4              |
| **Primary Button**     | Gradient             | Gradient             |
| **Secondary Border**   | #4F46E5              | #06B6D4              |
| **Shadow Intensity**   | Medium               | Subtle               |

---

## Semantic Colors (Both Themes)

These remain consistent across themes with adjusted opacity:

### Success
```css
Light: #22C55E (Green-500)
Dark:  #22C55E (Green-500)
Background Light: #F0FDF4
Background Dark:  rgba(34, 197, 94, 0.15)
```

### Warning
```css
Light: #F59E0B (Amber-500)
Dark:  #F59E0B (Amber-500)
Background Light: #FFFBEB
Background Dark:  rgba(245, 158, 11, 0.15)
```

### Error
```css
Light: #EF4444 (Red-500)
Dark:  #EF4444 (Red-500)
Background Light: #FEF2F2
Background Dark:  rgba(239, 68, 68, 0.15)
```

### Info
```css
Light: #3B82F6 (Blue-500)
Dark:  #3B82F6 (Blue-500)
Background Light: #EFF6FF
Background Dark:  rgba(59, 130, 246, 0.15)
```

---

## Visual Examples

### Example 1: Marketing Hero

**Light Theme:**
```
Background:   #F8FAFC (Canvas)
Card:         #FFFFFF with Shadow/Soft
Headline:     #0F172A (Display style)
Subheadline:  #334155 (Body Large)
Primary CTA:  Gradient button
Secondary:    Outline button (#4F46E5)
```

**Dark Theme:**
```
Background:   #0F172A (Canvas)
Card:         #1E293B with subtle shadow
Headline:     #FFFFFF (Display style)
Subheadline:  #E2E8F0 (Body Large)
Primary CTA:  Gradient button
Secondary:    Outline button (#06B6D4)
```

### Example 2: Dashboard Card

**Light Theme:**
```
Card BG:      #FFFFFF
Title:        #0F172A (H4)
Body Text:    #334155 (Body)
Metadata:     #64748B (Caption)
Border:       #E2E8F0
Icon:         #4F46E5
```

**Dark Theme:**
```
Card BG:      #1E293B
Title:        #FFFFFF (H4)
Body Text:    #E2E8F0 (Body)
Metadata:     #CBD5E1 (Caption)
Border:       rgba(226, 232, 240, 0.1)
Icon:         #06B6D4
```

### Example 3: Form Input

**Light Theme:**
```
Background:   #FFFFFF
Border:       #E2E8F0
Text:         #0F172A
Placeholder:  #CBD5E1
Label:        #334155
Focus Border: #4F46E5
Focus Ring:   rgba(79, 70, 229, 0.12)
```

**Dark Theme:**
```
Background:   #1E293B
Border:       rgba(226, 232, 240, 0.1)
Text:         #FFFFFF
Placeholder:  #64748B
Label:        #E2E8F0
Focus Border: #06B6D4
Focus Ring:   rgba(6, 182, 212, 0.20)
```

---

## Implementation

### CSS Variables (Complete Theme System)

```css
:root {
  /* Light Theme (Default) */
  --theme-bg-canvas: #F8FAFC;
  --theme-bg-card: #FFFFFF;
  --theme-bg-elevated: #FFFFFF;
  --theme-bg-soft: #F1F5F9;
  --theme-bg-input: #FFFFFF;
  --theme-bg-disabled: #F1F5F9;
  --theme-bg-code: #F8FAFC;
  
  --theme-text-primary: #0F172A;
  --theme-text-secondary: #334155;
  --theme-text-muted: #64748B;
  --theme-text-placeholder: #CBD5E1;
  --theme-text-on-primary: #FFFFFF;
  --theme-text-link: #4F46E5;
  --theme-text-link-hover: #06B6D4;
  
  --theme-border-subtle: #E2E8F0;
  --theme-border-strong: #CBD5E1;
  --theme-border-focus: #4F46E5;
  
  --theme-accent-primary: #4F46E5;
  --theme-accent-secondary: #06B6D4;
  --theme-gradient: linear-gradient(90deg, #4F46E5 0%, #06B6D4 100%);
  
  --theme-shadow-soft: 0px 1px 2px rgba(15, 23, 42, 0.05),
                       0px 1px 3px rgba(15, 23, 42, 0.10);
  --theme-shadow-medium: 0px 4px 6px rgba(15, 23, 42, 0.05),
                         0px 10px 15px rgba(15, 23, 42, 0.10);
}

/* Dark Theme Override */
[data-theme="dark"] {
  --theme-bg-canvas: #0F172A;
  --theme-bg-card: #1E293B;
  --theme-bg-elevated: #1E293B;
  --theme-bg-soft: rgba(79, 70, 229, 0.1);
  --theme-bg-input: #1E293B;
  --theme-bg-disabled: rgba(255, 255, 255, 0.05);
  --theme-bg-code: #0F172A;
  
  --theme-text-primary: #FFFFFF;
  --theme-text-secondary: #E2E8F0;
  --theme-text-muted: #CBD5E1;
  --theme-text-placeholder: #64748B;
  --theme-text-on-primary: #FFFFFF;
  --theme-text-link: #06B6D4;
  --theme-text-link-hover: #4F46E5;
  
  --theme-border-subtle: rgba(226, 232, 240, 0.1);
  --theme-border-strong: rgba(226, 232, 240, 0.2);
  --theme-border-focus: #06B6D4;
  
  --theme-accent-primary: #06B6D4;
  --theme-accent-secondary: #4F46E5;
  --theme-gradient: linear-gradient(90deg, #4F46E5 0%, #06B6D4 100%);
  
  --theme-shadow-soft: 0px 1px 2px rgba(0, 0, 0, 0.2),
                       0px 1px 3px rgba(0, 0, 0, 0.3);
  --theme-shadow-medium: 0px 4px 6px rgba(0, 0, 0, 0.2),
                         0px 10px 15px rgba(0, 0, 0, 0.3);
}
```

### Theme Switching Script

```javascript
// Theme toggle functionality
const themeToggle = () => {
  const currentTheme = document.documentElement.getAttribute('data-theme');
  const newTheme = currentTheme === 'dark' ? 'light' : 'dark';
  
  document.documentElement.setAttribute('data-theme', newTheme);
  localStorage.setItem('theme', newTheme);
};

// Apply saved theme on load
const savedTheme = localStorage.getItem('theme') || 'light';
document.documentElement.setAttribute('data-theme', savedTheme);

// Respect system preference if no saved theme
if (!localStorage.getItem('theme')) {
  const prefersDark = window.matchMedia('(prefers-color-scheme: dark)').matches;
  if (prefersDark) {
    document.documentElement.setAttribute('data-theme', 'dark');
  }
}
```

### React Theme Provider

```typescript
import { createContext, useContext, useEffect, useState } from 'react';

type Theme = 'light' | 'dark';

const ThemeContext = createContext<{
  theme: Theme;
  toggleTheme: () => void;
}>({ theme: 'light', toggleTheme: () => {} });

export const ThemeProvider = ({ children }: { children: React.ReactNode }) => {
  const [theme, setTheme] = useState<Theme>('light');

  useEffect(() => {
    const saved = localStorage.getItem('theme') as Theme;
    if (saved) {
      setTheme(saved);
      document.documentElement.setAttribute('data-theme', saved);
    } else {
      const prefersDark = window.matchMedia('(prefers-color-scheme: dark)').matches;
      const initial = prefersDark ? 'dark' : 'light';
      setTheme(initial);
      document.documentElement.setAttribute('data-theme', initial);
    }
  }, []);

  const toggleTheme = () => {
    const newTheme = theme === 'dark' ? 'light' : 'dark';
    setTheme(newTheme);
    localStorage.setItem('theme', newTheme);
    document.documentElement.setAttribute('data-theme', newTheme);
  };

  return (
    <ThemeContext.Provider value={{ theme, toggleTheme }}>
      {children}
    </ThemeContext.Provider>
  );
};

export const useTheme = () => useContext(ThemeContext);
```

---

## Usage Guidelines

### Do's
✅ Respect user's system preference by default
✅ Persist theme choice in localStorage
✅ Provide clear theme toggle UI
✅ Test all components in both themes
✅ Ensure sufficient contrast in both themes

### Don'ts
❌ Don't hard-code colors — always use theme tokens
❌ Don't assume users want dark theme at night
❌ Don't use theme as the only differentiator for state
❌ Don't forget to test images/illustrations in dark theme
❌ Don't make theme switching jarring (use transitions)

---

## Accessibility

- **Contrast ratios**: Meet WCAG AA (4.5:1) in both themes
- **Focus indicators**: Clearly visible in both themes
- **Preference respect**: Honor `prefers-color-scheme`
- **Reduced motion**: Smooth theme transitions with `prefers-reduced-motion`
- **Color independence**: Don't rely on color alone for meaning

---

**Last Updated**: December 2025  
**Version**: 1.0  
**Maintained by**: PS Technologies Design Team
