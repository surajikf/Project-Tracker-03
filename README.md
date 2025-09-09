# IKF Project Livetracker — Static Demo (HTML + CSS Only)

A fully static, multi-page demo for the IKF Project Livetracker. No JavaScript, no frameworks. All interactivity is simulated with CSS (anchors, details, checkboxes) and multiple pages.

## Open
- Double-click `index.html` to start. Works offline.

## Pages
- `index.html` — Role select + tour
- `admin.html` — Admin dashboard
- `manager.html` — PM/Dept dashboard
- `team.html` — Team dashboard
- `client.html` — Client portal
- `projects.html` — Projects list
- `project-details.html` — Project tabs, stages, resources, activity
- `timesheets.html` — Timesheets (My + Admin)
- `reports.html` — Reports (tabs + inline SVG charts)
- `resources.html` — Drive links + CSS modals
- `clients.html` — Directory
- `settings.html` — Theme preview
- `404.html` — Not found

## Assets
- `assets/css/styles.css` — Single stylesheet (variables, utilities, components)
- `assets/img/ikf-logo.svg`, `assets/img/favicon.svg`
- `assets/csv/` — `projects.csv`, `timesheets.csv`, `reports.csv`

## Interaction (CSS-only)
- Tabs with `:target` and classes
- Drawers via `<details>`
- Modals via anchor-target overlays
- Toggles via checkboxes (visual only)
- Tables are pre-sorted; headers styled for sort look

## Accessibility
- Semantic HTML5, landmarks, focus-visible, labels/aria where useful

## Branding
- Primary #0A2540, Teal #00BFA6, Saffron #F59E0B, Emerald #10B981, Rose #EF4444, Slate scale

## Notes
- All data is static and hard-coded to match the brief.
- Export links download prepared CSVs from `assets/csv`.
