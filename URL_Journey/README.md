# URL Journey Visualizer — DNS Lookup Diagram Template

A visual, fully responsive diagram of the DNS lookup process built with HTML5 and Sass. Translates the Client-Server model into a step-by-step flow using semantic HTML, Flexbox layout, and CSS-only arrows via `::after` pseudo-elements.

---

## Project Structure

```
URL_Journey/
├── scss/
│   ├── _variables.scss   # Design tokens (colors, arrow size, breakpoint)
│   ├── _base.scss        # Reset, box-sizing, centered page layout
│   ├── _diagram.scss     # DNS flow, Flexbox layout, CSS-only arrows, step cards
│   ├── _aside.scss       # Browser cache explanation panel
│   ├── _responsive.scss  # Mobile — vertical stacking, downward arrows
│   └── main.scss         # Entry point — imports all partials
├── index.html            # Main HTML file
├── favicon.ico           # Site favicon (replace with your own)
├── styles.css            # Unminified CSS (reference)
└── styles.min.css        # Compiled & minified production CSS
```

---

## Features

### Semantic HTML5
- A `<section>` wraps the entire DNS flow with an `aria-label`
- Each step is an `<article class="step-card">` with a number, heading, and description
- An `<aside>` holds the browser cache performance explanation
- Arrow connectors use `<div class="arrow" aria-hidden="true">` — hidden from screen readers as they are purely decorative

### CSS Layout — Flexbox
- `.dns-flow` uses `display: flex` with `flex-direction: row` to align all 7 steps horizontally
- On mobile (≤ 768px) it switches to `flex-direction: column` for a vertical stack

### CSS-Only Arrows
- Each `.arrow` div is a thin horizontal line (`width: 44px; height: 2px`)
- The arrowhead is drawn using the CSS border trick on `::after`:
  - A zero-width/height element with `border-left` set creates a right-pointing triangle
- On mobile, arrows rotate to point downward by swapping to `border-top` on `::after`

### DNS Steps Visualized
| Step | Node | Role |
|---|---|---|
| 1 | Browser | Initiates the URL resolution |
| 2 | Browser Cache | Returns IP instantly if cached — fastest path |
| 3 | DNS Resolver | ISP's recursive resolver queries the hierarchy |
| 4 | Root Server | Directs to the correct TLD server |
| 5 | TLD Server | Points to the authoritative name server |
| 6 | Authoritative Server | Returns the final IP address |
| 7 | Web Server | Serves the HTML page over TCP/IP |

### Cache Explainer — `<aside>`
The `<aside>` explains why the browser cache is the fastest step:
- DNS results are stored locally after the first visit (TTL-based)
- Cache hits require **zero network latency** — no packets leave the device
- Contrasted against steps 3–6 which each require internet round-trips

### Responsive Design
| Breakpoint | Layout |
|---|---|
| Desktop `> 768px` | Horizontal flow — left to right |
| Mobile `≤ 768px` | Vertical stack — top to bottom with downward arrows |

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
$primary:      #4f46e5;   // Browser step accent
$accent:       #0ea5e9;   // Resolver & auth server accent
$success:      #10b981;   // Cache & web server accent
$warning:      #f59e0b;   // Root & TLD server accent
$arrow-color:  #94a3b8;   // Arrow line and head color
$arrow-size:   12px;      // Arrowhead triangle size
$bp-mobile:    768px;     // Breakpoint for vertical stack
```

---

## Before Deploying

- Replace `favicon.ico` with your own
- Update the page title and meta description in `index.html`
- Swap emoji icons for SVG icons if a more polished look is needed

---

## License

This project is open source and available under the [MIT License](https://opensource.org/licenses/MIT).
