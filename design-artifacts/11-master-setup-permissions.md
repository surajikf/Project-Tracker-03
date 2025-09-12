# IKF Project Live Tracker - Master Setup Permission Matrix

## Master Setup Access Control

### Navigation Visibility
| Role | Master Setup Section | Departments | Projects | Users | Stages |
|------|---------------------|-------------|----------|-------|--------|
| Super Admin | ✅ Visible | ✅ Full Access | ✅ Full Access | ✅ Full Access | ✅ Full Access |
| Admin | ✅ Visible | ✅ Org Scope | ✅ Org Scope | ✅ Org Scope | ✅ Org Scope |
| Project Manager | ❌ Hidden | ❌ No Access | ❌ No Access | ❌ No Access | ❌ No Access |
| Team Member | ❌ Hidden | ❌ No Access | ❌ No Access | ❌ No Access | ❌ No Access |
| Client | ❌ Hidden | ❌ No Access | ❌ No Access | ❌ No Access | ❌ No Access |

## Departments Module Permissions

### Super Admin Permissions
| Action | Read | Create | Edit | Delete | Special |
|--------|------|--------|------|--------|---------|
| View All Departments | ✅ | - | - | - | System-wide visibility |
| Create Department | - | ✅ | - | - | No restrictions |
| Edit Department | - | - | ✅ | - | Can edit any department |
| Delete Department | - | - | - | ✅ | Soft delete with confirmation |
| Assign Dept Head | - | - | ✅ | - | Can assign any user |
| View Analytics | ✅ | - | - | - | Full analytics access |

### Admin Permissions
| Action | Read | Create | Edit | Delete | Special |
|--------|------|--------|------|--------|---------|
| View Departments | ✅ | - | - | - | Within organizational scope |
| Create Department | - | ✅ | - | - | Cannot create system departments |
| Edit Department | - | - | ✅ | - | Cannot edit system departments |
| Delete Department | - | - | - | ✅ | Soft delete, cannot delete system depts |
| Assign Dept Head | - | - | ✅ | - | Cannot assign Super Admin users |
| View Analytics | ✅ | - | - | - | Scoped analytics only |

### PM/Team/Client Permissions
| Action | Read | Create | Edit | Delete | Special |
|--------|------|--------|------|--------|---------|
| All Actions | ❌ | ❌ | ❌ | ❌ | No access to Departments module |

## Projects (under Customers) Module Permissions

### Super Admin Permissions
| Action | Read | Create | Edit | Delete | Special |
|--------|------|--------|------|--------|---------|
| View All Projects | ✅ | - | - | - | System-wide visibility |
| Create Project | - | ✅ | - | - | No restrictions |
| Edit Project | - | - | ✅ | - | Can edit any project |
| Archive Project | - | - | ✅ | - | Can archive any project |
| Delete Project | - | - | - | ✅ | Hard delete (Super Admin only) |
| Assign PM | - | - | ✅ | - | Can assign any user as PM |
| Bulk Operations | - | - | ✅ | - | Full bulk access |
| Export Data | ✅ | - | - | - | Full export access |

### Admin Permissions
| Action | Read | Create | Edit | Delete | Special |
|--------|------|--------|------|--------|---------|
| View Projects | ✅ | - | - | - | Within organizational scope |
| Create Project | - | ✅ | - | - | Cannot create system projects |
| Edit Project | - | - | ✅ | - | Cannot edit system projects |
| Archive Project | - | - | ✅ | - | Cannot archive system projects |
| Delete Project | - | - | - | ❌ | Cannot delete projects |
| Assign PM | - | - | ✅ | - | Cannot assign Super Admin users |
| Bulk Operations | - | - | ✅ | - | Limited bulk operations |
| Export Data | ✅ | - | - | - | Scoped export access |

### PM/Team/Client Permissions
| Action | Read | Create | Edit | Delete | Special |
|--------|------|--------|------|--------|---------|
| All Actions | ❌ | ❌ | ❌ | ❌ | No access to Projects module |

## Users Module Permissions

### Super Admin Permissions
| Action | Read | Create | Edit | Delete | Special |
|--------|------|--------|------|--------|---------|
| View All Users | ✅ | - | - | - | System-wide visibility |
| Invite User | - | ✅ | - | - | Can create any role including Super Admin |
| Edit User | - | - | ✅ | - | Can edit any user including Super Admin |
| Deactivate User | - | - | ✅ | - | Can deactivate any user |
| Delete User | - | - | - | ✅ | Hard delete (Super Admin only) |
| Change Roles | - | - | ✅ | - | Can change any role |
| Bulk Operations | - | - | ✅ | - | Full bulk access |
| View Security Data | ✅ | - | - | - | 2FA status, password flags |

### Admin Permissions
| Action | Read | Create | Edit | Delete | Special |
|--------|------|--------|------|--------|---------|
| View Users | ✅ | - | - | - | Cannot see Super Admin users |
| Invite User | - | ✅ | - | - | Cannot create Super Admin users |
| Edit User | - | - | ✅ | - | Cannot edit Super Admin users |
| Deactivate User | - | - | ✅ | - | Cannot deactivate Super Admin users |
| Delete User | - | - | - | ❌ | Cannot delete users |
| Change Roles | - | - | ✅ | - | Cannot change to/from Super Admin |
| Bulk Operations | - | - | ✅ | - | Cannot affect Super Admin users |
| View Security Data | ✅ | - | - | - | Limited security data |

### PM/Team/Client Permissions
| Action | Read | Create | Edit | Delete | Special |
|--------|------|--------|------|--------|---------|
| All Actions | ❌ | ❌ | ❌ | ❌ | No access to Users module |

## Stages Module Permissions

### Super Admin Permissions
| Action | Read | Create | Edit | Delete | Special |
|--------|------|--------|------|--------|---------|
| View All Stages | ✅ | - | - | - | System-wide visibility |
| Create Stage | - | ✅ | - | - | Can create standard and temporary stages |
| Edit Stage | - | - | ✅ | - | Can edit any stage including standard |
| Deactivate Stage | - | - | ✅ | - | Can deactivate any stage |
| Delete Stage | - | - | - | ✅ | Can delete any stage (if not attached) |
| Manage Standard Stages | - | - | ✅ | - | Can activate/deactivate standard stages |
| Weight Management | - | - | ✅ | - | Can normalize weights |
| View Analytics | ✅ | - | - | - | Full analytics access |

### Admin Permissions
| Action | Read | Create | Edit | Delete | Special |
|--------|------|--------|------|--------|---------|
| View Stages | ✅ | - | - | - | Can see all stages |
| Create Stage | - | ✅ | - | - | Can create temporary stages only |
| Edit Stage | - | - | ✅ | - | Cannot edit standard stages |
| Deactivate Stage | - | - | ✅ | - | Cannot deactivate standard stages |
| Delete Stage | - | - | - | ✅ | Can delete temporary stages only |
| Manage Standard Stages | - | - | ❌ | - | Cannot manage standard stages |
| Weight Management | - | - | ✅ | - | Limited weight management |
| View Analytics | ✅ | - | - | - | Scoped analytics only |

### PM/Team/Client Permissions
| Action | Read | Create | Edit | Delete | Special |
|--------|------|--------|------|--------|---------|
| All Actions | ❌ | ❌ | ❌ | ❌ | No access to Stages module |

## Permission Inheritance Rules

### Super Admin
- Inherits all permissions from all roles
- Can override any restriction
- Has system-wide visibility
- Can manage other Super Admin accounts

### Admin
- Inherits PM, Team, and Client permissions for organizational scope
- Cannot access Super Admin-only features
- Cannot delete global templates
- Cannot manage Super Admin users

### PM/Team/Client
- No access to Master Setup modules
- Redirected to "insufficient permissions" page if direct link accessed
- Shown guidance message with contact information

## UI Behavior Rules

### Visibility Rules
- **Hidden**: Master Setup section completely hidden from navigation for PM/Team/Client
- **Disabled**: Actions disabled with tooltip if Admin lacks specific permissions
- **Tooltip Text**: "Requires Super Admin access" for restricted actions

### Action Hierarchy
- **Primary Actions** differ by role:
  - Super Admin: "Delete", "Manage System", "Override Restrictions"
  - Admin: "Create", "Edit", "Bulk Operations"
  - PM/Team/Client: No Master Setup access

### Permission Indicators
- **Lock Icon**: Shows when Admin lacks rights (tooltip shows who can do it)
- **Role Badge**: Displays user's role next to their name
- **Permission Status**: Shows "System" vs "Organization" scope

## Error Handling

### Insufficient Permissions Page
```
Title: "Access Restricted"
Message: "You don't have permission to access Master Setup modules."
Action: "Contact your administrator" or "Return to Dashboard"
```

### Permission Denied Actions
```
Toast: "Action requires Super Admin access"
Tooltip: "Requires Super Admin access"
Modal: "You don't have permission to perform this action"
```

### Role Constraint Violations
```
Validation Error: "Admin cannot create Super Admin users"
Validation Error: "Cannot delete standard stages"
Validation Error: "Cannot edit system departments"
```
