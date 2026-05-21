# MyBrand — Responsive Webpage

A modern, fully responsive webpage built with HTML5 and Sass. Features animated UI components, an organized CSS architecture, and an optimized production build.

---

## Project Structure

```
Branding_Page/
├── scss/
│   ├── _variables.scss     # Design tokens (colors, spacing, breakpoints)
│   ├── _base.scss          # Reset, :root, body, .container
│   ├── _animations.scss    # All @keyframes + prefers-reduced-motion override
│   ├── _layout.scss        # Header, nav, hero, sections, footer
│   ├── _components.scss    # Buttons, cards, gallery, contact form
│   ├── _responsive.scss    # All media queries
│   └── main.scss           # Entry point — imports all partials
├── index.html              # Main HTML file
├── favicon.ico             # Site favicon (replace with your own)
├── styles.css              # Original unminified CSS (reference)
└── styles.min.css          # Compiled & minified production CSS
```

---

## Features

### Pages & Sections
- **Header** — Sticky top bar with logo and navigation links
- **Hero** — Full-width gradient banner with animated CTA button
- **About** — Team introduction section
- **Services** — Responsive 3-column card grid
- **Gallery** — Image grid with hover effects
- **Contact** — Accessible form with name, email, and message fields
- **Footer** — Dark bar with copyright text

### Responsive Design
| Breakpoint | Layout |
|---|---|
| Desktop `> 768px` | 3-column cards, full horizontal nav |
| Tablet `≤ 768px` | 2-column cards, reduced padding |
| Mobile `≤ 480px` | Single column, hamburger menu |

### Accessibility
- `<label>` elements with matching `for`/`id` pairs on all form fields
- Hamburger button has `aria-expanded` that toggles correctly on open/close
- `aria-controls` links the toggle button to the nav element
- Contact form success message uses `aria-live="polite"` for screen reader announcements
- All animations and transitions are disabled when the OS `prefers-reduced-motion` setting is on

### Animations & Hover Effects
- **Buttons** — Lift on hover, glow shadow, click ripple effect
- **Images** — Zoom + dim on hover, label overlay slides up
- **Hero** — Staggered `fadeInUp` entrance animation on load
- **Image skeletons** — Shimmer placeholder while images load; shimmer stops automatically once the image has loaded
- **Cards** — Lift + deeper shadow on hover

### Performance
- Sass compiled to minified CSS (~27% smaller than source)
- Cache-busting version query string (`?v=1.0.1`) on stylesheet link
- `loading="lazy"` on all images
- `clamp()` for fluid typography — no extra breakpoints needed for font sizes
- `<meta name="theme-color">` for browser chrome tinting on mobile
- Ripple effect skipped entirely when `prefers-reduced-motion` is active

### SEO
- `<meta name="description">` included for search engine snippets
- Semantic HTML5 elements throughout (`<header>`, `<main>`, `<section>`, `<footer>`)

---

## Prerequisites

- [Node.js](https://nodejs.org/) v14 or higher
- Sass (installed globally via npm)

---

## Getting Started

### 1. Install Sass
```bash
npm install -g sass
```

### 2. Verify installation
```bash
sass --version
```

### 3. Open the project
Simply open `index.html` in any browser — no build step needed to view the page since `styles.min.css` is already compiled.

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
<!-- Change v=1.0.1 to v=1.0.2, v=1.0.3, etc. -->
<link rel="stylesheet" href="styles.min.css?v=1.0.2" />
```

---

## Customization

All design tokens live in `scss/_variables.scss`. Edit them to retheme the entire site instantly:

```scss
$primary:      #4f46e5;   // Main brand color
$accent:       #7c3aed;   // Hero gradient end color
$text:         #1f2937;   // Body text
$radius:       8px;       // Border radius for cards/buttons
$bp-tablet:    768px;     // Tablet breakpoint
$bp-mobile:    480px;     // Mobile breakpoint
```

After editing, recompile with the watch or one-time compile command above.

---

## Before Deploying

- Replace the `picsum.photos` placeholder images in the gallery with your own
- Update the `<title>`, `<meta name="description">`, and logo text in `index.html`
- Add your own `favicon.ico`
- Wire up the contact form to a backend or third-party service (e.g. Formspree, Netlify Forms)

---

## Browser Support

Works in all modern browsers that support:
- CSS Grid & Flexbox
- CSS Custom Properties
- `clamp()` and `min()`
- `aspect-ratio`

---

## License

This project is open source and available under the [MIT License](https://opensource.org/licenses/MIT).
