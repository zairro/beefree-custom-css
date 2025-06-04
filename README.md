# beefree-custom-css
A repository for applying Custom CSS in Beefree SDK.

# Beefree SDK UI Customization Guide
This guide explains how to customize the Beefree SDK user interface by modifying the CSS file.

## Table of Contents
1. [Introduction](#introduction)
2. [Customizing the CSS](#customizing-the-css)
3. [Using Browser DevTools](#using-browser-devtools)
4. [CSS Structure Guidelines](#css-structure-guidelines)
5. [Theme Examples](#theme-examples)
6. [Best Practices](#best-practices)
7. [Troubleshooting](#troubleshooting)

## Introduction

This guide explains how to customize the Beefree SDK user interface by modifying the CSS file. You can completely transform the look and feel of the builder while maintaining all functionality.

## Customizing the CSS

### Basic Setup

1. Locate the CSS file in your project (typically `beefree-sdk.css`)
2. Make a backup before making changes
3. Use the following structure for new styles:

```css
/* Target elements using Beefree's class structure */
.widget-bar.widget-bar--cs {
  /* Your styles here */
}

/* Add custom variables at the top */
:root {
  --primary-color: #2F4F4F;
  --secondary-color: #228B22;
}
```

### Key Areas to Customize

- **Color scheme**: Modify the color variables
- **Typography**: Change font families and sizes
- **Layout**: Adjust spacing and dimensions
- **Components**: Style buttons, inputs, panels
- **Interactive states**: Hover, active, focus styles

## Using Browser DevTools

### Finding Element Classes

1. **Open DevTools**:
   - Right-click on any UI element → "Inspect"
   - Or press `F12`/`Ctrl+Shift+I` (Windows) or `Cmd+Opt+I` (Mac)

2. **Identify Classes**:
   - Hover over elements in the Elements panel
   - Look for class names in the HTML (usually starts with `bf-`, `bee-`, or `builder-`)

3. **Test Styles**:
   - In the Styles panel, add temporary CSS
   - Use the `+` button to add new rules
   - Test changes before adding to your CSS file


### Specific Techniques

- **Search for classes**: `Ctrl+F` in Elements panel
- **Force states**: Right-click element → "Force state" (hover, active, etc.)
- **Mobile view**: Toggle device toolbar (`Ctrl+Shift+M`)

## CSS Structure Guidelines

### Proper Selector Structure

Always follow Beefree's pattern:
```css
/* Correct */
.widget-bar.widget-bar--cs .tabset__tab--cs a {
  /* styles */
}

/* Avoid */
.tabset__tab a {
  /* too generic */
}
```

### Important Rules

1. **Use `!important` sparingly** but it's often needed to override defaults:
   ```css
   .bee--cs .btn-primary {
     background-color: var(--primary-color) !important;
   }
   ```

2. **Organize your CSS** by component:
   ```
   /* Tabs */
   /* Widgets */
   /* Inputs */
   /* Buttons */
   ```

3. **Comment your changes**:
   ```css
   /* Custom tab styling - added 2023-10-01 */
   .tabset__tab--cs {
     /* ... */
   }
   ```

## Theme Examples

### Earth Theme (Default)

```css
:root {
  /* Greens */
  --forest-green: #228B22;
  --sage-green: #9DC183;
  /* Blues */
  --ocean-blue: #1E90FF;
  /* Browns */
  --earth-brown: #8B4513;
}
```

### Dark Theme

```css
:root {
  --dark-1: #1a1a2e;
  --dark-2: #16213e;
  --accent: #0f3460;
  --highlight: #e94560;
}
```

### Light Theme

```css
:root {
  --light-1: #f8f9fa;
  --light-2: #e9ecef;
  --accent: #4361ee;
  --text: #212529;
}
```

## Best Practices

1. **Test incrementally**: Make small changes and verify they work
2. **Check responsiveness**: Test at different screen sizes
3. **Document changes**: Keep a changelog of your modifications
4. **Use variables**: For easier theme management
5. **Consider accessibility**:
   - Minimum contrast ratio of 4.5:1 for text
   - Visible focus states
   - Sufficient touch targets

## Troubleshooting

### Common Issues

| Issue | Solution |
|-------|----------|
| Styles not applying | Add `!important` or increase specificity |
| Layout breaks | Check for missing parent selectors |
| Colors not changing | Verify correct variable usage |
| Changes not visible | Clear cache (Ctrl+F5) |

### Debugging Tips

1. Check if your CSS file is loading in DevTools → Sources
2. Verify no syntax errors in CSS
3. Look for overrides in the Computed tab
4. Test in multiple browsers

## Additional Resources

- [Beefree SDK Documentation](https://beefree.io/docs)
- [CSS Specificity Guide](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity)
- [Color Contrast Checker](https://webaim.org/resources/contrastchecker/)
- [CSS Variables Guide](https://css-tricks.com/patterns-for-practical-css-custom-properties/)
