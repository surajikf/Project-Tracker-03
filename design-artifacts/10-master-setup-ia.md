# IKF Project Live Tracker - Master Setup Information Architecture

## Updated Navigation Structure

### Left Sidebar Navigation (Role-Aware)
```
Primary Navigation
├── Dashboard
├── Projects
├── Timesheets (Phase 2)
├── Reports
├── Resources
├── Master Setup (Super Admin/Admin only)
│   ├── Departments
│   ├── Projects (under Customers)
│   ├── Users
│   └── Stages
├── Admin (Role-gated)
│   ├── Super Admin: Full admin access
│   ├── Admin: User/Dept management
│   └── PM/Team/Client: Hidden
├── Settings (Super Admin only)
└── Help
```

### Master Setup Visibility Rules
- **Super Admin**: Full access to all Master Setup modules
- **Admin**: Access to all modules with organizational scope restrictions
- **PM/Team/Client**: No access - Master Setup section hidden from navigation

## Master Setup Module Structure

### 1. Departments Module
```
Master Setup › Departments
├── Analytics Widget (Top Card)
│   ├── Totals: # Departments, # Sub-departments
│   ├── Coverage: % projects with department assignments
│   ├── Risk: Unstaffed departments count
│   └── Quick Actions: New Department, Add Sub-department, Assign Dept Head
├── List View (Table)
│   ├── Columns: Department Name, Sub-Departments, Head, Created By, Last Updated
│   ├── Filters: by name, head, # of sub-departments
│   ├── Sort: by name, head, # of sub-departments
│   └── Actions: Edit, Delete (soft), Assign Head
├── Create Department (Modal/Form)
│   ├── Fields: name, sub-departments (repeatable chips), assign dept head
│   ├── Validation: unique name, ≥1 sub-department required
│   └── Actions: Save, Cancel
├── Edit Department (Inline/Modal)
│   ├── Fields: name, sub-departments, head assignment
│   ├── Validation: same as create
│   └── Actions: Save, Cancel, Delete
└── Empty State
    ├── Message: "No departments yet. Create your first to begin assigning users."
    └── Action: "Create Department"
```

### 2. Projects (under Customers) Module
```
Master Setup › Projects
├── Analytics Widget (Header Band + Card Grid)
│   ├── Totals: # Customers, # Projects, Projects by Status
│   ├── Delivery: avg % completion, # projects behind schedule
│   ├── Ownership: PM load distribution (top 5)
│   ├── Holds: Client Hold vs Team Hold counts
│   └── Quick Actions: New Project, Assign PM, Bulk Update Status, Export CSV
├── List View (Table)
│   ├── Columns: Customer, Project Name, Code, Status, Assigned PM, Start Date, End Date
│   ├── Filters: by Customer, PM, Status, Date
│   ├── Sort: by Customer, Project Name, Start Date, End Date
│   └── Actions: Edit, Archive/Unarchive, Delete (Super Admin only)
├── Create Project (Multi-step Form)
│   ├── Step 1: Customer lookup/create, project name, code
│   ├── Step 2: Dates, assign PM, departments
│   ├── Step 3: Resource links, settings
│   └── Actions: Previous, Next, Save, Cancel
├── Edit Project (Modal/Form)
│   ├── Fields: assignments, timelines, resource links
│   ├── Validation: required fields, date logic
│   └── Actions: Save, Cancel, Archive, Delete
└── Empty State
    ├── Message: "No projects for this customer yet. Add one to start tracking."
    └── Action: "Create Project"
```

### 3. Users Module
```
Master Setup › Users
├── Analytics Widget (Sticky Header Card)
│   ├── Role distribution: donut chart (Super Admin/Admin/PM/Team/Client)
│   ├── Utilization: # inactive vs active, unassigned users
│   ├── Security: users without 2FA, default password flags
│   └── Quick Actions: Invite User, Bulk Assign to Project, Change Roles
├── List View (Table)
│   ├── Columns: Name, Email, Role, Department(s), Project(s), Status
│   ├── Filters: by Role, Department, Project, Status
│   ├── Sort: by Name, Email, Role, Last Active
│   └── Actions: Edit, Deactivate/Reactivate, Delete (Super Admin only)
├── Invite User (Multi-step Form)
│   ├── Step 1: Name, email, role
│   ├── Step 2: Department(s), project(s)
│   ├── Step 3: Default password or invite email flow
│   └── Actions: Previous, Next, Send Invite, Cancel
├── Edit User (Modal/Form)
│   ├── Fields: role, assignments, status
│   ├── Validation: role constraints, assignment requirements
│   └── Actions: Save, Cancel, Deactivate, Delete
├── Bulk Actions Bar
│   ├── Appears when rows selected
│   ├── Actions: assign to project, change role, deactivate
│   └── Shows allowed bulk ops by role
└── Empty State
    ├── Message: "No users in this view. Add one to build your team."
    └── Action: "Invite User"
```

### 4. Stages Module
```
Master Setup › Stages
├── Analytics Widget (Right Rail Card)
│   ├── Weight integrity: live meter of active weight total (goal 100%)
│   ├── Usage: # projects using each stage, top 5 by usage
│   ├── Risk: projects missing required standard stages
│   └── Quick Actions: New Stage, Deactivate Temporary Stages, Normalize Weights
├── List View (Table)
│   ├── Columns: Stage Name, Type (Standard/Temporary), Weight (%), Sub-statuses, Active
│   ├── Filters: by Type, Active Status, Weight Range
│   ├── Sort: by Name, Type, Weight, Usage Count
│   └── Actions: Edit, Deactivate, Delete (if not attached to active project)
├── Create Stage (Modal/Form)
│   ├── Fields: name, type, weight %, optional sub-status set
│   ├── Validation: weight sum = 100%, unique name
│   └── Actions: Save, Cancel
├── Edit Stage (Modal/Form)
│   ├── Fields: name, weight, sub-status
│   ├── Validation: same as create
│   └── Actions: Save, Cancel, Deactivate, Delete
└── Empty State
    ├── Message: "No custom stages yet. Add a new one or use defaults."
    └── Action: "Create Stage"
```

## Breadcrumb Structure

### Master Setup Breadcrumbs
```
Home › Master Setup › Departments
Home › Master Setup › Projects
Home › Master Setup › Users
Home › Master Setup › Stages
```

### Sub-page Breadcrumbs
```
Home › Master Setup › Departments › Create Department
Home › Master Setup › Projects › Edit Project › Acme Website Revamp
Home › Master Setup › Users › Invite User
Home › Master Setup › Stages › Edit Stage › Design
```

## Role-Based Access Control

### Super Admin Access
- **Full CRUD** on all Master Setup modules
- **Delete protections override** (can delete standard stages, Super Admin users)
- **System-wide visibility** (all departments, users, projects)
- **Feature flag management** (can edit stage activation rules)

### Admin Access
- **CRUD within organizational scope** (cannot delete global templates)
- **Cannot manage Super Admin users** (create, edit, delete)
- **Cannot delete standard stages** (can only deactivate)
- **Cannot edit feature flags**

### PM/Team/Client Access
- **No access to Master Setup** (section hidden from navigation)
- **Insufficient permissions page** if direct link accessed
- **Guidance message** with contact information

## Responsive Behavior

### Desktop (1024px+)
- Full sidebar with Master Setup expandable section
- Multi-column analytics widgets
- Complete table displays with all columns
- Side-by-side form layouts

### Tablet (768px-1023px)
- Collapsible sidebar with Master Setup section
- Two-column analytics widgets
- Condensed table with horizontal scroll
- Stacked form layouts

### Mobile (360px-767px)
- Bottom navigation (Master Setup hidden for non-admin roles)
- Single-column analytics cards
- Stacked table rows
- Full-width form layouts
