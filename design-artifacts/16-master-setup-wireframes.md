# IKF Project Live Tracker - Master Setup Wireframes

## Master Setup Navigation

### Left Sidebar with Master Setup
```
┌─────────────────────────────────────────────────────────────────┐
│ IKF Logo                                                        │
├─────────────────────────────────────────────────────────────────┤
│ Dashboard                                                        │
│ Projects                                                         │
│ Timesheets                                                       │
│ Reports                                                          │
│ Resources                                                        │
│ ▼ Master Setup (Super Admin/Admin only)                        │
│   ├── Departments                                               │
│   ├── Projects                                                  │
│   ├── Users                                                     │
│   └── Stages                                                    │
│ Admin                                                            │
│ Settings (Super Admin only)                                     │
│ Help                                                             │
└─────────────────────────────────────────────────────────────────┘
```

### Master Setup Dashboard (Super Admin)
```
┌─────────────────────────────────────────────────────────────────┐
│ IKF | Master Setup Dashboard | [System Settings] [Help]         │
├─────────────────────────────────────────────────────────────────┤
│ Home › Master Setup                                             │
├─────────────────────────────────────────────────────────────────┤
│ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ │
│ │ Departments │ │ Projects    │ │ Users       │ │ Stages      │ │
│ │ 12          │ │ 24          │ │ 47          │ │ 8           │ │
│ │ [Manage]    │ │ [Manage]    │ │ [Manage]    │ │ [Manage]    │ │
│ └─────────────┘ └─────────────┘ └─────────────┘ └─────────────┘ │
├─────────────────────────────────────────────────────────────────┤
│ Recent Activity                                                 │
│ • New department "Sales" created by Admin                      │
│ • User "Sarah Johnson" invited by Admin                        │
│ • Stage "Custom Dev" deactivated by Super Admin                │
│ • Project "Acme Website" assigned to Priya Nair                │
└─────────────────────────────────────────────────────────────────┘
```

## Departments Module Wireframes

### Departments List View
```
┌─────────────────────────────────────────────────────────────────┐
│ Master Setup › Departments                                      │
├─────────────────────────────────────────────────────────────────┤
│ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ │
│ │ Total       │ │ Sub-dept    │ │ Coverage    │ │ Risk        │ │
│ │ Departments │ │ Count       │ │ % Projects  │ │ Unstaffed   │ │
│ │ 12          │ │ 24          │ │ 85%         │ │ 2           │ │
│ └─────────────┘ └─────────────┘ └─────────────┘ └─────────────┘ │
├─────────────────────────────────────────────────────────────────┤
│ [Search] [Filter: All] [Sort: Name] [New Department]           │
├─────────────────────────────────────────────────────────────────┤
│ Department Name │ Sub-Departments │ Head │ Created By │ Updated │
├─────────────────────────────────────────────────────────────────┤
│ Website         │ Design, Dev     │ Priya│ Admin      │ 2d ago │
│ Mobile          │ iOS, Android    │ Arjun│ Admin      │ 1w ago │
│ Marketing       │ Content, SEO    │ -    │ Admin      │ 3d ago │
│ Sales           │ Lead Gen, CRM   │ Sarah│ Admin      │ 5d ago │
└─────────────────────────────────────────────────────────────────┘
```

### Create Department Modal
```
┌─────────────────────────────────────────────────────────────────┐
│ Create Department                                    [Close]     │
├─────────────────────────────────────────────────────────────────┤
│ Department Name                                                 │
│ [________________________________]                             │
│                                                                 │
│ Sub-Departments                                                 │
│ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ [+ Add]        │
│ │ Design      │ │ Development │ │ QA          │                │
│ │ [×]         │ │ [×]         │ │ [×]         │                │
│ └─────────────┘ └─────────────┘ └─────────────┘                │
│                                                                 │
│ Assign Department Head                                          │
│ [Dropdown: Select User]                                         │
│                                                                 │
│ [Cancel] [Create Department]                                    │
└─────────────────────────────────────────────────────────────────┘
```

## Projects Module Wireframes

### Projects List View
```
┌─────────────────────────────────────────────────────────────────┐
│ Master Setup › Projects                                         │
├─────────────────────────────────────────────────────────────────┤
│ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ │
│ │ Customers   │ │ Projects    │ │ Ongoing     │ │ On Hold     │ │
│ │ 8           │ │ 24          │ │ 18          │ │ 3           │ │
│ └─────────────┘ └─────────────┘ └─────────────┘ └─────────────┘ │
│ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ │
│ │ Completed   │ │ Avg Progress│ │ Behind     │ │ Client Hold │ │
│ │ 3           │ │ 67%         │ │ 2           │ │ 1           │ │
│ └─────────────┘ └─────────────┘ └─────────────┘ └─────────────┘ │
├─────────────────────────────────────────────────────────────────┤
│ [Search] [Filter: All Customers] [Sort: Customer] [New Project] │
├─────────────────────────────────────────────────────────────────┤
│ Customer │ Project Name │ Code │ Status │ PM │ Start │ End │ Actions │
├─────────────────────────────────────────────────────────────────┤
│ Acme     │ Website Revamp│ ACME │ Ongoing│ Priya│ 8/1   │ 10/30│ [Edit] │
│ Acme     │ Mobile App    │ ACME2│ On Hold│ Priya│ 9/1   │ 12/15│ [Edit] │
│ Orchid   │ eCommerce    │ ORCH │ Ongoing│ Arjun│ 7/15  │ 11/15│ [Edit] │
│ Vista    │ Corporate Site│ VIST │ Complete│ Priya│ 5/1   │ 5/30 │ [Edit] │
└─────────────────────────────────────────────────────────────────┘
```

### Create Project - Step 1
```
┌─────────────────────────────────────────────────────────────────┐
│ Create Project - Step 1 of 3                                   │
├─────────────────────────────────────────────────────────────────┤
│ Customer                                                         │
│ [Search existing customer...] or [Create new customer]          │
│                                                                 │
│ Project Name                                                     │
│ [________________________________]                             │
│                                                                 │
│ Project Code                                                    │
│ [________________________________]                             │
│                                                                 │
│ Project Description                                              │
│ [________________________________]                             │
│ [________________________________]                             │
│                                                                 │
│ [Cancel] [Next]                                                 │
└─────────────────────────────────────────────────────────────────┘
```

## Users Module Wireframes

### Users List View
```
┌─────────────────────────────────────────────────────────────────┐
│ Master Setup › Users                                            │
├─────────────────────────────────────────────────────────────────┤
│ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ │
│ │ Total Users │ │ Active      │ │ Inactive    │ │ Unassigned  │ │
│ │ 47          │ │ 42          │ │ 5           │ │ 3           │ │
│ └─────────────┘ └─────────────┘ └─────────────┘ └─────────────┘ │
│ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ │
│ │ Super Admin │ │ Admin       │ │ PM          │ │ Team        │ │
│ │ 2           │ │ 3           │ │ 8           │ │ 28          │ │
│ └─────────────┘ └─────────────┘ └─────────────┘ └─────────────┘ │
├─────────────────────────────────────────────────────────────────┤
│ [Search] [Filter: All Roles] [Sort: Name] [Invite User]        │
├─────────────────────────────────────────────────────────────────┤
│ Name │ Email │ Role │ Department(s) │ Project(s) │ Status │ Actions │
├─────────────────────────────────────────────────────────────────┤
│ John │ john@ │ Super│ System Admin │ All Projects│ Active │ [Edit] │
│ Doe  │ ikf.com│ Admin│               │             │        │        │
├─────────────────────────────────────────────────────────────────┤
│ Priya│ priya@│ PM   │ Website       │ Acme, Orchid│ Active │ [Edit] │
│ Nair │ ikf.com│      │               │             │        │        │
├─────────────────────────────────────────────────────────────────┤
│ Sarah│ sarah@│ Team │ Marketing     │ Vista       │ Active │ [Edit] │
│ John │ ikf.com│      │               │             │        │        │
└─────────────────────────────────────────────────────────────────┘
```

### Invite User - Step 1
```
┌─────────────────────────────────────────────────────────────────┐
│ Invite User - Step 1 of 3                                      │
├─────────────────────────────────────────────────────────────────┤
│ Full Name                                                       │
│ [________________________________]                             │
│                                                                 │
│ Email Address                                                   │
│ [________________________________]                             │
│                                                                 │
│ Role                                                            │
│ [Dropdown: Select Role]                                        │
│ • Super Admin (Super Admin only)                              │
│ • Admin                                                        │
│ • Project Manager                                              │
│ • Team Member                                                  │
│ • Client                                                       │
│                                                                 │
│ [Cancel] [Next]                                                │
└─────────────────────────────────────────────────────────────────┘
```

## Stages Module Wireframes

### Stages List View
```
┌─────────────────────────────────────────────────────────────────┐
│ Master Setup › Stages                                           │
├─────────────────────────────────────────────────────────────────┤
│ ┌─────────────────────────┐ ┌─────────────────────────┐        │
│ │ Weight Integrity        │ │ Usage Statistics        │        │
│ │ Active Weight: 100% ✅  │ │ • Handshake: 24 projects│        │
│ │ ████████████████████████│ │ • Design: 22 projects    │        │
│ │ Target: 100%            │ │ • Development: 20       │        │
│ └─────────────────────────┘ └─────────────────────────┘        │
├─────────────────────────────────────────────────────────────────┤
│ [Search] [Filter: All Types] [Sort: Weight] [New Stage]       │
├─────────────────────────────────────────────────────────────────┤
│ Stage Name │ Type │ Weight │ Sub-statuses │ Active │ Usage │ Actions │
├─────────────────────────────────────────────────────────────────┤
│ Handshake  │ Std  │ 10%    │ 3            │ ✅     │ 24    │ [Edit]  │
│ Sitemap    │ Std  │ 5%     │ 2            │ ✅     │ 22    │ [Edit]  │
│ Design     │ Std  │ 25%    │ 4            │ ✅     │ 20    │ [Edit]  │
│ Development│ Std  │ 40%    │ 5            │ ✅     │ 18    │ [Edit]  │
│ QA & Test  │ Std  │ 15%    │ 3            │ ✅     │ 15    │ [Edit]  │
│ Go Live    │ Std  │ 5%     │ 2            │ ✅     │ 12    │ [Edit]  │
└─────────────────────────────────────────────────────────────────┘
```

### Create Stage Modal
```
┌─────────────────────────────────────────────────────────────────┐
│ Create Stage                                        [Close]     │
├─────────────────────────────────────────────────────────────────┤
│ Stage Name                                                       │
│ [________________________________]                             │
│                                                                 │
│ Stage Type                                                       │
│ ○ Standard Stage (used across all projects)                    │
│ ○ Temporary Stage (project-specific)                           │
│                                                                 │
│ Weight Percentage                                               │
│ [____] %                                                        │
│ Current total: 85% | Remaining: 15%                           │
│                                                                 │
│ Sub-statuses (Optional)                                         │
│ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ [+ Add]        │
│ │ In Progress │ │ On Hold     │ │ Completed   │                │
│ │ [×]         │ │ [×]         │ │ [×]         │                │
│ └─────────────┘ └─────────────┘ └─────────────┘                │
│                                                                 │
│ [Cancel] [Create Stage]                                         │
└─────────────────────────────────────────────────────────────────┘
```

## Mobile Wireframes

### Mobile Master Setup Navigation
```
┌─────────────────────────────────────────────────────────────────┐
│ IKF | Master Setup | [☰]                                       │
├─────────────────────────────────────────────────────────────────┤
│ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ │
│ │ Departments │ │ Projects    │ │ Users       │ │ Stages      │ │
│ │ 12          │ │ 24          │ │ 47          │ │ 8           │ │
│ └─────────────┘ └─────────────┘ └─────────────┘ └─────────────┘ │
├─────────────────────────────────────────────────────────────────┤
│ ┌─────────────────────────────────────────────────────────────┐ │
│ │ Departments                                                 │ │
│ │ • Website (Design, Dev) - Priya Nair                      │ │
│ │ • Mobile (iOS, Android) - Arjun Mehta                     │ │
│ │ • Marketing (Content, SEO) - Unassigned                   │ │
│ │ • Sales (Lead Gen, CRM) - Sarah Johnson                   │ │
│ └─────────────────────────────────────────────────────────────┘ │
│ ┌─────────────────────────────────────────────────────────────┐ │
│ │ Recent Activity                                             │ │
│ │ • New department "Sales" created                           │ │
│ │ • User "Sarah Johnson" invited                             │ │
│ │ • Stage "Custom Dev" deactivated                           │ │
│ └─────────────────────────────────────────────────────────────┘ │
└─────────────────────────────────────────────────────────────────┘
```

### Mobile Bottom Navigation
```
Bottom Navigation Bar
┌─────────────────────────────────────────────────────────────────┐
│ [🏠] [📋] [⏰] [📊] [📁] [⚙️] [☰]                             │
│ Home  Projects Timesheets Reports Resources Setup Menu         │
└─────────────────────────────────────────────────────────────────┘
```

## Responsive Behavior

### Desktop (1024px+)
- Full sidebar with Master Setup expandable section
- Multi-column analytics widgets
- Complete table displays with all columns
- Modal overlays for create/edit operations

### Tablet (768px-1023px)
- Collapsible sidebar with Master Setup section
- Two-column analytics widgets
- Condensed tables with horizontal scroll
- Full-width modals

### Mobile (360px-767px)
- Bottom navigation (Master Setup hidden for non-admin roles)
- Single-column analytics cards
- Stacked table rows
- Bottom sheet modals

## Permission States

### Insufficient Permissions Page
```
┌─────────────────────────────────────────────────────────────────┐
│ Access Restricted                                               │
├─────────────────────────────────────────────────────────────────┤
│ You don't have permission to access Master Setup modules.      │
│                                                                 │
│ Master Setup is only available to:                             │
│ • Super Admin (full access)                                    │
│ • Admin (organizational scope)                                 │
│                                                                 │
│ Contact your administrator for access.                         │
│                                                                 │
│ [Return to Dashboard] [Contact Admin]                          │
└─────────────────────────────────────────────────────────────────┘
```

### Disabled Action Tooltip
```
┌─────────────────────────────────────────────────────────────────┐
│ [Delete Department] (disabled)                                 │
│ Tooltip: "Requires Super Admin access"                        │
└─────────────────────────────────────────────────────────────────┘
```
