# Material 3 Expressive Design System Skill

Apply Google Material 3 Expressive design system to web pages in this repository.

## Instructions

When this skill is invoked, apply the following Material 3 Expressive design principles to the specified web page(s):

### 1. Design Tokens & Theme

- **Color System**: Use Material 3 dynamic color with expressive tonal palettes
  - Primary, Secondary, Tertiary color roles
  - Surface variants with elevated tonal ranges
  - High contrast ratios for accessibility
  - Support light and dark themes

- **Typography**: Material 3 Expressive type scale
  - Display Large/Medium/Small (57/45/36 sp)
  - Headline Large/Medium/Small (32/28/24 sp)
  - Title Large/Medium/Small (22/16/14 sp)
  - Body Large/Medium/Small (16/14/12 sp)
  - Label Large/Medium/Small (14/12/11 sp)
  - Use variable fonts with expressive weights (400-700)

- **Motion**: Expressive motion with emphasis curves
  - Standard: 300ms with emphasized decelerate
  - Emphasized: 500ms with emphasized decelerate
  - Use spring animations for interactive elements

- **Spacing**: 4dp grid system with expressive spacing
  - Compact: 4, 8, 12, 16dp
  - Medium: 8, 16, 24, 32dp
  - Expanded: 12, 24, 36, 48dp

### 2. Component Library

Implement or integrate Material 3 components:

- **Buttons**: Filled, Outlined, Text, Elevated, Tonal variants
- **Cards**: Elevated, Filled, Outlined with expressive corners
- **Navigation**: Navigation bar, rail, drawer with M3 styling
- **Input**: Text fields, chips, sliders with M3 states
- **Data Display**: Lists, tables, data visualizations with M3 density
- **Feedback**: Dialogs, snackbars, progress indicators

### 3. Implementation Options

Choose the appropriate implementation:

**A. Material Web Components (Recommended)**
```html
<!-- Add to HTML -->
<script type="module">
  import '@material/web/all.js';
</script>
<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;700&display=swap" rel="stylesheet">
```

**B. Material Design CSS Framework**
```html
<!-- Add Material 3 CSS -->
<link rel="stylesheet" href="https://unpkg.com/material-components-web@latest/dist/material-components-web.min.css">
```

**C. Custom CSS with M3 Tokens**
- Create CSS custom properties for M3 design tokens
- Implement component styles following M3 specifications

### 4. Layout & Structure

- **Container**: Max-width breakpoints (600/900/1200/1600dp)
- **Grid**: Responsive 4/8/12 column grid system
- **Elevation**: Use M3 elevation levels (0-5) with expressive shadows
- **Shape**: Apply M3 shape system (4/8/12/16/28dp corner radius)

### 5. States & Interactions

Implement Material 3 state layers:
- **Hover**: 8% opacity overlay
- **Focus**: 12% opacity overlay with visible focus ring
- **Pressed**: 12% opacity overlay
- **Dragged**: 16% opacity overlay
- **Disabled**: 38% opacity with no interaction

### 6. Accessibility Requirements

- WCAG 2.1 Level AA compliance minimum
- Keyboard navigation support
- ARIA labels and roles
- Touch target size minimum 48x48dp
- Screen reader optimization

### 7. Responsive Behavior

Implement Material 3 adaptive layouts:
- **Compact** (<600dp): Single column, bottom navigation
- **Medium** (600-840dp): Adaptive layouts, navigation rail
- **Expanded** (>840dp): Multi-column, navigation drawer

## Usage

Invoke this skill when:
- Creating new web pages for reports/dashboards
- Updating existing pages to M3 Expressive
- Ensuring design system consistency

## Output

After applying this skill, the web page should:
1. Use Material 3 Expressive design tokens
2. Implement M3 components correctly
3. Follow M3 layout and spacing guidelines
4. Support light/dark themes
5. Be fully accessible and responsive
6. Have smooth, expressive animations

## Resources

- [Material Design 3](https://m3.material.io/)
- [Material Web Components](https://github.com/material-components/material-web)
- [Material Design Guidelines](https://material.io/design)
