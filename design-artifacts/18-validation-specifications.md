# IKF Project Live Tracker - Validation Specifications (Master Setup)

## Form Validation Rules

### Departments Module Validation

#### Create Department Form
```
┌─────────────────────────────────────────────────────────────────┐
│ Create Department                                               │
├─────────────────────────────────────────────────────────────────┤
│ Department Name *                                               │
│ [________________________________]                             │
│ ✅ Valid: "Marketing Department"                               │
│ ❌ Error: "M" (too short)                                     │
│ ❌ Error: "Website" (already exists)                           │
│                                                                 │
│ Sub-Departments *                                              │
│ ┌─────────────┐ ┌─────────────┐ [+ Add]                        │
│ │ Content     │ │ SEO         │                                │
│ │ [×]         │ │ [×]         │                                │
│ └─────────────┘ └─────────────┘                                │
│ ✅ Valid: At least 1 sub-department                           │
│ ❌ Error: At least one sub-department is required             │
│                                                                 │
│ Assign Department Head                                          │
│ [Dropdown: Select User]                                         │
│ ✅ Valid: Any valid user                                       │
│ ❌ Error: User not found (Admin: cannot assign Super Admin)    │
└─────────────────────────────────────────────────────────────────┘
```

#### Validation Rules
- **Department Name**: Required, min 2 characters, max 50 characters, unique
- **Sub-Departments**: Required, min 1, max 10, unique within department
- **Department Head**: Optional, must be valid user, Admin cannot assign Super Admin

#### Error Messages
- **Name too short**: "Department name must be at least 2 characters"
- **Name too long**: "Department name cannot exceed 50 characters"
- **Name exists**: "A department with this name already exists"
- **No sub-departments**: "At least one sub-department is required"
- **Invalid head**: "Selected user is not available for assignment"

### Projects Module Validation

#### Create Project Form - Step 1
```
┌─────────────────────────────────────────────────────────────────┐
│ Create Project - Step 1 of 3                                   │
├─────────────────────────────────────────────────────────────────┤
│ Customer *                                                      │
│ [Search existing customer...] or [Create new customer]         │
│ ✅ Valid: "Acme Corp" (existing)                              │
│ ✅ Valid: "New Customer" (will be created)                     │
│ ❌ Error: Customer name is required                           │
│                                                                 │
│ Project Name *                                                  │
│ [________________________________]                             │
│ ✅ Valid: "Website Revamp"                                    │
│ ❌ Error: "W" (too short)                                     │
│ ❌ Error: "Mobile App" (already exists for this customer)     │
│                                                                 │
│ Project Code *                                                  │
│ [________________________________]                             │
│ ✅ Valid: "ACME-001"                                          │
│ ❌ Error: "A" (too short)                                      │
│ ❌ Error: "ACME-001" (already exists)                         │
│                                                                 │
│ Project Description                                             │
│ [________________________________]                             │
│ [________________________________]                             │
│ ✅ Valid: Any text (optional)                                 │
│ ❌ Error: Description cannot exceed 500 characters            │
└─────────────────────────────────────────────────────────────────┘
```

#### Create Project Form - Step 2
```
┌─────────────────────────────────────────────────────────────────┐
│ Create Project - Step 2 of 3                                   │
├─────────────────────────────────────────────────────────────────┤
│ Timeline                                                         │
│ Start Date *: [Date Picker]                                    │
│ End Date *: [Date Picker]                                       │
│ ✅ Valid: Start before end date                                │
│ ❌ Error: Start date is required                               │
│ ❌ Error: End date must be after start date                    │
│                                                                 │
│ Assign Project Manager *                                        │
│ [Dropdown: Select PM]                                           │
│ ✅ Valid: User with PM role                                    │
│ ❌ Error: Project manager is required                          │
│ ❌ Error: Selected user is not a Project Manager               │
│                                                                 │
│ Assign Departments *                                            │
│ ☑ Website                                                       │
│ ☑ Mobile                                                        │
│ ☐ Marketing                                                     │
│ ✅ Valid: At least 1 department selected                      │
│ ❌ Error: At least one department must be assigned              │
│                                                                 │
│ Budget (Optional)                                               │
│ [________________________________]                             │
│ ✅ Valid: Positive number                                      │
│ ❌ Error: Budget must be a positive number                     │
└─────────────────────────────────────────────────────────────────┘
```

#### Validation Rules
- **Customer**: Required, must exist or be creatable
- **Project Name**: Required, min 2 characters, max 100 characters, unique per customer
- **Project Code**: Required, min 2 characters, max 20 characters, unique across all projects
- **Description**: Optional, max 500 characters
- **Start Date**: Required, valid date
- **End Date**: Required, valid date, must be after start date
- **Project Manager**: Required, must be user with PM role
- **Departments**: Required, at least 1 department selected
- **Budget**: Optional, positive number if provided

### Users Module Validation

#### Invite User Form - Step 1
```
┌─────────────────────────────────────────────────────────────────┐
│ Invite User - Step 1 of 3                                      │
├─────────────────────────────────────────────────────────────────┤
│ Full Name *                                                     │
│ [________________________________]                             │
│ ✅ Valid: "Sarah Johnson"                                      │
│ ❌ Error: "S" (too short)                                      │
│ ❌ Error: Full name is required                                │
│                                                                 │
│ Email Address *                                                 │
│ [________________________________]                             │
│ ✅ Valid: "sarah@ikf.com"                                      │
│ ❌ Error: "sarah@" (invalid format)                            │
│ ❌ Error: "john@ikf.com" (already exists)                       │
│                                                                 │
│ Role *                                                          │
│ [Dropdown: Select Role]                                         │
│ ✅ Valid: Admin, PM, Team, Client                              │
│ ✅ Valid: Super Admin (Super Admin only)                       │
│ ❌ Error: Role is required                                      │
│ ❌ Error: Admin cannot create Super Admin users                │
└─────────────────────────────────────────────────────────────────┘
```

#### Invite User Form - Step 2
```
┌─────────────────────────────────────────────────────────────────┐
│ Invite User - Step 2 of 3                                      │
├─────────────────────────────────────────────────────────────────┤
│ Assign to Departments * (for PM/Team roles)                    │
│ ☑ Website                                                       │
│ ☑ Mobile                                                        │
│ ☐ Marketing                                                     │
│ ✅ Valid: At least 1 department for PM/Team                    │
│ ❌ Error: PM/Team members must be assigned to at least one dept │
│                                                                 │
│ Assign to Projects (Optional)                                   │
│ ☑ Acme Website Revamp                                          │
│ ☑ Orchid eCommerce Launch                                      │
│ ☐ Vista Realty Corporate Site                                  │
│ ✅ Valid: Any number of projects                               │
│ ❌ Error: Selected projects are not accessible                 │
└─────────────────────────────────────────────────────────────────┘
```

#### Validation Rules
- **Full Name**: Required, min 2 characters, max 100 characters
- **Email**: Required, valid email format, unique across all users
- **Role**: Required, must be valid role, Admin cannot create Super Admin
- **Departments**: Required for PM/Team roles, at least 1 department
- **Projects**: Optional, must be accessible to user's role

### Stages Module Validation

#### Create Stage Form
```
┌─────────────────────────────────────────────────────────────────┐
│ Create Stage                                                    │
├─────────────────────────────────────────────────────────────────┤
│ Stage Name *                                                    │
│ [________________________________]                             │
│ ✅ Valid: "Custom Development"                                 │
│ ❌ Error: "C" (too short)                                     │
│ ❌ Error: "Design" (already exists)                            │
│                                                                 │
│ Stage Type *                                                    │
│ ○ Standard Stage (used across all projects)                  │
│ ○ Temporary Stage (project-specific)                           │
│ ✅ Valid: Either option selected                               │
│ ❌ Error: Stage type is required                               │
│                                                                 │
│ Weight Percentage *                                             │
│ [____] %                                                        │
│ ✅ Valid: 15% (within range)                                  │
│ ❌ Error: Weight must be between 0% and 100%                   │
│ ❌ Error: Total weight would exceed 100% (currently 85%)      │
│                                                                 │
│ Sub-statuses (Optional)                                         │
│ ┌─────────────┐ ┌─────────────┐ [+ Add]                        │
│ │ In Progress │ │ On Hold     │                                │
│ │ [×]         │ │ [×]         │                                │
│ └─────────────┘ └─────────────┘                                │
│ ✅ Valid: Any number of sub-statuses                          │
│ ❌ Error: Sub-status names must be unique                      │
└─────────────────────────────────────────────────────────────────┘
```

#### Validation Rules
- **Stage Name**: Required, min 2 characters, max 50 characters, unique
- **Stage Type**: Required, Standard or Temporary
- **Weight Percentage**: Required, 0-100%, sum of active stages must equal 100%
- **Sub-statuses**: Optional, unique names within stage

## Real-time Validation

### Weight Validation (Stages)
```
┌─────────────────────────────────────────────────────────────────┐
│ Weight Management                                               │
├─────────────────────────────────────────────────────────────────┤
│ Current Active Stages:                                          │
│ • Handshake: 10%                                               │
│ • Sitemap: 5%                                                  │
│ • Design: 25%                                                  │
│ • Development: 40%                                             │
│ • QA & Testing: 15%                                           │
│ • Go Live: 5%                                                  │
│                                                                 │
│ Total: 100% ✅                                                 │
│                                                                 │
│ Adding new stage with 10% weight would result in 110% ❌       │
│ [Reduce existing weights] [Cancel]                             │
└─────────────────────────────────────────────────────────────────┘
```

### Email Validation (Users)
```
┌─────────────────────────────────────────────────────────────────┐
│ Email Address                                                   │
│ [sarah@ikf.com                ] ✅                             │
│ Valid email format                                             │
│                                                                 │
│ [sarah@ikf.com                ] ❌                             │
│ Email already exists                                           │
│                                                                 │
│ [sarah@                        ] ❌                             │
│ Please enter a valid email address                             │
└─────────────────────────────────────────────────────────────────┘
```

### Department Assignment Validation (Users)
```
┌─────────────────────────────────────────────────────────────────┐
│ Assign to Departments                                           │
│ ☑ Website                                                       │
│ ☑ Mobile                                                        │
│ ☐ Marketing                                                     │
│                                                                 │
│ ✅ Valid: 2 departments selected                               │
│                                                                 │
│ ☐ Website                                                       │
│ ☐ Mobile                                                        │
│ ☐ Marketing                                                     │
│                                                                 │
│ ❌ Error: PM/Team members must be assigned to at least one dept │
└─────────────────────────────────────────────────────────────────┘
```

## Form Submission Validation

### Multi-step Form Validation
```
┌─────────────────────────────────────────────────────────────────┐
│ Create Project - Step 3 of 3                                   │
├─────────────────────────────────────────────────────────────────┤
│ ⚠️ Please fix the following errors before continuing:          │
│                                                                 │
│ • Project code "ACME-001" already exists                       │
│ • End date must be after start date                            │
│ • At least one department must be assigned                     │
│                                                                 │
│ [Previous] [Save Project] (disabled)                          │
└─────────────────────────────────────────────────────────────────┘
```

### Bulk Operation Validation
```
┌─────────────────────────────────────────────────────────────────┐
│ Bulk Change Role                                                │
├─────────────────────────────────────────────────────────────────┤
│ ⚠️ Cannot change roles for the following users:                │
│                                                                 │
│ • John Doe: Admin cannot change Super Admin users             │
│ • Sarah Johnson: User is inactive                               │
│                                                                 │
│ 3 users will be updated successfully.                          │
│                                                                 │
│ [Cancel] [Change Roles for 3 Users]                            │
└─────────────────────────────────────────────────────────────────┘
```

## Error State Design

### Field-level Errors
```
┌─────────────────────────────────────────────────────────────────┐
│ Department Name                                                 │
│ [Invalid Input              ] ❌                               │
│ This field is required                                        │
│                                                                 │
│ Color: #EF4444                                                  │
│ Border: 1px solid #EF4444                                       │
│ Background: rgba(239, 68, 68, 0.05)                            │
└─────────────────────────────────────────────────────────────────┘
```

### Form-level Errors
```
┌─────────────────────────────────────────────────────────────────┐
│ ⚠️ Please fix the following errors:                            │
│                                                                 │
│ • Department name is required                                   │
│ • At least one sub-department is required                      │
│ • Selected department head is not available                     │
│                                                                 │
│ [Fix Errors]                                                    │
└─────────────────────────────────────────────────────────────────┘
```

### Success States
```
┌─────────────────────────────────────────────────────────────────┐
│ Department Name                                                 │
│ [Valid Input                ] ✅                               │
│                                                                 │
│ Color: #10B981                                                  │
│ Border: 1px solid #10B981                                       │
│ Background: rgba(16, 185, 129, 0.05)                           │
└─────────────────────────────────────────────────────────────────┘
```

## Accessibility Validation

### Screen Reader Support
```
┌─────────────────────────────────────────────────────────────────┐
│ Department Name                                                 │
│ [Invalid Input              ] ❌                               │
│ This field is required                                        │
│                                                                 │
│ SR-only: "Department name field has an error: This field is   │
│ required"                                                       │
└─────────────────────────────────────────────────────────────────┘
```

### Keyboard Navigation
- **Tab Order**: Logical flow through form fields
- **Error Focus**: Focus moves to first error field on submit
- **Skip Links**: Jump to error summary
- **Arrow Keys**: Navigate within grouped elements

## Validation Timing

### Real-time Validation
- **On Blur**: Validate field when user leaves it
- **On Change**: Validate for format (email, numbers)
- **On Submit**: Full validation before form submission

### Validation Delays
- **Debounce**: 300ms delay for search/autocomplete fields
- **Immediate**: Required field validation
- **Batch**: Multi-field validation on form submit

## Error Recovery

### Auto-correction
```
┌─────────────────────────────────────────────────────────────────┐
│ Project Code                                                    │
│ [acme-001                    ] ⚠️                             │
│ Suggested: "ACME-001" (uppercase)                              │
│ [Accept Suggestion] [Keep as is]                               │
└─────────────────────────────────────────────────────────────────┘
```

### Suggestion System
```
┌─────────────────────────────────────────────────────────────────┐
│ Department Name                                                 │
│ [marketing                     ] ❌                             │
│ Did you mean: "Marketing Department"?                          │
│ [Use Suggestion] [Create New]                                  │
└─────────────────────────────────────────────────────────────────┘
```
