# IKF Project Live Tracker – Content Style Guide (Role-Aware)

## Voice and Tone
- Professional, concise, action-oriented.
- Plain language; avoid jargon. Prefer verbs over nouns.
- Empathetic in errors; confident in confirmations; neutral in informational copy.
- Role-aware phrasing (address capabilities without exposing internals).

## Global Copy Standards
- Titles: Sentence case (e.g., “Project details”).
- Buttons: Verb-first, present tense (e.g., “Create project”, “Log time”).
- Labels: Noun-first, concise (e.g., “Due date”, “Stage owner”).
- Tooltips: 1 short sentence; start with a verb (e.g., “Requires Admin access”).
- Empty states: 1-line headline + 1-line next step + 1 primary action.
- Date/time: ISO-like display (YYYY-MM-DD); relative time only for activity (“2d ago”).
- Units: Use % for progress, h for hours, ₹ or $ for costs depending on locale.

## Role-Specific Language
- Super Admin: “Manage organization”, “Impersonate user”, “View audit logs”.
- Admin: “New project”, “Manage users”, “Department settings”, “Export data”.
- Project Manager: “Add stage”, “Assign members”, “Request approval”, “Resolve hold”.
- Team Member: “Log time”, “View tasks”, “Update status”, “Open resources”.
- Client (future): “Approve”, “Request changes”, “Leave feedback”.

## Primary Actions by Context
- Dashboard: Use single clear primary aligned to role.
- Project list: “New project” (Admin/PM); none for Team/Client.
- Project details: “Add stage” (PM), “Manage org” (Super Admin), “Approve” (Client).

## Tooltips and Disabled States
- Rule: Hide components without permission. If discoverability is needed, show disabled with explanatory tooltip.
- Standard string: “Requires {Role} access”. Examples:
  - “Requires Super Admin access” (system settings)
  - “Requires Admin access” (user management)
  - “Requires PM access” (stage edits)

## Toasts (Inline notifications)
- Types: success, warning, error, info.
- Anatomy: short title + optional detail; include SR-only variant.
- Examples:
  - Success: “Stage saved.” SR-only: “Success: Stage saved.”
  - Warning: “Client hold active.” SR-only: “Warning: Client hold active on Acme Website.”
  - Error: “Couldn’t save stage.” SR-only: “Error: Stage was not saved; check required fields.”

## Confirmation and Destructive Actions
- Confirmation titles are explicit and action-mirroring.
- Buttons: Secondary “Cancel” (default focus), Primary destructive labeled with noun.
- Copy by role:
  - Super Admin: “Delete department? This removes all sub-departments.”
  - Admin: “Archive project? You can restore it later from Settings.”
  - PM: “Remove stage? Tasks in this stage will be unassigned.”
  - Team: Destructive actions not shown.
  - Client: Destructive actions not shown.

## Holds and Approvals Copy
- Client Hold banner (amber): “Client Hold: Waiting for content approval — since {date}.”
- Team Hold banner (purple): “Team Hold: {reason} — since {date}.”
- Approval drawer CTAs (Client): “Approve”, “Request changes”. Confirmation messages:
  - Approve: “Approval recorded.”
  - Request changes: “Change request sent.”

## Empty States (by role)
- Super Admin: “No audit events — system is idle.” Action: “View settings”.
- Admin: “No projects yet — create your first project.” Action: “New project”.
- PM: “No active projects — create or get assigned.” Action: “New project”.
- Team: “No tasks assigned — check with your PM.” Action: “Open resources”.
- Client: “No approvals pending — we’ll notify you.” Action: “View project”.

## Error Messages
- Be specific, actionable, and short. Include field highlight where applicable.
- Field-level: “Enter a valid date (YYYY-MM-DD).”
- Form-level: “We couldn’t save your changes. Fix the errors and try again.”
- Permission: “You don’t have permission to do that.” (Don’t expose internal policy names.)

## Search Copy
- Global (Super Admin/Admin): Placeholder “Search projects, users, departments, resources”.
- Scoped (PM/Team): Placeholder “Search my projects, stages, resources”.
- Client: Placeholder “Search assigned projects and deliverables”.

## Breadcrumbs
- Pattern: “Home › {Section} › {Item}”.
- Use role-neutral nouns. Example: “Home › Projects › Acme Website Revamp › Stages”.

## Impersonation (Super Admin)
- Modal title: “Impersonation mode”.
- Modal body: “You are about to view the system as {user} ({role}). This action will be logged.”
- Banner: “Impersonating: {user} ({role})”. CTA: “Exit impersonation”.

## Accessibility Microcopy
- Links: Descriptive (“Open project details”), avoid “Click here”.
- Alt text: Functional (“IKF logo”), omit “image of”.
- Keyboard: Document shortcuts only where provided (e.g., “Press / to search”).
- SR-only: Provide equivalents for all toasts and banners.

## Internationalization Readiness
- Avoid concatenating variables in sentences that could reorder in other locales.
- Keep strings concise to limit wrapping at mobile breakpoints.

## Writing Checklist
- Clear audience and role.
- Verb-first buttons; sentence-case titles.
- One idea per sentence in helper text.
- Permission tooltips applied where needed.
- SR-only variants for all toasts and critical banners.


