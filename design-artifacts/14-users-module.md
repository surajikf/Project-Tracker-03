# IKF Project Live Tracker - Users Module Design

## Module Overview
**Path**: Master Setup › Users  
**Access**: Super Admin (full), Admin (org scope), PM/Team/Client (no access)  
**Breadcrumb**: Home › Master Setup › Users  
**Purpose**: Manage user accounts, roles, and assignments to departments/projects

## Analytics Widget (Sticky Header Card)

### Header Card Layout
```
┌─────────────────────────────────────────────────────────────────┐
│ Users Analytics                                                 │
├─────────────────────────────────────────────────────────────────┤
│ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ │
│ │ Total Users │ │ Active      │ │ Inactive    │ │ Unassigned  │ │
│ │ 47          │ │ 42          │ │ 5           │ │ 3           │ │
│ └─────────────┘ └─────────────┘ └─────────────┘ └─────────────┘ │
│ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ │
│ │ Super Admin │ │ Admin       │ │ PM          │ │ Team        │ │
│ │ 2           │ │ 3           │ │ 8           │ │ 28          │ │
│ └─────────────┘ └─────────────┘ └─────────────┘ └─────────────┘ │
│ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ │
│ │ Client      │ │ No 2FA     │ │ Default Pwd │ │ Last Login  │ │
│ │ 6           │ │ 12          │ │ 8           │ │ 2d ago      │ │
│ └─────────────┘ └─────────────┘ └─────────────┘ └─────────────┘ │
└─────────────────────────────────────────────────────────────────┘
```

### Role Distribution Donut Chart
```
┌─────────────────────────────────────────────────────────────────┐
│ Role Distribution                                               │
├─────────────────────────────────────────────────────────────────┤
│ ┌─────────────────────────┐ ┌─────────────────────────┐        │
│ │                         │ │ Super Admin: 2 (4%)      │        │
│ │        ████████         │ │ Admin: 3 (6%)            │        │
│ │     ██████████████      │ │ PM: 8 (17%)              │        │
│ │  ████████████████████   │ │ Team: 28 (60%)           │        │
│ │ ██████████████████████  │ │ Client: 6 (13%)          │        │
│ │                         │ │                         │        │
│ └─────────────────────────┘ └─────────────────────────┘        │
└─────────────────────────────────────────────────────────────────┘
```

### Analytics Components
- **Role Distribution**: Donut chart showing role breakdown
- **Utilization**: # inactive vs active, unassigned users count
- **Security**: Users without 2FA, default password flags
- **Activity**: Last login information, security alerts
- **Quick Actions**: Invite User, Bulk Assign to Project, Change Roles

## List View (Table)

### Table Structure
```
┌─────────────────────────────────────────────────────────────────┐
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

### Table Columns
- **Name**: User's full name, sortable
- **Email**: Email address, clickable to send email
- **Role**: Role badge (Super Admin/Admin/PM/Team/Client), filterable
- **Department(s)**: Chips showing assigned departments
- **Project(s)**: Chips showing assigned projects
- **Status**: Active/Inactive badge, filterable
- **Actions**: Edit, Deactivate/Reactivate, Delete (Super Admin only)

### Table Actions
- **Row Actions**: Edit, Deactivate/Reactivate, Delete (Super Admin only)
- **Bulk Actions**: Assign to Project, Change Role, Deactivate
- **Filters**: by Role, Department, Project, Status
- **Sort**: by Name, Email, Role, Last Active

## Invite User (Multi-step Form)

### Step 1: Basic Information
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

### Step 2: Assignments
```
┌─────────────────────────────────────────────────────────────────┐
│ Invite User - Step 2 of 3                                      │
├─────────────────────────────────────────────────────────────────┤
│ Assign to Departments                                           │
│ ☑ Website                                                       │
│ ☑ Mobile                                                        │
│ ☐ Marketing                                                     │
│ ☐ Sales                                                         │
│                                                                 │
│ Assign to Projects                                              │
│ ☑ Acme Website Revamp                                          │
│ ☑ Orchid eCommerce Launch                                      │
│ ☐ Vista Realty Corporate Site                                  │
│                                                                 │
│ [Previous] [Next]                                              │
└─────────────────────────────────────────────────────────────────┘
```

### Step 3: Access & Security
```
┌─────────────────────────────────────────────────────────────────┐
│ Invite User - Step 3 of 3                                      │
├─────────────────────────────────────────────────────────────────┤
│ Access Method                                                   │
│ ○ Send invitation email (recommended)                          │
│ ○ Set temporary password                                        │
│                                                                 │
│ Temporary Password (if selected)                               │
│ [________________________________]                             │
│                                                                 │
│ Security Settings                                               │
│ ☑ Require 2FA setup on first login                             │
│ ☑ Force password change on first login                         │
│                                                                 │
│ [Previous] [Send Invitation]                                   │
└─────────────────────────────────────────────────────────────────┘
```

### Form Validation
- **Full Name**: Required, min 2 characters
- **Email**: Required, valid email format, unique
- **Role**: Required, must be valid role
- **Departments**: At least one required for PM/Team roles
- **Projects**: Optional, but recommended for PM/Team roles

## Edit User (Modal/Form)

### Edit Modal Structure
```
┌─────────────────────────────────────────────────────────────────┐
│ Edit User: Priya Nair                              [Close]     │
├─────────────────────────────────────────────────────────────────┤
│ Basic Information                                               │
│ Name: [Priya Nair                    ]                         │
│ Email: [priya@ikf.com                ] (cannot be changed)     │
│                                                                 │
│ Role & Status                                                    │
│ Role: [Project Manager ▼]                                       │
│ Status: [Active ▼] [Deactivate]                                │
│                                                                 │
│ Assignments                                                      │
│ Departments: ☑ Website ☑ Mobile ☐ Marketing                   │
│ Projects: ☑ Acme Website ☑ Orchid eCommerce ☐ Vista Realty    │
│                                                                 │
│ Security                                                        │
│ Last Login: 2 days ago                                          │
│ 2FA Status: ✅ Enabled                                          │
│ Password: [Reset Password]                                     │
│                                                                 │
│ [Cancel] [Save Changes] [Delete User] (Super Admin only)       │
└─────────────────────────────────────────────────────────────────┘
```

### Edit Actions
- **Inline Edit**: Quick edits directly in table
- **Modal Edit**: Full form in modal overlay
- **Status Change**: Activate/Deactivate toggle
- **Role Change**: Dropdown with role constraints
- **Assignment**: Quick department/project assignment

## Deactivate/Reactivate User

### Deactivate Confirmation
```
┌─────────────────────────────────────────────────────────────────┐
│ Deactivate User                                                 │
├─────────────────────────────────────────────────────────────────┤
│ Are you sure you want to deactivate "Sarah Johnson"?           │
│                                                                 │
│ This will:                                                      │
│ • Prevent the user from logging in                             │
│ • Remove them from all active project assignments              │
│ • Preserve all historical data                                 │
│                                                                 │
│ You can reactivate them later if needed.                       │
│                                                                 │
│ [Cancel] [Deactivate User]                                     │
└─────────────────────────────────────────────────────────────────┘
```

### Deactivate Behavior
- **Status Change**: User marked as "Inactive"
- **Access Revoked**: Cannot log in to system
- **Assignments**: Removed from active projects
- **Data Retention**: All historical data preserved
- **Recovery**: Can be reactivated at any time

## Delete User (Super Admin Only)

### Delete Confirmation
```
┌─────────────────────────────────────────────────────────────────┐
│ Delete User                                                     │
├─────────────────────────────────────────────────────────────────┤
│ ⚠️ WARNING: This action cannot be undone!                      │
│                                                                 │
│ Are you sure you want to permanently delete "Sarah Johnson"?   │
│                                                                 │
│ This will permanently remove:                                  │
│ • User account and all login credentials                       │
│ • All timesheet entries                                        │
│ • All project assignments                                      │
│ • All historical activity                                      │
│                                                                 │
│ [Cancel] [Delete User Permanently]                              │
└─────────────────────────────────────────────────────────────────┘
```

## Bulk Operations

### Bulk Actions Bar
```
┌─────────────────────────────────────────────────────────────────┐
│ 5 users selected                                               │
│ [Assign to Project] [Change Role] [Deactivate] [Clear Selection] │
└─────────────────────────────────────────────────────────────────┘
```

### Bulk Actions Available
- **Assign to Project**: Assign multiple users to same project
- **Change Role**: Bulk role changes (with constraints)
- **Deactivate**: Bulk deactivation of users
- **Export Selected**: CSV export of selected users

### Bulk Role Change
```
┌─────────────────────────────────────────────────────────────────┐
│ Bulk Change Role                                                │
├─────────────────────────────────────────────────────────────────┤
│ Change role for 5 selected users to:                            │
│                                                                 │
│ [Dropdown: Select New Role]                                     │
│                                                                 │
│ ⚠️ Note: Admin cannot change users to/from Super Admin role    │
│                                                                 │
│ [Cancel] [Change Roles]                                         │
└─────────────────────────────────────────────────────────────────┘
```

## Role Constraints

### Admin Restrictions
- **Cannot create Super Admin users**: Role dropdown excludes Super Admin
- **Cannot edit Super Admin users**: Super Admin users hidden from Admin view
- **Cannot change to/from Super Admin**: Bulk operations exclude Super Admin role
- **Cannot delete users**: Delete action hidden for Admin role

### Super Admin Overrides
- **Can manage Super Admin users**: Full access to all user types
- **Can override role constraints**: Can change any role to any other role
- **Can delete any user**: Hard delete available for all users
- **Can see all users**: System-wide visibility

## Security Features

### 2FA Management
- **Status Display**: Shows 2FA enabled/disabled status
- **Enforcement**: Can require 2FA setup on first login
- **Reset**: Super Admin can reset 2FA for users
- **Analytics**: Count of users without 2FA

### Password Management
- **Reset**: Super Admin can reset user passwords
- **Temporary**: Can set temporary passwords for new users
- **Force Change**: Can require password change on first login
- **Default Detection**: Flags users with default passwords

## Empty State

### Empty State Design
```
┌─────────────────────────────────────────────────────────────────┐
│ 👥 No users in this view                                       │
│                                                                 │
│ Add users to build your team and start assigning them to       │
│ projects and departments.                                       │
│                                                                 │
│ [Invite User]                                                   │
└─────────────────────────────────────────────────────────────────┘
```

## Responsive Behavior

### Desktop (1024px+)
- Full analytics header with 12-column layout
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
- **Full Analytics**: All metrics visible including security data
- **Complete CRUD**: Create, edit, delete any user including Super Admin
- **System Users**: Can manage system-level users
- **Override Permissions**: Can change any role to any other role

### Admin View
- **Scoped Analytics**: Only organizational metrics
- **Limited CRUD**: Cannot create/edit/delete Super Admin users
- **Role Restrictions**: Cannot change users to/from Super Admin
- **Permission Indicators**: Lock icons for restricted actions

### PM/Team/Client View
- **No Access**: Module completely hidden
- **Redirect**: "Insufficient permissions" page if direct link accessed
- **Guidance**: Contact information for access requests
