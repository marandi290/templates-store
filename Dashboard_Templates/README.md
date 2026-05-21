# Dashboard Templates

A complete set of 8 production-ready dashboard templates built with HTML5 and Sass. Each dashboard features a fixed sidebar, sticky topbar, responsive layout, and a full set of domain-specific widgets — all built with zero dependencies.

---

## Dashboards

| # | Template | Accent | Description |
|---|---|---|---|
| 1 | [Analytics_Dashboard](./Analytics_Dashboard/) | Indigo | Traffic, page views, bounce rate, conversions, bar chart, donut chart |
| 2 | [Finance_Dashboard](./Finance_Dashboard/) | Sky Blue | Revenue, expenses, transactions table, budget progress bars |
| 3 | [CRM_Dashboard](./CRM_Dashboard/) | Violet | Deal pipeline (Kanban), contacts table, activity feed |
| 4 | [Project_Dashboard](./Project_Dashboard/) | Amber | Sprint board (Kanban), project progress, team workload |
| 5 | [AI_SaaS_Dashboard](./AI_SaaS_Dashboard/) | Cyan | Token usage meters, model cards, API request log, billing |
| 6 | [Admin_Panel](./Admin_Panel/) | Dark Slate | User management, system health bars, audit log, role distribution |
| 7 | [Team_Workspace](./Team_Workspace/) | Emerald | Member grid, standup feed, doc list, calendar strip |
| 8 | [DevOps_Dashboard](./DevOps_Dashboard/) | Red | CI/CD pipeline, service health + uptime bars, deploy log, resource meters |

---

## Structure

Each dashboard is fully self-contained:

```
Dashboard_Templates/
├── Analytics_Dashboard/
│   ├── scss/
│   │   ├── _variables.scss   # Design tokens (accent color, sidebar width, etc.)
│   │   ├── _base.scss        # Reset, CSS Grid body layout
│   │   ├── _layout.scss      # Sidebar, topbar, main content area
│   │   ├── _widgets.scss     # All domain-specific widget styles
│   │   ├── _responsive.scss  # Mobile sidebar collapse
│   │   └── main.scss         # Entry point
│   ├── index.html
│   ├── script.js
│   ├── styles.css
│   └── styles.min.css
├── Finance_Dashboard/        # Same structure
├── CRM_Dashboard/            # Same structure
├── Project_Dashboard/        # Same structure
├── AI_SaaS_Dashboard/        # Same structure
├── Admin_Panel/              # Same structure
├── Team_Workspace/           # Same structure
└── DevOps_Dashboard/         # Same structure
```

---

## Shared Architecture

All 8 dashboards share the same structural Sass partials (`_base.scss`, `_layout.scss`, `_responsive.scss`) and only differ in `_variables.scss` (accent color) and `_widgets.scss` (domain content).

### Layout
- `body` uses CSS Grid: `grid-template-columns: 240px 1fr`
- `.sidebar` is `position: fixed`, full height, scrollable
- `.topbar` is `position: sticky`, `grid-column: 2`
- `.main` has `margin-left: 240px` to clear the fixed sidebar

### Sidebar
- Logo, nav sections with labels, nav items with icons and badges
- User row in the footer with avatar, name, and role
- Active state managed by JS click handler

### Responsive (≤ 900px)
- Sidebar slides off-screen (`transform: translateX(-100%)`)
- Hamburger button in topbar toggles `.open` class
- A dark overlay closes the sidebar on click
- Main content fills full width

### Dark Themes
- AI SaaS — dark sidebar (`#0f172a`), light main area
- Admin Panel — dark sidebar (`#1f2937`), light main area
- DevOps — full dark theme (`#0f172a` background, `#1e293b` cards)

---

## Widget Inventory

| Widget | Used In |
|---|---|
| Stat cards (4-up grid) | All 8 |
| Bar chart (CSS-only) | Analytics |
| Donut chart (CSS conic-gradient) | Analytics, Finance |
| Data table | Analytics, Finance, CRM, Admin, DevOps |
| Activity / audit feed | Analytics, CRM, Admin |
| Budget / progress bars | Finance, Admin, AI SaaS, DevOps |
| Deal pipeline (Kanban) | CRM |
| Sprint board (Kanban) | Project |
| Team member grid | Project, Team Workspace |
| CI/CD pipeline steps | DevOps |
| Uptime bar blocks | DevOps |
| Deploy / API log | DevOps, AI SaaS |
| Token usage meters | AI SaaS |
| Model cards | AI SaaS |
| Standup feed | Team Workspace |
| Doc list | Team Workspace |
| Calendar strip | Team Workspace |

---

## Getting Started

Open any `index.html` directly in a browser — no build step needed.

---

## Development Workflow

### Watch mode
```bash
sass --watch scss/main.scss:styles.min.css --style=compressed --no-source-map
```

### One-time compile
```bash
sass scss/main.scss styles.min.css --style=compressed --no-source-map
```

---

## Customization

Each dashboard's accent color and sidebar style is controlled entirely by `scss/_variables.scss`. Change `$primary` and `$sidebar-bg` to retheme instantly.

```scss
// Example: switch Analytics to a teal accent
$primary:       #14b8a6;
$primary-dark:  #0d9488;
$primary-light: #ccfbf1;
```

---

## Before Deploying

- Replace placeholder names, numbers, and data with real content
- Wire up sidebar nav items to real routes
- Replace `favicon.ico` with your own
- Connect widgets to a real data source or API

---

## License

All templates are open source and available under the [MIT License](https://opensource.org/licenses/MIT).
