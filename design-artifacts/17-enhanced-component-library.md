# IKF Project Live Tracker - Enhanced Component Library (Master Setup)

## Analytics Cards

### Small Analytics Card
```
┌─────────────────────────────────────────────────────────────────┐
│ Total Departments                                               │
│ 12                                                              │
│ +2 from last month                                              │
└─────────────────────────────────────────────────────────────────┘
```

### Medium Analytics Card
```
┌─────────────────────────────────────────────────────────────────┐
│ Coverage % Projects                                             │
│ 85%                                                             │
│ ████████████████████████████████████████████████████████████   │
│ +5% from last month                                             │
└─────────────────────────────────────────────────────────────────┘
```

### Large Analytics Card
```
┌─────────────────────────────────────────────────────────────────┐
│ PM Load Distribution                                            │
├─────────────────────────────────────────────────────────────────┤
│ • Priya Nair: 6 projects                                       │
│ • Arjun Mehta: 4 projects                                      │
│ • Sarah Johnson: 3 projects                                    │
│ • Mike Chen: 2 projects                                        │
│ • Others: 9 projects                                           │
└─────────────────────────────────────────────────────────────────┘
```

### Analytics Card CSS Tokens
```css
:root {
  /* Analytics Card Sizes */
  --analytics-card-sm: 120px;
  --analytics-card-md: 200px;
  --analytics-card-lg: 300px;
  
  /* Analytics Colors */
  --analytics-positive: #10B981;
  --analytics-negative: #EF4444;
  --analytics-neutral: #64748B;
  --analytics-warning: #F59E0B;
  
  /* Analytics Backgrounds */
  --analytics-bg: #F8FAFC;
  --analytics-border: #E2E8F0;
  --analytics-shadow: 0 1px 3px rgba(0,0,0,0.1);
}
```

### Analytics Card States
```
Default State
┌─────────────────────────────────────────────────────────────────┐
│ Total Departments                                               │
│ 12                                                              │
│ +2 from last month                                              │
│ Background: #F8FAFC                                             │
│ Border: 1px solid #E2E8F0                                      │
│ Shadow: 0 1px 3px rgba(0,0,0,0.1)                              │
└─────────────────────────────────────────────────────────────────┘

Hover State
┌─────────────────────────────────────────────────────────────────┐
│ Total Departments                                               │
│ 12                                                              │
│ +2 from last month                                              │
│ Background: #FFFFFF                                             │
│ Border: 1px solid #CBD5E1                                      │
│ Shadow: 0 4px 6px rgba(0,0,0,0.1)                              │
│ Transform: translateY(-1px)                                    │
└─────────────────────────────────────────────────────────────────┘

Loading State
┌─────────────────────────────────────────────────────────────────┐
│ Total Departments                                               │
│ ████████████████████████████████████████████████████████████   │
│ Loading...                                                     │
│ Background: #F8FAFC                                             │
│ Border: 1px solid #E2E8F0                                      │
│ Shimmer animation                                              │
└─────────────────────────────────────────────────────────────────┘
```

## Progress Meters

### Weight Progress Meter
```
┌─────────────────────────────────────────────────────────────────┐
│ Weight Integrity                                                │
│ Active Weight Total: 100% ✅                                   │
│ ████████████████████████████████████████████████████████████   │
│ Target: 100% | Current: 100%                                   │
└─────────────────────────────────────────────────────────────────┘
```

### Usage Progress Meter
```
┌─────────────────────────────────────────────────────────────────┐
│ Stage Usage                                                     │
│ Design Stage: 20 projects                                      │
│ ████████████████████████████████████████████████████████████   │
│ 83% of active projects                                          │
└─────────────────────────────────────────────────────────────────┘
```

### Progress Meter CSS Tokens
```css
:root {
  /* Progress Meter Colors */
  --progress-meter-bg: #F1F5F9;
  --progress-meter-fill: #00BFA6;
  --progress-meter-target: #10B981;
  --progress-meter-warning: #F59E0B;
  --progress-meter-error: #EF4444;
  
  /* Progress Meter Heights */
  --progress-meter-height-sm: 8px;
  --progress-meter-height-md: 12px;
  --progress-meter-height-lg: 16px;
  
  /* Progress Meter Borders */
  --progress-meter-border: #E2E8F0;
  --progress-meter-radius: 999px;
}
```

### Progress Meter States
```
Default State
┌─────────────────────────────────────────────────────────────────┐
│ Weight Integrity                                                │
│ Active Weight Total: 100% ✅                                   │
│ ████████████████████████████████████████████████████████████   │
│ Background: #F1F5F9                                             │
│ Fill: #10B981                                                  │
│ Border: 1px solid #E2E8F0                                      │
└─────────────────────────────────────────────────────────────────┘

Warning State
┌─────────────────────────────────────────────────────────────────┐
│ Weight Integrity                                                │
│ Active Weight Total: 105% ⚠️                                   │
│ ████████████████████████████████████████████████████████████   │
│ Background: #F1F5F9                                             │
│ Fill: #F59E0B                                                  │
│ Border: 1px solid #F59E0B                                      │
└─────────────────────────────────────────────────────────────────┘

Error State
┌─────────────────────────────────────────────────────────────────┐
│ Weight Integrity                                                │
│ Active Weight Total: 80% ❌                                    │
│ ████████████████████████████████████████████████████████████   │
│ Background: #F1F5F9                                             │
│ Fill: #EF4444                                                  │
│ Border: 1px solid #EF4444                                      │
└─────────────────────────────────────────────────────────────────┘
```

## Bulk Actions Bar

### Bulk Actions Bar Layout
```
┌─────────────────────────────────────────────────────────────────┐
│ 3 items selected                                               │
│ [Assign to Project] [Change Role] [Deactivate] [Clear Selection] │
└─────────────────────────────────────────────────────────────────┘
```

### Bulk Actions Bar CSS Tokens
```css
:root {
  /* Bulk Actions Colors */
  --bulk-actions-bg: #F8FAFC;
  --bulk-actions-border: #E2E8F0;
  --bulk-actions-text: #334155;
  --bulk-actions-count: #00BFA6;
  
  /* Bulk Actions Spacing */
  --bulk-actions-padding: 12px 16px;
  --bulk-actions-gap: 8px;
  --bulk-actions-border-radius: 8px;
}
```

### Bulk Actions Bar States
```
Default State
┌─────────────────────────────────────────────────────────────────┐
│ 3 items selected                                               │
│ [Assign to Project] [Change Role] [Deactivate] [Clear Selection] │
│ Background: #F8FAFC                                             │
│ Border: 1px solid #E2E8F0                                      │
│ Text: #334155                                                   │
│ Count: #00BFA6                                                  │
└─────────────────────────────────────────────────────────────────┘

Empty State (Hidden)
┌─────────────────────────────────────────────────────────────────┐
│ (Bulk actions bar hidden when no items selected)               │
└─────────────────────────────────────────────────────────────────┘
```

## Enhanced Tables

### Master Setup Table
```
┌─────────────────────────────────────────────────────────────────┐
│ [Search] [Filter: All] [Sort: Name] [New Item]                 │
├─────────────────────────────────────────────────────────────────┤
│ ☐ │ Name │ Type │ Status │ Usage │ Last Updated │ Actions       │
├─────────────────────────────────────────────────────────────────┤
│ ☑ │ Item1│ Type1│ Active │ 24    │ 2d ago      │ [Edit] [Delete] │
│ ☐ │ Item2│ Type2│ Active │ 18    │ 1w ago      │ [Edit] [Delete] │
│ ☐ │ Item3│ Type3│ Inactive│ 0    │ 3d ago      │ [Edit] [Delete] │
└─────────────────────────────────────────────────────────────────┘
```

### Table Features
- **Checkboxes**: For bulk selection
- **Sticky Headers**: Headers remain visible during scroll
- **Density Toggle**: Compact/comfortable view options
- **Column Permissions**: Hide sensitive columns based on role
- **Sort Indicators**: Visual indicators for sort direction

### Enhanced Table CSS Tokens
```css
:root {
  /* Table Enhancement Colors */
  --table-selected-bg: #F0F9FF;
  --table-selected-border: #0EA5E9;
  --table-hover-bg: #FBFDFD;
  --table-sticky-bg: #F8FAFC;
  
  /* Table Enhancement Spacing */
  --table-density-compact: 8px 12px;
  --table-density-comfortable: 12px 16px;
  --table-density-spacious: 16px 20px;
}
```

## Role Badges (Enhanced)

### Master Setup Role Badges
```
Super Admin Badge
┌─────────────────┐
│ ● Super Admin   │
│   #000000       │
│   Contrast: 21:1│
└─────────────────┘

Admin Badge
┌─────────────────┐
│ ● Admin         │
│   #475569       │
│   Contrast: 4.5:1│
└─────────────────┘

PM Badge
┌─────────────────┐
│ ● PM            │
│   #4F46E5       │
│   Contrast: 4.5:1│
└─────────────────┘

Team Badge
┌─────────────────┐
│ ● Team          │
│   #0D9488       │
│   Contrast: 4.5:1│
└─────────────────┘

Client Badge
┌─────────────────┐
│ ● Client        │
│   #2563EB       │
│   Contrast: 4.5:1│
└─────────────────┘
```

## Permission Indicators

### Lock Icon Component
```
┌─────────────────────────────────────────────────────────────────┐
│ [🔒] Action Name (disabled)                                    │
│ Tooltip: "Requires Super Admin access"                        │
└─────────────────────────────────────────────────────────────────┘
```

### Permission Tooltip
```
┌─────────────────────────────────────────────────────────────────┐
│ Requires Super Admin access                                     │
│ Only Super Admin users can perform this action.                │
└─────────────────────────────────────────────────────────────────┘
```

## Form Components (Enhanced)

### Multi-step Form Progress
```
┌─────────────────────────────────────────────────────────────────┐
│ Create Project - Step 2 of 3                                   │
├─────────────────────────────────────────────────────────────────┤
│ ●─────●─────○                                                   │
│ Step 1 Step 2 Step 3                                          │
│ Basic   Timeline  Resources                                    │
│ Info    & Assign  & Settings                                   │
└─────────────────────────────────────────────────────────────────┘
```

### Inline Validation
```
┌─────────────────────────────────────────────────────────────────┐
│ Department Name                                                 │
│ [Marketing Department        ] ✅                              │
│                                                                 │
│ Sub-Departments                                                │
│ [Content] [SEO] [+ Add]                                        │
│ ⚠️ At least one sub-department is required                     │
└─────────────────────────────────────────────────────────────────┘
```

### Form Validation States
```
Valid State
┌─────────────────────────────────────────────────────────────────┐
│ Field Name                                                      │
│ [Valid Input                ] ✅                               │
│ Color: #10B981                                                  │
│ Border: 1px solid #10B981                                       │
└─────────────────────────────────────────────────────────────────┘

Error State
┌─────────────────────────────────────────────────────────────────┐
│ Field Name                                                      │
│ [Invalid Input              ] ❌                               │
│ Error: This field is required                                  │
│ Color: #EF4444                                                  │
│ Border: 1px solid #EF4444                                       │
└─────────────────────────────────────────────────────────────────┘

Warning State
┌─────────────────────────────────────────────────────────────────┐
│ Field Name                                                      │
│ [Warning Input              ] ⚠️                               │
│ Warning: This value may cause issues                           │
│ Color: #F59E0B                                                  │
│ Border: 1px solid #F59E0B                                       │
└─────────────────────────────────────────────────────────────────┘
```

## Modal Components (Enhanced)

### Confirmation Modal
```
┌─────────────────────────────────────────────────────────────────┐
│ Delete Department                                               │
├─────────────────────────────────────────────────────────────────┤
│ ⚠️ Are you sure you want to delete "Marketing Department"?     │
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

### Multi-step Modal
```
┌─────────────────────────────────────────────────────────────────┐
│ Invite User - Step 2 of 3                          [Close]     │
├─────────────────────────────────────────────────────────────────┤
│ ●─────●─────○                                                   │
│ Basic  Assign  Access                                           │
│ Info   ments   & Security                                       │
├─────────────────────────────────────────────────────────────────┤
│ Assign to Departments                                           │
│ ☑ Website                                                       │
│ ☑ Mobile                                                        │
│ ☐ Marketing                                                     │
│                                                                 │
│ [Previous] [Next]                                               │
└─────────────────────────────────────────────────────────────────┘
```

## Responsive Components

### Mobile Analytics Cards
```
┌─────────────────────────────────────────────────────────────────┐
│ ┌─────────────┐ ┌─────────────┐                                │
│ │ Total       │ │ Sub-dept    │                                │
│ │ Departments │ │ Count       │                                │
│ │ 12          │ │ 24          │                                │
│ └─────────────┘ └─────────────┘                                │
│ ┌─────────────┐ ┌─────────────┐                                │
│ │ Coverage    │ │ Risk        │                                │
│ │ % Projects  │ │ Unstaffed   │                                │
│ │ 85%         │ │ 2           │                                │
│ └─────────────┘ └─────────────┘                                │
└─────────────────────────────────────────────────────────────────┘
```

### Mobile Table (Stacked)
```
┌─────────────────────────────────────────────────────────────────┐
│ ┌─────────────────────────────────────────────────────────────┐ │
│ │ Website Department                                          │ │
│ │ Sub-departments: Design, Development                       │ │
│ │ Head: Priya Nair | Updated: 2d ago                         │ │
│ │ [Edit] [Delete]                                            │ │
│ └─────────────────────────────────────────────────────────────┘ │
│ ┌─────────────────────────────────────────────────────────────┐ │
│ │ Mobile Department                                           │ │
│ │ Sub-departments: iOS, Android                              │ │
│ │ Head: Arjun Mehta | Updated: 1w ago                        │ │
│ │ [Edit] [Delete]                                            │ │
│ └─────────────────────────────────────────────────────────────┘ │
└─────────────────────────────────────────────────────────────────┘
```

## Accessibility Enhancements

### Focus Management
```css
:root {
  /* Focus Colors */
  --focus-ring: #00BFA6;
  --focus-ring-width: 3px;
  --focus-ring-offset: 2px;
}

/* Enhanced Focus Styles */
.focus-visible {
  outline: var(--focus-ring-width) solid var(--focus-ring);
  outline-offset: var(--focus-ring-offset);
  box-shadow: 0 0 0 var(--focus-ring-width) var(--focus-ring);
}
```

### Screen Reader Support
```css
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  border: 0;
}

/* Analytics Card SR Text */
.analytics-card::after {
  content: "Analytics card showing ";
  @extend .sr-only;
}
```

### Keyboard Navigation
- **Tab Order**: Logical flow through all interactive elements
- **Skip Links**: Jump to main content, skip repetitive navigation
- **Arrow Keys**: Navigate within grouped elements (tables, lists)
- **Enter/Space**: Activate buttons and links
- **Escape**: Close modals and dropdowns
