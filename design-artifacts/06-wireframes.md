# IKF Project Live Tracker - Wireframes

## Key User Flows

### 1. Super Admin Impersonation Flow
```
Step 1: Impersonation Modal
┌─────────────────────────────────────────────────────────────────┐
│ ⚠️ Impersonation Mode                                          │
│ You are about to view the system as: John Doe (Team Member)    │
│ This action will be logged and audited.                        │
│ [Cancel] [Continue] [Exit Impersonation]                       │
└─────────────────────────────────────────────────────────────────┘

Step 2: Impersonation Banner
┌─────────────────────────────────────────────────────────────────┐
│ 🔄 Impersonating: John Doe (Team Member) | [Exit Impersonation] │
└─────────────────────────────────────────────────────────────────┘

Step 3: Team Member View
┌─────────────────────────────────────────────────────────────────┐
│ Header: IKF Logo | Team Dashboard | [Log Time] [View Tasks]     │
│ (Restricted actions hidden)                                    │
└─────────────────────────────────────────────────────────────────┘
```

### 2. Project Creation Flow (Admin/PM)
```
Step 1: New Project Button
┌─────────────────────────────────────────────────────────────────┐
│ [New Project] (Primary action button)                          │
└─────────────────────────────────────────────────────────────────┘

Step 2: Project Creation Wizard
┌─────────────────────────────────────────────────────────────────┐
│ New Project - Step 1 of 3                                      │
│ Project Name: [________________]                               │
│ Client: [________________]                                     │
│ Department: [Dropdown: Website | Mobile | Marketing]          │
│ [Cancel] [Next]                                                │
└─────────────────────────────────────────────────────────────────┘

Step 3: Team Assignment
┌─────────────────────────────────────────────────────────────────┐
│ New Project - Step 2 of 3                                      │
│ Assign Team Members:                                           │
│ ☑ Priya Nair (PM)                                             │
│ ☑ Riya Kapoor (Content Writer)                                │
│ ☐ Karan Shah (Designer)                                       │
│ ☐ Arjun Mehta (Developer)                                     │
│ [Back] [Next]                                                  │
└─────────────────────────────────────────────────────────────────┘

Step 4: Project Settings
┌─────────────────────────────────────────────────────────────────┐
│ New Project - Step 3 of 3                                      │
│ Budget: [________________]                                     │
│ Start Date: [Date Picker]                                     │
│ Due Date: [Date Picker]                                       │
│ [Back] [Create Project]                                        │
└─────────────────────────────────────────────────────────────────┘
```

### 3. Client Approval Flow (Future)
```
Step 1: Pending Approval Notification
┌─────────────────────────────────────────────────────────────────┐
│ 🔔 New approval request: Design Concept A (Orchid eCommerce)   │
│ [View Details] [Approve] [Request Changes]                     │
└─────────────────────────────────────────────────────────────────┘

Step 2: Approval Detail View
┌─────────────────────────────────────────────────────────────────┐
│ Design Concept A - Orchid eCommerce                            │
│ Progress: 32%                                                  │
│ Deliverable: [Image Preview]                                   │
│ Description: Homepage design with new color scheme             │
│ [Approve] [Request Changes] [Ask Question]                     │
└─────────────────────────────────────────────────────────────────┘

Step 3: Approval Confirmation
┌─────────────────────────────────────────────────────────────────┐
│ ✅ Design Concept A Approved                                   │
│ Your approval has been recorded and the team has been notified.│
│ [View Project] [Close]                                         │
└─────────────────────────────────────────────────────────────────┘
```

## Screen Wireframes

### Super Admin Dashboard
```
┌─────────────────────────────────────────────────────────────────┐
│ IKF | Super Admin Dashboard | [Impersonate] [Settings] [Help]   │
├─────────────────────────────────────────────────────────────────┤
│ Home › Dashboard                                                │
├─────────────────────────────────────────────────────────────────┤
│ System Health: 98% | Active Users: 247 | Compliance: 3 Alerts  │
├─────────────────────────────────────────────────────────────────┤
│ ┌─────────────────────────┐ ┌─────────────────────────┐        │
│ │ Compliance Alerts       │ │ System Performance      │        │
│ │ • Data retention policy │ │ • CPU: 45%              │        │
│ │   update required       │ │ • Memory: 67%           │        │
│ │ • Security audit due    │ │ • Storage: 23%          │        │
│ │ • Backup verification   │ │ • Uptime: 99.9%         │        │
│ └─────────────────────────┘ └─────────────────────────┘        │
│ ┌─────────────────────────┐ ┌─────────────────────────┐        │
│ │ Recent Audit Events     │ │ User Activity Summary   │        │
│ │ • Role change: Admin→PM │ │ • 15 new logins today   │        │
│ │ • Project created: Acme │ │ • 3 failed attempts     │        │
│ │ • Settings modified     │ │ • 2 impersonations      │        │
│ └─────────────────────────┘ └─────────────────────────┘        │
└─────────────────────────────────────────────────────────────────┘
```

### Admin Dashboard
```
┌─────────────────────────────────────────────────────────────────┐
│ IKF | Admin Dashboard | [New Project] [Export] [Help]           │
├─────────────────────────────────────────────────────────────────┤
│ Home › Dashboard                                                │
├─────────────────────────────────────────────────────────────────┤
│ Total Projects: 24 | Ongoing: 18 | On Hold: 3                  │
├─────────────────────────────────────────────────────────────────┤
│ ┌─────────────────────────┐ ┌─────────────────────────┐        │
│ │ Project Pipeline        │ │ Department Performance  │        │
│ │ • Design: 8 projects    │ │ • Website: 12 projects  │        │
│ │ • Development: 6        │ │ • Mobile: 8 projects    │        │
│ │ • Testing: 4            │ │ • Marketing: 4 projects │        │
│ └─────────────────────────┘ └─────────────────────────┘        │
│ ┌─────────────────────────┐ ┌─────────────────────────┐        │
│ │ Staffing Risks          │ │ Recent Activity         │        │
│ │ • Overloaded: 3 members │ │ • Project created: Acme │        │
│ │ • Underutilized: 2      │ │ • Timesheet approved    │        │
│ │ • Skills gap: Mobile    │ │ • Client hold: Orchid   │        │
│ └─────────────────────────┘ └─────────────────────────┘        │
└─────────────────────────────────────────────────────────────────┘
```

### Project Manager Dashboard
```
┌─────────────────────────────────────────────────────────────────┐
│ IKF | PM Dashboard | [Add Stage] [New Project] [Help]           │
├─────────────────────────────────────────────────────────────────┤
│ Home › Dashboard                                                │
├─────────────────────────────────────────────────────────────────┤
│ My Projects: 6 | Pending Approvals: 3 | Avg Progress: 67%      │
├─────────────────────────────────────────────────────────────────┤
│ ┌─────────────────────────┐ ┌─────────────────────────┐        │
│ │ My Portfolio            │ │ Stage Bottlenecks       │        │
│ │ • Acme Website: 48%     │ │ • Content Review (Acme) │        │
│ │ • Orchid eCommerce: 32% │ │ • Design Approval (Orchid) │     │
│ │ • IKF Marketing: 61%    │ │ • Testing (Phoenix)     │        │
│ └─────────────────────────┘ └─────────────────────────┘        │
│ ┌─────────────────────────┐ ┌─────────────────────────┐        │
│ │ Pending Approvals       │ │ Team Performance        │        │
│ │ • Design Concept A      │ │ • Riya Kapoor: 95%      │        │
│ │ • Content Outline       │ │ • Karan Shah: 87%       │        │
│ │ • Final QA              │ │ • Priya Nair: 92%       │        │
│ └─────────────────────────┘ └─────────────────────────┘        │
└─────────────────────────────────────────────────────────────────┘
```

### Team Member Dashboard
```
┌─────────────────────────────────────────────────────────────────┐
│ IKF | Team Dashboard | [Log Time] [View Tasks] [Help]           │
├─────────────────────────────────────────────────────────────────┤
│ Home › Dashboard                                                │
├─────────────────────────────────────────────────────────────────┤
│ My Tasks Today: 4 | Hours Logged: 32.5 | This Week: 18         │
├─────────────────────────────────────────────────────────────────┤
│ ┌─────────────────────────┐ ┌─────────────────────────┐        │
│ │ My Tasks Today          │ │ Quick Time Log          │        │
│ │ • Content writing (Acme)│ │ Project: [Dropdown]     │        │
│ │ • Design review (Orchid)│ │ Task: [Dropdown]        │        │
│ │ • Bug fixes (Phoenix)   │ │ Hours: [Input]          │        │
│ │ • Code review (IKF)     │ │ Notes: [Textarea]       │        │
│ └─────────────────────────┘ │ [Log Time Button]       │        │
│ ┌─────────────────────────┐ └─────────────────────────┘        │
│ │ Resource Shortcuts       │ ┌─────────────────────────┐        │
│ │ • Design Assets (GDrive) │ │ Project Updates         │        │
│ │ • Code Repository (Git)  │ │ • Acme: Stage completed │        │
│ │ • Documentation (Wiki)   │ │ • Orchid: Client feedback │      │
│ │ • Project Briefs (Share) │ │ • Phoenix: Testing started │     │
│ └─────────────────────────┘ └─────────────────────────┘        │
└─────────────────────────────────────────────────────────────────┘
```

### Client Dashboard (Future)
```
┌─────────────────────────────────────────────────────────────────┐
│ IKF | Client Portal | [Feedback] [Support] [Help]               │
├─────────────────────────────────────────────────────────────────┤
│ Home › Dashboard                                                │
├─────────────────────────────────────────────────────────────────┤
│ My Projects: 3 | Pending Approvals: 2 | Completed: 1           │
├─────────────────────────────────────────────────────────────────┤
│ ┌─────────────────────────┐ ┌─────────────────────────┐        │
│ │ Project Progress        │ │ Pending Approvals       │        │
│ │ • Acme Website: 48%     │ │ • Design Concept A      │        │
│ │ • Orchid eCommerce: 32% │ │ • Content Outline       │        │
│ │ • Vista Realty: 100%    │ │                         │        │
│ └─────────────────────────┘ └─────────────────────────┘        │
│ ┌─────────────────────────┐ ┌─────────────────────────┐        │
│ │ Recent Deliverables     │ │ Feedback Panel          │        │
│ │ • Design Mockups        │ │ • Submit feedback       │        │
│ │ • Content Draft         │ │ • Request changes       │        │
│ │ • Final Site            │ │ • Ask questions         │        │
│ └─────────────────────────┘ └─────────────────────────┘        │
└─────────────────────────────────────────────────────────────────┘
```

## Mobile Wireframes

### Mobile Dashboard (Team Member)
```
┌─────────────────────────────────────────────────────────────────┐
│ IKF | Team | [☰] [Log Time]                                    │
├─────────────────────────────────────────────────────────────────┤
│ My Tasks Today: 4 | Hours: 32.5                                │
├─────────────────────────────────────────────────────────────────┤
│ ┌─────────────────────────────────────────────────────────────┐ │
│ │ My Tasks Today                                             │ │
│ │ • Content writing (Acme)                                   │ │
│ │ • Design review (Orchid)                                   │ │
│ │ • Bug fixes (Phoenix)                                      │ │
│ │ • Code review (IKF)                                        │ │
│ └─────────────────────────────────────────────────────────────┘ │
│ ┌─────────────────────────────────────────────────────────────┐ │
│ │ Quick Time Log                                             │ │
│ │ Project: [Dropdown]                                        │ │
│ │ Task: [Dropdown]                                           │ │
│ │ Hours: [Input]                                             │ │
│ │ [Log Time Button]                                          │ │
│ └─────────────────────────────────────────────────────────────┘ │
│ ┌─────────────────────────────────────────────────────────────┐ │
│ │ Project Updates                                            │ │
│ │ • Acme: Stage completed                                    │ │
│ │ • Orchid: Client feedback                                  │ │
│ │ • Phoenix: Testing started                                 │ │
│ └─────────────────────────────────────────────────────────────┘ │
└─────────────────────────────────────────────────────────────────┘
```

### Mobile Navigation
```
Bottom Navigation Bar
┌─────────────────────────────────────────────────────────────────┐
│ [🏠] [📋] [⏰] [📊] [📁] [☰]                                   │
│ Home  Projects Timesheets Reports Resources Menu               │
└─────────────────────────────────────────────────────────────────┘
```

## Responsive Behavior

### Desktop (1024px+)
- Full sidebar navigation
- Multi-column layouts
- Complete action buttons
- Full table displays

### Tablet (768px-1023px)
- Collapsible sidebar
- Two-column layouts
- Condensed action buttons
- Horizontal scrolling tables

### Mobile (360px-767px)
- Bottom navigation
- Single-column layouts
- Icon-only buttons
- Stacked card layouts
