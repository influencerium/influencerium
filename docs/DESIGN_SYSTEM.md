# Influencerium Design System

**Design System and Brand Guidelines**

---

## 📋 Table of Contents

1. [Overview](#overview)
2. [Color Palette](#color-palette)
3. [Typography](#typography)
4. [Spacing & Layout](#spacing--layout)
5. [Components](#components)
6. [Icons](#icons)
7. [Accessibility](#accessibility)

---

## 🎨 Overview

The Influencerium Design System provides a comprehensive set of guidelines, components, and patterns for building consistent, accessible, and beautiful user interfaces across all platforms.

### Design Principles

1. **Clarity** - Clear communication through intuitive design
2. **Consistency** - Unified experience across all touchpoints
3. **Accessibility** - Inclusive design for all users
4. **Simplicity** - Minimal, focused interfaces
5. **Efficiency** - Fast, responsive interactions

---

## 🎭 Color Palette

### Primary Colors

| Color | Hex | RGB | Usage |
|-------|-----|-----|-------|
| **Black** | #000000 | 0, 0, 0 | Primary text, headers |
| **White** | #FFFFFF | 255, 255, 255 | Backgrounds, cards |
| **Dark Gray** | #333333 | 51, 51, 51 | Secondary text |
| **Light Gray** | #F5F5F5 | 245, 245, 245 | Backgrounds, borders |

### Accent Colors

| Color | Hex | RGB | Usage |
|-------|-----|-----|-------|
| **Blue** | #0066CC | 0, 102, 204 | Links, CTAs, primary actions |
| **Green** | #10B981 | 16, 185, 129 | Success, positive actions |
| **Red** | #EF4444 | 239, 68, 68 | Errors, destructive actions |
| **Yellow** | #F59E0B | 245, 158, 11 | Warnings, alerts |

### Semantic Colors

```css
/* Success */
--color-success: #10B981;
--color-success-light: #D1FAE5;
--color-success-dark: #065F46;

/* Error */
--color-error: #EF4444;
--color-error-light: #FEE2E2;
--color-error-dark: #7F1D1D;

/* Warning */
--color-warning: #F59E0B;
--color-warning-light: #FEF3C7;
--color-warning-dark: #92400E;

/* Info */
--color-info: #0066CC;
--color-info-light: #DBEAFE;
--color-info-dark: #1E40AF;
```

---

## 🔤 Typography

### Font Family

```css
/* Primary Font */
--font-primary: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;

/* Monospace Font */
--font-monospace: 'Courier New', Courier, monospace;
```

### Font Sizes

| Size | Pixels | Usage |
|------|--------|-------|
| **H1** | 32px | Page titles |
| **H2** | 28px | Section headers |
| **H3** | 24px | Subsection headers |
| **H4** | 20px | Small headers |
| **Body** | 16px | Regular text |
| **Small** | 14px | Secondary text |
| **Tiny** | 12px | Labels, captions |

### Font Weights

| Weight | Value | Usage |
|--------|-------|-------|
| **Light** | 300 | Subtle text |
| **Regular** | 400 | Body text |
| **Medium** | 500 | Emphasis |
| **Semibold** | 600 | Headers |
| **Bold** | 700 | Strong emphasis |

### Line Heights

```css
--line-height-tight: 1.2;
--line-height-normal: 1.5;
--line-height-relaxed: 1.75;
--line-height-loose: 2;
```

---

## 📐 Spacing & Layout

### Spacing Scale

```css
--spacing-xs: 4px;
--spacing-sm: 8px;
--spacing-md: 16px;
--spacing-lg: 24px;
--spacing-xl: 32px;
--spacing-2xl: 48px;
--spacing-3xl: 64px;
--spacing-4xl: 96px;
```

### Grid System

- **Grid Columns:** 12 columns
- **Gutter:** 16px
- **Max Width:** 1200px
- **Breakpoints:**
  - Mobile: 320px - 640px
  - Tablet: 641px - 1024px
  - Desktop: 1025px+

### Responsive Breakpoints

```css
/* Mobile First */
--breakpoint-sm: 640px;
--breakpoint-md: 768px;
--breakpoint-lg: 1024px;
--breakpoint-xl: 1280px;
--breakpoint-2xl: 1536px;
```

---

## 🧩 Components

### Buttons

#### Primary Button
- Background: #0066CC
- Text: White
- Padding: 12px 24px
- Border Radius: 6px
- Font Weight: 600

#### Secondary Button
- Background: #F5F5F5
- Text: #000000
- Padding: 12px 24px
- Border Radius: 6px
- Font Weight: 600

#### Danger Button
- Background: #EF4444
- Text: White
- Padding: 12px 24px
- Border Radius: 6px
- Font Weight: 600

### Input Fields

- Height: 40px
- Padding: 8px 12px
- Border: 1px solid #CCCCCC
- Border Radius: 6px
- Font Size: 16px
- Focus: Blue border (#0066CC)

### Cards

- Background: White
- Border Radius: 8px
- Box Shadow: 0 2px 4px rgba(0,0,0,0.1)
- Padding: 16px
- Margin Bottom: 16px

### Navigation

- Height: 64px
- Background: #000000
- Text: White
- Font Size: 16px
- Font Weight: 600

---

## 🎯 Icons

### Icon System

- **Size:** 24px (standard), 16px (small), 32px (large)
- **Stroke Width:** 2px
- **Color:** Inherit from text color
- **Library:** Feather Icons or similar

### Common Icons

- Menu (hamburger)
- Search (magnifying glass)
- User (person)
- Settings (gear)
- Logout (exit)
- Home (house)
- Bell (notifications)
- Message (chat)
- Heart (favorite)
- Star (rating)

---

## ♿ Accessibility

### WCAG 2.1 Compliance

- **Level:** AA (minimum)
- **Color Contrast:** 4.5:1 for text, 3:1 for graphics
- **Focus Indicators:** Visible on all interactive elements
- **Keyboard Navigation:** Full support

### Accessibility Guidelines

1. **Color Contrast**
   - Text: Minimum 4.5:1 ratio
   - Graphics: Minimum 3:1 ratio
   - Large text: Minimum 3:1 ratio

2. **Focus Management**
   - Visible focus indicators
   - Logical tab order
   - Focus trap in modals

3. **Semantic HTML**
   - Proper heading hierarchy
   - Semantic elements (nav, main, article, etc.)
   - ARIA labels where needed

4. **Motion & Animation**
   - Respect `prefers-reduced-motion`
   - No auto-playing videos
   - No flashing content

5. **Text Alternatives**
   - Alt text for images
   - Captions for videos
   - Transcripts for audio

---

## 📱 Responsive Design

### Mobile First Approach

- Design for mobile first
- Enhance for larger screens
- Test on real devices
- Touch targets: Minimum 44x44px

### Responsive Patterns

- Stacked layout on mobile
- 2-column on tablet
- 3+ column on desktop
- Flexible images and text

---

## 🎨 Usage Examples

### Button Usage

```html
<!-- Primary Button -->
<button class="btn btn-primary">Click Me</button>

<!-- Secondary Button -->
<button class="btn btn-secondary">Cancel</button>

<!-- Danger Button -->
<button class="btn btn-danger">Delete</button>
```

### Card Usage

```html
<div class="card">
  <h3>Card Title</h3>
  <p>Card content goes here</p>
</div>
```

### Input Usage

```html
<input type="text" class="input" placeholder="Enter text">
```

---

## 📞 Support

For design system questions:
- **GitHub:** https://github.com/influencerium/influencerium
- **Email:** support@influencerium.com

---

**Last Updated:** December 24, 2025  
**Version:** 1.0.0  
**Status:** ✅ Complete
