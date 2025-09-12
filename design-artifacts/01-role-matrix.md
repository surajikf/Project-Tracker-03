# IKF Project Live Tracker - Role Matrix & Permissions

## Role Hierarchy
Super Admin → Admin → Project Manager → Team Member → Client (future)

---

## Comprehensive Role Matrix

### Super Admin
**Scope**: System-wide control and visibility
**Color**: Black (#000000)
**Access Level**: Full system access

| Page/Feature | Read | Write | Delete | Special Actions |
|--------------|------|-------|--------|-----------------|
| **Global Settings** | ✅ | ✅ | ✅ | Manage org structure, feature flags |
| **Role Management** | ✅ | ✅ | ✅ | Create/edit/delete roles, assign permissions |
| **Department Libraries** | ✅ | ✅ | ✅ | Manage departments & sub-departments |
| **Audit Logs** | ✅ | ❌ | ❌ | Export, filter, search all logs |
| **Security & Compliance** | ✅ | ✅ | ✅ | Configure security policies |
| **Data Retention** | ✅ | ✅ | ✅ | Set retention policies |
| **Report Templates** | ✅ | ✅ | ✅ | Create/edit/delete templates |
| **Feature Flags** | ✅ | ✅ | ✅ | Enable/disable features |
| **All Projects** | ✅ | ✅ | ✅ | Full CRUD, impersonate lower roles |
| **All Timesheets** | ✅ | ✅ | ✅ | Approve, edit, export |
| **All Approvals** | ✅ | ✅ | ✅ | Override any approval |
| **All Holds** | ✅ | ✅ | ✅ | Remove any hold |
| **User Accounts** | ✅ | ✅ | ✅ | Create/edit/delete (except other Super Admins) |
| **System Health** | ✅ | ✅ | ❌ | Monitor, restart services |

**Special Capabilities**:
- Impersonation mode with warning modal and banner
- Override any restriction
- Access to all audit trails
- System configuration management

---

### Admin
**Scope**: Organization and project operations
**Color**: Slate (#475569)
**Access Level**: Operational management

| Page/Feature | Read | Write | Delete | Special Actions |
|--------------|------|-------|--------|-----------------|
| **Dashboard** | ✅ | ❌ | ❌ | View org-wide KPIs, project pipeline |
| **Projects** | ✅ | ✅ | ✅ | Full CRUD within operational scope |
| **Department Management** | ✅ | ✅ | ✅ | Manage departments/sub-departments |
| **User Management** | ✅ | ✅ | ❌ | Create/edit users (except Super Admin) |
| **Resource Links** | ✅ | ✅ | ✅ | Manage resource link policies |
| **Status Categories** | ✅ | ✅ | ✅ | Create/edit status categories |
| **Reports** | ✅ | ✅ | ❌ | Generate and export reports |
| **Timesheets** | ✅ | ✅ | ❌ | Approve, edit team timesheets |
| **Approvals** | ✅ | ✅ | ❌ | Approve/reject within scope |
| **Holds** | ✅ | ✅ | ❌ | Manage holds (except system-level) |
| **Clients** | ✅ | ✅ | ✅ | Manage client accounts |
| **Settings** | ❌ | ❌ | ❌ | No access to global settings |

**Restrictions**:
- Cannot access system-level settings
- Cannot change feature flags
- Cannot impersonate other users
- Cannot access audit logs

---

### Project Manager
**Scope**: Portfolio and delivery management
**Color**: Indigo (#4F46E5)
**Access Level**: Project-focused management

| Page/Feature | Read | Write | Delete | Special Actions |
|--------------|------|-------|--------|-----------------|
| **Dashboard** | ✅ | ❌ | ❌ | View portfolio KPIs, stage bottlenecks |
| **My Projects** | ✅ | ✅ | ❌ | Create/edit own projects only |
| **Project Stages** | ✅ | ✅ | ✅ | Manage stages within own projects |
| **Team Assignments** | ✅ | ✅ | ❌ | Assign members in allowed departments |
| **Deliverables** | ✅ | ✅ | ✅ | Manage deliverables within projects |
| **Client Approvals** | ✅ | ✅ | ❌ | Request client approvals |
| **Timesheet Rollups** | ✅ | ❌ | ❌ | View timesheet summaries for own projects |
| **Project Reports** | ✅ | ✅ | ❌ | Generate project-level reports |
| **Resource Links** | ✅ | ✅ | ❌ | Access permitted resource links |
| **Holds** | ✅ | ✅ | ❌ | Manage holds within own projects |
| **Settings** | ❌ | ❌ | ❌ | No access to global settings |

**Restrictions**:
- Cannot access other teams' restricted projects
- Cannot manage global settings
- Cannot access user management
- Cannot view system-wide reports

---

### Team Member
**Scope**: Individual task management
**Color**: Teal (#0D9488)
**Access Level**: Task-focused participation

| Page/Feature | Read | Write | Delete | Special Actions |
|--------------|------|-------|--------|-----------------|
| **Dashboard** | ✅ | ❌ | ❌ | View assigned tasks, timesheet quick log |
| **Assigned Projects** | ✅ | ❌ | ❌ | View only assigned projects/stages |
| **Stage Sub-status** | ✅ | ✅ | ❌ | Update sub-status where allowed |
| **Timesheets** | ✅ | ✅ | ❌ | Log own timesheets |
| **Resource Links** | ✅ | ❌ | ❌ | View permitted resource links |
| **Project Progress** | ✅ | ❌ | ❌ | View progress of assigned projects |
| **Deliverables** | ✅ | ❌ | ❌ | View assigned deliverables |
| **Settings** | ❌ | ❌ | ❌ | No access to settings |

**Restrictions**:
- No cross-project visibility unless assigned
- Cannot create or delete projects
- Cannot manage team assignments
- Cannot access reports or analytics
- Cannot manage holds or approvals

---

### Client (Future)
**Scope**: Project oversight and approval
**Color**: Blue (#2563EB)
**Access Level**: Read-only with approval rights

| Page/Feature | Read | Write | Delete | Special Actions |
|--------------|------|-------|--------|-----------------|
| **Dashboard** | ✅ | ❌ | ❌ | View assigned projects, progress overview |
| **Assigned Projects** | ✅ | ❌ | ❌ | View only assigned projects |
| **Project Progress** | ✅ | ❌ | ❌ | View progress percentages |
| **Deliverables** | ✅ | ❌ | ❌ | View deliverables |
| **Approvals** | ✅ | ✅ | ❌ | Approve/request changes on designated stages |
| **Feedback** | ✅ | ✅ | ❌ | Submit feedback and comments |
| **Project Overview** | ✅ | ❌ | ❌ | View project status and timeline |
| **Settings** | ❌ | ❌ | ❌ | No access to settings |

**Restrictions**:
- Read-only access to assigned projects only
- Cannot view internal project details
- Cannot access timesheets or internal reports
- Cannot manage team or resources
- Cannot access system settings

---

## Permission Inheritance Rules

1. **Super Admin** inherits all permissions from all roles
2. **Admin** inherits PM, Team, and Client permissions for operational scope
3. **Project Manager** inherits Team and Client permissions for own projects
4. **Team Member** inherits Client permissions for assigned projects
5. **Client** has the most restricted access

## Action Ownership Matrix

| Action | Owner Role | Required Permission |
|--------|------------|-------------------|
| Manage Organization | Super Admin | Global Settings |
| Create Project | Admin, PM | Project CRUD |
| Assign Team Members | Admin, PM | User Management |
| Approve Timesheets | Admin, PM | Timesheet Management |
| Request Client Approval | PM | Client Communication |
| Log Timesheets | Team Member | Personal Timesheet |
| Approve Deliverables | Client | Client Approval |
| Override Holds | Super Admin | System Override |
| View Audit Logs | Super Admin | Audit Access |
| Manage Feature Flags | Super Admin | System Configuration |

## UI Behavior Rules

### Visibility Rules
- **Hidden**: Components completely hidden if no permission
- **Disabled**: Components shown but disabled with tooltip if discoverability needed
- **Tooltip Text**: "Requires {Role} access" for disabled actions

### Action Hierarchy
- **Primary Actions** differ by role:
  - Super Admin: "Manage Org"
  - Admin: "New Project" 
  - PM: "Add Stage"
  - Team: "Log Time"
  - Client: "Approve"

### Status & Holds Display
- **Client Hold**: Amber banner chip with reason + timestamp
- **Team Hold**: Purple banner chip with reason + timestamp
- **Surface on**: Dashboards and project detail views

### Audit Cues
- **Super Admin/Admin**: Inline "last changed by {user} on {date}" near stage toggles and approvals
- **Impersonation**: Header banner + exit button; restricted actions hidden to match target role
