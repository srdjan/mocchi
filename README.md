# sem-mochi

**Semantic-First CSS Framework with Minimal Class Usage**

## Overview

sem-mochi is a modern CSS framework designed around the principle of semantic markup, focusing on styling native HTML elements directly while minimizing class usage. It leverages advanced CSS features and selectors to create a highly maintainable styling approach that prioritizes the inherent semantic meaning of HTML elements.

## Key Principles

1. **Semantic HTML First**: Style native HTML elements directly rather than abstracting with classes
2. **Attribute-Based Variations**: Use HTML attributes for component variations instead of modifier classes
3. **ARIA-Driven States**: Leverage ARIA attributes to manage interactive states
4. **Minimal Classes**: Only use classes for true composition patterns that cannot be achieved with standard HTML elements

## Architecture

sem-mochi is structured using CSS cascade layers for explicit specificity control:

```css
@layer tokens, base, elements, composition, states, queries;
```

This layered approach enables predictable styling without specificity conflicts, allowing for:

- Clear separation of concerns
- Deterministic cascade application
- Isolated styling contexts

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

<nav>
  <a href="/" aria-current="page">Home</a>
  <a href="/about">About</a>
  <a href="/contact">Contact</a>
</nav>
```

### Attribute-Based Variants

Component variations use HTML attributes:

```html
<!-- Primary button -->
<button primary>Primary Action</button>

<!-- Outline button -->
<button outline>Secondary Action</button>

<!-- Success alert -->
<aside data-type="success">Operation completed successfully.</aside>
```

### ARIA-Driven States

Interactive states are controlled by ARIA attributes:

```html
<!-- Active navigation item -->
<a href="/current-page" aria-current="page">Current Page</a>

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
  --sm-bg: #ffffff;
  --sm-fg: var(--sm-color-gray-900);
  --sm-accent: var(--sm-color-blue-500);
  --sm-success: var(--sm-color-green-500);
  --sm-warning: var(--sm-color-yellow-500);
  --sm-error: var(--sm-color-red-500);
  
  --sm-space: clamp(1rem, 0.9rem + 0.5vw, 1.25rem);
  --sm-radius: 0.375rem;
}
```

### Logical Properties for Internationalization

Full support for RTL languages and logical flow directions:

```css
blockquote {
  padding-block: var(--sm-space);
  padding-inline: var(--sm-space);
  border-inline-start: 4px solid var(--sm-accent);
}
```

### Container Queries for Component-Based Responsiveness

Layout adjustments based on container size rather than viewport:

```css
@container layout (min-width: 40rem) {
  .card {
    display: grid;
    grid-template-columns: 1fr 2fr;
  }
}
```

### Advanced Selector Patterns

Leveraging modern CSS selectors for sophisticated styling:

```css
/* Style for required fields */
label:has(+ [required])::after {
  content: " *";
  color: var(--sm-error);
}

/* Tooltip display */
[data-tooltip]:hover::after {
  content: attr(data-tooltip);
  /* Styling properties */
}
```

## Composition Patterns

A minimal set of composition classes for layout needs:

```html
<!-- Two-column layout -->
<div class="two-columns">
  <div>First column content</div>
  <div>Second column content</div>
</div>

<!-- Auto-grid layout -->
<div class="auto-grid">
  <article>Item 1</article>
  <article>Item 2</article>
  <article>Item 3</article>
</div>

<!-- Card pattern -->
<article class="card">
  <header>Card Title</header>
  <div class="content">Main content</div>
  <footer>Card footer</footer>
</article>
```

## JavaScript-Less Interactivity

Pure CSS implementations of typically JavaScript-dependent components:

```css
/* CSS-only tabs */
.tab-btn:focus + .tab-panel {
  display: block;
}

/* CSS-only modal via :target selector */
.modal:target {
  display: flex;
}
```

## Accessibility Features

Strong focus on accessibility with built-in patterns:

```html
<!-- Skip link for keyboard users -->
<a href="#main-content" class="skip-link">Skip to main content</a>

<!-- Properly structured form -->
<label for="email">Email Address</label>
<input type="email" id="email" name="email" required>

<!-- Accessible tables -->
<table>
  <caption>User Data</caption>
  <tr>
    <th scope="col">Name</th>
    <th scope="col">Email</th>
  </tr>
  <!-- Table data -->
</table>
```

## Responsive Design

Responsive behavior with minimal overhead:

```css
/* Mobile-first media queries */
@media (min-width: 768px) {
  /* Medium screen adjustments */
}

@media (min-width: 1024px) {
  /* Large screen adjustments */
}

/* Media feature queries */
@media (prefers-reduced-motion: reduce) {
  /* Motion reduction accommodations */
}

@media (prefers-contrast: more) {
  /* High contrast adjustments */
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
   <div class="two-columns">
     <!-- Two column content -->
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
