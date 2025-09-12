# IKF Project Live Tracker - Copy Specifications (Master Setup)

## Voice and Tone Guidelines

### Master Setup Specific Voice
- **Authoritative**: Confident in system management capabilities
- **Precise**: Exact terminology for technical operations
- **Helpful**: Clear guidance for complex workflows
- **Secure**: Emphasize data protection and access control

### Role-Aware Language
- **Super Admin**: "System-wide", "Global", "Override", "Audit"
- **Admin**: "Organizational", "Manage", "Configure", "Assign"
- **PM/Team/Client**: No Master Setup access (redirected with guidance)

## Tooltips and Help Text

### Permission Tooltips
```
Standard Format: "Requires {Role} access"

Examples:
• "Requires Super Admin access" (system settings)
• "Requires Admin access" (user management)
• "Requires Super Admin access" (delete standard stages)
• "Requires Admin access" (create departments)
```

### Action Tooltips
```
Format: "{Action} {Object}" or "Cannot {Action} {Reason}"

Examples:
• "Delete department and all sub-departments"
• "Cannot delete standard stages"
• "Assign user to multiple projects"
• "Cannot change Super Admin users"
```

### Field Help Text
```
Format: Brief explanation of field purpose and requirements

Examples:
• "Unique identifier for the project across all customers"
• "Percentage weight must total 100% across all active stages"
• "At least one department required for PM/Team roles"
• "Email will be used for login and notifications"
```

## Toast Notifications

### Success Toasts
```
Format: "{Action} {Object} successfully"

Examples:
• "Department created successfully"
• "User invited successfully"
• "Stage updated successfully"
• "Project assigned successfully"

SR-only: "Success: {Action} {Object}"
```

### Error Toasts
```
Format: "Could not {action} {object}. {Reason}"

Examples:
• "Could not create department. Name already exists"
• "Could not invite user. Email already registered"
• "Could not update stage. Weight total exceeds 100%"
• "Could not assign project. User not found"

SR-only: "Error: {Action} failed - {Reason}"
```

### Warning Toasts
```
Format: "{Warning message}. {Action required}"

Examples:
• "Weight total is 105%. Reduce weights to continue"
• "User has no department assignments. Assign departments to continue"
• "Project has no assigned PM. Assign PM to continue"
• "Department has no head assigned. Consider assigning a head"

SR-only: "Warning: {Warning message}"
```

### Info Toasts
```
Format: "{Information message}"

Examples:
• "Bulk operation completed for 5 users"
• "Standard stages cannot be deleted"
• "Changes saved automatically"
• "Export will be available in 2 minutes"

SR-only: "Info: {Information message}"
```

## Empty States

### Departments Empty State
```
Title: "No departments yet"
Description: "Create your first department to begin assigning users and organizing your projects."
Action: "Create Department"
Icon: 📁 (folder)
```

### Projects Empty State
```
Title: "No projects for this customer yet"
Description: "Add a project to start tracking progress and managing your team's work."
Action: "Create Project"
Icon: 📋 (clipboard)
```

### Users Empty State
```
Title: "No users in this view"
Description: "Add users to build your team and start assigning them to projects and departments."
Action: "Invite User"
Icon: 👥 (people)
```

### Stages Empty State
```
Title: "No custom stages yet"
Description: "Add a new custom stage or use the default standard stages for your projects."
Action: "Create Stage"
Icon: 📋 (clipboard)
```

## Confirmation Messages

### Delete Confirmations
```
Format: "Are you sure you want to delete {object}?"

Examples:
• "Are you sure you want to delete 'Marketing Department'?"
• "Are you sure you want to delete 'Sarah Johnson'?"
• "Are you sure you want to delete 'Custom Development Stage'?"

Warning: "This action cannot be undone."
```

### Archive Confirmations
```
Format: "Are you sure you want to archive {object}?"

Examples:
• "Are you sure you want to archive 'Acme Website Revamp'?"
• "Are you sure you want to deactivate 'Sarah Johnson'?"

Note: "You can restore it later if needed."
```

### Bulk Action Confirmations
```
Format: "Are you sure you want to {action} {count} {objects}?"

Examples:
• "Are you sure you want to deactivate 5 users?"
• "Are you sure you want to assign 3 projects to Priya Nair?"
• "Are you sure you want to change roles for 2 users?"

Note: "This action will affect multiple items."
```

## Error Messages

### Field Validation Errors
```
Format: "{Field} {error description}"

Examples:
• "Department name is required"
• "Email address is invalid"
• "Weight percentage must be between 0% and 100%"
• "At least one sub-department is required"
• "Project code already exists"
• "End date must be after start date"
```

### Permission Errors
```
Format: "You don't have permission to {action}"

Examples:
• "You don't have permission to delete standard stages"
• "You don't have permission to create Super Admin users"
• "You don't have permission to edit system departments"
• "You don't have permission to access Master Setup"
```

### System Errors
```
Format: "We couldn't {action}. {Reason}"

Examples:
• "We couldn't save your changes. Please try again"
• "We couldn't load the data. Check your connection"
• "We couldn't process your request. Contact support"
• "We couldn't send the invitation. Check the email address"
```

## Form Labels and Instructions

### Form Section Headers
```
Format: "{Action} {Object}"

Examples:
• "Create Department"
• "Edit User"
• "Assign Project"
• "Manage Stages"
```

### Field Labels
```
Format: Clear, concise labels

Examples:
• "Department Name"
• "Project Code"
• "Email Address"
• "Weight Percentage"
• "Start Date"
• "End Date"
• "Assign to Departments"
• "Stage Type"
```

### Required Field Indicators
```
Format: "*" after field label

Examples:
• "Department Name *"
• "Project Code *"
• "Email Address *"
• "Weight Percentage *"
```

### Optional Field Indicators
```
Format: "(Optional)" after field label

Examples:
• "Project Description (Optional)"
• "Budget (Optional)"
• "Sub-statuses (Optional)"
• "Resource Links (Optional)"
```

## Button Labels

### Primary Actions
```
Format: Verb-first, present tense

Examples:
• "Create Department"
• "Invite User"
• "Save Changes"
• "Assign Project"
• "Update Stage"
• "Delete User"
• "Archive Project"
```

### Secondary Actions
```
Format: Clear, descriptive

Examples:
• "Cancel"
• "Previous"
• "Next"
• "Clear Selection"
• "Reset to Defaults"
• "Export CSV"
• "Bulk Assign"
```

### Destructive Actions
```
Format: Explicit, noun-focused

Examples:
• "Delete Department"
• "Delete User Permanently"
• "Archive Project"
• "Deactivate User"
• "Remove Stage"
```

## Search and Filter Labels

### Search Placeholders
```
Format: "Search {objects}..."

Examples:
• "Search departments..."
• "Search projects..."
• "Search users..."
• "Search stages..."
• "Search customers..."
```

### Filter Labels
```
Format: "Filter by {criteria}"

Examples:
• "Filter by Status"
• "Filter by Role"
• "Filter by Department"
• "Filter by Type"
• "Filter by Date"
```

### Sort Labels
```
Format: "Sort by {criteria}"

Examples:
• "Sort by Name"
• "Sort by Date"
• "Sort by Weight"
• "Sort by Usage"
• "Sort by Status"
```

## Analytics Labels

### Metric Labels
```
Format: Clear, descriptive metric names

Examples:
• "Total Departments"
• "Sub-department Count"
• "Coverage % Projects"
• "Unstaffed Departments"
• "Active Users"
• "Role Distribution"
• "Weight Integrity"
• "Stage Usage"
```

### Change Indicators
```
Format: "{Direction} {Amount} from {timeframe}"

Examples:
• "+2 from last month"
• "-5% from last week"
• "No change from yesterday"
• "+12% from last quarter"
```

### Status Labels
```
Format: Clear status indicators

Examples:
• "✅ Active"
• "❌ Inactive"
• "⚠️ Warning"
• "🔒 Locked"
• "📊 Analytics"
• "⚙️ Settings"
```

## Accessibility Copy

### Screen Reader Text
```
Format: Descriptive text for screen readers

Examples:
• "Analytics card showing total departments count"
• "Table with 5 rows of department data"
• "Form with 3 required fields"
• "Button to create new department"
• "Link to edit department details"
• "Warning message about weight validation"
```

### Skip Links
```
Format: "Skip to {destination}"

Examples:
• "Skip to main content"
• "Skip to navigation"
• "Skip to search"
• "Skip to table"
• "Skip to form"
```

### Focus Indicators
```
Format: Clear focus state descriptions

Examples:
• "Department name field focused"
• "Create button focused"
• "Table row selected"
• "Modal dialog open"
• "Dropdown menu expanded"
```

## Internationalization Considerations

### Avoid Concatenation
```
❌ Bad: "User " + name + " created"
✅ Good: "User {name} created"

❌ Bad: "Department " + count + " selected"
✅ Good: "{count} departments selected"
```

### Cultural Sensitivity
```
• Use neutral language for global audience
• Avoid region-specific references
• Consider different date formats
• Use inclusive terminology
• Avoid assumptions about user roles
```

### Translation Readiness
```
• Keep strings concise
• Use consistent terminology
• Avoid complex sentence structures
• Provide context for translators
• Test with different text lengths
```
