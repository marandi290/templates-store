# Blog Card — Responsive Blog Card Template

A semantic, fully responsive blog card built with HTML5 and Sass. Uses Flexbox for internal layout and a CSS Media Query to switch between horizontal (desktop) and vertical (mobile) layouts.

---

## Project Structure

```
Blog_Card/
├── scss/
│   ├── _variables.scss   # Design tokens (colors, radius, breakpoint)
│   ├── _base.scss        # Reset, box-sizing, centered body
│   ├── _card.scss        # Blog card Flexbox layout & Box Model
│   ├── _responsive.scss  # Media query at 600px
│   └── main.scss         # Entry point — imports all partials
├── index.html            # Main HTML file
├── favicon.ico           # Site favicon (replace with your own)
├── styles.css            # Unminified CSS (reference)
└── styles.min.css        # Compiled & minified production CSS
```

---

## Features

### Semantic HTML5
- `<article>` wraps the entire card
- `<figure>` contains the card image
- `<footer>` holds the author and date meta row
- Heading hierarchy: `h3` for the card title, `p` for excerpt and tag

### Layout — Flexbox
- Desktop: card is a horizontal row (`flex-direction: row`) with the image on the left and content on the right
- Content body uses `flex-direction: column` with `justify-content: space-between` to push the footer to the bottom
- Footer meta row uses `justify-content: space-between` and `align-items: center` to space author and date

### Responsiveness
| Breakpoint | Layout |
|---|---|
| Desktop `> 600px` | Horizontal — image left, content right |
| Mobile `≤ 600px` | Vertical stack — image on top, content below |

### Box Model
- `box-sizing: border-box` applied globally via reset
- `padding` on the card body and footer
- `margin` reset on all elements
- `border` on the card and footer divider

### Accessibility
- `<time datetime="...">` for machine-readable publish date
- Descriptive `alt` text on all images
- `<meta name="description">` and `<meta name="theme-color">` in `<head>`

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
$primary:    #4f46e5;   // Tag color
$text:       #1f2937;   // Body text
$muted:      #6b7280;   // Excerpt & date text
$bg:         #f3f4f6;   // Page background
$border:     #e5e7eb;   // Card & footer border
$radius:     10px;      // Card border radius
$bp-mobile:  600px;     // Breakpoint for vertical stack
```

---

## Before Deploying

- Replace the `picsum.photos` placeholder images with your own
- Replace `favicon.ico` with your own
- Update the card content (title, excerpt, author, date) in `index.html`

---

## License

This project is open source and available under the [MIT License](https://opensource.org/licenses/MIT).
