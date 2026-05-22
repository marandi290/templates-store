# Landing Sections

A collection of reusable landing page section templates built with semantic HTML, modular Sass, and responsive layout patterns.

## Categories

- `CTA_Sections/` — Call-to-action sections for download, free trial, newsletter, and waitlist pages.
- `Feature_Sections/` — Feature highlight blocks including comparison, tabs, timeline, bento grid, and zigzag layouts.
- `Hero_Sections/` — Landing page hero sections for agencies, AI SaaS, course pages, developer tools, mobile apps, and startups.
- `Social_Proof/` — Trust-building sections with case studies, company logos, metrics, testimonials, and user reviews.

## Folder Structure

Each section contains its own preview page and Sass source files:

```
Landing_Sections/
├── CTA_Sections/
├── Feature_Sections/
├── Hero_Sections/
├── Social_Proof/
├── _base.scss
└── _variables.scss
```

Each section folder includes:

- `index.html` — preview page
- `styles.css` — compiled CSS output
- `styles.min.css` — minified compiled CSS
- `scss/main.scss` — Sass entrypoint
- `scss/_variables.scss` — section-specific tokens
- `scss/_base.scss` — section layout helpers and shared styles
- `scss/_section.scss` — section-specific styling rules

## Usage

1. Open any section's `index.html` in a browser to preview the layout.
2. Customize the markup in `index.html` and style tokens in `scss/_variables.scss`.
3. Recompile the section Sass when you change styles.

### Compile Sass

From a section folder:

```bash
cd Landing_Sections/CTA_Sections/Download_App_CTA
sass scss/main.scss styles.min.css --style=compressed --no-source-map
```

Or compile both outputs:

```bash
sass scss/main.scss styles.css --style=expanded --no-source-map
sass scss/main.scss styles.min.css --style=compressed --no-source-map
```

## Notes

- The top-level `Landing_Sections/_base.scss` and `_variables.scss` files provide shared design tokens and helpers across all sections.
- Each section is intentionally self-contained so it can be copied into another project with minimal dependencies.
- If your editor or Git shows line ending warnings, the files are maintained with consistent LF formatting for Sass compatibility.

## Contribution

To add a new landing section:

1. Create a new folder under one of the category directories.
2. Add `index.html`, `styles.css`, `styles.min.css`, and a `scss/` folder.
3. Use `scss/main.scss` as the Sass entrypoint and include `@use "variables";`, `@use "base";`, and `@use "section";`.
4. Keep the section styles isolated in `scss/_section.scss`.
