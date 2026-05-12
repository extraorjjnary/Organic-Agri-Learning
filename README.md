# AgriLearn Pro — Organic Agriculture Learning Platform

## Project Overview

**AgriLearn Pro** (also referenced as *Greenfield* in some screens) is a **mobile-first, offline-capable digital learning platform** designed for Senior High School learners (Grade 11–12) enrolled in agricultural tracks at Philippine Farm Schools. The platform delivers high-quality, interactive educational content for Organic Agriculture that remains fully accessible in rural environments with limited or no internet connectivity.

---

## Goals

| Goal | Description |
|------|-------------|
| **Offline-First Learning** | All core modules are downloadable and fully functional without an active internet connection. |
| **Interactive Content Delivery** | Lessons include step-by-step instructions, rich media (illustrations, diagrams), and in-lesson knowledge checks. |
| **Field Integration** | Students can log practical field activities (e.g., composting, crop care) directly from their device. |
| **Progress Tracking** | Student progress is tracked locally and syncs to the server when connectivity is restored. |
| **Administrative Control** | Teachers/admins manage the academic structure (school years, year levels, subjects, competencies) and author lesson content. |
| **Analytics** | Admins can view platform-wide engagement metrics and student performance data. |

---

## Target Audience

- **Students:** Grade 11–12 learners in agricultural track Farm Schools
- **Admins / Teachers:** Institutional administrators who manage academic content, structure, and analytics
- **Environment:** Rural Farm Schools with intermittent connectivity; devices may be low-end Android tablets or phones

---

## Technology Stack (UI Prototypes)

All screens are self-contained HTML prototypes built with:

- **Tailwind CSS v3** (via CDN) — utility-first styling
- **Google Fonts: Lexend** — hyper-legible typeface for outdoor/field use
- **Material Symbols Outlined** — icon library
- **Vanilla JavaScript** — lightweight interactivity (tab switching, dark mode, form handling)
- **Design System:** [Neon Scholastic](#design-system) — custom design language

---

## File Structure

```
organic_agri_learning/
│
├── README.md                          ← This file
│
├── docs/
│   └── PRD.md                         ← Product Requirements Document
│
├── design-system/
│   └── DESIGN.md                      ← Neon Scholastic design system spec
│
└── src/
    ├── student/                        ← All student-facing screens
    │   ├── auth/                       ← Authentication
    │   │   ├── login.mobile.html
    │   │   └── login.desktop.html
    │   │
    │   ├── dashboard/                  ← Student home/progress overview
    │   │   ├── dashboard.mobile.html
    │   │   ├── dashboard.mobile.v2.html
    │   │   └── dashboard.desktop.html
    │   │
    │   ├── learning/                   ← Module browsing & lesson content
    │   │   ├── module-library.mobile.html
    │   │   ├── module-library.desktop.html
    │   │   ├── lesson-view.mobile.html
    │   │   └── lesson-view.desktop.html
    │   │
    │   └── field/                      ← Field activity logging
    │       ├── activity-log.mobile.html
    │       └── activity-log.desktop.html
    │
    └── admin/                          ← All admin-facing screens
        ├── academic/                   ← Academic structure management
        │   ├── manage-academic-structure.mobile.html
        │   ├── manage-subjects.mobile.html
        │   ├── manage-subjects.desktop.html
        │   ├── manage-year-levels.mobile.html
        │   ├── manage-year-levels.desktop.html
        │   ├── manage-school-years.mobile.html
        │   ├── manage-school-years.desktop.html
        │   └── manage-competencies.desktop.html
        │
        ├── content/                    ← Lesson content authoring
        │   ├── lesson-editor.mobile.html
        │   └── lesson-editor.desktop.html
        │
        └── analytics/                  ← Platform-wide reporting
            ├── analytics-dashboard.mobile.html
            └── analytics-dashboard.desktop.html
```

---

## Screen Catalogue & Responsibilities

### Student Screens

#### `src/student/auth/`

| File | Responsibility |
|------|---------------|
| `login.mobile.html` | Student sign-in for mobile devices. Clean, nature-themed layout with school/student ID and password fields. Establishes the "Greenfield" brand identity with a leaf motif. |
| `login.desktop.html` | Desktop version of the same login flow. Split-panel layout: branding/illustration left, form right. Same Lexend typography and Tailwind styling. |

#### `src/student/dashboard/`

| File | Responsibility |
|------|---------------|
| `dashboard.mobile.html` | Original mobile student home screen. Displays a personalized welcome, visual progress indicators for active modules, "Continue Learning" shortcut, and offline availability status badges. |
| `dashboard.mobile.v2.html` | Revised iteration of the mobile dashboard with updated layout and component refinements (same feature scope). Use this as the canonical mobile dashboard. |
| `dashboard.desktop.html` | Desktop student home. Features a sidebar navigation (labeled "Greenfield"), a broader content grid showing module progress, announcements, and quick-access cards for recent lessons. |

#### `src/student/learning/`

| File | Responsibility |
|------|---------------|
| `module-library.mobile.html` | Mobile module browser. Presents categorized learning modules (Soil Preparation, Organic Fertilizer, Crop Care) with download/sync status indicators, search, and filter tabs. |
| `module-library.desktop.html` | Desktop module library. Richer grid layout with sidebar navigation, module cards including download progress, category tags, and completion percentages. |
| `lesson-view.mobile.html` | Interactive lesson reader (mobile). Example: "Organic Composting" lesson. Shows step-by-step content with a progress bar, lesson sections, rich media placeholders, and inline knowledge checks/quizzes. |
| `lesson-view.desktop.html` | Desktop lesson reader (branded "EcoLearn"). Editorial-style full-width content with a persistent sidebar for lesson navigation, large typography, and multimedia embeds. |

#### `src/student/field/`

| File | Responsibility |
|------|---------------|
| `activity-log.mobile.html` | Mobile field activity logger. A form for recording organic agricultural practices: activity type selection, date picker, weather conditions input, observation notes, and photo upload (stored locally). Core offline tool for students working in the field. |
| `activity-log.desktop.html` | Desktop field log (branded "FieldLog Pro"). Two-column layout: left is the entry form; right shows a recent-activity feed. Supports the same data fields as the mobile version. |

---

### Admin Screens

#### `src/admin/academic/`

These screens form the institutional configuration layer, allowing admins to set up the academic framework that lessons and students are organized within.

| File | Responsibility |
|------|---------------|
| `manage-academic-structure.mobile.html` | Unified mobile hub for the academic structure. Tab-based navigation switching between School Years, Year Levels, and Subjects in one consolidated view. |
| `manage-subjects.mobile.html` | Mobile list view of all subjects (e.g., Organic Agriculture I, Crop Science). Includes search, filter by year level, and add/edit/delete actions per subject. |
| `manage-subjects.desktop.html` | Desktop table view of subjects with sortable columns, bulk-action checkboxes, and a slide-over form panel for editing. Uses the Neon Scholastic design system. |
| `manage-year-levels.mobile.html` | Mobile management of year levels (Grade 11, Grade 12, etc.). Displays student counts per level with add/edit actions. |
| `manage-year-levels.desktop.html` | Desktop year-level management (branded "EduManage"). Data table with stats overview cards and inline editing. |
| `manage-school-years.mobile.html` | Mobile view for configuring school years (e.g., 2024–2025, 2025–2026). Lets admins set active/archived status and date ranges. |
| `manage-school-years.desktop.html` | Desktop school year management (branded "EduAdmin"). Full-width table with status badges, date ranges, and an "Add School Year" modal flow. |
| `manage-competencies.desktop.html` | Desktop-only screen for defining learning competencies per subject/year level. Uses the full Neon Scholastic system (TopAppBar + SideNavBar). Maps competencies to curriculum standards. |

#### `src/admin/content/`

| File | Responsibility |
|------|---------------|
| `lesson-editor.mobile.html` | Mobile lesson authoring tool. Allows teachers to create or edit a lesson: set title, description, assign subject/year level, upload cover media, and add/reorder content sections (text blocks, media embeds, quiz items). |
| `lesson-editor.desktop.html` | Desktop lesson editor (branded "Greenfield LMS"). Richer two-panel layout with a live preview pane, breadcrumb navigation, drag-and-drop section reordering, and full metadata controls. |

#### `src/admin/analytics/`

| File | Responsibility |
|------|---------------|
| `analytics-dashboard.mobile.html` | Mobile admin analytics overview (branded "AgriLearn Admin Dashboard"). Key metrics cards (active students, modules completed, avg. quiz scores), a bar chart of module engagement, and a recent-activity feed. |
| `analytics-dashboard.desktop.html` | Desktop analytics hub (branded "EduAdmin"). Full sidebar navigation, multi-chart layout (line graphs, bar charts), per-subject engagement breakdowns, and downloadable report indicators. |

---

## Design System

The project uses the **Neon Scholastic** design system, documented in `design-system/DESIGN.md`.

### Key Principles

| Principle | Detail |
|-----------|--------|
| **Color** | Neon Lime (`#5bec13`) as the primary action color against a neutral slate/white palette. Primary color reserved for high-intent CTAs only. |
| **Typography** | Lexend font family throughout. Display: 30px/Black. Titles: 18px/Bold. Body: 14px/Regular. Labels: 12px/Semibold. |
| **Borders** | "No-Line" rule — sectioning uses color blocking, not borders. Borders only appear in data tables or tight component groupings. |
| **Corners** | Minimum `rounded-lg` everywhere; primary buttons use `rounded-xl` or `rounded-full`. |
| **Shadows** | `shadow-sm` lifts content cards; `shadow-lg` with primary glow (`shadow-primary/20`) on the main CTA button. |
| **Dark Mode** | Full dark mode support on all screens via Tailwind's `dark:` variant classes. |

---

## Naming Convention

All files follow this pattern:

```
{feature-name}.{viewport}.html
```

- `{feature-name}` — kebab-case functional name (e.g., `lesson-view`, `activity-log`)
- `{viewport}` — `mobile` or `desktop`
- `.v2` suffix — denotes a revised iteration of the same screen

---

## Original → Organized File Mapping

| Original Folder | New Path |
|----------------|----------|
| `student_login_mobile/` | `src/student/auth/login.mobile.html` |
| `student_login_desktop/` | `src/student/auth/login.desktop.html` |
| `dashboard/` | `src/student/dashboard/dashboard.mobile.html` |
| `updated_student_dashboard/` | `src/student/dashboard/dashboard.mobile.v2.html` |
| `student_dashboard_desktop/` | `src/student/dashboard/dashboard.desktop.html` |
| `module_library/` | `src/student/learning/module-library.mobile.html` |
| `module_library_desktop/` | `src/student/learning/module-library.desktop.html` |
| `composting_lesson/` | `src/student/learning/lesson-view.mobile.html` |
| `composting_lesson_desktop/` | `src/student/learning/lesson-view.desktop.html` |
| `field_activity_log/` | `src/student/field/activity-log.mobile.html` |
| `field_activity_log_desktop/` | `src/student/field/activity-log.desktop.html` |
| `create_edit_lesson/` | `src/admin/content/lesson-editor.mobile.html` |
| `create_edit_lesson_desktop/` | `src/admin/content/lesson-editor.desktop.html` |
| `manage_subjects/` | `src/admin/academic/manage-subjects.mobile.html` |
| `manage_subjects_desktop/` | `src/admin/academic/manage-subjects.desktop.html` |
| `manage_year_levels/` | `src/admin/academic/manage-year-levels.mobile.html` |
| `manage_year_levels_desktop/` | `src/admin/academic/manage-year-levels.desktop.html` |
| `manage_school_years/` | `src/admin/academic/manage-school-years.mobile.html` |
| `manage_school_years_desktop/` | `src/admin/academic/manage-school-years.desktop.html` |
| `manage_academic_structure/` | `src/admin/academic/manage-academic-structure.mobile.html` |
| `manage_competencies_desktop/` | `src/admin/academic/manage-competencies.desktop.html` |
| `admin_analytics_dashboard/` | `src/admin/analytics/analytics-dashboard.mobile.html` |
| `admin_analytics_dashboard_desktop/` | `src/admin/analytics/analytics-dashboard.desktop.html` |
| `neon_scholastic/DESIGN.md` | `design-system/DESIGN.md` |
| `project_prd_*.html` | `docs/PRD.md` |
