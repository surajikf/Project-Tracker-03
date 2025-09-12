# IKF Project Live Tracker - Information Architecture

## System-Wide Information Architecture

```
IKF Project Live Tracker
├── Dashboard (Role-aware)
│   ├── Super Admin: KPIs, compliance alerts, audit log feed, system health
│   ├── Admin: pipeline snapshot, project filters, department heatmap, staffing risks
│   ├── PM: portfolio view, stage bottlenecks, pending approvals, holds, burndown
│   ├── Team: my tasks today/this week, timesheet quick log, resource shortcuts
│   └── Client: project list, progress, approvals, feedback panel
├── Projects
│   ├── Project List (Filtered by role)
│   ├── Project Details
│   │   ├── Overview (Progress bar with weighted stages)
│   │   ├── Stages (On/off toggle with sub-status)
│   │   ├── Assignments (Dept/sub-dept/members)
│   │   ├── Resource Links (GDrive, etc.)
│   │   ├── Timeline
│   │   └── Comments/Activity
│   └── New Project (Admin/PM only)
├── Timesheets (Phase 2)
│   ├── Log Form
│   ├── Weekly/Monthly Tables
│   ├── Summaries
│   └── Export Actions
├── Reports
│   ├── Project Reports (Role-scoped)
│   ├── Timesheet Reports (Admin/PM only)
│   ├── Department Reports (Admin only)
│   └── System Reports (Super Admin only)
├── Resources
│   ├── Resource Links (Permission-based)
│   ├── Templates
│   └── Libraries
├── Admin (Role-gated)
│   ├── User Management (Admin/Super Admin)
│   ├── Department Management (Admin/Super Admin)
│   ├── Role Management (Super Admin only)
│   ├── Audit Logs (Super Admin only)
│   └── System Settings (Super Admin only)
├── Settings (Super Admin only)
│   ├── Global Settings
│   ├── Feature Flags
│   ├── Security & Compliance
│   ├── Data Retention
│   └── Report Templates
└── Help
    ├── Documentation
    ├── Support
    └── Tour/Onboarding
```

## Per-Role Information Architecture

### Super Admin IA
```
Super Admin View
├── Dashboard
│   ├── System-wide KPIs
│   ├── Compliance alerts
│   ├── Audit log feed
│   └── System health status
├── Projects (All)
│   ├── All Projects List
│   ├── Project Details (Full access)
│   └── New Project
├── Timesheets (All)
│   ├── All Timesheets
│   ├── Approvals
│   └── Reports
├── Reports (All)
│   ├── System Reports
│   ├── Department Reports
│   ├── Project Reports
│   └── Custom Reports
├── Resources (All)
│   ├── All Resource Links
│   ├── Templates
│   └── Libraries
├── Admin
│   ├── User Management
│   ├── Department Management
│   ├── Role Management
│   ├── Audit Logs
│   └── System Settings
├── Settings
│   ├── Global Settings
│   ├── Feature Flags
│   ├── Security & Compliance
│   ├── Data Retention
│   └── Report Templates
└── Help
```

### Admin IA
```
Admin View
├── Dashboard
│   ├── Pipeline snapshot
│   ├── Project filters (On Hold/Ongoing/Completed)
│   ├── Department heatmap
│   └── Staffing risks
├── Projects (Operational scope)
│   ├── All Projects List
│   ├── Project Details (Full access)
│   └── New Project
├── Timesheets (Team management)
│   ├── Team Timesheets
│   ├── Approvals
│   └── Reports
├── Reports (Operational)
│   ├── Department Reports
│   ├── Project Reports
│   └── Team Reports
├── Resources (Managed)
│   ├── Resource Links
│   ├── Templates
│   └── Libraries
├── Admin
│   ├── User Management
│   ├── Department Management
│   └── Client Management
└── Help
```

### Project Manager IA
```
Project Manager View
├── Dashboard
│   ├── My Portfolio
│   ├── Stage bottlenecks
│   ├── Pending approvals
│   └── Holds overview
├── Projects (Own projects only)
│   ├── My Projects List
│   ├── Project Details (Own projects)
│   └── New Project
├── Timesheets (Project rollups)
│   ├── Project Timesheet Summaries
│   └── Team Timesheets (Own projects)
├── Reports (Project-level)
│   ├── Project Reports
│   └── Team Performance
├── Resources (Assigned)
│   ├── Project Resource Links
│   └── Templates
└── Help
```

### Team Member IA
```
Team Member View
├── Dashboard
│   ├── My Tasks Today/This Week
│   ├── Timesheet Quick Log
│   └── Resource Shortcuts
├── Projects (Assigned only)
│   ├── My Assigned Projects
│   └── Project Details (Assigned projects)
├── Timesheets (Personal)
│   ├── Log Time
│   ├── Weekly View
│   └── Monthly View
├── Resources (Permitted)
│   └── Assigned Resource Links
└── Help
```

### Client IA (Future)
```
Client View
├── Dashboard
│   ├── Project List
│   ├── Progress Overview
│   ├── Pending Approvals
│   └── Feedback Panel
├── Projects (Assigned only)
│   ├── My Projects
│   └── Project Details (Read-only)
├── Approvals
│   ├── Pending Approvals
│   ├── Approval History
│   └── Request Changes
└── Help
```

## Navigation Structure

### Global Navigation (Role-aware)
```
Primary Nav
├── Dashboard
├── Projects
├── Timesheets (Phase 2)
├── Reports
├── Resources
├── Admin (Role-gated)
│   ├── Super Admin: Full admin access
│   ├── Admin: User/Dept management
│   └── PM/Team/Client: Hidden
├── Settings (Super Admin only)
└── Help
```

### Breadcrumb Structure
```
Home › [Section] › [Subsection] › [Item]

Examples:
- Home › Projects › Acme Website Revamp › Stages
- Home › Dashboard › System Health
- Home › Admin › User Management › Edit User
- Home › Projects › New Project › Basic Info
```

## Search Architecture

### Global Search (Super Admin/Admin)
- **Scope**: All projects, users, departments, resources
- **Filters**: By type, status, department, date range
- **Results**: Ranked by relevance and permissions

### Scoped Search (PM/Team)
- **Scope**: Own projects and assigned resources only
- **Filters**: By project, stage, status
- **Results**: Limited to accessible content

### Client Search (Future)
- **Scope**: Assigned projects only
- **Filters**: By project, deliverable type
- **Results**: Read-only project information

## Page Hierarchy & Access Control

### Level 1: Public/Shared
- Dashboard (role-specific)
- Help
- Login/Logout

### Level 2: Role-Gated
- Projects (filtered by role)
- Timesheets (permission-based)
- Reports (scope-based)
- Resources (access-controlled)

### Level 3: Admin-Only
- User Management
- Department Management
- System Settings

### Level 4: Super Admin-Only
- Role Management
- Audit Logs
- Feature Flags
- Global Settings

## Content Organization

### Dashboard Content by Role
```
Super Admin Dashboard
├── System Health Widget
├── Compliance Alerts
├── Audit Log Feed
├── User Activity Summary
└── System Performance Metrics

Admin Dashboard
├── Project Pipeline
├── Department Performance
├── Staffing Overview
├── Risk Alerts
└── Recent Activity

PM Dashboard
├── Portfolio Overview
├── Stage Bottlenecks
├── Pending Approvals
├── Team Performance
└── Upcoming Deadlines

Team Dashboard
├── My Tasks
├── Timesheet Quick Log
├── Resource Access
├── Project Updates
└── Notifications

Client Dashboard
├── Project Progress
├── Pending Approvals
├── Recent Deliverables
├── Feedback Status
└── Timeline View
```

## Responsive Navigation

### Desktop (1024px+)
- Full sidebar with labels
- Breadcrumb navigation
- Global search bar
- Role indicator

### Tablet (768px-1023px)
- Collapsible sidebar
- Icon-only navigation
- Breadcrumb navigation
- Role indicator

### Mobile (360px-767px)
- Hamburger menu
- Bottom navigation
- Stacked breadcrumbs
- Role indicator in header
