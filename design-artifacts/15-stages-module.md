# IKF Project Live Tracker - Stages Module Design

## Module Overview
**Path**: Master Setup › Stages  
**Access**: Super Admin (full), Admin (org scope), PM/Team/Client (no access)  
**Breadcrumb**: Home › Master Setup › Stages  
**Purpose**: Manage project stages with weight validation and usage tracking

## Analytics Widget (Right Rail Card)

### Right Rail Layout
```
┌─────────────────────────────────────────────────────────────────┐
│ Stage Analytics                                                 │
├─────────────────────────────────────────────────────────────────┤
│ Weight Integrity                                                │
│ ┌─────────────────────────────────────────────────────────────┐ │
│ │ Active Weight Total: 100% ✅                               │ │
│ │ ████████████████████████████████████████████████████████   │ │
│ │ Target: 100% | Current: 100%                               │ │
│ └─────────────────────────────────────────────────────────────┘ │
│                                                                 │
│ Usage Statistics                                                │
│ • Handshake: 24 projects                                       │
│ • Design: 22 projects                                          │
│ • Development: 20 projects                                     │
│ • QA & Testing: 18 projects                                    │
│ • Go Live: 15 projects                                         │
│                                                                 │
│ Risk Indicators                                                 │
│ ⚠️ 2 projects missing required standard stages                │
│                                                                 │
│ Quick Actions                                                   │
│ [New Stage] [Deactivate Temporary] [Normalize Weights]        │
└─────────────────────────────────────────────────────────────────┘
```

### Analytics Components
- **Weight Integrity**: Live meter showing active weight total (goal 100%)
- **Usage Statistics**: # projects using each stage, top 5 by usage
- **Risk Indicators**: Projects missing required standard stages
- **Quick Actions**: New Stage, Deactivate Temporary Stages, Normalize Weights

## List View (Table)

### Table Structure
```
┌─────────────────────────────────────────────────────────────────┐
│ [Search] [Filter: All Types] [Sort: Weight] [New Stage]       │
├─────────────────────────────────────────────────────────────────┤
│ Stage Name │ Type │ Weight │ Sub-statuses │ Active │ Usage │ Actions │
├─────────────────────────────────────────────────────────────────┤
│ Handshake  │ Std  │ 10%    │ 3            │ ✅     │ 24    │ [Edit]  │
│ Sitemap    │ Std  │ 5%     │ 2            │ ✅     │ 22    │ [Edit]  │
│ Design     │ Std  │ 25%    │ 4            │ ✅     │ 20    │ [Edit]  │
│ Development│ Std  │ 40%    │ 5            │ ✅     │ 18    │ [Edit]  │
│ QA & Test  │ Std  │ 15%    │ 3            │ ✅     │ 15    │ [Edit]  │
│ Go Live    │ Std  │ 5%     │ 2            │ ✅     │ 12    │ [Edit]  │
│ Custom Dev │ Temp │ 0%     │ 0            │ ❌     │ 0     │ [Edit]  │
└─────────────────────────────────────────────────────────────────┘
```

### Table Columns
- **Stage Name**: Stage identifier, sortable
- **Type**: Standard/Temporary badge, filterable
- **Weight (%)**: Percentage weight, sortable, with validation
- **Sub-statuses**: Count of sub-statuses, clickable to view
- **Active**: Toggle status, filterable
- **Usage**: Number of projects using this stage
- **Actions**: Edit, Deactivate, Delete (if not attached to active project)

### Table Actions
- **Row Actions**: Edit, Deactivate, Delete (if not attached to active project)
- **Bulk Actions**: Deactivate Temporary Stages, Normalize Weights
- **Filters**: by Type, Active Status, Weight Range
- **Sort**: by Name, Type, Weight, Usage Count

## Create Stage (Modal/Form)

### Create Modal Structure
```
┌─────────────────────────────────────────────────────────────────┐
│ Create Stage                                        [Close]     │
├─────────────────────────────────────────────────────────────────┤
│ Stage Name                                                       │
│ [________________________________]                             │
│                                                                 │
│ Stage Type                                                       │
│ ○ Standard Stage (used across all projects)                    │
│ ○ Temporary Stage (project-specific)                           │
│                                                                 │
│ Weight Percentage                                               │
│ [____] %                                                        │
│ Current total: 85% | Remaining: 15%                           │
│                                                                 │
│ Sub-statuses (Optional)                                         │
│ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ [+ Add]        │
│ │ In Progress │ │ On Hold     │ │ Completed   │                │
│ │ [×]         │ │ [×]         │ │ [×]         │                │
│ └─────────────┘ └─────────────┘ └─────────────┘                │
│                                                                 │
│ [Cancel] [Create Stage]                                         │
└─────────────────────────────────────────────────────────────────┘
```

### Form Fields
- **Stage Name**: Text input, required, unique validation
- **Stage Type**: Radio buttons (Standard/Temporary)
- **Weight Percentage**: Number input, required, validation against total
- **Sub-statuses**: Repeatable chips with add/remove functionality

### Validation Rules
- **Stage Name**: Required, unique, min 2 characters
- **Weight Percentage**: Required, 0-100%, sum of active stages must equal 100%
- **Standard Stages**: Cannot be deleted, can only be deactivated
- **Temporary Stages**: Can be deleted if not attached to active projects

### Real-time Validation
- **Weight Total**: Shows running total and remaining percentage
- **Error States**: Red border and error message if total exceeds 100%
- **Success States**: Green indicator when total equals 100%

## Edit Stage (Modal/Form)

### Edit Modal Structure
```
┌─────────────────────────────────────────────────────────────────┐
│ Edit Stage: Design                                  [Close]     │
├─────────────────────────────────────────────────────────────────┤
│ Stage Name                                                       │
│ [Design Stage                    ]                             │
│                                                                 │
│ Stage Type                                                       │
│ ○ Standard Stage (cannot be changed)                           │
│ ○ Temporary Stage                                              │
│                                                                 │
│ Weight Percentage                                               │
│ [25] %                                                          │
│ Current total: 100% ✅                                         │
│                                                                 │
│ Sub-statuses                                                    │
│ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ [+ Add]        │
│ │ In Progress │ │ On Hold     │ │ Completed   │                │
│ │ [×]         │ │ [×]         │ │ [×]         │                │
│ └─────────────┘ └─────────────┘ └─────────────┘                │
│                                                                 │
│ Usage Information                                               │
│ Used in 20 active projects                                      │
│ Last used: 2 days ago                                           │
│                                                                 │
│ [Cancel] [Save Changes] [Deactivate] [Delete] (if temp)       │
└─────────────────────────────────────────────────────────────────┘
```

### Edit Actions
- **Inline Edit**: Quick edits directly in table
- **Modal Edit**: Full form in modal overlay
- **Weight Adjustment**: Real-time validation of total weights
- **Sub-status Management**: Add/remove sub-statuses

## Deactivate Stage

### Deactivate Confirmation
```
┌─────────────────────────────────────────────────────────────────┐
│ Deactivate Stage                                               │
├─────────────────────────────────────────────────────────────────┤
│ Are you sure you want to deactivate "Custom Development"?      │
│                                                                 │
│ This will:                                                      │
│ • Remove the stage from new project creation                   │
│ • Keep existing projects using this stage intact               │
│ • Allow reactivation later if needed                           │
│                                                                 │
│ ⚠️ Note: Standard stages cannot be deactivated by Admin        │
│                                                                 │
│ [Cancel] [Deactivate Stage]                                    │
└─────────────────────────────────────────────────────────────────┘
```

### Deactivate Behavior
- **Status Change**: Stage marked as "Inactive"
- **New Projects**: Stage not available for new project creation
- **Existing Projects**: Projects using this stage remain unaffected
- **Recovery**: Can be reactivated at any time

## Delete Stage (Temporary Only)

### Delete Confirmation
```
┌─────────────────────────────────────────────────────────────────┐
│ Delete Stage                                                    │
├─────────────────────────────────────────────────────────────────┤
│ ⚠️ WARNING: This action cannot be undone!                      │
│                                                                 │
│ Are you sure you want to permanently delete "Custom Development"? │
│                                                                 │
│ This will permanently remove:                                  │
│ • The stage from all projects                                   │
│ • All associated sub-statuses                                   │
│ • All historical stage data                                     │
│                                                                 │
│ ⚠️ Cannot delete if stage is attached to active projects       │
│                                                                 │
│ [Cancel] [Delete Stage Permanently]                             │
└─────────────────────────────────────────────────────────────────┘
```

### Delete Constraints
- **Temporary Stages Only**: Standard stages cannot be deleted
- **No Active Projects**: Cannot delete if stage is used in active projects
- **Super Admin Only**: Only Super Admin can delete stages
- **Cascade Effects**: Removes stage from all projects and historical data

## Weight Management

### Weight Validation
```
┌─────────────────────────────────────────────────────────────────┐
│ Weight Validation                                               │
├─────────────────────────────────────────────────────────────────┤
│ Current Active Stages:                                          │
│ • Handshake: 10%                                               │
│ • Sitemap: 5%                                                  │
│ • Design: 25%                                                  │
│ • Development: 40%                                             │
│ • QA & Testing: 15%                                            │
│ • Go Live: 5%                                                  │
│                                                                 │
│ Total: 100% ✅                                                 │
│                                                                 │
│ [Normalize Weights] [Reset to Defaults]                        │
└─────────────────────────────────────────────────────────────────┘
```

### Normalize Weights
```
┌─────────────────────────────────────────────────────────────────┐
│ Normalize Weights                                               │
├─────────────────────────────────────────────────────────────────┤
│ Current total: 105% (5% over)                                  │
│                                                                 │
│ Normalize options:                                              │
│ ○ Reduce all stages proportionally                             │
│ ○ Reduce largest stages first                                  │
│ ○ Reset to default weights                                     │
│                                                                 │
│ [Cancel] [Normalize Weights]                                   │
└─────────────────────────────────────────────────────────────────┘
```

## Standard Stages Management

### Default Standard Stages
```
┌─────────────────────────────────────────────────────────────────┐
│ Standard Stages (System Defaults)                              │
├─────────────────────────────────────────────────────────────────┤
│ 1. Handshake (10%) - Initial project setup                     │
│ 2. Sitemap (5%) - Site structure planning                      │
│ 3. Data Gathering (5%) - Requirements collection              │
│ 4. Content Writing (10%) - Content creation                    │
│ 5. Design (25%) - Visual design and mockups                    │
│ 6. Development (40%) - Code implementation                     │
│ 7. QA & Testing (15%) - Quality assurance                      │
│ 8. Tech Support/Go Live (5%) - Launch and support              │
│                                                                 │
│ Total: 100%                                                    │
│                                                                 │
│ [Reset to Defaults] [Customize Weights]                         │
└─────────────────────────────────────────────────────────────────┘
```

### Standard Stage Constraints
- **Cannot Delete**: Standard stages cannot be permanently deleted
- **Can Deactivate**: Super Admin can deactivate standard stages
- **Weight Management**: Can adjust weights but total must equal 100%
- **System Integration**: Used across all projects by default

## Bulk Operations

### Bulk Actions Bar
```
┌─────────────────────────────────────────────────────────────────┐
│ 3 stages selected                                              │
│ [Deactivate Selected] [Normalize Weights] [Clear Selection]    │
└─────────────────────────────────────────────────────────────────┘
```

### Bulk Actions Available
- **Deactivate Selected**: Bulk deactivation of temporary stages
- **Normalize Weights**: Adjust weights to total 100%
- **Export Selected**: CSV export of selected stages

## Empty State

### Empty State Design
```
┌─────────────────────────────────────────────────────────────────┐
│ 📋 No custom stages yet                                        │
│                                                                 │
│ Add a new custom stage or use the default standard stages       │
│ for your projects.                                             │
│                                                                 │
│ [Create Stage] [View Defaults]                                 │
└─────────────────────────────────────────────────────────────────┘
```

## Responsive Behavior

### Desktop (1024px+)
- Right rail analytics card
- Complete table with all columns visible
- Modal overlays for create/edit
- Side-by-side weight management

### Tablet (768px-1023px)
- Top analytics card
- Condensed table with horizontal scroll
- Full-width modals
- Stacked weight management

### Mobile (360px-767px)
- Single-column analytics cards
- Stacked table rows
- Full-width forms
- Bottom sheet modals

## Role-Based Variations

### Super Admin View
- **Full Analytics**: All metrics visible including system-wide usage
- **Complete CRUD**: Create, edit, delete any stage including standard
- **Standard Stage Management**: Can deactivate standard stages
- **Weight Override**: Can override weight validation constraints

### Admin View
- **Scoped Analytics**: Only organizational metrics
- **Limited CRUD**: Cannot edit/delete standard stages
- **Temporary Stages Only**: Can only manage temporary stages
- **Weight Management**: Can adjust weights within constraints

### PM/Team/Client View
- **No Access**: Module completely hidden
- **Redirect**: "Insufficient permissions" page if direct link accessed
- **Guidance**: Contact information for access requests
