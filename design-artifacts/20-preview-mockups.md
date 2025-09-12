# IKF Project Live Tracker - Master Setup Preview Mockups

## Master Setup Dashboard Overview

### Super Admin Master Setup Dashboard
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
│                                                                 │
│ System Health                                                   │
│ • All modules operational ✅                                   │
│ • Last backup: 2 hours ago                                     │
│ • Audit log: 1,234 entries today                               │
└─────────────────────────────────────────────────────────────────┘
```

## Departments Module Mockups

### Departments List with Analytics
```
┌─────────────────────────────────────────────────────────────────┐
│ Master Setup › Departments                                      │
├─────────────────────────────────────────────────────────────────┤
│ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ │
│ │ Total       │ │ Sub-dept    │ │ Coverage    │ │ Risk        │ │
│ │ Departments │ │ Count       │ │ % Projects  │ │ Unstaffed   │ │
│ │ 12          │ │ 24          │ │ 85%         │ │ 2           │ │
│ │ +2 this month│ │ +4 this week│ │ +5% vs last │ │ ⚠️ Needs    │ │
│ └─────────────┘ └─────────────┘ └─────────────┘ └─────────────┘ │
├─────────────────────────────────────────────────────────────────┤
│ Coverage Heatmap: ████████████████████████████████████████████ │
│ Website: 8 projects | Mobile: 6 projects | Marketing: 4 projects │
├─────────────────────────────────────────────────────────────────┤
│ [Search departments...] [Filter: All] [Sort: Name] [New Department] │
├─────────────────────────────────────────────────────────────────┤
│ Department Name │ Sub-Departments │ Head │ Created By │ Updated │
├─────────────────────────────────────────────────────────────────┤
│ Website         │ Design, Dev     │ Priya│ Admin      │ 2d ago │
│ Mobile          │ iOS, Android    │ Arjun│ Admin      │ 1w ago │
│ Marketing       │ Content, SEO    │ -    │ Admin      │ 3d ago │
│ Sales           │ Lead Gen, CRM   │ Sarah│ Admin      │ 5d ago │
│ Design          │ UI, UX          │ Karan│ Admin      │ 1d ago │
│ Development     │ Frontend, Backend│ Mike│ Admin      │ 4d ago │
└─────────────────────────────────────────────────────────────────┘
```

### Create Department Modal
```
┌─────────────────────────────────────────────────────────────────┐
│ Create Department                                    [Close]     │
├─────────────────────────────────────────────────────────────────┤
│ Department Name *                                               │
│ [Quality Assurance              ] ✅                          │
│                                                                 │
│ Sub-Departments *                                               │
│ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ [+ Add]        │
│ │ Testing     │ │ Automation  │ │ Manual QA   │                │
│ │ [×]         │ │ [×]         │ │ [×]         │                │
│ └─────────────┘ └─────────────┘ └─────────────┘                │
│                                                                 │
│ Assign Department Head                                          │
│ [Dropdown: Select User]                                         │
│ • Priya Nair (PM)                                              │
│ • Arjun Mehta (PM)                                             │
│ • Sarah Johnson (Team)                                         │
│                                                                 │
│ [Cancel] [Create Department]                                   │
└─────────────────────────────────────────────────────────────────┘
```

## Projects Module Mockups

### Projects List with Customer Hierarchy
```
┌─────────────────────────────────────────────────────────────────┐
│ Master Setup › Projects                                         │
├─────────────────────────────────────────────────────────────────┤
│ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ │
│ │ Customers   │ │ Projects    │ │ Ongoing     │ │ On Hold     │ │
│ │ 8           │ │ 24          │ │ 18          │ │ 3           │ │
│ │ +1 this week│ │ +3 this week│ │ +2 this week│ │ -1 this week│ │
│ └─────────────┘ └─────────────┘ └─────────────┘ └─────────────┘ │
│ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ │
│ │ Completed   │ │ Avg Progress│ │ Behind     │ │ Client Hold │ │
│ │ 3           │ │ 67%         │ │ 2           │ │ 1           │ │
│ │ +1 this week│ │ +5% vs last │ │ ⚠️ At risk  │ │ ⚠️ Needs    │ │
│ └─────────────┘ └─────────────┘ └─────────────┘ └─────────────┘ │
├─────────────────────────────────────────────────────────────────┤
│ PM Load Distribution                                            │
│ • Priya Nair: 6 projects (25%)                                 │
│ • Arjun Mehta: 4 projects (17%)                                │
│ • Sarah Johnson: 3 projects (12%)                              │
│ • Mike Chen: 2 projects (8%)                                   │
│ • Others: 9 projects (38%)                                      │
├─────────────────────────────────────────────────────────────────┤
│ [Search projects...] [Filter: All Customers] [Sort: Customer] [New Project] │
├─────────────────────────────────────────────────────────────────┤
│ Customer │ Project Name │ Code │ Status │ PM │ Start │ End │ Actions │
├─────────────────────────────────────────────────────────────────┤
│ Acme     │ Website Revamp│ ACME │ Ongoing│ Priya│ 8/1   │ 10/30│ [Edit] │
│ Acme     │ Mobile App    │ ACME2│ On Hold│ Priya│ 9/1   │ 12/15│ [Edit] │
│ Orchid   │ eCommerce    │ ORCH │ Ongoing│ Arjun│ 7/15  │ 11/15│ [Edit] │
│ Vista    │ Corporate Site│ VIST │ Complete│ Priya│ 5/1   │ 5/30 │ [Edit] │
│ BlueWave │ Microsite     │ BLUE │ Ongoing│ Arjun│ 8/15  │ 12/10│ [Edit] │
│ IKF      │ Marketing Site│ IKF  │ Ongoing│ Priya│ 7/1   │ 10/5 │ [Edit] │
└─────────────────────────────────────────────────────────────────┘
```

### Create Project - Step 2 (Timeline & Assignment)
```
┌─────────────────────────────────────────────────────────────────┐
│ Create Project - Step 2 of 3                                   │
├─────────────────────────────────────────────────────────────────┤
│ ●─────●─────○                                                   │
│ Basic  Timeline  Resources                                     │
│ Info   & Assign  & Settings                                    │
├─────────────────────────────────────────────────────────────────┤
│ Timeline                                                         │
│ Start Date *: [8/15/2024]                                      │
│ End Date *: [12/10/2024]                                        │
│ Duration: 117 days                                             │
│                                                                 │
│ Assign Project Manager *                                        │
│ [Priya Nair ▼]                                                 │
│ • Priya Nair (PM) - 6 active projects                          │
│ • Arjun Mehta (PM) - 4 active projects                         │
│ • Sarah Johnson (Team) - Not available                         │
│                                                                 │
│ Assign Departments *                                            │
│ ☑ Website                                                       │
│ ☑ Mobile                                                        │
│ ☐ Marketing                                                     │
│ ☐ Sales                                                         │
│                                                                 │
│ Budget (Optional)                                               │
│ [$45,000]                                                       │
│                                                                 │
│ [Previous] [Next]                                               │
└─────────────────────────────────────────────────────────────────┘
```

## Users Module Mockups

### Users List with Role Distribution
```
┌─────────────────────────────────────────────────────────────────┐
│ Master Setup › Users                                            │
├─────────────────────────────────────────────────────────────────┤
│ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ │
│ │ Total Users │ │ Active      │ │ Inactive    │ │ Unassigned  │ │
│ │ 47          │ │ 42          │ │ 5           │ │ 3           │ │
│ │ +3 this week│ │ +2 this week│ │ +1 this week│ │ ⚠️ Needs    │ │
│ └─────────────┘ └─────────────┘ └─────────────┘ └─────────────┘ │
│ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ │
│ │ Super Admin │ │ Admin       │ │ PM          │ │ Team        │ │
│ │ 2           │ │ 3           │ │ 8           │ │ 28          │ │
│ │ 4%          │ │ 6%          │ │ 17%         │ │ 60%         │ │
│ └─────────────┘ └─────────────┘ └─────────────┘ └─────────────┘ │
│ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ │
│ │ Client      │ │ No 2FA      │ │ Default Pwd │ │ Last Login  │ │
│ │ 6           │ │ 12          │ │ 8           │ │ 2d ago      │ │
│ │ 13%         │ │ ⚠️ Security  │ │ ⚠️ Security  │ │ Active      │ │
│ └─────────────┘ └─────────────┘ └─────────────┘ └─────────────┘ │
├─────────────────────────────────────────────────────────────────┤
│ Role Distribution                                               │
│ ┌─────────────────────────┐ ┌─────────────────────────┐        │
│ │        ████████         │ │ Super Admin: 2 (4%)    │        │
│ │     ██████████████      │ │ Admin: 3 (6%)          │        │
│ │  ████████████████████   │ │ PM: 8 (17%)            │        │
│ │ ██████████████████████  │ │ Team: 28 (60%)         │        │
│ │                         │ │ Client: 6 (13%)        │        │
│ └─────────────────────────┘ └─────────────────────────┘        │
├─────────────────────────────────────────────────────────────────┤
│ [Search users...] [Filter: All Roles] [Sort: Name] [Invite User] │
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
├─────────────────────────────────────────────────────────────────┤
│ Mike │ mike@ │ Team │ Development   │ BlueWave    │ Active │ [Edit] │
│ Chen │ ikf.com│      │               │             │        │        │
└─────────────────────────────────────────────────────────────────┘
```

### Invite User - Step 2 (Assignments)
```
┌─────────────────────────────────────────────────────────────────┐
│ Invite User - Step 2 of 3                                      │
├─────────────────────────────────────────────────────────────────┤
│ ●─────●─────○                                                   │
│ Basic  Assign  Access                                           │
│ Info   ments   & Security                                       │
├─────────────────────────────────────────────────────────────────┤
│ Assign to Departments * (for PM/Team roles)                    │
│ ☑ Website                                                       │
│ ☑ Mobile                                                        │
│ ☐ Marketing                                                     │
│ ☐ Sales                                                         │
│ ☐ Design                                                        │
│ ☐ Development                                                   │
│                                                                 │
│ Assign to Projects (Optional)                                   │
│ ☑ Acme Website Revamp                                          │
│ ☑ Orchid eCommerce Launch                                      │
│ ☐ Vista Realty Corporate Site                                  │
│ ☐ BlueWave Foods Microsite                                     │
│ ☐ IKF Marketing Site Refresh                                    │
│                                                                 │
│ Department Coverage: 2/6 departments (33%)                     │
│ Project Coverage: 2/5 projects (40%)                           │
│                                                                 │
│ [Previous] [Next]                                               │
└─────────────────────────────────────────────────────────────────┘
```

## Stages Module Mockups

### Stages List with Weight Management
```
┌─────────────────────────────────────────────────────────────────┐
│ Master Setup › Stages                                           │
├─────────────────────────────────────────────────────────────────┤
│ ┌─────────────────────────┐ ┌─────────────────────────┐        │
│ │ Weight Integrity        │ │ Usage Statistics        │        │
│ │ Active Weight: 100% ✅  │ │ • Handshake: 24 projects│        │
│ │ ████████████████████████│ │ • Sitemap: 22 projects   │        │
│ │ Target: 100%            │ │ • Design: 20 projects   │        │
│ │                         │ │ • Development: 18        │        │
│ │ [Normalize Weights]     │ │ • QA & Testing: 15      │        │
│ └─────────────────────────┘ └─────────────────────────┘        │
├─────────────────────────────────────────────────────────────────┤
│ Risk Indicators                                                 │
│ ⚠️ 2 projects missing required standard stages                │
│ • Acme Mobile App: Missing "QA & Testing"                      │
│ • BlueWave Microsite: Missing "Go Live"                       │
│                                                                 │
│ [Fix Missing Stages] [View All Projects]                       │
├─────────────────────────────────────────────────────────────────┤
│ [Search stages...] [Filter: All Types] [Sort: Weight] [New Stage] │
├─────────────────────────────────────────────────────────────────┤
│ Stage Name │ Type │ Weight │ Sub-statuses │ Active │ Usage │ Actions │
├─────────────────────────────────────────────────────────────────┤
│ Handshake  │ Std  │ 10%    │ 3            │ ✅     │ 24    │ [Edit]  │
│ Sitemap    │ Std  │ 5%     │ 2            │ ✅     │ 22    │ [Edit]  │
│ Data Gather│ Std  │ 5%     │ 2            │ ✅     │ 20    │ [Edit]  │
│ Content    │ Std  │ 10%    │ 3            │ ✅     │ 18    │ [Edit]  │
│ Design     │ Std  │ 25%    │ 4            │ ✅     │ 20    │ [Edit]  │
│ Development│ Std  │ 40%    │ 5            │ ✅     │ 18    │ [Edit]  │
│ QA & Test  │ Std  │ 15%    │ 3            │ ✅     │ 15    │ [Edit]  │
│ Go Live    │ Std  │ 5%     │ 2            │ ✅     │ 12    │ [Edit]  │
└─────────────────────────────────────────────────────────────────┘
```

### Create Stage Modal with Weight Validation
```
┌─────────────────────────────────────────────────────────────────┐
│ Create Stage                                        [Close]     │
├─────────────────────────────────────────────────────────────────┤
│ Stage Name *                                                    │
│ [Custom Development             ] ✅                           │
│                                                                 │
│ Stage Type *                                                    │
│ ○ Standard Stage (used across all projects)                  │
│ ○ Temporary Stage (project-specific) ✅                        │
│                                                                 │
│ Weight Percentage *                                             │
│ [10] %                                                          │
│ Current total: 90% | Remaining: 10% ✅                        │
│                                                                 │
│ Sub-statuses (Optional)                                         │
│ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ [+ Add]        │
│ │ In Progress │ │ On Hold     │ │ Completed   │                │
│ │ [×]         │ │ [×]         │ │ [×]         │                │
│ └─────────────┘ └─────────────┘ └─────────────┘                │
│                                                                 │
│ Usage Preview                                                   │
│ This stage will be available for:                              │
│ • New project creation                                          │
│ • Existing project stage management                             │
│ • Progress tracking and reporting                               │
│                                                                 │
│ [Cancel] [Create Stage]                                         │
└─────────────────────────────────────────────────────────────────┘
```

## Mobile Mockups

### Mobile Master Setup Dashboard
```
┌─────────────────────────────────────────────────────────────────┐
│ IKF | Master Setup | [☰]                                       │
├─────────────────────────────────────────────────────────────────┤
│ ┌─────────────┐ ┌─────────────┐                                │
│ │ Departments │ │ Projects    │                                │
│ │ 12          │ │ 24          │                                │
│ └─────────────┘ └─────────────┘                                │
│ ┌─────────────┐ ┌─────────────┐                                │
│ │ Users       │ │ Stages      │                                │
│ │ 47          │ │ 8           │                                │
│ └─────────────┘ └─────────────┘                                │
├─────────────────────────────────────────────────────────────────┤
│ ┌─────────────────────────────────────────────────────────────┐ │
│ │ Recent Activity                                             │ │
│ │ • New department "Sales" created                           │ │
│ │ • User "Sarah Johnson" invited                             │ │
│ │ • Stage "Custom Dev" deactivated                           │ │
│ │ • Project "Acme Website" assigned                          │ │
│ └─────────────────────────────────────────────────────────────┘ │
└─────────────────────────────────────────────────────────────────┘
```

### Mobile Departments List
```
┌─────────────────────────────────────────────────────────────────┐
│ Master Setup › Departments                                      │
├─────────────────────────────────────────────────────────────────┤
│ ┌─────────────┐ ┌─────────────┐                                │
│ │ Total       │ │ Sub-dept    │                                │
│ │ Departments │ │ Count       │                                │
│ │ 12          │ │ 24          │                                │
│ └─────────────┘ └─────────────┘                                │
│ ┌─────────────┐ ┌─────────────┐                                │
│ │ Coverage    │ │ Risk        │                                │
│ │ % Projects  │ │ Unstaffed   │                                │
│ │ 85%         │ │ 2           │                                │
│ └─────────────┘ └─────────────┘                                │
├─────────────────────────────────────────────────────────────────┤
│ [Search] [Filter] [Sort] [New]                                │
├─────────────────────────────────────────────────────────────────┤
│ ┌─────────────────────────────────────────────────────────────┐ │
│ │ Website Department                                          │ │
│ │ Sub-departments: Design, Development                       │ │
│ │ Head: Priya Nair | Updated: 2d ago                        │ │
│ │ [Edit] [Delete]                                            │ │
│ └─────────────────────────────────────────────────────────────┘ │
│ ┌─────────────────────────────────────────────────────────────┐ │
│ │ Mobile Department                                           │ │
│ │ Sub-departments: iOS, Android                              │ │
│ │ Head: Arjun Mehta | Updated: 1w ago                       │ │
│ │ [Edit] [Delete]                                            │ │
│ └─────────────────────────────────────────────────────────────┘ │
└─────────────────────────────────────────────────────────────────┘
```

## Analytics Data Examples

### Sample Analytics Data
```
Departments Analytics:
• Total Departments: 12 (+2 this month)
• Sub-department Count: 24 (+4 this week)
• Coverage % Projects: 85% (+5% vs last month)
• Unstaffed Departments: 2 (⚠️ Needs attention)

Projects Analytics:
• Customers: 8 (+1 this week)
• Projects: 24 (+3 this week)
• Ongoing: 18 (+2 this week)
• On Hold: 3 (-1 this week)
• Completed: 3 (+1 this week)
• Avg Progress: 67% (+5% vs last month)
• Behind Schedule: 2 (⚠️ At risk)
• Client Hold: 1 (⚠️ Needs attention)

Users Analytics:
• Total Users: 47 (+3 this week)
• Active: 42 (+2 this week)
• Inactive: 5 (+1 this week)
• Unassigned: 3 (⚠️ Needs attention)
• Super Admin: 2 (4%)
• Admin: 3 (6%)
• PM: 8 (17%)
• Team: 28 (60%)
• Client: 6 (13%)
• No 2FA: 12 (⚠️ Security risk)
• Default Password: 8 (⚠️ Security risk)

Stages Analytics:
• Weight Integrity: 100% ✅
• Handshake: 24 projects
• Sitemap: 22 projects
• Design: 20 projects
• Development: 18 projects
• QA & Testing: 15 projects
• Go Live: 12 projects
• Missing Stages: 2 projects (⚠️ Risk)
```

## Responsive Behavior Examples

### Desktop (1024px+)
- Full sidebar with Master Setup expandable section
- Multi-column analytics widgets (4-column layout)
- Complete table displays with all columns
- Modal overlays for create/edit operations
- Side-by-side form layouts

### Tablet (768px-1023px)
- Collapsible sidebar with Master Setup section
- Two-column analytics widgets
- Condensed tables with horizontal scroll
- Full-width modals
- Stacked form layouts

### Mobile (360px-767px)
- Bottom navigation (Master Setup hidden for non-admin roles)
- Single-column analytics cards
- Stacked table rows
- Bottom sheet modals
- Full-width forms
