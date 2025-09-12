# IKF Project Live Tracker - Projects (under Customers) Module Design

## Module Overview
**Path**: Master Setup › Projects  
**Access**: Super Admin (full), Admin (org scope), PM/Team/Client (no access)  
**Breadcrumb**: Home › Master Setup › Projects  
**Hierarchy**: Each Project belongs to a Customer. Customers can have multiple Projects.

## Analytics Widget (Header Band + Card Grid)

### Header Band Layout
```
┌─────────────────────────────────────────────────────────────────┐
│ Projects Analytics                                              │
├─────────────────────────────────────────────────────────────────┤
│ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ │
│ │ Customers   │ │ Projects    │ │ Ongoing     │ │ On Hold     │ │
│ │ 8           │ │ 24          │ │ 18          │ │ 3           │ │
│ └─────────────┘ └─────────────┘ └─────────────┘ └─────────────┘ │
│ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ │
│ │ Completed   │ │ Avg Progress│ │ Behind     │ │ Client Hold │ │
│ │ 3           │ │ 67%         │ │ 2           │ │ 1           │ │
│ └─────────────┘ └─────────────┘ └─────────────┘ └─────────────┘ │
└─────────────────────────────────────────────────────────────────┘
```

### Card Grid Layout
```
┌─────────────────────────────────────────────────────────────────┐
│ Delivery Metrics                                                │
├─────────────────────────────────────────────────────────────────┤
│ ┌─────────────────────────┐ ┌─────────────────────────┐        │
│ │ PM Load Distribution    │ │ Project Status Overview │        │
│ │ • Priya Nair: 6 projects│ │ ████████████████████████ │        │
│ │ • Arjun Mehta: 4        │ │ Ongoing: 75%             │        │
│ │ • Sarah Johnson: 3      │ │ On Hold: 12.5%           │        │
│ │ • Mike Chen: 2          │ │ Completed: 12.5%         │        │
│ │ • Others: 9             │ │                         │        │
│ └─────────────────────────┘ └─────────────────────────┘        │
└─────────────────────────────────────────────────────────────────┘
```

### Analytics Components
- **Totals**: # Customers, # Projects, Projects by Status (segmented badges)
- **Delivery**: avg % completion (weighted), # projects behind schedule
- **Ownership**: PM load distribution (top 5 PMs by count)
- **Holds**: counts for Client Hold vs Team Hold; clickable chips filter table
- **Quick Actions**: New Project, Assign PM, Bulk Update Status, Export CSV

## List View (Table)

### Table Structure
```
┌─────────────────────────────────────────────────────────────────┐
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

### Table Columns
- **Customer**: Customer name, sortable, filterable
- **Project Name**: Project title, clickable to details
- **Code**: Project code (e.g., ACME-001), unique identifier
- **Status**: Badge (On Hold/Ongoing/Completed), filterable
- **Assigned PM**: Project manager name, clickable to user details
- **Start Date**: Project start date, sortable
- **End Date**: Project end date, sortable
- **Actions**: Edit, Archive/Unarchive, Delete (Super Admin only)

### Table Actions
- **Row Actions**: Edit, Archive/Unarchive, Delete (Super Admin only)
- **Bulk Actions**: Assign PM, Bulk Update Status, Export CSV
- **Filters**: by Customer, PM, Status, Date range
- **Sort**: by Customer, Project Name, Start Date, End Date, Status

## Create Project (Multi-step Form)

### Step 1: Basic Information
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

### Step 2: Timeline & Assignment
```
┌─────────────────────────────────────────────────────────────────┐
│ Create Project - Step 2 of 3                                   │
├─────────────────────────────────────────────────────────────────┤
│ Timeline                                                         │
│ Start Date: [Date Picker]                                       │
│ End Date: [Date Picker]                                         │
│                                                                 │
│ Assign Project Manager                                           │
│ [Dropdown: Select PM]                                           │
│                                                                 │
│ Assign Departments                                               │
│ ☑ Website                                                        │
│ ☑ Mobile                                                         │
│ ☐ Marketing                                                      │
│                                                                 │
│ Budget (Optional)                                                │
│ [________________________________]                             │
│                                                                 │
│ [Previous] [Next]                                                │
└─────────────────────────────────────────────────────────────────┘
```

### Step 3: Resources & Settings
```
┌─────────────────────────────────────────────────────────────────┐
│ Create Project - Step 3 of 3                                   │
├─────────────────────────────────────────────────────────────────┤
│ Resource Links                                                   │
│ • Design Assets: [GDrive link]                                  │
│ • Code Repository: [GitHub link]                                │
│ • Documentation: [Confluence link]                              │
│                                                                 │
│ Project Settings                                                 │
│ ☑ Enable client portal                                          │
│ ☑ Require approval for stage changes                            │
│ ☐ Auto-assign based on department                               │
│                                                                 │
│ [Previous] [Create Project]                                     │
└─────────────────────────────────────────────────────────────────┘
```

### Form Validation
- **Customer**: Required, must exist or be created
- **Project Name**: Required, unique per customer
- **Project Code**: Required, unique across all projects
- **Dates**: Start date must be before end date
- **PM**: Required, must be valid user with PM role
- **Departments**: At least one required

## Edit Project (Modal/Form)

### Edit Modal Structure
```
┌─────────────────────────────────────────────────────────────────┐
│ Edit Project: Acme Website Revamp                   [Close]     │
├─────────────────────────────────────────────────────────────────┤
│ Customer: Acme Corp (cannot be changed)                         │
│                                                                 │
│ Project Name: [Acme Website Revamp        ]                     │
│ Project Code: [ACME-001                   ]                     │
│                                                                 │
│ Timeline                                                         │
│ Start Date: [8/1/2024] End Date: [10/30/2024]                  │
│                                                                 │
│ Assignments                                                      │
│ PM: [Priya Nair ▼]                                              │
│ Departments: ☑ Website ☑ Mobile ☐ Marketing                    │
│                                                                 │
│ Status                                                           │
│ [Ongoing ▼] [Archive] [Delete] (Super Admin only)               │
│                                                                 │
│ [Cancel] [Save Changes]                                         │
└─────────────────────────────────────────────────────────────────┘
```

### Edit Actions
- **Inline Edit**: Quick edits directly in table
- **Modal Edit**: Full form in modal overlay
- **Status Change**: Archive/Unarchive toggle
- **Assignment**: Quick PM/department assignment

## Archive/Unarchive Project

### Archive Confirmation
```
┌─────────────────────────────────────────────────────────────────┐
│ Archive Project                                                 │
├─────────────────────────────────────────────────────────────────┤
│ Are you sure you want to archive "Acme Website Revamp"?        │
│                                                                 │
│ This will:                                                      │
│ • Hide the project from active project lists                   │
│ • Prevent new tasks from being assigned                        │
│ • Keep all historical data intact                              │
│                                                                 │
│ You can unarchive it later if needed.                          │
│                                                                 │
│ [Cancel] [Archive Project]                                     │
└─────────────────────────────────────────────────────────────────┘
```

### Archive Behavior
- **Status Change**: Project marked as "Archived"
- **Visibility**: Hidden from active project lists
- **Data Retention**: All historical data preserved
- **Recovery**: Can be unarchived at any time

## Delete Project (Super Admin Only)

### Delete Confirmation
```
┌─────────────────────────────────────────────────────────────────┐
│ Delete Project                                                  │
├─────────────────────────────────────────────────────────────────┤
│ ⚠️ WARNING: This action cannot be undone!                      │
│                                                                 │
│ Are you sure you want to permanently delete "Acme Website Revamp"? │
│                                                                 │
│ This will permanently remove:                                  │
│ • All project data and history                                 │
│ • All timesheet entries                                        │
│ • All project files and resources                              │
│ • All team assignments                                         │
│                                                                 │
│ [Cancel] [Delete Project Permanently]                           │
└─────────────────────────────────────────────────────────────────┘
```

## Bulk Operations

### Bulk Actions Bar
```
┌─────────────────────────────────────────────────────────────────┐
│ 3 projects selected                                            │
│ [Assign PM] [Change Status] [Export Selected] [Clear Selection] │
└─────────────────────────────────────────────────────────────────┘
```

### Bulk Actions Available
- **Assign PM**: Assign same PM to multiple projects
- **Change Status**: Bulk status updates (Ongoing, On Hold, Completed)
- **Export Selected**: CSV export of selected projects
- **Archive**: Bulk archive multiple projects

## Empty State

### Empty State Design
```
┌─────────────────────────────────────────────────────────────────┐
│ 📋 No projects for this customer yet                           │
│                                                                 │
│ Add a project to start tracking progress and managing your      │
│ team's work.                                                   │
│                                                                 │
│ [Create Project]                                                │
└─────────────────────────────────────────────────────────────────┘
```

## Customer Management

### Customer Lookup/Create
```
┌─────────────────────────────────────────────────────────────────┐
│ Select Customer                                                 │
├─────────────────────────────────────────────────────────────────┤
│ [Search customers...]                                           │
│                                                                 │
│ Recent Customers                                                │
│ • Acme Corp (3 projects)                                       │
│ • Orchid Spa (1 project)                                       │
│ • Vista Realty (2 projects)                                    │
│                                                                 │
│ [Create New Customer]                                          │
└─────────────────────────────────────────────────────────────────┘
```

### Create New Customer
```
┌─────────────────────────────────────────────────────────────────┐
│ Create New Customer                                             │
├─────────────────────────────────────────────────────────────────┤
│ Customer Name                                                   │
│ [________________________________]                             │
│                                                                 │
│ Contact Information                                             │
│ Email: [________________________]                             │
│ Phone: [________________________]                             │
│                                                                 │
│ [Cancel] [Create Customer]                                      │
└─────────────────────────────────────────────────────────────────┘
```

## Responsive Behavior

### Desktop (1024px+)
- Full analytics header band with 8-column layout
- Complete table with all columns visible
- Multi-step form with side-by-side layouts
- Modal overlays for edit operations

### Tablet (768px-1023px)
- Two-row analytics layout
- Condensed table with horizontal scroll
- Stacked form layouts
- Full-width modals

### Mobile (360px-767px)
- Single-column analytics cards
- Stacked table rows
- Full-width forms
- Bottom sheet modals

## Role-Based Variations

### Super Admin View
- **Full Analytics**: All metrics visible
- **Complete CRUD**: Create, edit, delete any project
- **System Projects**: Can manage system-level projects
- **Hard Delete**: Can permanently delete projects

### Admin View
- **Scoped Analytics**: Only organizational metrics
- **Limited CRUD**: Cannot edit/delete system projects
- **User Restrictions**: Cannot assign Super Admin users as PM
- **Soft Delete Only**: Can only archive projects

### PM/Team/Client View
- **No Access**: Module completely hidden
- **Redirect**: "Insufficient permissions" page if direct link accessed
- **Guidance**: Contact information for access requests
