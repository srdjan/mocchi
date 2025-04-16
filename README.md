# sem-mochi

**A Semantic-First Modern CSS Framework with Minimal Class Usage**

![sem-mochi logo](https://via.placeholder.com/1200x300/3b82f6/ffffff?text=sem-mochi)

sem-mochi is a modern CSS framework designed around the principle of semantic markup, focusing on styling native HTML elements directly while minimizing class usage. It leverages advanced CSS features and selectors to create a highly maintainable styling approach that prioritizes the inherent semantic meaning of HTML elements.

## Table of Contents

- [Overview](#overview)
- [Key Features](#key-features)
- [Installation](#installation)
- [Architecture](#architecture)
- [Usage Guide](#usage-guide)
  - [Typography](#typography)
  - [Buttons](#buttons)
  - [Forms](#forms)
  - [Cards](#cards)
  - [Navigation](#navigation)
  - [Layout](#layout)
  - [Themes](#themes)
  - [Utilities](#utilities)
- [Customization](#customization)
- [Browser Support](#browser-support)
- [Philosophy](#philosophy)
- [Contributing](#contributing)
- [License](#license)

## Overview

sem-mochi takes a fundamentally different approach to CSS frameworks. Instead of requiring numerous utility classes or component classes, it styles native HTML elements directly and uses attributes for variations. This results in cleaner, more semantic HTML that's easier to maintain and more accessible by default.

```html
<!-- Traditional CSS framework -->
<button class="btn btn-primary btn-lg">Submit</button>

<!-- sem-mochi approach -->
<button primary>Submit</button>
```

## Key Features

- **Semantic-First Approach**: Style native HTML elements directly with minimal class usage
- **Attribute-Based Variations**: Uses HTML attributes instead of classes for component variations
- **Modular Architecture**: Organized into logical modules for better maintainability
- **HSL-Based Color System**: Programmatically generated color palette for consistent theming
- **Component-Specific Custom Properties**: Better encapsulation and customization
- **Enhanced Accessibility**: Robust keyboard navigation and focus management
- **Comprehensive Animation System**: Consistent timing functions and animations
- **Improved Layout System**: Flexible grid and container components
- **Container Query Support**: For component-level responsive design
- **Dark Mode & High Contrast Themes**: Built-in accessibility features
- **Modern CSS Features**: Leverages CSS nesting, logical properties, and advanced selectors
- **Performance Optimized**: Uses CSS containment and content-visibility

## Installation

### Option 1: CDN (Coming Soon)

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/sem-mochi@latest/dist/sem-mochi.min.css">
```

### Option 2: NPM (Coming Soon)

```bash
npm install sem-mochi
```

Then import in your JavaScript:

```javascript
import 'sem-mochi/dist/sem-mochi.min.css';
```

### Option 3: Download

Download the latest release from the [releases page](https://github.com/sem-mochi/sem-mochi/releases) and include it in your project:

```html
<link rel="stylesheet" href="path/to/sem-mochi.css">
```

## Architecture

sem-mochi is structured using CSS cascade layers for explicit specificity control:

```css
@layer tokens, theme, base, elements, components, layout, states, utilities, queries;
```

This layered approach enables predictable styling without specificity conflicts, allowing for:

- Clear separation of concerns
- Deterministic cascade application
- Isolated styling contexts

### File Structure

```
src/
├── tokens/
│   ├── _colors.css       /* Color system and semantic tokens */
│   ├── _typography.css   /* Font families, sizes, and scales */
│   ├── _spacing.css      /* Spacing system and layout tokens */
│   └── _effects.css      /* Shadows, animations, and effects */
├── themes/
│   ├── _light.css        /* Light theme variables */
│   ├── _dark.css         /* Dark theme variables */
│   └── _high-contrast.css /* High contrast theme for accessibility */
├── base/
│   ├── _reset.css        /* Modern CSS reset */
│   └── _elements.css     /* Base element styling */
├── components/
│   ├── _buttons.css      /* Button components and variations */
│   ├── _cards.css        /* Card components and variations */
│   ├── _navigation.css   /* Navigation components */
│   └── ...               /* Other components */
├── layout/
│   ├── _container.css    /* Container components */
│   ├── _grid.css         /* Grid system */
│   └── ...               /* Other layout components */
├── utilities/
│   ├── _accessibility.css /* Accessibility utilities */
│   ├── _animations.css    /* Animation utilities */
│   └── ...                /* Other utilities */
└── sem-mochi.css         /* Main entry file */
```

## Usage Guide

### Typography

sem-mochi provides a comprehensive typography system with fluid sizing and proper vertical rhythm.

```html
<h1>Main Heading</h1>
<p>Regular paragraph text with <em>emphasis</em> and <strong>strong importance</strong>.</p>
<h2>Secondary Heading</h2>
<p>Another paragraph with <a href="#">a link</a> inside it.</p>
<blockquote>
  <p>This is a blockquote with a citation.</p>
  <cite>— Author Name</cite>
</blockquote>
```

#### Text Variations

```html
<p class="text-sm">Small text for less emphasis</p>
<p class="text-lg">Larger text for more emphasis</p>
<p class="text-center">Centered text</p>
<p class="text-muted">Muted text with reduced emphasis</p>
```

### Buttons

Buttons use attributes for variations instead of classes:

```html
<!-- Button variations -->
<button>Default Button</button>
<button primary>Primary Button</button>
<button secondary>Secondary Button</button>
<button outline>Outline Button</button>
<button ghost>Ghost Button</button>

<!-- Semantic variations -->
<button success>Success Button</button>
<button warning>Warning Button</button>
<button error>Error Button</button>

<!-- Size variations -->
<button size="sm">Small Button</button>
<button size="lg">Large Button</button>

<!-- Full width button -->
<button full-width>Full Width Button</button>

<!-- Icon button -->
<button icon>
  <svg><!-- SVG icon --></svg>
</button>

<!-- Circular button -->
<button circular>
  <svg><!-- SVG icon --></svg>
</button>

<!-- Disabled state -->
<button disabled>Disabled Button</button>
```

### Forms

Form elements are styled for consistency and accessibility:

```html
<form>
  <!-- Text input -->
  <div>
    <label for="name">Name</label>
    <input type="text" id="name" placeholder="Enter your name">
  </div>

  <!-- Required input -->
  <div>
    <label for="email">Email</label>
    <input type="email" id="email" required placeholder="Enter your email">
  </div>

  <!-- Textarea -->
  <div>
    <label for="message">Message</label>
    <textarea id="message" rows="4" placeholder="Enter your message"></textarea>
  </div>

  <!-- Select -->
  <div>
    <label for="country">Country</label>
    <select id="country">
      <option value="">Select a country</option>
      <option value="us">United States</option>
      <option value="ca">Canada</option>
      <option value="mx">Mexico</option>
    </select>
  </div>

  <!-- Checkbox -->
  <div>
    <input type="checkbox" id="subscribe">
    <label for="subscribe">Subscribe to newsletter</label>
  </div>

  <!-- Radio buttons -->
  <div>
    <input type="radio" id="option1" name="options" value="option1">
    <label for="option1">Option 1</label>
  </div>
  <div>
    <input type="radio" id="option2" name="options" value="option2">
    <label for="option2">Option 2</label>
  </div>

  <!-- Form actions -->
  <div>
    <button primary type="submit">Submit</button>
    <button type="reset">Reset</button>
  </div>
</form>
```

### Cards

Cards use a simple structure with optional attributes for variations:

```html
<!-- Basic card -->
<div class="card">
  <div class="card-header">
    <h3>Card Title</h3>
  </div>
  <div class="card-body">
    <p>Card content goes here.</p>
  </div>
  <div class="card-footer">
    <button>Action</button>
  </div>
</div>

<!-- Card with shadow -->
<div class="card" shadow>
  <!-- Card content -->
</div>

<!-- Card with hover effect -->
<div class="card" hover>
  <!-- Card content -->
</div>

<!-- Card with color variation -->
<div class="card" primary>
  <!-- Card content -->
</div>

<!-- Card sizes -->
<div class="card" size="sm">
  <!-- Card content -->
</div>

<div class="card" size="lg">
  <!-- Card content -->
</div>

<!-- Horizontal card -->
<div class="card" horizontal>
  <img src="image.jpg" class="card-image" start>
  <div class="card-body">
    <h3>Horizontal Card</h3>
    <p>Content for horizontal card layout.</p>
  </div>
</div>

<!-- Interactive card -->
<div class="card" interactive>
  <!-- Card content -->
</div>
```

### Navigation

Navigation components with various styles:

```html
<!-- Basic navigation -->
<nav role="navigation">
  <div>
    <a href="/" aria-current="page">Home</a>
    <a href="/about">About</a>
    <a href="/services">Services</a>
    <a href="/contact">Contact</a>
  </div>
</nav>

<!-- Sticky navigation -->
<nav role="navigation" sticky>
  <!-- Navigation content -->
</nav>

<!-- Compact navigation -->
<nav role="navigation" compact>
  <!-- Navigation content -->
</nav>

<!-- Tabs navigation -->
<nav role="navigation" tabs>
  <!-- Navigation content -->
</nav>

<!-- Pills navigation -->
<nav role="navigation" pills>
  <!-- Navigation content -->
</nav>

<!-- Collapsible navigation (for mobile) -->
<nav role="navigation" collapsible>
  <div>
    <a href="/" class="brand">Site Name</a>
    <button class="nav-toggle" aria-expanded="false" aria-controls="nav-menu">
      <span class="sr-only">Toggle navigation</span>
      <svg><!-- Menu icon --></svg>
    </button>
  </div>
  <div id="nav-menu">
    <!-- Navigation links -->
  </div>
</nav>
```

### Layout

sem-mochi provides a flexible grid system and container components using attributes instead of classes:

```html
<!-- Basic container -->
<div container>
  <!-- Content -->
</div>

<!-- Container with max-width -->
<div container max-width="lg">
  <!-- Content -->
</div>

<!-- Container with padding -->
<div container padding="sm">
  <!-- Content -->
</div>

<!-- Grid layout -->
<div grid>
  <div col-span="6">Left column</div>
  <div col-span="6">Right column</div>
</div>

<!-- Grid with gap -->
<div grid gap="md">
  <!-- Grid items -->
</div>

<!-- Responsive grid -->
<div grid>
  <div col-span="12" col-sm-span="full" col-md-span="6">
    Responsive column
  </div>
  <!-- More columns -->
</div>

<!-- Auto-fit grid -->
<div grid="auto-fit">
  <!-- Items will automatically fit based on available space -->
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>

<!-- Legacy class support is also available -->
<div class="grid">
  <div class="col-span-6">Legacy class support</div>
</div>
```

### Themes

sem-mochi includes built-in support for light, dark, and high-contrast themes:

```html
<!-- Theme toggle -->
<input type="checkbox" id="theme-toggle" aria-label="Toggle dark mode">

<!-- Manual theme setting -->
<html data-theme="light">
  <!-- Light theme content -->
</html>

<html data-theme="dark">
  <!-- Dark theme content -->
</html>

<html data-theme="high-contrast">
  <!-- High contrast theme content -->
</html>
```

JavaScript for theme toggle:

```javascript
// Theme Toggle Functionality
document.addEventListener('DOMContentLoaded', () => {
  const themeToggle = document.getElementById('theme-toggle');
  const html = document.documentElement;

  // Check for saved theme preference or respect OS preference
  const savedTheme = localStorage.getItem('theme');
  const prefersDark = window.matchMedia('(prefers-color-scheme: dark)').matches;

  // Apply the appropriate theme
  if (savedTheme === 'dark' || (!savedTheme && prefersDark)) {
    html.setAttribute('data-theme', 'dark');
    themeToggle.checked = true;
  } else {
    html.setAttribute('data-theme', 'light');
    themeToggle.checked = false;
  }

  // Toggle theme when the checkbox changes
  themeToggle.addEventListener('change', () => {
    if (themeToggle.checked) {
      html.setAttribute('data-theme', 'dark');
      localStorage.setItem('theme', 'dark');
    } else {
      html.setAttribute('data-theme', 'light');
      localStorage.setItem('theme', 'light');
    }
  });
});
```

### Utilities

sem-mochi includes essential utilities for common needs, using attributes instead of classes:

```html
<!-- Accessibility -->
<a href="#main-content" skip-link>Skip to main content</a>
<span sr-only>Text only for screen readers</span>

<!-- Animations -->
<div animate="fade-in">Fades in</div>
<div animate="slide-in-up">Slides up</div>
<div animate="pulse">Pulses</div>

<!-- Animation modifiers -->
<div animate="fade-in" delay="300">Delayed animation</div>
<div animate="slide-in-up" duration="slow">Slow animation</div>

<!-- Reduced motion -->
<div motion="safe">Only shown when animations are enabled</div>
<div motion="reduce">Only shown when reduced motion is preferred</div>

<!-- Legacy class support is also available -->
<div class="animate-fade-in">Legacy class support</div>
```

## Customization

sem-mochi is designed to be easily customizable through CSS custom properties.

### Customizing Colors

```css
:root {
  /* Change primary color */
  --sm-color-primary-h: 240; /* Change hue to purple */
  --sm-color-primary-s: 80%; /* Adjust saturation */

  /* Override specific semantic colors */
  --sm-accent: rebeccapurple;
  --sm-border: #dddddd;
}
```

### Customizing Typography

```css
:root {
  /* Change font families */
  --sm-font-sans: 'Roboto', sans-serif;
  --sm-font-mono: 'Fira Code', monospace;

  /* Adjust type scale */
  --sm-scale-ratio: 1.25; /* Larger scale ratio */

  /* Change base font size */
  --sm-font-base-size: 1.125rem;
}
```

### Customizing Components

```css
:root {
  /* Customize buttons */
  --button-radius: 0; /* Square buttons */

  /* Customize cards */
  --card-radius: 1rem; /* Rounder cards */
  --card-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
}
```

### Creating a Custom Build

For more extensive customization, you can create a custom build:

1. Clone the repository
2. Modify the source files in the `src/` directory
3. Build the CSS using your preferred build tool

## Browser Support

sem-mochi uses modern CSS features including:

- CSS Custom Properties
- CSS Nesting
- Container Queries
- Logical Properties
- CSS Grid and Flexbox
- Advanced selectors including `:has()`

For browsers that don't support certain features, appropriate fallbacks are provided through feature queries.

| Feature | Chrome | Firefox | Safari | Edge |
|---------|--------|---------|--------|------|
| Basic styling | 90+ | 90+ | 14+ | 90+ |
| CSS Nesting | 112+ | 117+ | 16.4+ | 112+ |
| Container Queries | 105+ | 110+ | 16+ | 105+ |
| :has() selector | 105+ | 121+ | 15.4+ | 105+ |

## Philosophy

sem-mochi represents a return to the original vision of the web where content structure drives presentation. By leveraging modern CSS capabilities, we can now achieve sophisticated styling while respecting the semantic meaning of HTML elements.

This approach creates a more maintainable, accessible, and future-proof development pattern compared to utility-first or heavily class-based CSS frameworks.

### Core Principles

1. **Semantic HTML First**: Write meaningful HTML that describes the content, not the presentation
2. **Attributes Over Classes**: Use HTML attributes instead of classes for variations and utilities
3. **Minimal Classes**: Use classes only when absolutely necessary for complex composition patterns
4. **ARIA for States**: Leverage ARIA attributes for interactive states
5. **Progressive Enhancement**: Provide fallbacks for older browsers while leveraging modern features
6. **Backward Compatibility**: Maintain legacy class support for backward compatibility

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

---

Made with ❤️ by the sem-mochi team
