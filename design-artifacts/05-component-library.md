# IKF Project Live Tracker - Component Library

## Role Badge System

### Role Badge Specifications
```
Super Admin Badge
┌─────────────────┐
│ ● Super Admin   │
│   #000000       │
│   Contrast: 21:1│
└─────────────────┘

Admin Badge
┌─────────────────┐
│ ● Admin         │
│   #475569       │
│   Contrast: 4.5:1│
└─────────────────┘

Project Manager Badge
┌─────────────────┐
│ ● PM            │
│   #4F46E5       │
│   Contrast: 4.5:1│
└─────────────────┘

Team Member Badge
┌─────────────────┐
│ ● Team          │
│   #0D9488       │
│   Contrast: 4.5:1│
└─────────────────┘

Client Badge
┌─────────────────┐
│ ● Client        │
│   #2563EB       │
│   Contrast: 4.5:1│
└─────────────────┘
```

### Role Badge CSS Tokens
```css
:root {
  /* Role Colors */
  --role-super-admin: #000000;
  --role-admin: #475569;
  --role-pm: #4F46E5;
  --role-team: #0D9488;
  --role-client: #2563EB;
  
  /* Role Backgrounds */
  --role-super-admin-bg: rgba(0, 0, 0, 0.1);
  --role-admin-bg: rgba(71, 85, 105, 0.1);
  --role-pm-bg: rgba(79, 70, 229, 0.1);
  --role-team-bg: rgba(13, 148, 136, 0.1);
  --role-client-bg: rgba(37, 99, 235, 0.1);
  
  /* Role Borders */
  --role-super-admin-border: #000000;
  --role-admin-border: #475569;
  --role-pm-border: #4F46E5;
  --role-team-border: #0D9488;
  --role-client-border: #2563EB;
}
```

### Role Badge Component States
```
Default State
┌─────────────────┐
│ ● Super Admin   │
│   Background: rgba(0,0,0,0.1) │
│   Border: 1px solid #000000   │
│   Text: #000000               │
└─────────────────┘

Hover State
┌─────────────────┐
│ ● Super Admin   │
│   Background: rgba(0,0,0,0.15)│
│   Border: 1px solid #000000   │
│   Text: #000000               │
│   Transform: translateY(-1px) │
└─────────────────┘

Active State
┌─────────────────┐
│ ● Super Admin   │
│   Background: #000000         │
│   Border: 1px solid #000000   │
│   Text: #FFFFFF               │
│   Box-shadow: 0 2px 4px rgba(0,0,0,0.2) │
└─────────────────┘

Disabled State
┌─────────────────┐
│ ● Super Admin   │
│   Background: rgba(0,0,0,0.05)│
│   Border: 1px solid #E2E8F0   │
│   Text: #94A3B8               │
│   Opacity: 0.6                │
└─────────────────┘
```

## Progress Bar Component

### Weighted Progress Bar
```
Progress Bar with Stage Weights
┌─────────────────────────────────────────────────────────────────┐
│ ████████████████████████████████████████████████████████████████│
│ 48% Complete                                                   │
└─────────────────────────────────────────────────────────────────┘

Stage Breakdown Tooltip
┌─────────────────────────────────────────────────────────────────┐
│ Stage Weights:                                                 │
│ • Planning: 100% (Weight: 10%)                                │
│ • Design: 80% (Weight: 25%)                                   │
│ • Development: 30% (Weight: 40%)                              │
│ • Testing: 0% (Weight: 20%)                                   │
│ • Launch: 0% (Weight: 5%)                                     │
└─────────────────────────────────────────────────────────────────┘
```

### Progress Bar Color System
```css
:root {
  /* Progress Colors */
  --progress-critical: #EF4444;    /* 0-24% */
  --progress-at-risk: #F59E0B;     /* 25-49% */
  --progress-on-track: #EAB308;    /* 50-74% */
  --progress-almost: #10B981;      /* 75-99% */
  --progress-complete: #2563EB;    /* 100% */
  
  /* Progress Backgrounds */
  --progress-bg: #F1F5F9;
  --progress-border: #E2E8F0;
  
  /* Progress Heights */
  --progress-height-sm: 6px;
  --progress-height-md: 10px;
  --progress-height-lg: 16px;
}
```

### Progress Bar States
```
Default State
┌─────────────────────────────────────────────────────────────────┐
│ ████████████████████████████████████████████████████████████████│
│ 48% Complete                                                   │
│ Background: #F1F5F9                                            │
│ Border: 1px solid #E2E8F0                                     │
│ Fill: #EAB308 (on-track color)                                │
└─────────────────────────────────────────────────────────────────┘

Hover State
┌─────────────────────────────────────────────────────────────────┐
│ ████████████████████████████████████████████████████████████████│
│ 48% Complete                                                   │
│ Background: #F8FAFC                                            │
│ Border: 1px solid #CBD5E1                                     │
│ Fill: #EAB308 (on-track color)                                │
│ Box-shadow: 0 2px 4px rgba(0,0,0,0.1)                        │
└─────────────────────────────────────────────────────────────────┘

Loading State
┌─────────────────────────────────────────────────────────────────┐
│ ████████████████████████████████████████████████████████████████│
│ Loading...                                                     │
│ Background: #F1F5F9                                            │
│ Border: 1px solid #E2E8F0                                     │
│ Fill: Animated gradient                                        │
└─────────────────────────────────────────────────────────────────┘
```

## Hold Banner Components

### Client Hold Banner
```
Client Hold Banner
┌─────────────────────────────────────────────────────────────────┐
│ ⚠️ Client Hold: Waiting for content approval (2 days)          │
│ Reason: Client requested changes to homepage copy              │
│ Started: 2024-09-10 by Priya Nair                             │
│ [Resolve Hold] [Contact Client] [View Details]                 │
└─────────────────────────────────────────────────────────────────┘
```

### Team Hold Banner
```
Team Hold Banner
┌─────────────────────────────────────────────────────────────────┐
│ ⚠️ Team Hold: Design assets delayed (1 day)                    │
│ Reason: Designer unavailable due to illness                    │
│ Started: 2024-09-11 by Karan Shah                             │
│ [Resolve Hold] [Reassign] [View Details]                       │
└─────────────────────────────────────────────────────────────────┘
```

### Hold Banner CSS Tokens
```css
:root {
  /* Hold Colors */
  --hold-client: #F59E0B;        /* Amber */
  --hold-team: #8B5CF6;          /* Purple */
  --hold-client-bg: rgba(245, 158, 11, 0.1);
  --hold-team-bg: rgba(139, 92, 246, 0.1);
  
  /* Hold Borders */
  --hold-client-border: #F59E0B;
  --hold-team-border: #8B5CF6;
  
  /* Hold Text */
  --hold-client-text: #92400E;
  --hold-team-text: #6B21A8;
}
```

### Hold Banner States
```
Default State
┌─────────────────────────────────────────────────────────────────┐
│ ⚠️ Client Hold: Waiting for content approval (2 days)          │
│ Background: rgba(245, 158, 11, 0.1)                           │
│ Border: 1px solid #F59E0B                                      │
│ Text: #92400E                                                  │
└─────────────────────────────────────────────────────────────────┘

Dismissed State
┌─────────────────────────────────────────────────────────────────┐
│ ✅ Client Hold Resolved                                        │
│ Background: rgba(16, 185, 129, 0.1)                           │
│ Border: 1px solid #10B981                                      │
│ Text: #065F46                                                  │
└─────────────────────────────────────────────────────────────────┘
```

## Table Components

### Role-Based Table Columns
```
Super Admin Table
┌─────────────────────────────────────────────────────────────────┐
│ Project | Client | PM | Status | Progress | Cost | Actions      │
│ Acme    | Acme   | Priya| Ongoing| 48%     | $45K | [Edit]      │
└─────────────────────────────────────────────────────────────────┘

Admin Table
┌─────────────────────────────────────────────────────────────────┐
│ Project | Client | PM | Status | Progress | Cost | Actions      │
│ Acme    | Acme   | Priya| Ongoing| 48%     | $45K | [Edit]      │
└─────────────────────────────────────────────────────────────────┘

PM Table
┌─────────────────────────────────────────────────────────────────┐
│ Project | Client | Status | Progress | Team | Actions           │
│ Acme    | Acme   | Ongoing| 48%     | 4    | [Edit]            │
└─────────────────────────────────────────────────────────────────┘

Team Table
┌─────────────────────────────────────────────────────────────────┐
│ Project | Status | Progress | My Tasks | Actions               │
│ Acme    | Ongoing| 48%     | 3        | [View]                │
└─────────────────────────────────────────────────────────────────┘

Client Table
┌─────────────────────────────────────────────────────────────────┐
│ Project | Status | Progress | Deliverables | Actions           │
│ Acme    | Ongoing| 48%     | 2 Pending   | [Approve]          │
└─────────────────────────────────────────────────────────────────┘
```

### Table Component States
```
Default State
┌─────────────────────────────────────────────────────────────────┐
│ Header: #F8FAFC background, #334155 text                       │
│ Row: #FFFFFF background, #0F172A text                          │
│ Border: 1px solid #E2E8F0                                      │
│ Hover: #FBFDFD background                                       │
└─────────────────────────────────────────────────────────────────┘

Loading State
┌─────────────────────────────────────────────────────────────────┐
│ Header: #F8FAFC background, #334155 text                       │
│ Row: Skeleton placeholder with shimmer animation               │
│ Border: 1px solid #E2E8F0                                      │
└─────────────────────────────────────────────────────────────────┘

Empty State
┌─────────────────────────────────────────────────────────────────┐
│ No projects found                                              │
│ Create your first project to get started                       │
│ [New Project Button]                                           │
└─────────────────────────────────────────────────────────────────┘
```

## Button Components

### Role-Specific Primary Actions
```
Super Admin Primary Actions
┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐
│ Manage Org      │ │ System Settings │ │ Audit Logs      │
│ #000000         │ │ #000000         │ │ #000000         │
└─────────────────┘ └─────────────────┘ └─────────────────┘

Admin Primary Actions
┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐
│ New Project     │ │ Manage Users    │ │ Export Data     │
│ #475569         │ │ #475569         │ │ #475569         │
└─────────────────┘ └─────────────────┘ └─────────────────┘

PM Primary Actions
┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐
│ Add Stage       │ │ New Project     │ │ Request Approval│
│ #4F46E5         │ │ #4F46E5         │ │ #4F46E5         │
└─────────────────┘ └─────────────────┘ └─────────────────┘

Team Primary Actions
┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐
│ Log Time        │ │ View Tasks      │ │ Access Resources│
│ #0D9488         │ │ #0D9488         │ │ #0D9488         │
└─────────────────┘ └─────────────────┘ └─────────────────┘

Client Primary Actions
┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐
│ Approve         │ │ Request Changes │ │ Submit Feedback │
│ #2563EB         │ │ #2563EB         │ │ #2563EB         │
└─────────────────┘ └─────────────────┘ └─────────────────┘
```

### Button States
```
Default State
┌─────────────────┐
│ New Project     │
│ Background: #475569 │
│ Text: #FFFFFF   │
│ Border: 1px solid #475569 │
│ Box-shadow: 0 1px 2px rgba(0,0,0,0.06) │
└─────────────────┘

Hover State
┌─────────────────┐
│ New Project     │
│ Background: #374151 │
│ Text: #FFFFFF   │
│ Border: 1px solid #374151 │
│ Box-shadow: 0 6px 16px rgba(0,0,0,0.12) │
│ Transform: translateY(-1px) │
└─────────────────┘

Active State
┌─────────────────┐
│ New Project     │
│ Background: #1F2937 │
│ Text: #FFFFFF   │
│ Border: 1px solid #1F2937 │
│ Box-shadow: 0 1px 2px rgba(0,0,0,0.06) │
│ Transform: translateY(0) │
└─────────────────┘

Disabled State
┌─────────────────┐
│ New Project     │
│ Background: #F1F5F9 │
│ Text: #94A3B8   │
│ Border: 1px solid #E2E8F0 │
│ Box-shadow: none │
│ Cursor: not-allowed │
└─────────────────┘
```

## Modal/Drawer Components

### Impersonation Modal
```
Impersonation Warning Modal
┌─────────────────────────────────────────────────────────────────┐
│ ⚠️ Impersonation Mode                                          │
│ You are now viewing the system as: John Doe (Team Member)      │
│ This action will be logged and audited.                        │
│ [Exit Impersonation] [Continue] [Cancel]                       │
└─────────────────────────────────────────────────────────────────┘
```

### Confirmation Modal
```
Delete Confirmation Modal
┌─────────────────────────────────────────────────────────────────┐
│ Delete Project                                                  │
│ Are you sure you want to delete "Acme Website Revamp"?         │
│ This action cannot be undone.                                  │
│ [Cancel] [Delete Project]                                      │
└─────────────────────────────────────────────────────────────────┘
```

### Drawer Component
```
Project Details Drawer
┌─────────────────────────────────────────────────────────────────┐
│ Project Details                                    [Close]     │
├─────────────────────────────────────────────────────────────────┤
│ Project Information                                             │
│ • Name: Acme Website Revamp                                    │
│ • Client: Acme Corp                                            │
│ • PM: Priya Nair                                               │
│ • Status: Ongoing                                              │
│ • Progress: 48%                                                │
├─────────────────────────────────────────────────────────────────┤
│ Actions                                                         │
│ [Edit Project] [Archive] [Delete] [Export]                     │
└─────────────────────────────────────────────────────────────────┘
```

## Form Components

### Role-Based Form Fields
```
Super Admin Form
┌─────────────────────────────────────────────────────────────────┐
│ Project Name: [________________]                               │
│ Client: [________________]                                     │
│ PM: [Dropdown: All Users]                                     │
│ Department: [Dropdown: All Departments]                       │
│ Budget: [________________]                                     │
│ Start Date: [Date Picker]                                     │
│ Due Date: [Date Picker]                                       │
│ Status: [Dropdown: All Statuses]                              │
│ [Save] [Cancel] [Save & Create Another]                       │
└─────────────────────────────────────────────────────────────────┘

PM Form
┌─────────────────────────────────────────────────────────────────┐
│ Project Name: [________________]                               │
│ Client: [________________]                                     │
│ Department: [Dropdown: Assigned Departments]                  │
│ Budget: [________________]                                     │
│ Start Date: [Date Picker]                                     │
│ Due Date: [Date Picker]                                       │
│ [Save] [Cancel]                                               │
└─────────────────────────────────────────────────────────────────┘
```

## Accessibility Specifications

### Focus States
```css
:root {
  /* Focus Colors */
  --focus-ring: #00BFA6;
  --focus-ring-width: 3px;
  --focus-ring-offset: 2px;
}

/* Focus Styles */
.focus-visible {
  outline: var(--focus-ring-width) solid var(--focus-ring);
  outline-offset: var(--focus-ring-offset);
}
```

### Color Contrast Ratios
- **Super Admin**: 21:1 (AAA)
- **Admin**: 4.5:1 (AA)
- **PM**: 4.5:1 (AA)
- **Team**: 4.5:1 (AA)
- **Client**: 4.5:1 (AA)

### Hit Target Sizes
- **Minimum**: 44px × 44px
- **Recommended**: 48px × 48px
- **Touch-friendly**: 56px × 56px

## Responsive Breakpoints

### Mobile (360px-767px)
- Single-column layout
- Stacked components
- Icon-only navigation
- Bottom sheet modals

### Tablet (768px-1023px)
- Two-column layout
- Collapsible sidebar
- Side drawer modals
- Condensed tables

### Desktop (1024px+)
- Multi-column layout
- Full sidebar
- Center modals
- Full table display
