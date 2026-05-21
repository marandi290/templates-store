# Pricing Table — Interactive Pricing Table Template

A responsive three-column pricing table built with HTML5 and Sass. Demonstrates CSS specificity layers (element → class → ID), interactive `:hover` states, and basic JavaScript file linking.

---

## Project Structure

```
Pricing_Table/
├── scss/
│   ├── _variables.scss   # Design tokens (colors, radius, breakpoints)
│   ├── _base.scss        # Reset, box-sizing, centered body
│   ├── _table.scss       # Pricing table layout, specificity rules, :hover
│   ├── _responsive.scss  # Media query — stacks columns on smaller screens
│   └── main.scss         # Entry point — imports all partials
├── index.html            # Main HTML file
├── script.js             # JS file linking confirmation
├── favicon.ico           # Site favicon (replace with your own)
├── styles.css            # Unminified CSS (reference)
└── styles.min.css        # Compiled & minified production CSS
```

---

## Features

### HTML Structure
- A container `<div class="pricing-table">` holds three nested plan `<div>`s: Basic, Pro, and Enterprise
- Each plan contains a name, price (`<h2>`), description, feature list (`<ul>`), and a CTA button

### CSS Specificity — Three Layers
| Layer | Selector Type | Target | Effect |
|---|---|---|---|
| 1 | Element (`h2`) | All plan prices | Default muted grey color |
| 2 | Class (`.pro-price`) | Pro plan price only | Overrides to bright amber |
| 3 | ID (`#btn-pro`) | Pro plan CTA button only | Overrides to amber background |

### Pseudo-Classes
- All `.btn-plan` buttons change background color on `:hover`
- The Pro plan `#btn-pro` has its own `:hover` state that darkens the amber color

### Responsive Design
| Breakpoint | Layout |
|---|---|
| Desktop `> 900px` | 3-column grid |
| Tablet / Mobile `≤ 900px` | Single column stack |

### JavaScript
- `script.js` is linked via `<script src="script.js">` at the bottom of `index.html`
- Logs `Pricing Table: script.js loaded successfully.` to the browser console on page load

---

## Prerequisites

- [Node.js](https://nodejs.org/) v14 or higher
- Sass installed globally:
```bash
npm install -g sass
```

---

## Getting Started

Simply open `index.html` in any browser — no build step needed since `styles.min.css` is already compiled.

To confirm JS is running, open the browser DevTools console (`F12`) and look for:
```
Pricing Table: script.js loaded successfully.
```

---

## Development Workflow

### Watch mode — auto-recompile on save
```bash
sass --watch scss/main.scss:styles.min.css --style=compressed --no-source-map
```

### One-time compile
```bash
sass scss/main.scss styles.min.css --style=compressed --no-source-map
```

### After each recompile for production
Bump the version query in `index.html` to bust the browser cache:
```html
<!-- Change v=1.0.0 to v=1.0.1, v=1.0.2, etc. -->
<link rel="stylesheet" href="styles.min.css?v=1.0.1" />
```

---

## Customization

All design tokens live in `scss/_variables.scss`:

```scss
$primary:      #4f46e5;   // Default accent & button color
$pro-price:    #f59e0b;   // Pro plan price & CTA color
$pro-bg:       #1e1b4b;   // Pro plan card background
$text:         #1f2937;   // Body text
$muted:        #6b7280;   // Default price color (element selector)
$radius:       12px;      // Card border radius
$bp-tablet:    900px;     // Breakpoint for single-column stack
```

---

## Before Deploying

- Replace `favicon.ico` with your own
- Update plan names, prices, and features in `index.html`
- Wire up the CTA buttons to your checkout or sign-up flow

---

## License

This project is open source and available under the [MIT License](https://opensource.org/licenses/MIT).
