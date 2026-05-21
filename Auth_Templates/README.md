# Auth Templates — Authentication & User Flow

A complete set of 8 production-ready authentication page templates built with HTML5 and Sass. All templates share a unified design system and are fully responsive, accessible, and ready to wire up to any backend.

---

## Templates

| # | Template | Description |
|---|---|---|
| 1 | [Login](./Login/) | Email + password sign-in with remember me and forgot password link |
| 2 | [Signup](./Signup/) | Full registration form with name, email, password, confirm password, and terms checkbox |
| 3 | [Forgot_Password](./Forgot_Password/) | Single email field to request a password reset link |
| 4 | [Reset_Password](./Reset_Password/) | New password + confirm password fields for completing a reset |
| 5 | [OTP_Verification](./OTP_Verification/) | 6-digit OTP input with auto-advance focus and resend option |
| 6 | [Two_Factor_Auth](./Two_Factor_Auth/) | 6-digit code input with Authenticator App / SMS method toggle |
| 7 | [Magic_Link](./Magic_Link/) | Passwordless sign-in — email field that sends a magic link |
| 8 | [Social_Login](./Social_Login/) | Google, GitHub, and X (Twitter) OAuth buttons with email fallback |

---

## Structure

Each template is fully self-contained:

```
Auth_Templates/
├── Login/
│   ├── scss/
│   │   ├── _variables.scss   # Design tokens
│   │   ├── _base.scss        # Reset, box-sizing, centered body
│   │   ├── _form.scss        # Auth card, inputs, buttons, links
│   │   ├── _responsive.scss  # Mobile adjustments
│   │   └── main.scss         # Entry point
│   ├── index.html
│   ├── styles.css
│   └── styles.min.css
├── Signup/             # Same structure
├── Forgot_Password/    # Same structure
├── Reset_Password/     # Same structure
├── OTP_Verification/   # Same structure + OTP digit inputs
├── Two_Factor_Auth/    # Same structure + method toggle + OTP inputs
├── Magic_Link/         # Same structure
└── Social_Login/       # Same structure + social provider buttons
```

---

## Shared Design System

All 8 templates use the same design tokens in `scss/_variables.scss`:

```scss
$primary:       #4f46e5;   // Brand color — buttons, focus rings, links
$primary-dark:  #3730a3;   // Button hover state
$primary-light: #e0e7ff;   // Focus ring glow
$danger:        #ef4444;   // Error states
$success:       #10b981;   // Success states
$text:          #1f2937;   // Body text
$muted:         #6b7280;   // Labels, hints, secondary text
$bg:            #f3f4f6;   // Page background
$border:        #e5e7eb;   // Input and card borders
$radius:        10px;      // Input border radius
$radius-lg:     16px;      // Card border radius
$bp-mobile:     480px;     // Mobile breakpoint
```

Edit these tokens in any template's `_variables.scss` to retheme it instantly.

---

## Features

### Accessibility
- All form inputs have `<label>` elements with matching `for`/`id` pairs
- OTP inputs use `role="group"` with `aria-label` and individual `aria-label` per digit
- `autocomplete` attributes set correctly on all inputs
- `novalidate` on forms — validation is handled in JS, not browser defaults
- `aria-hidden="true"` on decorative icons

### Responsiveness
On screens ≤ 480px the card border, shadow, and background are removed so the form fills the screen naturally.

### JavaScript
Each template includes a minimal inline `<script>` that:
- Prevents default form submission
- Shows a placeholder `alert()` indicating where to wire up the backend
- OTP/2FA templates include auto-advance focus logic between digit inputs
- Two_Factor_Auth includes the method toggle (Authenticator App / SMS)

### Navigation
Templates are cross-linked where logical:
- Login → Forgot Password, Signup
- Signup → Login
- Forgot Password → Login
- Reset Password → Login
- OTP / 2FA / Magic Link → Login

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

## Before Deploying

- Replace the `MyBrand` logo text with your own brand name or logo image
- Replace `favicon.ico` with your own
- Wire up form submissions to your backend or auth provider (e.g. Firebase, Auth0, Supabase)
- Replace `alert()` placeholders in each `<script>` with real logic
- For Social Login, replace the `btn-social` click handlers with your OAuth flow

---

## License

All templates are open source and available under the [MIT License](https://opensource.org/licenses/MIT).
