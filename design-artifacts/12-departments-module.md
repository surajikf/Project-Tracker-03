# IKF Project Live Tracker - Departments Module Design

## Module Overview
**Path**: Master Setup › Departments  
**Access**: Super Admin (full), Admin (org scope), PM/Team/Client (no access)  
**Breadcrumb**: Home › Master Setup › Departments

## Analytics Widget (Top Card)

### Layout Structure
```
┌─────────────────────────────────────────────────────────────────┐
│ Departments Analytics                                           │
├─────────────────────────────────────────────────────────────────┤
│ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ │
│ │ Total       │ │ Sub-dept    │ │ Coverage    │ │ Risk        │ │
│ │ Departments │ │ Count       │ │ % Projects  │ │ Unstaffed   │ │
│ │ 12          │ │ 24          │ │ 85%         │ │ 2           │ │
│ └─────────────┘ └─────────────┘ └─────────────┘ └─────────────┘ │
├─────────────────────────────────────────────────────────────────┤
│ Coverage Heatmap: ████████████████████████████████████████████ │
│ [New Department] [Add Sub-department] [Assign Dept Head]        │
└─────────────────────────────────────────────────────────────────┘
```

### Analytics Components
- **Totals Card**: # Departments, # Sub-departments (distinct count)
- **Coverage Card**: % projects with department assignments
- **Heatmap Sparkline**: Departments by active projects (visual bar)
- **Risk Card**: "Unstaffed departments" count (dept exists but no head assigned)
- **Quick Actions**: Primary action buttons for common operations

### Data Visualization
- **Heatmap**: Horizontal bar showing project distribution across departments
- **Color Coding**: Green (well-staffed), Yellow (understaffed), Red (unstaffed)
- **Tooltip**: Shows department name and project count on hover

## List View (Table)

### Table Structure
```
┌─────────────────────────────────────────────────────────────────┐
│ [Search] [Filter: All] [Sort: Name] [New Department]           │
├─────────────────────────────────────────────────────────────────┤
│ Department Name │ Sub-Departments │ Head │ Created By │ Updated │
├─────────────────────────────────────────────────────────────────┤
│ Website         │ Design, Dev     │ Priya│ Admin      │ 2d ago │
│ Mobile          │ iOS, Android    │ Arjun│ Admin      │ 1w ago │
│ Marketing       │ Content, SEO    │ -    │ Admin      │ 3d ago │
│ Sales           │ Lead Gen, CRM    │ Sarah│ Admin      │ 5d ago │
└─────────────────────────────────────────────────────────────────┘
```

### Table Columns
- **Department Name**: Primary identifier, sortable
- **Sub-Departments**: Chips showing sub-departments, count indicator
- **Head**: Assigned department head (name or "Unassigned")
- **Created By**: User who created the department
- **Last Updated**: Relative time (e.g., "2d ago")

### Table Actions
- **Row Actions**: Edit, Delete (soft), Assign Head
- **Bulk Actions**: Assign Head, Delete (when rows selected)
- **Filters**: by name, head, # of sub-departments
- **Sort**: by name, head, # of sub-departments, last updated

## Create Department (Modal)

### Modal Structure
```
┌─────────────────────────────────────────────────────────────────┐
│ Create Department                                    [Close]     │
├─────────────────────────────────────────────────────────────────┤
│ Department Name                                                 │
│ [________________________________]                             │
│                                                                 │
│ Sub-Departments                                                │
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

### Form Fields
- **Department Name**: Text input, required, unique validation
- **Sub-Departments**: Repeatable chips with add/remove functionality
- **Assign Department Head**: Dropdown with user list (excludes Super Admin for Admin role)

### Validation Rules
- **Department Name**: Required, unique, min 2 characters
- **Sub-Departments**: Minimum 1 required
- **Department Head**: Optional, must be valid user

### Form States
- **Default**: Empty form with placeholder text
- **Validating**: Real-time validation feedback
- **Error**: Inline error messages below fields
- **Success**: Confirmation message and redirect to list

## Edit Department (Inline/Modal)

### Inline Edit Structure
```
┌─────────────────────────────────────────────────────────────────┐
│ Department: Website                                             │
│ ┌─────────────────────────────────────────────────────────────┐ │
│ │ Name: [Website Department        ] [Save] [Cancel]          │ │
│ │ Sub-depts: [Design] [Development] [QA] [+ Add]             │ │
│ │ Head: [Priya Nair ▼] [Assign]                              │ │
│ └─────────────────────────────────────────────────────────────┘ │
└─────────────────────────────────────────────────────────────────┘
```

### Edit Actions
- **Inline Edit**: Click to edit directly in table row
- **Modal Edit**: Full form in modal overlay
- **Quick Assign**: Direct head assignment without full edit

### Permission Indicators
- **Lock Icon**: Shows when Admin cannot edit system departments
- **Tooltip**: "Requires Super Admin access" for restricted actions
- **Disabled State**: Grayed out with explanation

## Delete Department (Soft Delete)

### Confirmation Modal
```
┌─────────────────────────────────────────────────────────────────┐
│ Delete Department                                               │
├─────────────────────────────────────────────────────────────────┤
│ Are you sure you want to delete "Marketing Department"?         │
│                                                                 │
│ This will:                                                      │
│ • Remove the department from all projects                      │
│ • Unassign all users from this department                      │
│ • Archive all sub-departments                                  │
│                                                                 │
│ This action cannot be undone.                                  │
│                                                                 │
│ [Cancel] [Delete Department]                                   │
└─────────────────────────────────────────────────────────────────┘
```

### Soft Delete Behavior
- **Status Change**: Department marked as "deleted" but not removed
- **Cascade Effects**: Users unassigned, projects updated
- **Recovery**: Super Admin can restore deleted departments
- **Audit Trail**: Delete action logged with user and timestamp

## Empty State

### Empty State Design
```
┌─────────────────────────────────────────────────────────────────┐
│ 📁 No departments yet                                          │
│                                                                 │
│ Create your first department to begin assigning users and      │
│ organizing your projects.                                       │
│                                                                 │
│ [Create Department]                                             │
└─────────────────────────────────────────────────────────────────┘
```

### Empty State Components
- **Icon**: Folder icon (📁)
- **Title**: "No departments yet"
- **Description**: Explanation of what departments are used for
- **Action**: Primary "Create Department" button

## Responsive Behavior

### Desktop (1024px+)
- Full analytics widget with 4-column layout
- Complete table with all columns visible
- Side-by-side form layouts
- Modal overlays for create/edit

### Tablet (768px-1023px)
- Two-column analytics layout
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
- **Complete CRUD**: Create, edit, delete any department
- **System Departments**: Can manage system-level departments
- **Override Permissions**: Can delete protected departments

### Admin View
- **Scoped Analytics**: Only organizational metrics
- **Limited CRUD**: Cannot edit/delete system departments
- **User Restrictions**: Cannot assign Super Admin users as heads
- **Permission Indicators**: Lock icons for restricted actions

### PM/Team/Client View
- **No Access**: Module completely hidden
- **Redirect**: "Insufficient permissions" page if direct link accessed
- **Guidance**: Contact information for access requests
