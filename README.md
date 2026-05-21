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
| 5 | [Auth_Templates](./Auth_Templates/) | A complete set of 8 auth/user-flow templates: Login, Signup, Forgot Password, Reset Password, OTP, 2FA, Magic Link, Social Login |
| 6 | [Dashboard_Templates](./Dashboard_Templates/) | A complete set of 8 dashboard templates: Analytics, Finance, CRM, Project Management, AI SaaS, Admin Panel, Team Workspace, DevOps |

---

## Structure

Each template lives in its own folder and is fully independent:

```
Templates Store/
├── Branding_Page/       # Template 1
├── Blog_Card/           # Template 2
├── Pricing_Table/       # Template 3
├── URL_Journey/         # Template 4
└── Auth_Templates/      # Template 5 — 8 auth flow templates
    ├── Login/
    ├── Signup/
    ├── Forgot_Password/
    ├── Reset_Password/
    ├── OTP_Verification/
    ├── Two_Factor_Auth/
    ├── Magic_Link/
    └── Social_Login/
└── Dashboard_Templates/ # Template 6 — 8 dashboard templates
    ├── Analytics_Dashboard/
    ├── Finance_Dashboard/
    ├── CRM_Dashboard/
    ├── Project_Dashboard/
    ├── AI_SaaS_Dashboard/
    ├── Admin_Panel/
    ├── Team_Workspace/
    └── DevOps_Dashboard/
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
