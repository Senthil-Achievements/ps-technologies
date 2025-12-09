# PS Technologies Design System
## Patterns: Marketing Pages

---

## Overview
Marketing patterns create compelling, conversion-focused experiences for landing pages, product pages, and promotional content.

---

## Hero Section

### Standard Hero
```
┌────────────────────────────────────────────────────┐
│ [Logo]  Home  Product  Pricing      [Get Started] │
├────────────────────────────────────────────────────┤
│                                                    │
│                                                    │
│      Transform Your Workflow                      │
│      with AI-Powered Tools                        │
│                                                    │
│   Build, launch, and scale your business with     │
│   PS Technologies' intelligent automation          │
│                                                    │
│   [Start Free Trial]  [Watch Demo →]              │
│                                                    │
│                                        [Product    │
│                                         Screenshot]│
└────────────────────────────────────────────────────┘
```

**Specifications**:
```css
Min Height: 600px
Background: linear-gradient(135deg, #0F172A 0%, #1E293B 100%)
             with subtle pattern overlay
Padding: 80px 40px (Space/80 Space/40)
Text Align: center (or left for split layout)

Headline:
  Font: Display (56px, Semi-bold)
  Color: #FFFFFF
  Max Width: 800px
  Margin: 0 auto 24px
  Line Height: 1.1
  
Subheadline:
  Font: Body Large (18px, Regular)
  Color: rgba(255, 255, 255, 0.8)
  Max Width: 600px
  Margin: 0 auto 40px
  
CTA Buttons:
  Display: flex
  Gap: 16px (Space/16)
  Justify Content: center
  
Product Visual:
  Max Width: 900px
  Margin: 60px auto 0
  Border Radius: 16px (Radius/LG)
  Box Shadow: var(--shadow-xl)
```

### Split Hero (Image Right)
```
┌──────────────────────────────────────────┐
│ [Logo] Nav Items      [Get Started]     │
├──────────────────┬───────────────────────┤
│                  │                       │
│ Transform Your   │                       │
│ Workflow         │    [Product           │
│                  │     Screenshot/       │
│ Description...   │     Illustration]     │
│                  │                       │
│ [Start Free]     │                       │
│ [Watch Demo]     │                       │
│                  │                       │
└──────────────────┴───────────────────────┘
```

---

## Social Proof Section

```
┌────────────────────────────────────────────────────┐
│                                                    │
│        Trusted by 10,000+ companies worldwide      │
│                                                    │
│   [Logo] [Logo] [Logo] [Logo] [Logo] [Logo]       │
│                                                    │
└────────────────────────────────────────────────────┘
```

**Specifications**:
```css
Padding: 60px 40px (Space/60 Space/40)
Background: var(--bg-soft)
Text Align: center

Headline:
  Font: Caption/Medium (14px, 500)
  Color: var(--text-muted)
  Text Transform: Uppercase
  Letter Spacing: 0.1em
  Margin Bottom: 32px
  
Logo Grid:
  Display: flex
  Justify Content: center
  Align Items: center
  Gap: 48px (Space/48)
  Flex Wrap: wrap
  
  Logos:
    Height: 32px
    Width: auto
    Filter: grayscale(100%)
    Opacity: 0.6
    Transition: all 0.3s
    
    Hover:
      Filter: grayscale(0%)
      Opacity: 1
```

---

## Features Section

### 3-Column Features
```
┌────────────────────────────────────────────────────┐
│                                                    │
│           Powerful features for modern teams       │
│                                                    │
│   Everything you need to build, ship, and scale   │
│                                                    │
├────────────┬────────────┬────────────────────────┤
│            │            │                        │
│   [🚀]     │   [⚡]     │   [🔒]                │
│            │            │                        │
│ Lightning  │  Real-time │  Enterprise           │
│ Fast       │  Sync      │  Security             │
│            │            │                        │
│ Description│Description │Description            │
│ text here  │text here   │text here              │
│            │            │                        │
│ Learn more→│Learn more→ │Learn more→            │
│            │            │                        │
└────────────┴────────────┴────────────────────────┘
```

**Specifications**:
```css
Padding: 96px 40px (Space/96 Space/40)
Background: var(--theme-bg-canvas)

Section Header:
  Text Align: center
  Max Width: 800px
  Margin: 0 auto 64px
  
  Title:
    Font: H2 (36px, Semi-bold)
    Margin Bottom: 16px
    
  Description:
    Font: Body Large (18px)
    Color: var(--text-secondary)
    
Features Grid:
  Display: grid
  Grid Template Columns: repeat(auto-fit, minmax(300px, 1fr))
  Gap: 40px (Space/40)
  Max Width: 1200px
  Margin: 0 auto
  
Feature Card:
  Text Align: center
  Padding: 32px (Space/32)
  
  Icon:
    Width: 48px
    Height: 48px
    Margin: 0 auto 20px
    Background: linear-gradient(135deg, #4F46E5, #06B6D4)
    Border Radius: 12px
    Display: flex
    Align Items: center
    Justify Content: center
    
  Title:
    Font: H4 (22px, Medium)
    Margin Bottom: 12px
    
  Description:
    Font: Body (16px)
    Color: var(--text-secondary)
    Line Height: 1.6
    Margin Bottom: 16px
    
  Link:
    Font: Body/Medium (16px, 500)
    Color: var(--accent-primary)
    Display: inline-flex
    Align Items: center
    Gap: 6px
```

### Feature with Screenshot
```
┌────────────────────────────────────────────────────┐
│                                                    │
│ ┌──────────────────┐  ┌──────────────────────┐   │
│ │                  │  │                      │   │
│ │  [Screenshot]    │  │  AI-Powered Tools    │   │
│ │                  │  │                      │   │
│ │                  │  │  Description of the  │   │
│ │                  │  │  feature with key    │   │
│ │                  │  │  benefits...         │   │
│ │                  │  │                      │   │
│ │                  │  │  • Benefit 1         │   │
│ │                  │  │  • Benefit 2         │   │
│ │                  │  │  • Benefit 3         │   │
│ │                  │  │                      │   │
│ └──────────────────┘  │  [Learn More →]      │   │
│                       └──────────────────────┘   │
│                                                    │
└────────────────────────────────────────────────────┘
```

**Alternating Layout**: Image left, then image right

---

## Pricing Section

### 3-Tier Pricing
```
┌────────────────────────────────────────────────────┐
│                                                    │
│              Choose your plan                      │
│       Flexible pricing for teams of all sizes     │
│                                                    │
├────────────┬────────────┬────────────────────────┤
│            │            │                        │
│ STARTER    │ PROFESSIONAL│  ENTERPRISE           │
│            │   POPULAR  │                        │
│ $29/month  │ $79/month  │  Custom                │
│            │            │                        │
│ ✓ Feature  │ Everything │ Everything            │
│ ✓ Feature  │   in       │   in Pro              │
│ ✓ Feature  │  Starter   │                        │
│ ✗ Feature  │ ✓ Feature  │ ✓ Feature             │
│ ✗ Feature  │ ✓ Feature  │ ✓ Feature             │
│            │ ✓ Feature  │ ✓ Feature             │
│            │            │ ✓ Priority             │
│            │            │   Support              │
│            │            │                        │
│[Get Started]│[Get Started]│[Contact Sales]       │
│            │            │                        │
└────────────┴────────────┴────────────────────────┘
```

**Specifications**:
```css
Padding: 96px 40px (Space/96 Space/40)
Background: var(--bg-soft)

Pricing Grid:
  Display: grid
  Grid Template Columns: repeat(auto-fit, minmax(300px, 1fr))
  Gap: 32px (Space/32)
  Max Width: 1200px
  Margin: 0 auto
  
Pricing Card:
  Background: var(--theme-bg-card)
  Border: 2px solid var(--border-subtle)
  Border Radius: 16px (Radius/LG)
  Padding: 40px (Space/40)
  Text Align: center
  Position: relative
  Transition: transform 0.3s, box-shadow 0.3s
  
  Hover:
    Transform: translateY(-4px)
    Box Shadow: var(--shadow-large)
    
Popular Badge:
  Position: absolute
  Top: -12px
  Left: 50%
  Transform: translateX(-50%)
  Background: var(--accent-gradient)
  Color: #FFFFFF
  Padding: 6px 16px
  Border Radius: 20px
  Font: Label (12px, Semi-bold)
  
Plan Name:
  Font: Label (12px, Uppercase)
  Color: var(--text-muted)
  Margin Bottom: 16px
  
Price:
  Font: H2 (36px, Semi-bold)
  Margin Bottom: 8px
  
  Per Month:
    Font: Caption (14px)
    Color: var(--text-muted)
    Font Weight: Regular
    
Features List:
  Text Align: left
  Margin: 32px 0
  
  Feature:
    Display: flex
    Align Items: flex-start
    Gap: 10px
    Margin Bottom: 12px
    Font: Body (16px)
    
    Icon:
      Width: 20px
      Height: 20px
      Color: var(--color-success) or var(--text-muted)
      Flex Shrink: 0
```

---

## CTA Section

```
┌────────────────────────────────────────────────────┐
│                                                    │
│                                                    │
│        Ready to transform your workflow?           │
│                                                    │
│   Join 10,000+ companies using PS Technologies     │
│                                                    │
│   [Start Free Trial]    [Schedule Demo]            │
│                                                    │
│   No credit card required • 14-day free trial      │
│                                                    │
│                                                    │
└────────────────────────────────────────────────────┘
```

**Specifications**:
```css
Padding: 96px 40px (Space/96 Space/40)
Background: linear-gradient(135deg, #4F46E5, #06B6D4)
Color: #FFFFFF
Text Align: center

Headline:
  Font: H2 (36px, Semi-bold)
  Margin Bottom: 16px
  
Description:
  Font: Body Large (18px)
  Opacity: 0.9
  Margin Bottom: 40px
  
CTA Buttons:
  Display: flex
  Justify Content: center
  Gap: 16px
  Margin Bottom: 24px
  
Fine Print:
  Font: Caption (14px)
  Opacity: 0.8
```

---

## Testimonials Section

```
┌────────────────────────────────────────────────────┐
│                                                    │
│         What our customers are saying              │
│                                                    │
├────────────┬────────────┬────────────────────────┤
│            │            │                        │
│ "Amazing   │ "Best tool │ "Game changer         │
│  platform  │  we've     │  for our              │
│  for our   │  used!"    │  team!"               │
│  team."    │            │                        │
│            │ Description│ Description           │
│ [Avatar]   │            │                        │
│ Name       │ [Avatar]   │ [Avatar]              │
│ Title      │ Name       │ Name                  │
│            │ Title      │ Title                 │
└────────────┴────────────┴────────────────────────┘
```

**Testimonial Card**:
```css
Background: var(--theme-bg-card)
Border: 1px solid var(--border-subtle)
Border Radius: 12px (Radius/MD)
Padding: 32px (Space/32)
Box Shadow: var(--shadow-soft)

Quote:
  Font: Body Large (18px)
  Color: var(--text-primary)
  Line Height: 1.6
  Margin Bottom: 24px
  Font Style: italic
  
Author:
  Display: flex
  Align Items: center
  Gap: 12px
  
  Avatar:
    Width: 48px
    Height: 48px
    Border Radius: 50%
    
  Name:
    Font: Body/Medium (16px, 500)
    
  Title:
    Font: Caption (14px)
    Color: var(--text-muted)
```

---

## FAQ Section

```
┌────────────────────────────────────────────────────┐
│                                                    │
│          Frequently Asked Questions                │
│                                                    │
│ ┌────────────────────────────────────────────┐   │
│ │ What is PS Technologies?              [▾] │   │
│ └────────────────────────────────────────────┘   │
│                                                    │
│ ┌────────────────────────────────────────────┐   │
│ │ How does pricing work?                [▾] │   │
│ │ ────────────────────────────────────────   │   │
│ │ Detailed answer explaining pricing...      │   │
│ └────────────────────────────────────────────┘   │
│                                                    │
│ ┌────────────────────────────────────────────┐   │
│ │ Can I cancel anytime?                 [▾] │   │
│ └────────────────────────────────────────────┘   │
│                                                    │
└────────────────────────────────────────────────────┘
```

**Accordion Item**:
```css
Background: var(--theme-bg-card)
Border: 1px solid var(--border-subtle)
Border Radius: 12px (Radius/MD)
Margin Bottom: 12px
Transition: all 0.3s

Question:
  Display: flex
  Justify Content: space-between
  Align Items: center
  Padding: 20px 24px
  Font: Body/Medium (16px, 500)
  Cursor: pointer
  
  Icon:
    Transition: transform 0.3s
    Transform: rotate(0deg) when closed
              rotate(180deg) when open
              
Answer:
  Padding: 0 24px 20px
  Font: Body (16px)
  Color: var(--text-secondary)
  Line Height: 1.6
  Display: none when closed
          block when open
```

---

## Footer

```
┌────────────────────────────────────────────────────┐
│                                                    │
│ [Logo]                                             │
│ PS Technologies                                    │
│ Building the future of work                        │
│                                                    │
│ Product      Company      Resources    Legal      │
│ Features     About        Blog         Privacy    │
│ Pricing      Careers      Docs         Terms      │
│ Integrations Contact      Support      Cookies    │
│                                                    │
│ ────────────────────────────────────────────────   │
│                                                    │
│ © 2025 PS Technologies. All rights reserved.      │
│                                                    │
│ [Twitter] [LinkedIn] [GitHub]                      │
│                                                    │
└────────────────────────────────────────────────────┘
```

**Specifications**:
```css
Padding: 64px 40px 32px (Space/64 Space/40 Space/32)
Background: var(--theme-bg-card)
Border Top: 1px solid var(--border-subtle)

Top Section:
  Display: grid
  Grid Template Columns: 2fr repeat(4, 1fr)
  Gap: 48px (Space/48)
  Margin Bottom: 48px
  
  @media (max-width: 768px) {
    Grid Template Columns: 1fr
  }
  
Brand Column:
  Logo:
    Height: 32px
    Margin Bottom: 16px
    
  Tagline:
    Font: Body (16px)
    Color: var(--text-secondary)
    
Link Columns:
  Heading:
    Font: Body/Semi-bold (16px, 600)
    Margin Bottom: 16px
    
  Links:
    Display: flex
    Flex Direction: column
    Gap: 10px
    
    Link:
      Font: Body (16px)
      Color: var(--text-muted)
      Transition: color 0.2s
      
      Hover:
        Color: var(--accent-primary)
        
Bottom Section:
  Display: flex
  Justify Content: space-between
  Align Items: center
  Padding Top: 32px
  Border Top: 1px solid var(--border-subtle)
  
  Copyright:
    Font: Caption (14px)
    Color: var(--text-muted)
    
  Social Links:
    Display: flex
    Gap: 16px
```

---

## Responsive Patterns

### Mobile (<768px)
```
- Stack hero sections vertically
- Single column feature grids
- Simplified pricing cards (1 column)
- Simplified footer (1 column)
- Smaller font sizes (refer to typography responsive scale)
- Reduced spacing
```

### Tablet (768px - 1023px)
```
- 2-column feature grids
- 2-column pricing
- Adjusted spacing
```

---

## Accessibility

✅ **Semantic HTML**: Proper heading hierarchy
✅ **Alt Text**: Descriptive alt text for all images
✅ **Contrast**: Meet WCAG AA standards
✅ **Keyboard Navigation**: All interactive elements accessible
✅ **ARIA Labels**: Clear labels for screen readers
✅ **Focus Indicators**: Visible focus states

---

## Performance

✅ Lazy load images below fold
✅ Optimize hero images (WebP format)
✅ Minimize animation on scroll
✅ Use CSS transforms for better performance
✅ Defer non-critical JavaScript

---

**Last Updated**: December 2025  
**Version**: 1.0  
**Maintained by**: PS Technologies Design Team
