# sem-mochi

**Semantic-First CSS Framework with Minimal Class Usage**

## Overview

sem-mochi is a modern CSS framework designed around the principle of semantic markup, focusing on styling native HTML elements directly while minimizing class usage. It leverages advanced CSS features and selectors to create a highly maintainable styling approach that prioritizes the inherent semantic meaning of HTML elements.

## Key Features

- **Modular Architecture**: Organized into logical modules for better maintainability
- **HSL-Based Color System**: Programmatically generated color palette for consistent theming
- **Component-Specific Custom Properties**: Better encapsulation and customization
- **Enhanced Accessibility**: Robust keyboard navigation and focus management
- **Comprehensive Animation System**: Consistent timing functions and animations
- **Improved Layout System**: Flexible grid and container components
- **Container Query Support**: For component-level responsive design
- **Dark Mode & High Contrast Themes**: Built-in accessibility features

## Architecture

sem-mochi is structured using CSS cascade layers for explicit specificity control:

```css
@layer tokens, theme, base, elements, components, layout, states, utilities, queries;
```

This layered approach enables predictable styling without specificity conflicts, allowing for:

- Clear separation of concerns
- Deterministic cascade application
- Isolated styling contexts

## File Structure

```
src/
├── tokens/
│   ├── _colors.css
│   ├── _typography.css
│   ├── _spacing.css
│   └── _effects.css
├── themes/
│   ├── _light.css
│   ├── _dark.css
│   └── _high-contrast.css
├── base/
│   ├── _reset.css
│   └── _elements.css
├── components/
│   ├── _buttons.css
│   ├── _cards.css
│   └── ...
├── layout/
│   ├── _container.css
│   ├── _grid.css
│   └── ...
├── utilities/
│   ├── _accessibility.css
│   ├── _animations.css
│   └── ...
└── sem-mochi.css
```

## Usage Approach

### Traditional CSS vs sem-mochi

**Traditional approach:**

```html
<button class="btn btn-primary btn-lg">Submit</button>
```

**sem-mochi approach:**

```html
<button primary>Submit</button>
```

### Native Element Styling

Elements are styled directly without requiring classes:

```html
<header>
  <h1>Page Title</h1>
  <p>Subtitle content</p>
</header>

<!-- Expanded accordion header -->
<h3>
  <button aria-expanded="true" aria-controls="panel1">Section Title</button>
</h3>
<div id="panel1" aria-labelledby="header1">Content...</div>
```

## Technical Implementation

### CSS Custom Properties

Semantic design tokens using CSS custom properties:

```css
:root {
  /* HSL-based color system */
  --sm-color-primary-h: 217;
  --sm-color-primary-s: 91%;
  --sm-luminance-500: 50%;
  --sm-color-primary-500: hsl(var(--sm-color-primary-h), var(--sm-color-primary-s), var(--sm-luminance-500));
  
  /* Semantic tokens */
  --sm-bg: #ffffff;
  --sm-fg: var(--sm-color-neutral-900);
  --sm-accent: var(--sm-color-primary-500);
  
  /* Spacing system */
  --sm-space: clamp(1rem, 0.9rem + 0.5vw, 1.25rem);
}
```

### Component-Specific Properties

```css
button {
  --button-bg: var(--sm-accent);
  --button-color: white;
  --button-hover-bg: var(--sm-accent-subtle);
  
  background-color: var(--button-bg);
  color: var(--button-color);
}

button:hover {
  background-color: var(--button-hover-bg);
}
```

## Benefits

1. **Improved Accessibility**: ARIA attributes are first-class styling hooks
2. **Reduced Markup**: Cleaner HTML with fewer classes
3. **Self-Documenting**: Markup conveys semantic meaning
4. **Enhanced Maintainability**: Styling changes don't require HTML modifications
5. **Better SEO**: Search engines understand semantic HTML better than class-based markup
6. **Reduced Bundle Size**: Less CSS required for styling
7. **Simplified Development**: Component styling follows HTML structure
8. **Improved Performance**: Optimized with CSS containment and content-visibility

## Getting Started

1. Include the sem-mochi.css file in your HTML:

   ```html
   <link rel="stylesheet" href="path/to/sem-mochi.css">
   ```

2. Write semantic HTML without worrying about excessive classes:

   ```html
   <header>
     <h1>Page Title</h1>
   </header>
   
   <main>
     <section>
       <h2>Section Title</h2>
       <p>Content goes here...</p>
       
       <button primary>Primary Action</button>
       <button outline>Secondary Action</button>
     </section>
   </main>
   
   <footer>
     <p>Footer content</p>
   </footer>
   ```

3. For layouts, use the minimal composition classes:

   ```html
   <div class="grid">
     <div class="col-span-6">Left column</div>
     <div class="col-span-6">Right column</div>
   </div>
   ```

## Browser Support

sem-mochi uses modern CSS features including:

- CSS Custom Properties
- CSS Nesting
- Container Queries
- Logical Properties
- CSS Grid and Flexbox
- Advanced selectors including `:has()`

For browsers that don't support certain features, appropriate fallbacks are provided through feature queries.

## Philosophy

sem-mochi represents a return to the original vision of the web where content structure drives presentation. By leveraging modern CSS capabilities, we can now achieve sophisticated styling while respecting the semantic meaning of HTML elements.

This approach creates a more maintainable, accessible, and future-proof development pattern compared to utility-first or heavily class-based CSS frameworks.

## License

MIT License
