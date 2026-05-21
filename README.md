# Templates Store

A growing collection of free, production-ready HTML + Sass webpage templates. Each template is self-contained, fully responsive, and built to be customized and deployed with minimal effort.

---

## Templates

| # | Template | Description |
|---|---|---|
| 1 | [Branding_Page](./Branding_Page/) | A modern single-page branding/marketing site with animated hero, services cards, gallery, and contact form |
| 2 | [Blog_Card](./Blog_Card/) | A responsive blog card with semantic HTML5, Flexbox layout, and a 600px breakpoint switching horizontal to vertical |
| 3 | [Pricing_Table](./Pricing_Table/) | A responsive three-column pricing table demonstrating CSS specificity layers, :hover states, and JS file linking |
| 4 | [URL_Journey](./URL_Journey/) | A visual DNS lookup diagram using semantic HTML, Flexbox, CSS-only arrows, and a browser cache explainer |

---

## Structure

Each template lives in its own folder and is fully independent:

```
Templates Store/
├── Branding_Page/       # Template 1
│   ├── scss/            # Sass source files
│   ├── index.html       # Main HTML file
│   ├── styles.css       # Unminified CSS (reference)
│   ├── styles.min.css   # Compiled & minified production CSS
│   └── README.md        # Template-specific documentation
├── Blog_Card/           # Template 2
│   ├── scss/            # Sass source files
│   ├── index.html       # Main HTML file
│   ├── styles.css       # Unminified CSS (reference)
│   ├── styles.min.css   # Compiled & minified production CSS
│   └── README.md        # Template-specific documentation
├── Pricing_Table/       # Template 3
│   ├── scss/            # Sass source files
│   ├── index.html       # Main HTML file
│   ├── script.js        # JS file linking confirmation
│   ├── styles.css       # Unminified CSS (reference)
│   ├── styles.min.css   # Compiled & minified production CSS
│   └── README.md        # Template-specific documentation
└── URL_Journey/         # Template 4
    ├── scss/            # Sass source files
    ├── index.html       # Main HTML file
    ├── styles.css       # Unminified CSS (reference)
    ├── styles.min.css   # Compiled & minified production CSS
    └── README.md        # Template-specific documentation
```

---

## Using a Template

1. Copy the template folder into your project
2. Open `index.html` in a browser — it works out of the box
3. Edit content in `index.html` and design tokens in `scss/_variables.scss`
4. Recompile CSS after any Sass changes:
```bash
sass scss/main.scss styles.min.css --style=compressed --no-source-map
```
5. Follow the **Before Deploying** checklist in each template's `README.md`

---

## Tech Stack

- **HTML5** — Semantic markup
- **Sass** — Modular CSS architecture with design tokens
- **Vanilla JS** — No frameworks or dependencies

---

## Prerequisites

- [Node.js](https://nodejs.org/) v14 or higher
- Sass installed globally:
```bash
npm install -g sass
```

---

## License

All templates are open source and available under the [MIT License](https://opensource.org/licenses/MIT).
