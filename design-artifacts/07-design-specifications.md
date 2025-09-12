# IKF Project Live Tracker - Design Specifications

## Design Tokens

### Color System
```css
:root {
  /* Brand Colors */
  --brand-primary: #0A2540;      /* IKF Navy */
  --brand-teal: #00BFA6;         /* IKF Teal */
  --brand-saffron: #F59E0B;      /* IKF Saffron */
  --brand-emerald: #10B981;      /* IKF Emerald */
  --brand-rose: #EF4444;         /* IKF Rose */
  
  /* Role Colors */
  --role-super-admin: #000000;   /* Black */
  --role-admin: #475569;         /* Slate */
  --role-pm: #4F46E5;           /* Indigo */
  --role-team: #0D9488;         /* Teal */
  --role-client: #2563EB;       /* Blue */
  
  /* Neutral Colors */
  --slate-900: #0F172A;         /* Dark text */
  --slate-700: #334155;         /* Medium text */
  --slate-500: #64748B;         /* Muted text */
  --slate-300: #CBD5E1;         /* Light border */
  --slate-200: #E2E8F0;         /* Very light border */
  --slate-100: #F1F5F9;         /* Background */
  --white: #FFFFFF;             /* White */
  
  /* Status Colors */
  --status-ongoing: #00BFA6;    /* Teal */
  --status-onhold: #F59E0B;     /* Saffron */
  --status-completed: #10B981;  /* Emerald */
  --status-critical: #EF4444;   /* Rose */
  
  /* Progress Colors */
  --progress-critical: #EF4444; /* 0-24% */
  --progress-at-risk: #F59E0B;  /* 25-49% */
  --progress-on-track: #EAB308; /* 50-74% */
  --progress-almost: #10B981;   /* 75-99% */
  --progress-complete: #2563EB; /* 100% */
  
  /* Hold Colors */
  --hold-client: #F59E0B;       /* Amber */
  --hold-team: #8B5CF6;         /* Purple */
}
```

### Typography Scale
```css
:root {
  /* Font Families */
  --font-sans: "Inter", system-ui, -apple-system, "Segoe UI", Roboto, Arial, sans-serif;
  --font-display: "DM Sans", "Inter", system-ui, -apple-system, "Segoe UI", Roboto, Arial, sans-serif;
  
  /* Font Sizes */
  --fs-xs: 12px;    /* Captions */
  --fs-sm: 14px;    /* Meta text */
  --fs-md: 16px;    /* Body text */
  --fs-lg: 18px;    /* H3 */
  --fs-xl: 22px;    /* H2 */
  --fs-2xl: 28px;   /* H1 */
  
  /* Font Weights */
  --fw-normal: 400;
  --fw-medium: 500;
  --fw-semibold: 600;
  --fw-bold: 700;
  --fw-extrabold: 800;
  
  /* Line Heights */
  --lh-tight: 1.2;
  --lh-normal: 1.5;
  --lh-relaxed: 1.6;
}
```

### Spacing Scale
```css
:root {
  --space-1: 4px;
  --space-2: 8px;
  --space-3: 12px;
  --space-4: 16px;
  --space-5: 20px;
  --space-6: 24px;
  --space-8: 32px;
  --space-10: 40px;
  --space-12: 48px;
  --space-16: 64px;
  --space-20: 80px;
  --space-24: 96px;
}
```

### Border Radius
```css
:root {
  --radius-sm: 8px;
  --radius-md: 12px;
  --radius-lg: 16px;
  --radius-xl: 20px;
  --radius-full: 999px;
}
```

### Shadows
```css
:root {
  --shadow-sm: 0 1px 2px rgba(0,0,0,0.06);
  --shadow-md: 0 6px 16px rgba(2,6,23,0.12);
  --shadow-lg: 0 12px 30px rgba(2,6,23,0.16);
  --shadow-xl: 0 20px 40px rgba(2,6,23,0.20);
}
```

## Component Specifications

### Role Badge Component
```css
.role-badge {
  display: inline-flex;
  align-items: center;
  gap: var(--space-2);
  padding: var(--space-2) var(--space-3);
  border-radius: var(--radius-full);
  font-size: var(--fs-sm);
  font-weight: var(--fw-semibold);
  border: 1px solid;
  transition: all 0.2s ease;
}

.role-badge--super-admin {
  background: rgba(0, 0, 0, 0.1);
  color: var(--role-super-admin);
  border-color: var(--role-super-admin);
}

.role-badge--admin {
  background: rgba(71, 85, 105, 0.1);
  color: var(--role-admin);
  border-color: var(--role-admin);
}

.role-badge--pm {
  background: rgba(79, 70, 229, 0.1);
  color: var(--role-pm);
  border-color: var(--role-pm);
}

.role-badge--team {
  background: rgba(13, 148, 136, 0.1);
  color: var(--role-team);
  border-color: var(--role-team);
}

.role-badge--client {
  background: rgba(37, 99, 235, 0.1);
  color: var(--role-client);
  border-color: var(--role-client);
}
```

### Progress Bar Component
```css
.progress-bar {
  position: relative;
  height: var(--space-3);
  border-radius: var(--radius-full);
  background: var(--slate-100);
  border: 1px solid var(--slate-200);
  overflow: hidden;
}

.progress-bar__fill {
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  border-radius: var(--radius-full);
  transition: width 0.8s ease-out;
}

.progress-bar__fill--critical {
  background: linear-gradient(90deg, var(--progress-critical), #DC2626);
}

.progress-bar__fill--at-risk {
  background: linear-gradient(90deg, var(--progress-at-risk), #D97706);
}

.progress-bar__fill--on-track {
  background: linear-gradient(90deg, var(--progress-on-track), #CA8A04);
}

.progress-bar__fill--almost {
  background: linear-gradient(90deg, var(--progress-almost), #059669);
}

.progress-bar__fill--complete {
  background: linear-gradient(90deg, var(--progress-complete), #1D4ED8);
}

.progress-bar__label {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: var(--fs-sm);
  font-weight: var(--fw-bold);
  color: var(--slate-700);
}
```

### Hold Banner Component
```css
.hold-banner {
  display: flex;
  align-items: center;
  gap: var(--space-3);
  padding: var(--space-4);
  border-radius: var(--radius-md);
  border: 1px solid;
  margin-bottom: var(--space-6);
}

.hold-banner--client {
  background: rgba(245, 158, 11, 0.1);
  border-color: var(--hold-client);
  color: #92400E;
}

.hold-banner--team {
  background: rgba(139, 92, 246, 0.1);
  border-color: var(--hold-team);
  color: #6B21A8;
}

.hold-banner__icon {
  font-size: var(--fs-lg);
}

.hold-banner__content {
  flex: 1;
}

.hold-banner__title {
  font-weight: var(--fw-bold);
  margin-bottom: var(--space-1);
}

.hold-banner__reason {
  font-size: var(--fs-sm);
  opacity: 0.8;
}

.hold-banner__actions {
  display: flex;
  gap: var(--space-2);
}
```

### Button Component
```css
.btn {
  display: inline-flex;
  align-items: center;
  gap: var(--space-2);
  padding: var(--space-3) var(--space-4);
  border-radius: var(--radius-md);
  border: 1px solid;
  font-weight: var(--fw-bold);
  font-size: var(--fs-md);
  text-decoration: none;
  cursor: pointer;
  transition: all 0.2s ease;
  box-shadow: var(--shadow-sm);
}

.btn:hover {
  transform: translateY(-1px);
  box-shadow: var(--shadow-md);
}

.btn:active {
  transform: translateY(0);
  box-shadow: var(--shadow-sm);
}

.btn--primary {
  background: var(--brand-primary);
  color: var(--white);
  border-color: var(--brand-primary);
}

.btn--secondary {
  background: var(--white);
  color: var(--slate-700);
  border-color: var(--slate-200);
}

.btn--ghost {
  background: transparent;
  color: var(--slate-700);
  border-color: var(--slate-200);
}

.btn--small {
  padding: var(--space-2) var(--space-3);
  font-size: var(--fs-sm);
  border-radius: var(--radius-sm);
}

.btn--disabled {
  background: var(--slate-100);
  color: var(--slate-500);
  border-color: var(--slate-200);
  cursor: not-allowed;
  opacity: 0.6;
}
```

### Table Component
```css
.table {
  width: 100%;
  border-collapse: separate;
  border-spacing: 0;
  background: var(--white);
  border: 1px solid var(--slate-200);
  border-radius: var(--radius-lg);
  overflow: hidden;
  box-shadow: var(--shadow-sm);
}

.table thead th {
  position: sticky;
  top: 0;
  background: linear-gradient(180deg, #F8FAFC, #F1F5F9);
  color: var(--slate-700);
  text-align: left;
  padding: var(--space-4);
  font-size: var(--fs-sm);
  text-transform: uppercase;
  letter-spacing: 0.04em;
  border-bottom: 1px solid var(--slate-200);
  font-weight: var(--fw-semibold);
}

.table tbody td {
  padding: var(--space-4);
  border-bottom: 1px solid var(--slate-200);
  vertical-align: middle;
}

.table tbody tr:nth-child(even) {
  background: var(--white);
}

.table tbody tr:hover {
  background: #FBFDFD;
}

.table tbody tr:last-child td {
  border-bottom: none;
}
```

### Card Component
```css
.card {
  background: var(--white);
  border: 1px solid var(--slate-200);
  border-radius: var(--radius-xl);
  padding: var(--space-6);
  box-shadow: var(--shadow-md);
  transition: all 0.2s ease;
}

.card:hover {
  transform: translateY(-2px);
  box-shadow: var(--shadow-lg);
  border-color: var(--slate-300);
}

.card__header {
  margin-bottom: var(--space-4);
}

.card__title {
  font-size: var(--fs-lg);
  font-weight: var(--fw-bold);
  color: var(--slate-900);
  margin: 0;
}

.card__content {
  color: var(--slate-700);
}

.card__actions {
  margin-top: var(--space-4);
  display: flex;
  gap: var(--space-2);
}
```

## State Specifications

### Loading States
```css
.loading-skeleton {
  background: linear-gradient(90deg, var(--slate-100) 25%, var(--slate-200) 50%, var(--slate-100) 75%);
  background-size: 200% 100%;
  animation: loading 1.5s infinite;
}

@keyframes loading {
  0% { background-position: 200% 0; }
  100% { background-position: -200% 0; }
}

.loading-spinner {
  width: 24px;
  height: 24px;
  border: 2px solid var(--slate-200);
  border-top: 2px solid var(--brand-teal);
  border-radius: 50%;
  animation: spin 1s linear infinite;
}

@keyframes spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}
```

### Empty States
```css
.empty-state {
  text-align: center;
  padding: var(--space-12) var(--space-6);
  color: var(--slate-500);
}

.empty-state__icon {
  font-size: 48px;
  margin-bottom: var(--space-4);
  opacity: 0.5;
}

.empty-state__title {
  font-size: var(--fs-lg);
  font-weight: var(--fw-bold);
  margin-bottom: var(--space-2);
  color: var(--slate-700);
}

.empty-state__description {
  margin-bottom: var(--space-6);
}

.empty-state__action {
  margin-top: var(--space-4);
}
```

### Error States
```css
.error-state {
  text-align: center;
  padding: var(--space-8) var(--space-6);
  color: var(--brand-rose);
}

.error-state__icon {
  font-size: 48px;
  margin-bottom: var(--space-4);
}

.error-state__title {
  font-size: var(--fs-lg);
  font-weight: var(--fw-bold);
  margin-bottom: var(--space-2);
}

.error-state__description {
  margin-bottom: var(--space-6);
  color: var(--slate-700);
}

.error-state__action {
  margin-top: var(--space-4);
}
```

## Responsive Specifications

### Breakpoints
```css
:root {
  --breakpoint-sm: 640px;
  --breakpoint-md: 768px;
  --breakpoint-lg: 1024px;
  --breakpoint-xl: 1280px;
  --breakpoint-2xl: 1536px;
}
```

### Mobile (360px-767px)
```css
@media (max-width: 767px) {
  .grid-4 { grid-template-columns: repeat(2, minmax(0, 1fr)); }
  .grid-3 { grid-template-columns: repeat(2, minmax(0, 1fr)); }
  .grid-2 { grid-template-columns: 1fr; }
  
  .app-header { padding: var(--space-4); }
  .app-content { padding: var(--space-4); }
  
  .table { font-size: var(--fs-sm); }
  .table thead th { padding: var(--space-3); }
  .table tbody td { padding: var(--space-3); }
  
  .btn { padding: var(--space-2) var(--space-3); }
  .btn--small { padding: var(--space-1) var(--space-2); }
}
```

### Tablet (768px-1023px)
```css
@media (min-width: 768px) and (max-width: 1023px) {
  .app { grid-template-columns: 72px 1fr; }
  .sidebar { padding: var(--space-4) var(--space-2); }
  .sidebar nav a span { display: none; }
  
  .grid-4 { grid-template-columns: repeat(3, minmax(0, 1fr)); }
  .grid-3 { grid-template-columns: repeat(2, minmax(0, 1fr)); }
}
```

### Desktop (1024px+)
```css
@media (min-width: 1024px) {
  .app { grid-template-columns: 260px 1fr; }
  .sidebar { padding: var(--space-6) var(--space-4); }
  .sidebar nav a span { display: inline; }
  
  .grid-4 { grid-template-columns: repeat(4, minmax(0, 1fr)); }
  .grid-3 { grid-template-columns: repeat(3, minmax(0, 1fr)); }
  .grid-2 { grid-template-columns: repeat(2, minmax(0, 1fr)); }
}
```

## Accessibility Specifications

### Focus States
```css
:root {
  --focus-ring: var(--brand-teal);
  --focus-ring-width: 3px;
  --focus-ring-offset: 2px;
}

.focus-visible {
  outline: var(--focus-ring-width) solid var(--focus-ring);
  outline-offset: var(--focus-ring-offset);
}

.btn:focus-visible {
  outline: var(--focus-ring-width) solid var(--focus-ring);
  outline-offset: var(--focus-ring-offset);
}
```

### Color Contrast
- **Super Admin**: 21:1 (AAA)
- **Admin**: 4.5:1 (AA)
- **PM**: 4.5:1 (AA)
- **Team**: 4.5:1 (AA)
- **Client**: 4.5:1 (AA)

### Hit Target Sizes
- **Minimum**: 44px × 44px
- **Recommended**: 48px × 48px
- **Touch-friendly**: 56px × 56px

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

.skip-link {
  position: absolute;
  left: -9999px;
  top: auto;
  width: 1px;
  height: 1px;
  overflow: hidden;
}

.skip-link:focus {
  position: static;
  width: auto;
  height: auto;
  padding: var(--space-2) var(--space-3);
  background: var(--brand-teal);
  color: #05322a;
  border-radius: var(--radius-sm);
}
```
