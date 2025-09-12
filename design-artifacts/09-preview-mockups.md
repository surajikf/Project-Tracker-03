# IKF Project Live Tracker – Preview Mockups (Representative Project)

Project: Acme Website Revamp
PM: Priya Nair | Department: Website | Client: Acme Corp
Breadcrumbs: Home › Projects › Acme Website Revamp › Stages

## Snapshot A — 35% Completion (At Risk, Client Hold)

Header
- Status: Ongoing
- Progress bar: 35% (color bucket: 25–49 = At Risk / Orange)
- Primary action (PM): Add stage | Secondary: Request approval

Banners
- Client Hold (amber): “Client Hold: Waiting for content approval — since 2024-09-10 (2d).”
  - Actions: View details | Contact client | Resolve hold (Admin/PM)
- Audit cue (visible to Super Admin/Admin): “Last changed by Karan Shah on 2024-09-11 13:40.”

Overview (Weighted Stages)
- Planning 100% (10%) | Design 40% (25%) | Development 10% (40%) | Testing 0% (20%) | Launch 0% (5%)
- Tooltip (stage weights) on progress bar

Stages (selected: Design)
- Stage: Design — Sub-status: In Progress
- Owner: Karan Shah | Due: 2024-09-20 | Toggle: Enabled (PM/Admin)
- Approval chip: “Awaiting client approval: Concept A”
- Inline action (PM): Request approval

Approvals Drawer (Client)
- Title: “Design Concept A — Orchid eCommerce” (example)
- CTA: Approve | Request changes
- Comments box (required for Request changes)

Tables
- Columns visible to PM/Admin: Project | Client | PM | Status | Progress | Due | Actions
- Cost column hidden from Team/Client

## Snapshot B — 70% Completion (On Track, No Holds)

Header
- Status: Ongoing
- Progress bar: 70% (color bucket: 50–74 = On Track / Yellow)
- Primary action (PM): Add stage | Secondary: Generate report

Banners
- None (no holds)
- Audit cue: “Last changed by Priya Nair on 2024-09-14 09:05.”

Overview (Weighted Stages)
- Planning 100% (10%) | Design 90% (25%) | Development 60% (40%) | Testing 20% (20%) | Launch 0% (5%)

Stages
- Stage: Development — Sub-status: In Progress
- Owner: Arjun Mehta | Due: 2024-10-05 | Toggle: Enabled (PM/Admin)
- Dependencies: Testing blocked until QA checklist uploaded

Dashboards (Role tiles)
- PM: Portfolio card shows Acme 70%, Orchid 32%, IKF 61%
- Admin: Pipeline shows fewer on-hold badges
- Team (assigned): “My tasks this week” includes Dev tickets for Acme

## Snapshot C — 100% Completion (Complete, Approvals Resolved)

Header
- Status: Completed
- Progress bar: 100% (color bucket: 100 = Complete / Blue)
- Primary action (Admin): Export | Secondary: Archive project

Banners
- Resolved banner (green): “All holds resolved. Project closed 2024-10-30.”
- Client approval badges: “Final QA — Approved on 2024-10-28 by Acme Corp”

Overview (Weighted Stages)
- All stages 100% (weights unchanged)

Stages
- All toggles disabled (read-only). Sub-status: Completed
- Activity stream highlights latest approvals and final deployment

Reports & Exports
- Project-level report ready (PM/Admin): PDF/CSV
- Timesheet summary available (PM/Admin). Hidden from Team/Client

## Accessibility & Responsive Notes (applies to all snapshots)
- Ensure progress-bar contrast meets WCAG 2.2 AA in both light/dark themes.
- 44px minimum hit targets for banner CTAs, stage toggles, and approval buttons.
- Tab order: Header actions → Banners → Overview → Stages → Side panels.
- Mobile: Stages list stacks; progress bar label becomes inline (e.g., “70%”).

## Consistency Checklist
- Holds surfaced on dashboards and project detail in all states.
- Approval status visible where relevant (chips, drawer).
- Column permissions respected (cost hidden from Team/Client).
- Disabled-with-tooltip only where discoverability is required.


