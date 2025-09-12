# IKF Project Live Tracker - Project Details Page

## Project Details Layout Structure

### Header Section
```
┌─────────────────────────────────────────────────────────────────┐
│ Project Title | Status Badge | Progress Bar | [Actions]         │
│ Acme Website Revamp | Ongoing | ████████░░ 48% | [Edit] [Archive] │
├─────────────────────────────────────────────────────────────────┤
│ Hold Banner (if applicable)                                     │
│ ⚠️ Client Hold: Waiting for content approval (2 days)          │
│ or                                                              │
│ ⚠️ Team Hold: Design assets delayed (1 day)                    │
└─────────────────────────────────────────────────────────────────┘
```

### Main Content Layout
```
┌─────────────────────────────────────────────────────────────────┐
│ Tab Navigation                                                  │
│ [Overview] [Stages] [Team] [Resources] [Timeline] [Activity]    │
├─────────────────────────────────────────────────────────────────┤
│ Tab Content (Role-based visibility)                            │
│ ┌─────────────────┐ ┌─────────────────┐                       │
│ │ Left Column     │ │ Right Column    │                       │
│ │ • Project Info  │ │ • Quick Actions │                       │
│ │ • Progress      │ │ • Recent Updates│                       │
│ │ • Stages        │ │ • Team Status   │                       │
│ └─────────────────┘ └─────────────────┘                       │
└─────────────────────────────────────────────────────────────────┘
```

## Role-Based Project Details Views

### Super Admin View
**Full access to all project information and controls**

#### Overview Tab
```
┌─────────────────────────────────────────────────────────────────┐
│ Project Information                                             │
│ • Name: Acme Website Revamp                                    │
│ • Client: Acme Corp                                            │
│ • PM: Priya Nair                                               │
│ • Department: Website                                          │
│ • Start Date: 2024-08-01                                       │
│ • Due Date: 2024-10-30                                         │
│ • Budget: $45,000                                              │
│ • Status: Ongoing                                              │
├─────────────────────────────────────────────────────────────────┤
│ Progress Overview (Weighted Stages)                            │
│ ████████████████████████████████████████████████████████████████│
│ 48% Complete                                                   │
│ • Planning: 100% (Weight: 10%)                                │
│ • Design: 80% (Weight: 25%)                                   │
│ • Development: 30% (Weight: 40%)                              │
│ • Testing: 0% (Weight: 20%)                                   │
│ • Launch: 0% (Weight: 5%)                                     │
├─────────────────────────────────────────────────────────────────┤
│ Stage Management                                               │
│ [Toggle Stage] [Edit Stage] [Add Stage] [Delete Stage]        │
│ • Planning ✓ (Completed)                                      │
│ • Design ✓ (In Progress)                                      │
│ • Development ○ (Pending)                                     │
│ • Testing ○ (Pending)                                         │
│ • Launch ○ (Pending)                                          │
└─────────────────────────────────────────────────────────────────┘
```

#### Team Tab
```
┌─────────────────────────────────────────────────────────────────┐
│ Team Assignments (Full Management)                             │
│ [Add Member] [Bulk Assign] [Export Team]                       │
├─────────────────────────────────────────────────────────────────┤
│ Department: Website                                            │
│ • Priya Nair (PM) - priya@ikf.com                             │
│ • Riya Kapoor (Content Writer) - riya@ikf.com                 │
│ • Karan Shah (Designer) - karan@ikf.com                       │
│ • Arjun Mehta (Developer) - arjun@ikf.com                     │
├─────────────────────────────────────────────────────────────────┤
│ Sub-department: Content                                        │
│ • Sarah Johnson (Copywriter) - sarah@ikf.com                  │
│ • Mike Chen (Editor) - mike@ikf.com                           │
└─────────────────────────────────────────────────────────────────┘
```

#### Resources Tab
```
┌─────────────────────────────────────────────────────────────────┐
│ Resource Links (Full Access)                                   │
│ [Add Resource] [Manage Permissions] [Sync All]                 │
├─────────────────────────────────────────────────────────────────┤
│ Design Assets                                                  │
│ • GDrive: /Projects/Acme/Design                               │
│ • Figma: Acme Website Design System                           │
│ • Adobe XD: Wireframes v2.1                                   │
├─────────────────────────────────────────────────────────────────┤
│ Development                                                    │
│ • GitHub: ikf/acme-website                                    │
│ • Jira: ACME-001 to ACME-045                                  │
│ • Staging: https://acme-staging.ikf.com                       │
└─────────────────────────────────────────────────────────────────┘
```

### Admin View
**Operational management access**

#### Overview Tab
```
┌─────────────────────────────────────────────────────────────────┐
│ Project Information (Editable)                                 │
│ • Name: Acme Website Revamp [Edit]                             │
│ • Client: Acme Corp [Edit]                                     │
│ • PM: Priya Nair [Reassign]                                    │
│ • Department: Website [Change]                                 │
│ • Start Date: 2024-08-01 [Edit]                               │
│ • Due Date: 2024-10-30 [Edit]                                 │
│ • Budget: $45,000 [Edit]                                       │
│ • Status: Ongoing [Change]                                     │
├─────────────────────────────────────────────────────────────────┤
│ Progress Overview (Weighted Stages)                            │
│ ████████████████████████████████████████████████████████████████│
│ 48% Complete                                                   │
│ • Planning: 100% (Weight: 10%)                                │
│ • Design: 80% (Weight: 25%)                                   │
│ • Development: 30% (Weight: 40%)                              │
│ • Testing: 0% (Weight: 20%)                                   │
│ • Launch: 0% (Weight: 5%)                                     │
├─────────────────────────────────────────────────────────────────┤
│ Stage Management (Operational)                                │
│ [Toggle Stage] [Edit Stage] [Add Stage]                       │
│ • Planning ✓ (Completed)                                      │
│ • Design ✓ (In Progress)                                      │
│ • Development ○ (Pending)                                     │
│ • Testing ○ (Pending)                                         │
│ • Launch ○ (Pending)                                          │
└─────────────────────────────────────────────────────────────────┘
```

#### Team Tab
```
┌─────────────────────────────────────────────────────────────────┐
│ Team Assignments (Operational Management)                      │
│ [Add Member] [Bulk Assign] [Export Team]                       │
├─────────────────────────────────────────────────────────────────┤
│ Department: Website                                            │
│ • Priya Nair (PM) - priya@ikf.com [Reassign]                  │
│ • Riya Kapoor (Content Writer) - riya@ikf.com [Remove]        │
│ • Karan Shah (Designer) - karan@ikf.com [Remove]              │
│ • Arjun Mehta (Developer) - arjun@ikf.com [Remove]            │
├─────────────────────────────────────────────────────────────────┤
│ Sub-department: Content                                        │
│ • Sarah Johnson (Copywriter) - sarah@ikf.com [Remove]         │
│ • Mike Chen (Editor) - mike@ikf.com [Remove]                  │
└─────────────────────────────────────────────────────────────────┘
```

### Project Manager View
**Own projects management**

#### Overview Tab
```
┌─────────────────────────────────────────────────────────────────┐
│ Project Information (Own Projects Only)                        │
│ • Name: Acme Website Revamp                                    │
│ • Client: Acme Corp                                            │
│ • PM: Priya Nair (You)                                         │
│ • Department: Website                                          │
│ • Start Date: 2024-08-01                                       │
│ • Due Date: 2024-10-30                                         │
│ • Budget: $45,000                                              │
│ • Status: Ongoing                                              │
├─────────────────────────────────────────────────────────────────┤
│ Progress Overview (Weighted Stages)                            │
│ ████████████████████████████████████████████████████████████████│
│ 48% Complete                                                   │
│ • Planning: 100% (Weight: 10%)                                │
│ • Design: 80% (Weight: 25%)                                   │
│ • Development: 30% (Weight: 40%)                              │
│ • Testing: 0% (Weight: 20%)                                   │
│ • Launch: 0% (Weight: 5%)                                     │
├─────────────────────────────────────────────────────────────────┤
│ Stage Management (Own Projects)                               │
│ [Toggle Stage] [Edit Stage] [Add Stage]                       │
│ • Planning ✓ (Completed)                                      │
│ • Design ✓ (In Progress)                                      │
│ • Development ○ (Pending)                                     │
│ • Testing ○ (Pending)                                         │
│ • Launch ○ (Pending)                                          │
└─────────────────────────────────────────────────────────────────┘
```

#### Team Tab
```
┌─────────────────────────────────────────────────────────────────┐
│ Team Assignments (Department Members Only)                     │
│ [Add Member] [Bulk Assign]                                     │
├─────────────────────────────────────────────────────────────────┤
│ Department: Website                                            │
│ • Priya Nair (PM) - priya@ikf.com (You)                       │
│ • Riya Kapoor (Content Writer) - riya@ikf.com [Assign]        │
│ • Karan Shah (Designer) - karan@ikf.com [Assign]              │
│ • Arjun Mehta (Developer) - arjun@ikf.com [Assign]            │
├─────────────────────────────────────────────────────────────────┤
│ Available Team Members                                         │
│ • Sarah Johnson (Copywriter) - sarah@ikf.com [Add]            │
│ • Mike Chen (Editor) - mike@ikf.com [Add]                     │
└─────────────────────────────────────────────────────────────────┘
```

### Team Member View
**Assigned projects only**

#### Overview Tab
```
┌─────────────────────────────────────────────────────────────────┐
│ Project Information (Read-only)                                │
│ • Name: Acme Website Revamp                                    │
│ • Client: Acme Corp                                            │
│ • PM: Priya Nair                                               │
│ • Department: Website                                          │
│ • Start Date: 2024-08-01                                       │
│ • Due Date: 2024-10-30                                         │
│ • Status: Ongoing                                              │
├─────────────────────────────────────────────────────────────────┤
│ Progress Overview (Read-only)                                  │
│ ████████████████████████████████████████████████████████████████│
│ 48% Complete                                                   │
│ • Planning: 100% (Weight: 10%)                                │
│ • Design: 80% (Weight: 25%)                                   │
│ • Development: 30% (Weight: 40%)                              │
│ • Testing: 0% (Weight: 20%)                                   │
│ • Launch: 0% (Weight: 5%)                                     │
├─────────────────────────────────────────────────────────────────┤
│ My Tasks (Assigned Only)                                       │
│ • Content writing for homepage (Due: 2024-09-15)              │
│ • Review design mockups (Due: 2024-09-20)                     │
│ • Update project documentation (Due: 2024-09-25)              │
└─────────────────────────────────────────────────────────────────┘
```

#### Resources Tab
```
┌─────────────────────────────────────────────────────────────────┐
│ Resource Links (Assigned Only)                                 │
│ [Request Access] [Sync]                                        │
├─────────────────────────────────────────────────────────────────┤
│ Design Assets                                                  │
│ • GDrive: /Projects/Acme/Design [Open]                        │
│ • Figma: Acme Website Design System [Open]                    │
├─────────────────────────────────────────────────────────────────┤
│ Development                                                    │
│ • GitHub: ikf/acme-website [Open]                             │
│ • Jira: ACME-001 to ACME-045 [Open]                           │
└─────────────────────────────────────────────────────────────────┘
```

### Client View (Future)
**Read-only with approval rights**

#### Overview Tab
```
┌─────────────────────────────────────────────────────────────────┐
│ Project Information (Read-only)                                │
│ • Name: Acme Website Revamp                                    │
│ • Client: Acme Corp (You)                                      │
│ • PM: Priya Nair                                               │
│ • Start Date: 2024-08-01                                       │
│ • Due Date: 2024-10-30                                         │
│ • Status: Ongoing                                              │
├─────────────────────────────────────────────────────────────────┤
│ Progress Overview (Read-only)                                  │
│ ████████████████████████████████████████████████████████████████│
│ 48% Complete                                                   │
│ • Planning: 100% (Weight: 10%)                                │
│ • Design: 80% (Weight: 25%)                                   │
│ • Development: 30% (Weight: 40%)                              │
│ • Testing: 0% (Weight: 20%)                                   │
│ • Launch: 0% (Weight: 5%)                                     │
├─────────────────────────────────────────────────────────────────┤
│ Pending Approvals                                              │
│ • Design Concept A [Approve] [Request Changes]                 │
│ • Content Outline [Approve] [Request Changes]                  │
│ • Final QA [Approve] [Request Changes]                         │
└─────────────────────────────────────────────────────────────────┘
```

## Progress Bar Component

### Weighted Stage Progress
```
Progress Bar with Stage Weights
████████████████████████████████████████████████████████████████
48% Complete

Stage Breakdown:
┌─────────────┬─────────┬─────────┬─────────┬─────────┐
│ Planning    │ Design  │ Develop │ Testing │ Launch  │
│ 100% (10%)  │ 80% (25%)│ 30% (40%)│ 0% (20%)│ 0% (5%) │
│ ████████    │ ████████│ ███     │         │         │
└─────────────┴─────────┴─────────┴─────────┴─────────┘
```

### Color Coding
- **0-24%**: Red (#EF4444) - Critical
- **25-49%**: Orange (#F59E0B) - At Risk
- **50-74%**: Yellow (#EAB308) - On Track
- **75-99%**: Green (#10B981) - Almost Complete
- **100%**: Blue (#2563EB) - Complete

## Hold Banners

### Client Hold Banner
```
┌─────────────────────────────────────────────────────────────────┐
│ ⚠️ Client Hold: Waiting for content approval (2 days)          │
│ Reason: Client requested changes to homepage copy              │
│ Started: 2024-09-10 by Priya Nair                             │
│ [Resolve Hold] [Contact Client] [View Details]                 │
└─────────────────────────────────────────────────────────────────┘
```

### Team Hold Banner
```
┌─────────────────────────────────────────────────────────────────┐
│ ⚠️ Team Hold: Design assets delayed (1 day)                    │
│ Reason: Designer unavailable due to illness                    │
│ Started: 2024-09-11 by Karan Shah                             │
│ [Resolve Hold] [Reassign] [View Details]                       │
└─────────────────────────────────────────────────────────────────┘
```

## Stage Management

### Stage Toggle Component
```
Stage: Design
┌─────────────────────────────────────────────────────────────────┐
│ [Toggle Switch] Design Stage                                   │
│ Status: In Progress                                            │
│ Sub-status: [Dropdown: In Progress | On Hold | Completed]     │
│ Owner: Karan Shah                                              │
│ Due: 2024-09-20                                               │
│ [Edit Stage] [View Details] [Add Task]                        │
└─────────────────────────────────────────────────────────────────┘
```

### Stage List with Permissions
```
Stages (Role-based actions)
┌─────────────────────────────────────────────────────────────────┐
│ ✓ Planning (Completed)                                         │
│   Sub-status: Completed                                        │
│   Owner: Priya Nair                                            │
│   [View Details] [Archive]                                     │
├─────────────────────────────────────────────────────────────────┤
│ ✓ Design (In Progress)                                         │
│   Sub-status: In Progress                                      │
│   Owner: Karan Shah                                            │
│   [Toggle] [Edit] [View Details] [Add Task]                   │
├─────────────────────────────────────────────────────────────────┤
│ ○ Development (Pending)                                        │
│   Sub-status: Not Started                                      │
│   Owner: Arjun Mehta                                           │
│   [Toggle] [Edit] [View Details] [Add Task]                   │
└─────────────────────────────────────────────────────────────────┘
```

## Responsive Behavior

### Desktop (1024px+)
- Full tab navigation
- Side-by-side content layout
- Complete action buttons
- Full stage management interface

### Tablet (768px-1023px)
- Collapsible tab navigation
- Stacked content layout
- Condensed action buttons
- Simplified stage management

### Mobile (360px-767px)
- Bottom tab navigation
- Single-column layout
- Icon-only action buttons
- Card-based stage management
