# IKF Project Live Tracker - Role-Specific Dashboards

## Super Admin Dashboard

### Layout Structure
```
┌─────────────────────────────────────────────────────────────────┐
│ Header: IKF Logo | Super Admin Dashboard | [Impersonate] [Help] │
├─────────────────────────────────────────────────────────────────┤
│ Breadcrumb: Home › Dashboard                                    │
├─────────────────────────────────────────────────────────────────┤
│ System Health Banner (if alerts)                               │
├─────────────────────────────────────────────────────────────────┤
│ KPI Row (4 columns)                                             │
│ ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐                │
│ │System   │ │Active   │ │Compliance│ │Audit    │                │
│ │Health   │ │Users    │ │Status   │ │Events   │                │
│ │98%      │ │247      │ │3 Alerts │ │1,234    │                │
│ └─────────┘ └─────────┘ └─────────┘ └─────────┘                │
├─────────────────────────────────────────────────────────────────┤
│ Main Content (2 columns)                                        │
│ ┌─────────────────────────────┐ ┌─────────────────────────────┐ │
│ │ Compliance Alerts           │ │ System Performance          │ │
│ │ • Data retention policy     │ │ • CPU Usage: 45%            │ │
│ │   update required           │ │ • Memory: 67%               │ │
│ │ • Security audit due        │ │ • Storage: 23%              │ │
│ │ • Backup verification       │ │ • Uptime: 99.9%             │ │
│ └─────────────────────────────┘ └─────────────────────────────┘ │
│ ┌─────────────────────────────┐ ┌─────────────────────────────┐ │
│ │ Recent Audit Events         │ │ User Activity Summary       │ │
│ │ • Role change: Admin→PM     │ │ • 15 new logins today       │ │
│ │ • Project created: Acme     │ │ • 3 failed attempts         │ │
│ │ • Settings modified         │ │ • 2 impersonations          │ │
│ └─────────────────────────────┘ └─────────────────────────────┘ │
└─────────────────────────────────────────────────────────────────┘
```

### Key Components
- **System Health Indicator**: Real-time system status with color coding
- **Compliance Alerts**: Critical system alerts requiring attention
- **Audit Log Feed**: Recent system changes and user actions
- **Performance Metrics**: System resource utilization
- **User Activity**: Login patterns and security events

### Actions Available
- **Impersonate User**: Dropdown with warning modal
- **System Settings**: Direct access to global configuration
- **Audit Export**: Download comprehensive audit logs
- **Emergency Actions**: System restart, maintenance mode

---

## Admin Dashboard

### Layout Structure
```
┌─────────────────────────────────────────────────────────────────┐
│ Header: IKF Logo | Admin Dashboard | [New Project] [Export]     │
├─────────────────────────────────────────────────────────────────┤
│ Breadcrumb: Home › Dashboard                                    │
├─────────────────────────────────────────────────────────────────┤
│ KPI Row (3 columns)                                             │
│ ┌─────────┐ ┌─────────┐ ┌─────────┐                            │
│ │Total    │ │Ongoing  │ │On Hold  │                            │
│ │Projects │ │Projects │ │Projects │                            │
│ │24       │ │18       │ │3        │                            │
│ └─────────┘ └─────────┘ └─────────┘                            │
├─────────────────────────────────────────────────────────────────┤
│ Main Content (2 columns)                                        │
│ ┌─────────────────────────────┐ ┌─────────────────────────────┐ │
│ │ Project Pipeline            │ │ Department Performance      │ │
│ │ • Design: 8 projects        │ │ • Website: 12 projects      │ │
│ │ • Development: 6 projects   │ │ • Mobile: 8 projects        │ │
│ │ • Testing: 4 projects       │ │ • Marketing: 4 projects     │ │
│ └─────────────────────────────┘ └─────────────────────────────┘ │
│ ┌─────────────────────────────┐ ┌─────────────────────────────┐ │
│ │ Staffing Risks              │ │ Recent Activity             │ │
│ │ • Overloaded: 3 team members│ │ • Project created: Acme     │ │
│ │ • Underutilized: 2 members  │ │ • Timesheet approved        │ │
│ │ • Skills gap: Mobile dev    │ │ • Client hold: Orchid       │ │
│ └─────────────────────────────┘ └─────────────────────────────┘ │
└─────────────────────────────────────────────────────────────────┘
```

### Key Components
- **Project Pipeline**: Visual representation of project flow
- **Department Heatmap**: Performance across departments
- **Staffing Overview**: Resource allocation and risks
- **Recent Activity**: Latest system changes and updates

### Actions Available
- **New Project**: Create new project with wizard
- **Export Data**: CSV export of projects and reports
- **Manage Users**: Access to user management
- **Department Settings**: Configure department policies

---

## Project Manager Dashboard

### Layout Structure
```
┌─────────────────────────────────────────────────────────────────┐
│ Header: IKF Logo | PM Dashboard | [Add Stage] [New Project]     │
├─────────────────────────────────────────────────────────────────┤
│ Breadcrumb: Home › Dashboard                                    │
├─────────────────────────────────────────────────────────────────┤
│ KPI Row (4 columns)                                             │
│ ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐                │
│ │My       │ │Pending  │ │Avg      │ │Holds    │                │
│ │Projects │ │Approvals│ │Progress │ │Active   │                │
│ │6        │ │3        │ │67%      │ │1        │                │
│ └─────────┘ └─────────┘ └─────────┘ └─────────┘                │
├─────────────────────────────────────────────────────────────────┤
│ Main Content (2 columns)                                        │
│ ┌─────────────────────────────┐ ┌─────────────────────────────┐ │
│ │ My Portfolio                │ │ Stage Bottlenecks           │ │
│ │ • Acme Website: 48%         │ │ • Content Review (Acme)     │ │
│ │ • Orchid eCommerce: 32%     │ │ • Design Approval (Orchid)  │ │
│ │ • IKF Marketing: 61%        │ │ • Testing (Phoenix)         │ │
│ └─────────────────────────────┘ └─────────────────────────────┘ │
│ ┌─────────────────────────────┐ ┌─────────────────────────────┐ │
│ │ Pending Approvals           │ │ Team Performance            │ │
│ │ • Design Concept A (Orchid) │ │ • Riya Kapoor: 95% on time  │ │
│ │ • Content Outline (Acme)    │ │ • Karan Shah: 87% on time   │ │
│ │ • Final QA (Vista)          │ │ • Priya Nair: 92% on time   │ │
│ └─────────────────────────────┘ └─────────────────────────────┘ │
└─────────────────────────────────────────────────────────────────┘
```

### Key Components
- **Portfolio Overview**: Visual progress of all managed projects
- **Stage Bottlenecks**: Identified delays and blockers
- **Pending Approvals**: Client approvals awaiting action
- **Team Performance**: Individual team member metrics

### Actions Available
- **Add Stage**: Create new project stage
- **New Project**: Start new project
- **Request Approval**: Send items for client approval
- **Manage Holds**: Resolve project holds

---

## Team Member Dashboard

### Layout Structure
```
┌─────────────────────────────────────────────────────────────────┐
│ Header: IKF Logo | Team Dashboard | [Log Time] [View Tasks]     │
├─────────────────────────────────────────────────────────────────┤
│ Breadcrumb: Home › Dashboard                                    │
├─────────────────────────────────────────────────────────────────┤
│ KPI Row (3 columns)                                             │
│ ┌─────────┐ ┌─────────┐ ┌─────────┐                            │
│ │My Tasks │ │Hours    │ │This     │                            │
│ │Today    │ │Logged   │ │Week     │                            │
│ │4        │ │32.5     │ │18       │                            │
│ └─────────┘ └─────────┘ └─────────┘                            │
├─────────────────────────────────────────────────────────────────┤
│ Main Content (2 columns)                                        │
│ ┌─────────────────────────────┐ ┌─────────────────────────────┐ │
│ │ My Tasks Today              │ │ Quick Time Log              │ │
│ │ • Content writing (Acme)    │ │ Project: [Dropdown]         │ │
│ │ • Design review (Orchid)    │ │ Task: [Dropdown]            │ │
│ │ • Bug fixes (Phoenix)       │ │ Hours: [Input]              │ │
│ │ • Code review (IKF)         │ │ Notes: [Textarea]           │ │
│ └─────────────────────────────┘ │ [Log Time Button]           │ │
│ ┌─────────────────────────────┐ └─────────────────────────────┘ │
│ │ Resource Shortcuts          │ ┌─────────────────────────────┐ │
│ │ • Design Assets (GDrive)    │ │ Project Updates             │ │
│ │ • Code Repository (GitHub)  │ │ • Acme: Stage completed     │ │
│ │ • Documentation (Confluence)│ │ • Orchid: Client feedback   │ │
│ │ • Project Briefs (SharePoint)│ │ • Phoenix: Testing started  │ │
│ └─────────────────────────────┘ └─────────────────────────────┘ │
└─────────────────────────────────────────────────────────────────┘
```

### Key Components
- **My Tasks**: Today's assigned tasks with priorities
- **Quick Time Log**: Streamlined timesheet entry
- **Resource Shortcuts**: Quick access to project resources
- **Project Updates**: Latest project notifications

### Actions Available
- **Log Time**: Quick timesheet entry
- **View Tasks**: Detailed task list
- **Access Resources**: Direct links to project files
- **Update Status**: Mark tasks as complete

---

## Client Dashboard (Future)

### Layout Structure
```
┌─────────────────────────────────────────────────────────────────┐
│ Header: IKF Logo | Client Portal | [Feedback] [Support]         │
├─────────────────────────────────────────────────────────────────┤
│ Breadcrumb: Home › Dashboard                                    │
├─────────────────────────────────────────────────────────────────┤
│ KPI Row (3 columns)                                             │
│ ┌─────────┐ ┌─────────┐ ┌─────────┐                            │
│ │My       │ │Pending  │ │Completed│                            │
│ │Projects │ │Approvals│ │Projects │                            │
│ │3        │ │2        │ │1        │                            │
│ └─────────┘ └─────────┘ └─────────┘                            │
├─────────────────────────────────────────────────────────────────┤
│ Main Content (2 columns)                                        │
│ ┌─────────────────────────────┐ ┌─────────────────────────────┐ │
│ │ Project Progress            │ │ Pending Approvals           │ │
│ │ • Acme Website: 48%         │ │ • Design Concept A          │ │
│ │ • Orchid eCommerce: 32%     │ │   (Orchid eCommerce)        │ │
│ │ • Vista Realty: 100%        │ │ • Content Outline           │ │
│ └─────────────────────────────┘ │   (Acme Website)            │ │
│ ┌─────────────────────────────┐ └─────────────────────────────┘ │
│ │ Recent Deliverables         │ ┌─────────────────────────────┐ │
│ │ • Design Mockups (Orchid)   │ │ Feedback Panel              │ │
│ │ • Content Draft (Acme)      │ │ • Submit feedback           │ │
│ │ • Final Site (Vista)        │ │ • Request changes           │ │
│ └─────────────────────────────┘ │ • Ask questions             │ │
│                                 └─────────────────────────────┘ │
└─────────────────────────────────────────────────────────────────┘
```

### Key Components
- **Project Progress**: Visual progress of assigned projects
- **Pending Approvals**: Items requiring client approval
- **Recent Deliverables**: Latest project deliverables
- **Feedback Panel**: Communication tools for client input

### Actions Available
- **Approve Items**: Approve pending deliverables
- **Request Changes**: Submit change requests
- **Submit Feedback**: Provide project feedback
- **View Timeline**: Project milestone timeline

---

## Dashboard Responsive Behavior

### Desktop (1024px+)
- Full 4-column KPI layout
- Side-by-side content sections
- Complete action buttons visible
- Full navigation sidebar

### Tablet (768px-1023px)
- 3-column KPI layout
- Stacked content sections
- Condensed action buttons
- Collapsible navigation

### Mobile (360px-767px)
- 2-column KPI layout
- Single-column content
- Icon-only action buttons
- Bottom navigation bar

## Dashboard State Variations

### Loading State
- Skeleton placeholders for all content
- Shimmer animation on KPI cards
- Disabled action buttons
- Loading spinner in content areas

### Empty State
- Role-specific empty state messages
- Suggested next actions
- Help links and documentation
- Onboarding prompts

### Error State
- Error message with retry option
- Fallback content where possible
- Contact support information
- Graceful degradation

### Offline State
- Cached data display
- Offline indicator
- Sync status
- Limited functionality notice
