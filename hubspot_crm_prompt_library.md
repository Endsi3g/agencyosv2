# HubSpot CRM Clone - Optimized AI Prompt Library

A comprehensive, reusable prompt library for building a HubSpot-inspired CRM with AI assistance. Use these prompts with Claude, Gemini, or any capable AI model throughout your project.

---

## Table of Contents

1. [How to Use This Library](#how-to-use-this-library)
2. [Prompt Framework & Best Practices](#prompt-framework--best-practices)
3. [Phase 1: Reverse-Engineering](#phase-1-reverse-engineering)
4. [Phase 2: Backend Architecture](#phase-2-backend-architecture)
5. [Phase 3: Frontend Development](#phase-3-frontend-development)
6. [Phase 4: Integration & Real-time Features](#phase-4-integration--real-time-features)
7. [Phase 5: Advanced Features & Polish](#phase-5-advanced-features-polish)
8. [Phase 6: Testing & Optimization](#phase-6-testing-optimization)
9. [Phase 7: Deployment & Documentation](#phase-7-deployment-documentation)
10. [Troubleshooting & Refinement](#troubleshooting-refinement)

---

## How to Use This Library

### The Meta-Prompt (Use This First)

Start with this prompt when beginning a new session with Claude/Gemini:

```text
I'm building a HubSpot-inspired CRM desktop application using:
- Frontend: Electron + React + TypeScript + Tailwind CSS + Framer Motion
- Backend: Node.js + Express + Prisma + PostgreSQL
- Design: Linear-inspired minimalist aesthetic with dark mode

I'll be asking you to help with specific features. Please:
1. Provide complete, production-ready code (not snippets or pseudocode)
2. Include TypeScript types and full error handling
3. Follow the tech stack above unless I specify otherwise
4. Include comments explaining complex logic
5. Assume I have limited coding experience - explain non-obvious decisions
6. For file structures, clearly indicate folder paths and file names
7. When I provide feedback on generated code, iterate on it rather than starting over

Here are my 5 core features:
1. CRM Contacts (manage contacts, properties, activity timeline)
2. Email Campaigns (build, send, track email campaigns)
3. Analytics Dashboard (real-time metrics and charts)
4. Automation Builder (visual workflow builder)
5. Prospection Sequences (multi-step outreach sequences)

I'll reference specific features and ask for help. Ready to proceed?
```

### How to Customize Prompts

Each prompt in this library has **[VARIABLE]** placeholders. Replace them:

- **[FEATURE_NAME]** → "CRM Contacts", "Email Campaigns", etc.
- **[COMPONENT_NAME]** → "ContactList", "EmailBuilder", etc.
- **[API_ENDPOINT]** → "/api/contacts", "/api/campaigns", etc.
- **[DESCRIPTION]** → Your specific requirement

### Prompt Quality Checklist

Before submitting a prompt, ensure it includes:

- ✅ Clear context (what you're building, tech stack)
- ✅ Specific requirements (what should be included)
- ✅ Output format (full code, structure, file paths)
- ✅ Any constraints (styling system, error handling, performance)
- ✅ Reference to related features if interdependent

---

## Prompt Framework & Best Practices

### The 5-Part Prompt Structure

Use this structure for complex features:

```text
**CONTEXT:** [What you're building and why]

**REQUIREMENTS:**
1. [First requirement]
2. [Second requirement]
3. [Third requirement]

**TECHNICAL CONSTRAINTS:**
- Tech stack: [Your tools]
- Styling: [How it should look]
- Performance: [Any optimization needs]

**OUTPUT FORMAT:**
[Specify: full code, file structure, commented explanations, TypeScript types]

**EXAMPLES/REFERENCE:**
[Link to similar features, design systems, or examples]
```

### Weak vs. Strong Prompt Examples

**❌ Weak:** "Build the automation workflow builder please"

- Too vague, missing requirements and constraints

**✅ Strong:** "Create a React Flow-based automation workflow builder component with: (1) Drag-and-drop trigger/condition/action nodes, (2) Configuration panel on slide-in from right, (3) Dark theme customized for React Flow matching Linear's aesthetic (#0E0E10 background), (4) Node types with different colors (green trigger, yellow condition, blue action, purple delay), (5) Validation for incomplete workflows. Include TypeScript types, Tailwind styling, and complete component exports. Save as /src/components/workflows/WorkflowBuilder.tsx"

---

## Phase 1: Reverse-Engineering

### 1.1: Create a Feature Analysis Template

```text
I need to reverse-engineer HubSpot's [FEATURE_NAME] feature for my CRM clone.

Create a detailed analysis document including:

1. **User Interface Breakdown:**
   - Main view layout (sections, panels, sidebars)
   - List view components (tables, cards, filters)
   - Detail view structure (left panel, main content, right sidebar)
   - Modals and popups used in this feature
   - Navigation and breadcrumbs

2. **User Flows:**
   - Primary workflow (how users complete the main task)
   - Secondary workflows (alternative paths)
   - Micro-interactions (what happens on button click, form submit, etc.)

3. **Data Model:**
   - Primary entity for this feature and all its properties
   - Related entities (what other objects it connects to)
   - Required fields vs. optional fields
   - Custom fields or flexible properties

4. **Business Logic:**
   - Validation rules (what makes data valid?)
   - Constraints (limits, exclusions)
   - Calculations (if applicable)
   - State transitions (how does this feature change over time?)

5. **Integration Points:**
   - How this feature connects to other CRM features
   - Events it triggers (what happens in other features when this changes?)
   - Data it needs from other features

Format as a structured specification document with clear sections and examples. Include UI sketches where helpful.
```

### 1.2: Create a Design System Analysis Prompt

```text
I'm analyzing HubSpot's design system for a Linear-inspired CRM clone.

Create a complete design system specification including:

1. **Color Palette:**
   - List all primary colors used (backgrounds, text, accents)
   - Provide hex codes or visual descriptions
   - Semantic colors (success, error, warning, info)
   - How colors change in light vs. dark mode

2. **Typography:**
   - Font families used (primary, secondary)
   - Font sizes and their uses (headings, body, labels, captions)
   - Font weights and their purposes
   - Line heights and letter spacing
   - How typography scales on different screen sizes

3. **Spacing & Layout:**
   - Base spacing unit (e.g., 4px, 8px grid)
   - Padding and margin conventions
   - Breakpoints for responsive design
   - Max-width for content areas

4. **Component Patterns:**
   - Buttons (primary, secondary, tertiary, sizes)
   - Form inputs (text, select, checkbox, radio, toggle)
   - Tables (headers, rows, sorting, pagination)
   - Cards (variants, shadows, hover states)
   - Modals and overlays
   - Navigation (top bar, sidebar, breadcrumbs)
   - Notifications (toasts, alerts, badges)

5. **Animation & Motion:**
   - Transition durations (fast, normal, slow)
   - Easing functions used
   - When animations are applied (on hover, state change, navigation)
   - Loading states and how they animate

6. **Visual Hierarchy:**
   - How important elements stand out
   - Use of size, color, weight, positioning
   - Emphasis techniques

Output as a design system guide with visual examples where possible. Prioritize what we can replicate with Tailwind CSS + Framer Motion.
```

### 1.3: Reverse-Engineer a Specific Page

```text
Create a detailed specification for reverse-engineering HubSpot's [PAGE_NAME] page.

Include:
1. Page URL structure and routing
2. Header/toolbar components and actions
3. Main content area (primary data display)
4. Sidebars (filters, details, related data)
5. All interactive elements (buttons, links, dropdowns, etc.)
6. Loading states and empty states
7. Error states and validation feedback
8. Responsive behavior on different screen sizes
9. Keyboard shortcuts and accessibility features
10. Real-time updates if applicable

Provide pseudo-code or pseudoHTML structure showing the layout hierarchy. List all API calls that would happen on page load and during interactions.
```

---

## Phase 2: Backend Architecture

### 2.1: Initialize Backend Project Structure

```text
Set up a complete Node.js + Express + Prisma backend for a HubSpot-inspired CRM.

Create the project structure and all necessary files:

1. **Folder Structure:**
   - /src directory with: routes/, controllers/, services/, models/, middleware/, utils/, config/
   - /prisma directory with schema.prisma
   - Root config files: package.json, .env.example, tsconfig.json, .gitignore

2. **package.json:**
   - Dependencies: express, prisma, @prisma/client, bcrypt, jsonwebtoken, dotenv, cors, helmet, morgan, express-validator, nodemailer, bull (job queue), socket.io, axios
   - Dev dependencies: typescript, ts-node, @types/node, @types/express, prisma, nodemon
   - Scripts: dev (with nodemon), build, start, generate (prisma), seed (database)

3. **Environment Setup:**
   - .env.example with all required variables (DATABASE_URL, JWT_SECRET, EMAIL_SERVICE_KEY, etc.)
   - config/index.ts exporting environment variables with defaults
   - Database connection setup in config/database.ts

4. **Express App Setup (src/index.ts):**
   - Middleware setup (cors, helmet, morgan, json parsing)
   - Error handling middleware
   - Basic routes structure
   - 404 handler

5. **Authentication Middleware (src/middleware/auth.ts):**
   - JWT token verification
   - User extraction from token
   - Error handling for invalid tokens

6. **Database Connection (src/config/database.ts):**
   - Prisma client initialization
   - Connection handling
   - Error logging

For each file, provide complete code including imports, exports, and comments explaining key sections. Use TypeScript with strict typing.
```

### 2.2: Design Complete Database Schema

```text
Create a complete Prisma schema for a HubSpot-inspired CRM with these 5 features:
1. CRM Contacts
2. Email Campaigns
3. Analytics Dashboard
4. Automation Builder
5. Prospection Sequences

**Models Required:**

**User & Auth:**
- User (id, email, password_hash, first_name, last_name, company, created_at, updated_at)
- Role (admin, sales, marketing)
- Permission (feature-based)

**Core CRM:**
- Contact (id, email, first_name, last_name, company_id, phone, lifecycle_stage, lead_score, tags[], custom_fields JSON, properties JSON, created_at, updated_at, deleted_at)
- Company (id, name, industry, employees, domain, created_at, updated_at)
- List (id, name, description, contacts[], user_id, created_at)
- Tag (id, name, color, used_count)

**Activities & Timeline:**
- Activity (id, contact_id, type: "note"|"call"|"email"|"meeting", title, description, created_by_id, created_at)
- Note (id, contact_id, content, created_by_id, created_at, updated_at)
- Call (id, contact_id, duration, direction: "inbound"|"outbound", created_by_id, created_at)
- Meeting (id, contact_id, title, scheduled_at, duration, created_by_id, created_at)
- Task (id, contact_id, title, description, due_date, status, created_by_id, created_at)

**Email & Campaigns:**
- EmailTemplate (id, name, subject, body HTML, preview_text, thumbnail_url, created_by_id, created_at, updated_at)
- EmailCampaign (id, name, template_id, recipient_list_id, status: "draft"|"scheduled"|"sending"|"sent", scheduled_at, sent_at, a_b_testing JSON, user_id, created_at, updated_at)
- EmailEvent (id, campaign_id, contact_id, type: "sent"|"opened"|"clicked"|"bounced"|"unsubscribed", clicked_link_url, opened_at, clicked_at, bounced_at, metadata JSON, created_at)
- Unsubscribe (id, email, reason, created_at)

**Automation & Workflows:**
- AutomationWorkflow (id, name, description, trigger JSON, workflow_steps JSON, active, user_id, created_at, updated_at, deleted_at)
- WorkflowExecution (id, workflow_id, contact_id, current_step_index, status: "in_progress"|"completed"|"failed", execution_log JSON[], completed_at, failed_at, created_at)
- WorkflowEvent (event_type: "contact.created"|"contact.property_changed"|"email.opened"|"form.submitted", contact_id, workflow_id, triggered_at)

**Prospection Sequences:**
- ProspectionSequence (id, name, description, steps JSON (email template id, delay, task type), enrollment_criteria JSON, user_id, active, created_at, updated_at)
- SequenceEnrollment (id, sequence_id, contact_id, current_step_index, status: "active"|"completed"|"unenrolled", unenroll_reason, enrolled_at, completed_at, last_step_completed_at, created_at)
- SequenceExecution (id, enrollment_id, step_index, type: "email"|"task", executed_at, response_received: boolean, response_type, created_at)

**Analytics:**
- AnalyticsEvent (id, event_type, user_id, contact_id, metadata JSON, created_at)
- CampaignAnalytics (cached for performance: id, campaign_id, sent_count, delivered_count, opened_count, clicked_count, unsubscribed_count, last_updated)

**Relationships & Constraints:**
- Each Contact belongs to a User (for multi-tenant support)
- Contacts have many Activities
- Campaigns have many EmailEvents
- Workflows have many WorkflowExecutions
- Sequences have many SequenceEnrollments
- All users must have unique emails
- Soft deletes for Contacts and Workflows (deleted_at field)
- Created_at and updated_at timestamps everywhere

Include: field types, required fields, defaults, indexes for performance (email, created_at, user_id), and relationships (one-to-many, many-to-many). Provide complete Prisma schema file content with comments explaining complex relationships.
```

### 2.3: Build API Endpoint for a Feature

```text
Create complete REST API endpoints for [FEATURE_NAME] with:

**Available Endpoints:**
[LIST 3-5 SPECIFIC ENDPOINTS NEEDED]

For each endpoint, provide:
1. Route definition with HTTP method and path
2. Request body schema with validation
3. Response schema with example data
4. Error cases and status codes returned
5. Authentication & authorization requirements
6. Complete controller function with:
   - Input validation
   - Business logic
   - Error handling
   - Response formatting
7. Service layer functions (separate business logic from routes)
8. Prisma queries with optimizations (select specific fields, eager load relations)
9. TypeScript interfaces for request/response types

Include:
- Request validation using express-validator with clear error messages
- Proper HTTP status codes (200, 201, 400, 401, 403, 404, 500)
- Consistent error response format
- Pagination for list endpoints
- Filtering and sorting where applicable
- Soft deletes where appropriate
- Optimistic locking to prevent race conditions if needed

Provide complete, production-ready code organized by file:
- /src/routes/[FEATURE_NAME].ts
- /src/controllers/[FEATURE_NAME]Controller.ts
- /src/services/[FEATURE_NAME]Service.ts
- /src/types/[FEATURE_NAME].ts

Include imports, exports, and error handling. Use TypeScript with strict types.
```

### 2.4: Implement Complex Backend Logic

```text
Implement a [COMPLEX_FEATURE] engine for the CRM with:

**Requirements:**
[DETAIL THE SPECIFIC LOGIC NEEDED]

**System Design:**
1. Overall architecture (how components interact)
2. Data flow (input → processing → output)
3. State management (how state changes over time)
4. Error handling and edge cases
5. Performance considerations

**Implementation:**
1. Main service class with typed parameters and return values
2. Helper functions for subtasks
3. Event emitters for important state changes
4. Logging for debugging
5. Unit-testable functions (pure functions where possible)

**Integration:**
1. How this integrates with other features
2. Database queries and Prisma operations
3. External service calls if applicable (email sending, etc.)

Example: "Create the automation workflow execution engine that: (1) listens for trigger events (contact.created, property.changed, email.opened), (2) evaluates conditions, (3) executes actions sequentially, (4) handles delays using Bull job queue, (5) logs execution history, (6) supports error recovery."

Provide complete, production-ready code with TypeScript, error handling, and comments explaining complex logic.
```

### 2.5: Create Database Seeders

```text
Create database seed data for development and testing including:

**Sample Data to Generate:**
1. 5 test users with different roles
2. 50 sample contacts with realistic data (names, emails, companies, lifecycle stages, lead scores)
3. 3 sample companies
4. 10 email templates with HTML bodies
5. 3 sample campaigns in different statuses
6. Sample email events (opens, clicks, bounces) for campaigns
7. 3 automation workflows with different trigger types
8. 5 prospection sequences with multi-step configurations
9. Sample activities (notes, calls, meetings) for contacts
10. Sample tags and lists

**File Structure:**
- /prisma/seed.ts (main seeder file)
- /prisma/seeders/ directory with individual seeder functions
- /prisma/data/ directory with sample data (contact names, companies, email templates)

**Seeding Script:**
- package.json script: "prisma db seed"
- Handles idempotency (safe to run multiple times)
- Clears existing data option
- Progress logging
- Error handling

Provide complete seed file with realistic sample data. Make email/contact data look real. Include comments explaining what data is being created and why.
```

---

## Phase 3: Frontend Development

### 3.1: Create a React Component with Full Styling

```text
Create a [COMPONENT_NAME] React component with:

**Component Purpose:**
[DESCRIBE WHAT THIS COMPONENT DOES]

**Props Interface:**
- List all props with TypeScript types
- Mark required vs. optional
- Provide default values

**Functionality:**
[LIST KEY FEATURES: Click handlers, form handling, state management, etc.]

**Styling Requirements:**
- Dark mode (backgrounds #0E0E10, #1A1A1D, text #E4E4E7)
- Tailwind CSS only (core utilities)
- Hover states, focus states, disabled states
- Match Linear's minimalist aesthetic
- Responsive design for different screen sizes

**Animations:**
[SPECIFY FRAMER MOTION ANIMATIONS: entrance, exit, interactions]

**State Management:**
- Use React hooks (useState, useContext, useCallback)
- Zustand integration if needed
- Optimization notes (useMemo, useCallback where needed)

**Accessibility:**
- ARIA labels where needed
- Keyboard navigation
- Semantic HTML

**File Structure:**
- /src/components/[FEATURE]/[COMPONENT_NAME].tsx (main component)
- /src/components/[FEATURE]/[COMPONENT_NAME].module.css (if needed for complex styling)
- /src/types/[FEATURE].ts (TypeScript interfaces)

Provide complete component code with:
- Import statements
- TypeScript interfaces
- Component function with hooks
- Event handlers
- Return JSX with Tailwind classes
- Framer Motion variants
- Export statement
- Comments explaining complex sections
```

### 3.2: Build a Complex Page/View

```text
Create a complete [PAGE_NAME] page for the Electron app with:

**Page Layout:**
[DESCRIBE THE LAYOUT: sidebar, header, main content area, right panel, etc.]

**Key Sections:**
1. [Section 1 name and description]
2. [Section 2 name and description]
3. [Section 3 name and description]

**Components on This Page:**
- List all sub-components this page uses
- How they communicate (props, shared state, callbacks)

**State Management:**
- Zustand store hooks used
- Local component state
- Data fetching and caching strategy
- Loading/error/success states

**API Integration:**
- What endpoints this page calls
- When data is fetched (on mount, on filter change, etc.)
- How results are paginated
- Real-time updates (WebSocket)

**User Interactions:**
[DETAIL THE USER FLOWS: filter, search, select, create, edit, delete, etc.]

**Styling & Animations:**
- Dark mode Tailwind classes
- Framer Motion page transitions
- Component entrance animations
- Interactive micro-animations

**File Structure:**
- /src/pages/[PAGE_NAME]/index.tsx (main page)
- /src/pages/[PAGE_NAME]/components/ (sub-components)
- /src/pages/[PAGE_NAME]/hooks/ (custom hooks)
- /src/stores/[FEATURE]Store.ts (Zustand store)

Provide complete page implementation with all sub-components, hooks, state management, API calls, and styling. Include TypeScript types and comments.
```

### 3.3: Create Reusable UI Component Library

```text
Create a library of reusable UI components for the CRM with:

**Base Components:**
1. Button (variants: primary, secondary, ghost, sizes: sm, md, lg, states: default, hover, active, disabled)
2. Input (text, email, password, textarea, with labels, error states, success states)
3. Select/Dropdown (single select, multi-select, searchable)
4. Checkbox & Radio
5. Toggle Switch
6. Badge/Tag
7. Card (standard, hoverable, variant for list items)
8. Modal/Dialog (slide-in, centered, sizes)
9. Alert (success, error, warning, info with close button)
10. Spinner/Loading (skeleton screens)
11. Avatar (profile pictures)
12. Tooltip
13. Breadcrumbs
14. Pagination

For each component:
- TypeScript interface with all props
- Tailwind styling with dark mode
- All interactive states (hover, focus, active, disabled)
- Framer Motion variants if animated
- Accessibility features (ARIA labels, keyboard navigation)
- Size variants and style variants
- Example usage

**File Structure:**
- /src/components/ui/ (one file per component)
- /src/components/ui/index.ts (barrel export)
- /src/types/ui.ts (shared TypeScript types)

Provide complete component library code with:
- All components fully implemented
- Consistent styling approach
- Reusable animation variants
- Exported as a cohesive design system
- Ready to use across all pages

Include comments showing example usage: <Button variant="primary" size="md">Click me</Button>
```

### 3.4: Build a Data Table Component

```text
Create a flexible, reusable data table component with:

**Features:**
1. Column definitions with headers (sortable, resizable)
2. Rows with data (striped styling, hover highlight)
3. Sorting (click header to sort ascending/descending)
4. Pagination (next/prev buttons, page indicator, rows per page selector)
5. Row selection (checkbox column, select all toggle, bulk action bar)
6. Filters (sidebar or inline)
7. Search/quick filter
8. Loading state (skeleton rows)
9. Empty state
10. Expandable rows for details
11. Inline editing optional
12. Export to CSV
13. Responsive on small screens

**Component Props:**
- columns: Array of column definitions (key, label, width, sortable, render function)
- data: Array of row objects
- onSort: Callback when sorting changes
- onPaginate: Callback for pagination
- onRowSelect: Callback for selected rows
- loading: boolean
- emptyState: React component

**Styling:**
- Dark Tailwind theme
- Hover states on rows
- Sticky header
- Alternating row colors
- Action buttons in toolbar above table
- Smooth animations on load and updates

**Performance:**
- Virtualization for large datasets (react-window)
- Memoization to prevent unnecessary re-renders
- Efficient sorting and filtering

Provide complete, production-ready table component with:
- TypeScript interfaces for columns and data
- All features implemented
- Framer Motion animations
- Proper state management
- Usage examples
```

### 3.5: Implement Form Builder

```text
Create a flexible form component system for:
- Creating/editing contacts
- Creating/editing campaigns
- Configuring automations
- Enrolling in sequences
- Filtering and searching

**Form Features:**
1. Dynamic field types (text, email, password, textarea, select, multiselect, checkbox, radio, date, date-range, file upload, rich text)
2. Field-level validation with error messages
3. Required/optional fields with visual indicators
4. Help text and tooltips
5. Inline error display (red text below field)
6. Success feedback (checkmark animation)
7. Submit button (disabled until valid, loading state)
8. Cancel button with unsaved changes warning
9. Field grouping and conditional rendering (show/hide fields based on other fields)
10. Custom field rendering
11. Form-level validation

**Form Data Structure:**
- Schema definition (validation rules, field configs)
- TypeScript types for form values
- Error object mapping field names to error messages

**Accessibility:**
- Label associations
- Error announcements (aria-invalid, aria-describedby)
- Keyboard navigation
- Form submission on Enter

**File Structure:**
- /src/components/forms/Form.tsx (main form wrapper)
- /src/components/forms/FormField.tsx (individual field)
- /src/components/forms/useForm.ts (custom hook for form state)
- /src/types/forms.ts (TypeScript interfaces)

Provide complete form system with validation, error handling, and all field types implemented. Include examples for contact, campaign, and automation forms.
```

---

## Phase 4: Integration & Real-time Features

### 4.1: Create API Client with Interceptors

```text
Create a complete Axios API client for the Electron app with:

**Features:**
1. Base URL configuration
2. Request interceptor (add JWT token to Authorization header)
3. Response interceptor (handle errors consistently)
4. Error handling (401 → logout, 403 → permission error, 500 → generic error)
5. Token refresh logic (on 401, refresh token and retry original request)
6. Request timeout (30 seconds)
7. Request deduplication (prevent duplicate requests)
8. Offline detection
9. Request retry logic with exponential backoff for failed requests

**File Structure:**
- /src/services/api/client.ts (axios instance)
- /src/services/api/endpoints.ts (typed API methods)
- /src/services/api/errors.ts (error handling)

**API Methods Organized by Feature:**
```typescript
// Auth
auth.login(email, password): Promise<AuthResponse>
auth.register(email, password, name): Promise<AuthResponse>
auth.refresh(): Promise<TokenResponse>
auth.logout(): void

// Contacts
contacts.getAll(filters, page, limit): Promise<PaginatedResponse<Contact>>
contacts.getById(id): Promise<Contact>
contacts.create(data): Promise<Contact>
contacts.update(id, data): Promise<Contact>
contacts.delete(id): Promise<void>
contacts.import(file): Promise<ImportResult>
contacts.export(filters): Promise<Blob>
contacts.bulkUpdate(ids, data): Promise<BulkUpdateResult>

// Campaigns
campaigns.getAll(): Promise<Campaign[]>
campaigns.getById(id): Promise<Campaign>
campaigns.create(data): Promise<Campaign>
campaigns.update(id, data): Promise<Campaign>
campaigns.delete(id): Promise<void>
campaigns.send(id): Promise<void>
campaigns.getAnalytics(id): Promise<CampaignAnalytics>

// Similar for: Sequences, Workflows, Analytics
```

**Error Handling:**

- Custom error types (ValidationError, AuthError, NetworkError, etc.)
- User-friendly error messages
- Error logging for debugging
- Automatic retry logic

Provide complete API client code with TypeScript, full error handling, and organized endpoint methods.

```

### 4.2: Build Zustand State Stores

```

Create Zustand stores for state management with:

**Store Structure (each feature gets a store):**

1. **authStore** (user authentication & permissions)
   - State: user, token, refreshToken, isAuthenticated, loading
   - Actions: login, register, logout, refresh, updateUser
   - Selectors: isAuthenticated, hasPermission(feature)

2. **contactStore** (contacts list & details)
   - State: contacts[], selectedContact, filters, search, page, loading
   - Actions: fetchContacts, selectContact, createContact, updateContact, deleteContact, setFilters, search
   - Selectors: filteredContacts, selectedContactWithActivities

3. **campaignStore** (campaigns & email templates)
   - State: campaigns[], selectedCampaign, templates[], loading
   - Actions: fetchCampaigns, selectCampaign, createCampaign, sendCampaign, getAnalytics
   - Selectors: getAnalyticsForCampaign(id)

4. **sequenceStore** (prospection sequences)
   - State: sequences[], selectedSequence, enrollments, loading
   - Actions: fetchSequences, selectSequence, createSequence, enrollContact, unenrollContact
   - Selectors: getSequenceWithEnrollments(id)

5. **workflowStore** (automation workflows)
   - State: workflows[], selectedWorkflow, canvasState, executionLog, loading
   - Actions: fetchWorkflows, selectWorkflow, updateWorkflow, activateWorkflow, testWorkflow
   - Selectors: activeWorkflows, workflowWithExecutions

6. **analyticsStore** (dashboard data)
   - State: dashboardMetrics, dateRange, chartData, loading
   - Actions: fetchDashboard, setDateRange, refreshAnalytics
   - Selectors: getTrendData(metric, dateRange)

7. **uiStore** (UI state)
   - State: sidebarCollapsed, activeModal, notifications[], commandPaletteOpen
   - Actions: toggleSidebar, openModal, closeModal, addNotification, removeNotification, toggleCommandPalette

**Store Features:**

- Persist to localStorage (optional)
- Optimistic updates for better UX
- Loading states and error handling
- Efficient selectors to prevent unnecessary re-renders
- Combined actions that call multiple endpoints

Provide each store with:

- TypeScript interfaces for state
- Typed actions with parameters
- Selectors for derived state
- Error handling
- Integration with API client

```

### 4.3: Implement WebSocket Real-time Updates

```

Set up real-time features using Socket.io for:

**Server-side Implementation:**

1. Socket.io server setup in Node.js
2. JWT authentication on socket connection
3. Event emitters in services (emit when data changes)
4. Room-based broadcasting (user-specific rooms)
5. Reconnection handling

**Client-side Implementation (Electron):**

1. Socket.io client connection
2. Auto-reconnection with exponential backoff
3. Event listeners for data updates
4. Update Zustand stores when events received

**Events to Implement:**

```text
Server → Client Events:
- contact:created (new contact added → broadcast to user)
- contact:updated (contact modified → update in store)
- contact:deleted (contact removed)
- email:sent (campaign email sent)
- email:opened (recipient opened email → update analytics)
- email:clicked (recipient clicked link)
- campaign:completed (campaign finished sending)
- workflow:triggered (workflow executed for a contact)
- workflow:step_completed (contact advanced in workflow)
- sequence:enrolled (contact added to sequence)
- sequence:step_completed (next step in sequence)
- analytics:updated (dashboard metrics changed)
- notification:new (push notification for user)
```

**Real-time Features:**

1. New contact appears in list immediately
2. Email open/click counts update on analytics dashboard
3. Workflow execution history shows in real-time
4. Sequence progress updates for enrolled contacts
5. Toast notifications for important events (workflow completed, email replied, etc.)

**Client Integration:**

- Initialize socket connection on app startup
- Update Zustand stores on socket events
- Handle disconnection and reconnection gracefully
- Unsubscribe from events on component unmount

Provide complete Socket.io setup for both server and client with event handlers, Zustand store integration, and error handling.

```

### 4.4: Add Animations & Transitions

```text

Enhance the UI with Framer Motion animations for:

**Page Transitions:**

- Define animation variants for page entrance/exit (fade + slide)
- Apply to layout.animatePresence to animate route changes
- Duration: 200-300ms with cubic-bezier(0.4, 0, 0.2, 1)

**List Animations:**

- Stagger children animations (contacts appearing one-by-one)
- New items slide in from top with fade
- Deleted items fade out and collapse height
- Smooth transitions on list updates

**Micro-interactions:**

- Button hover: scale 1.02 (150ms)
- Card hover: lift with shadow (translateY -4px)
- Input focus: border color transition (200ms)
- Toggle switch: slide animation with smooth easing
- Checkbox: checkmark draw animation
- Loading spinner: smooth continuous rotation

**Data Updates:**

- New row in table: slideInUp animation
- Metric card values: countUp animation
- Chart data: smooth transition between data sets
- Progress bars: animated fill

**Modals & Overlays:**

- Modal slide in from right (300ms)
- Backdrop fade in (200ms)
- Dropdown menus scale from origin point (150ms)
- Toast notifications slide in from corner

**Framer Motion Setup:**

- Create animation variants file: /src/config/animationVariants.ts
- Define reusable variants (pageEnter, pageExit, listItem, etc.)
- Use consistent timing: fast=150ms, normal=200ms, slow=300ms
- Apply cubic-bezier(0.4, 0, 0.2, 1) for easing

**Implementation Files:**

- /src/config/animationVariants.ts (variant definitions)
- Wrap pages in AnimatePresence for exit animations
- Apply variants to motion.div components
- Use transition prop for timing control

Provide animation variants configuration and implementation examples for key interactions.

```

---

## Phase 5: Advanced Features & Polish

### 5.1: Create Command Palette

```text

Implement a Cmd+K command palette with:

**Features:**

1. Global keyboard shortcut (Cmd+K on Mac, Ctrl+K on Windows)
2. Modal overlay with search input
3. Fuzzy search across:
   - Navigation items (Contacts, Campaigns, etc.)
   - Contacts (by name, email, company)
   - Campaigns (by name, status)
   - Sequences (by name)
   - Workflows (by name)
   - Recent items (last 5 viewed)
   - Quick actions (Create contact, Create campaign, etc.)

4. Keyboard navigation:
   - Up/Down arrows to move through results
   - Enter to select
   - Escape to close
   - Type to search
   - Number keys for quick access (1-9)

5. Result categories with icons:
   - 🔍 Navigation
   - 👤 Contacts
   - 📧 Campaigns
   - 🔗 Sequences
   - ⚙️ Workflows
   - ⭐ Recent
   - ⚡ Actions

6. Result preview (show more info on hover)
7. Customizable key binding (allow users to change shortcut)

**Implementation:**

- Use cmdk library or build custom
- Global keyboard listener using useEffect
- State management in Zustand (isOpen)
- Integrate with React Router for navigation
- Search logic with fuzzy matching

**File Structure:**

- /src/components/CommandPalette.tsx
- /src/hooks/useCommandPalette.ts
- /src/config/commands.ts (action definitions)

Provide complete command palette component with fuzzy search, keyboard navigation, and all the above features.

```

### 5.2: Implement CSV Import/Export

```text

Create CSV import/export functionality with:

**CSV Export:**

1. Select data to export (current view with filters applied)
2. Choose columns to include (checkbox selection)
3. Export format options (CSV, Excel)
4. Download with timestamped filename
5. Show success toast

**CSV Import:**

1. Drag-and-drop file upload area (or click to select)
2. Parse CSV and show preview (first 5 rows)
3. Column mapping interface (drag to reorder, match to contact properties)
4. Validation:
   - Check required fields present
   - Validate email format
   - Check for duplicates
   - Flag rows with errors
5. Progress bar during import (batch processing)
6. Results summary (X imported, Y skipped, Z errored)
7. Option to download error report

**Bulk Actions:**

1. Select multiple rows (checkbox column)
2. Bulk action toolbar appears at bottom:
   - Delete selected
   - Add to list
   - Remove from list
   - Update property (open dropdown to select)
   - Enroll in sequence
   - Export selected
3. Confirmation modal for destructive actions
4. Progress indicator for batch operations
5. Undo button for last action (keep in memory for session)

**Implementation:**

- Use PapaParse for CSV parsing
- XLSX library for Excel support
- Batch API calls with progress tracking
- Error handling and reporting
- Optimistic UI updates

**File Structure:**

- /src/utils/csvImportExport.ts (parsing logic)
- /src/components/ImportModal.tsx
- /src/components/BulkActionsToolbar.tsx
- /src/hooks/useBulkActions.ts

Provide complete import/export implementation with validation, error handling, and progress feedback.

```

### 5.3: Build Email Template Editor

```text

Create a WYSIWYG email template editor with:

**Editor Features:**

1. Rich text toolbar: Bold, Italic, Underline, Headings (H1-H3), Lists (UL/OL), Links, Images
2. Text formatting options (font size, color, alignment)
3. Block types: Paragraph, heading, divider, image block, button, table
4. Drag-and-drop blocks (reorder content)
5. Undo/Redo (last 20 actions)

**Personalization:**

1. Token insertion menu (dropdown showing available contact properties)
2. Insert as {{contact.firstName}}, {{contact.email}}, etc.
3. Default value for missing data: {{contact.firstName|User}}
4. Conditional blocks: {{#if contact.premium}}...{{/if}}

**Templates & Variants:**

1. Save template with name and category
2. Save as new variant (A/B testing)
3. Template library (browse, search, use existing)
4. Template categories (promotional, transactional, welcome, etc.)

**Preview:**

1. Desktop view (600px width)
2. Mobile view (320px width)
3. Preview with sample contact data
4. Dark mode preview

**Upload & Images:**

1. Drag-and-drop image upload
2. Image compression
3. Image sizing controls
4. CDN integration for image hosting

**File Structure:**

- /src/components/EmailEditor/EmailEditor.tsx (main component)
- /src/components/EmailEditor/Toolbar.tsx
- /src/components/EmailEditor/PreviewPane.tsx
- /src/components/EmailEditor/useEmailEditor.ts (state management)

**Technology:**

- TipTap or Draft.js for rich text editing
- Custom block rendering
- Tailwind for styling

Provide complete email editor with all features, rich text handling, and template management.

```

### 5.4: Build Notification System

```text

Create a comprehensive notification system with:

**Toast Notifications:**

1. Types: success, error, warning, info
2. Auto-dismiss after 5 seconds (configurable)
3. Manual dismiss button (X)
4. Action buttons (e.g., "View contact")
5. Max 3 visible at once (queue additional)
6. Stack vertically (top-right corner)
7. Slide in/out animation

**Notification Center (Bell Icon):**

1. Bell icon in header with unread badge
2. Click to open dropdown panel
3. Show recent notifications (last 20)
4. Notification content: icon, title, description, timestamp
5. Mark as read/unread
6. Delete individual notifications
7. "Clear all" button
8. Link to related item (click to navigate)
9. Different notification types with icons:
   - Contact activity (blue)
   - Campaign sent (purple)
   - Email opened (green)
   - Workflow triggered (orange)
   - Sequence completed (yellow)

**Notification Types:**

- Contact replied (show who and excerpt)
- Campaign sent (X emails sent)
- Workflow executed (X contacts entered workflow Y)
- Sequence step failed (contact unenrolled)
- New contact created (show contact name)
- Analytics milestone (1000 contacts reached)

**Notification Preferences:**

1. Settings page for notification control
2. Toggle notification types on/off:
   - Contact activity notifications
   - Campaign metrics
   - Workflow updates
   - Sequence updates
3. Notification delivery method:
   - In-app only
   - Desktop notifications (Electron API)
   - Email digest (daily/weekly)
4. Quiet hours (no notifications between 6pm-9am)

**Implementation:**

- Zustand store for notifications queue
- Toast component for temporary notifications
- Notification center component
- Socket.io events trigger notifications
- Local storage for notification history

**File Structure:**

- /src/components/Notifications/Toast.tsx
- /src/components/Notifications/NotificationCenter.tsx
- /src/components/Notifications/NotificationItem.tsx
- /src/stores/notificationStore.ts
- /src/hooks/useNotification.ts

Provide complete notification system with all components, state management, and preferences handling.

```

### 5.5: Implement Advanced Search & Filtering

```text

Create advanced search and filtering system with:

**Global Search:**

1. Search box in command palette
2. Results grouped by type (Contacts, Campaigns, Sequences, Workflows)
3. Fuzzy matching
4. Recent searches (last 10)
5. Search suggestions based on history

**Contact Filtering:**

1. Filter sidebar (collapsible)
2. Filter sections:
   - Lifecycle Stage (multi-select: Lead, MQL, SQL, Opportunity, Customer, Evangelist)
   - Tags (multi-select with search)
   - Lead Score (range slider, 0-100)
   - Date Created (date range picker)
   - Company (search/select)
   - Last Activity (last 7 days, 30 days, 90 days, custom)
   - Custom properties (dynamic based on schema)

3. Active filters display as removable chips at top
4. Filter count badge ("5 active filters")
5. Save filter as segment (name + save button)
6. Saved segments list with delete/edit options

**Smart Segments (Pre-built):**

1. New contacts (created in last 7 days)
2. Hot leads (high lead score, recent activity)
3. Engaged contacts (opened emails, clicked, replied)
4. Unengaged (no activity in 30 days)
5. Inactive (no activity in 90 days)
6. Pro subscribers (custom property = true)
7. Custom segment builder (AND/OR logic with conditions)

**Saved Segments:**

1. Create custom segments with AND/OR conditions
2. Segment builder UI (add condition, choose operator)
3. Real-time count of matching contacts
4. Use in campaigns and sequences
5. Edit/rename/delete segments
6. Share segments with team members

**Implementation:**

- Filter state in Zustand
- API endpoints for filtered queries
- Segment builder component
- Segment save/load logic
- Real-time count updates

**File Structure:**

- /src/components/Filters/FilterSidebar.tsx
- /src/components/Filters/FilterChips.tsx
- /src/components/Segments/SegmentBuilder.tsx
- /src/components/Segments/SavedSegments.tsx
- /src/hooks/useFilters.ts
- /src/hooks/useSegments.ts

Provide complete filtering and segmentation system with all UI components and business logic.

```

---

## Phase 6: Testing & Optimization

### 6.1: Create Backend API Tests

```text

Set up comprehensive testing for backend APIs using Jest and Supertest with:

**Test Structure:**

- Test file: /src/routes/**tests**/[FEATURE].test.ts
- Setup: Test database, seeded data, JWT tokens
- Cleanup: Clear database after each test
- Organized test suites by feature

**Tests to Include:**

For Authentication:

- Register with valid data (returns 201, user created)
- Register with invalid email (returns 400)
- Register with duplicate email (returns 409)
- Login with correct credentials (returns 200, tokens)
- Login with wrong password (returns 401)
- Token refresh succeeds with valid refresh token
- Logout clears tokens
- Protected routes return 401 without token

For [FEATURE_NAME] API:

- GET /api/[FEATURE] returns 200 with paginated data
- GET /api/[FEATURE] filters work correctly
- GET /api/[FEATURE]/:id returns 200 with correct data
- GET /api/[FEATURE]/:id returns 404 for nonexistent
- POST /api/[FEATURE] with valid data creates resource
- POST /api/[FEATURE] with invalid data returns 400
- PUT /api/[FEATURE]/:id updates resource
- DELETE /api/[FEATURE]/:id soft deletes resource
- Bulk operations work correctly

For Business Logic:

- Workflow execution evaluates conditions correctly
- Email events update campaign analytics
- Sequence enrollment adds contact to correct step
- Automation trigger fires on correct event

**Mocking:**

- Mock external services (email provider, storage)
- Mock database with test data
- Mock JWT tokens

**Coverage:**

- Aim for 80%+ code coverage
- Test happy paths and error cases
- Test edge cases (empty data, max limits, etc.)

Provide:

- Complete test setup with Jest configuration
- Example test file with all test types
- Database seeding for tests
- Test utilities and helpers

```

### 6.2: Create Frontend Component Tests

```text

Set up frontend component testing using React Testing Library with:

**Test Structure:**

- Test file: /src/components/**tests**/[COMPONENT].test.tsx
- Setup: Render component, mock API/store
- Cleanup: After each test
- Organized by component

**Tests to Include:**

For Form Components:

- Form renders with all fields
- Validation shows error on invalid input
- Form submits with valid data
- Submit button disabled until form valid
- Cancel button shows unsaved changes warning

For Data Table:

- Table renders with correct columns and rows
- Sorting works (click column header)
- Pagination works (next/prev buttons)
- Row selection works (checkbox toggle, select all)
- Bulk actions appear when rows selected
- Filtering narrows results

For Modal/Dialog:

- Modal opens and closes correctly
- Backdrop click closes modal
- ESC key closes modal
- Form inside modal submits correctly

For List Components:

- List renders items correctly
- Loading state shows skeleton
- Empty state displays when no data
- New items appear with animation
- Delete removes item from list

**Mocking:**

- Mock API calls using MSW (Mock Service Worker)
- Mock Zustand stores using create mock
- Mock Framer Motion animations

**Accessibility:**

- Test ARIA labels
- Test keyboard navigation
- Test focus management

Provide:

- Jest and React Testing Library configuration
- MSW setup for API mocking
- Example tests for each component type
- Testing utilities and custom render function

```

### 6.3: Create E2E Tests

```text

Set up end-to-end testing using Playwright with:

**Test Structure:**

- Test file: /e2e/[FEATURE].spec.ts
- Setup: Launch app, login
- Cleanup: Logout, close app
- Critical user journeys only

**Test Scenarios:**

Authentication Journey:

- Open app
- Go to login page
- Enter credentials
- Click login
- Verify dashboard loads
- Verify user is logged in

CRM Contacts Journey:

- Navigate to Contacts
- Click "Create contact"
- Fill in contact form (name, email, company)
- Click save
- Verify contact appears in list
- Click on contact
- Edit a property
- Verify change saved
- Delete contact
- Verify removed from list

Campaign Journey:

- Go to Campaigns
- Click "Create campaign"
- Select email template
- Choose recipient list
- Schedule for tomorrow
- Review and send test email
- Verify campaign status changes
- Click on campaign
- Verify analytics show sent count

Automation Journey:

- Go to Automations
- Click "Create workflow"
- Add trigger (contact created)
- Add action (send email)
- Save workflow
- Activate workflow
- Create new contact
- Verify workflow executed

Analytics Journey:

- Go to Analytics
- Verify dashboard metrics display
- Change date range
- Verify charts update
- Click campaign metric
- Verify drill-down works

**Configuration:**

- Playwright config with different browsers (Chrome, Firefox, Safari)
- Test different viewport sizes (desktop, tablet, mobile)
- Screenshots on failure
- Video recording on failure
- Parallel test execution

Provide:

- Playwright configuration
- Example E2E tests for critical journeys
- Test utilities and fixtures
- CI/CD integration setup

```

### 6.4: Performance Optimization

```text

Optimize the application for speed and performance:

**Frontend Optimizations:**

Code Splitting:

- Lazy load routes (React.lazy + Suspense)
- Chunk splitting for large libraries (React Flow, Recharts)
- Dynamic imports for modals and complex components

Component Optimization:

- Wrap expensive components with React.memo
- Use useMemo for expensive calculations
- Use useCallback for event handlers passed to children
- Avoid inline object/function creation in render

List Virtualization:

- Use react-window for large lists (1000+ items)
- Implement for contact table, campaign list
- Reduces DOM nodes and improves scroll performance

Image Optimization:

- Compress images (ImageOptim, TinyPNG)
- Use WebP format with PNG fallback
- Lazy load images (loading="lazy")
- Optimize avatar images specifically

Input Debouncing:

- Debounce search input (300ms delay)
- Debounce filter changes
- Prevent excessive API calls

Bundle Analysis:

- Use webpack-bundle-analyzer
- Identify and remove unused dependencies
- Tree shake unused code

**Backend Optimizations:**

Database Optimization:

- Add indexes on frequently queried fields (email, user_id, created_at)
- Optimize Prisma queries (select specific fields, eager load strategically)
- Implement pagination (default 50 per page)
- Cache analytics queries in Redis (5-minute TTL)

API Performance:

- Compress responses (gzip)
- Implement rate limiting (100 req/min per user)
- Cache static assets
- Use CDN for images and static files

Query Optimization:

- Avoid N+1 queries (use Prisma include strategically)
- Pre-fetch related data in single query
- Use aggregation queries for analytics
- Implement query caching layer

Concurrency:

- Use database transactions for multi-step operations
- Implement optimistic locking for updates
- Queue jobs for long-running operations (email sends, imports)

**Provide:**

- Specific code changes with before/after examples
- Detailed performance improvements (X% faster)
- Database index definitions
- Caching strategy
- Monitoring setup to track improvements

```

### 6.5: Create Complete Testing Setup

```text

Create a comprehensive testing infrastructure including:

**Jest Configuration (/jest.config.js):**

- Coverage thresholds (80%+ for statements, branches, functions, lines)
- Test environment setup (node for backend, jsdom for frontend)
- Module resolution and aliasing
- Transform setup for TypeScript

**Backend Testing Setup:**

- Test database setup (separate test DB)
- Database seeding for tests
- JWT token generation for tests
- API test utilities (authenticated requests, etc.)
- Mock external services

**Frontend Testing Setup:**

- MSW (Mock Service Worker) for API mocking
- Zustand store mocking
- Electron IPC mocking
- React Router test utilities
- Custom render function with providers

**CI/CD Integration:**

- GitHub Actions workflow for running tests
- Parallelize tests across multiple jobs
- Upload coverage reports to Codecov
- Fail if coverage drops below threshold

**Test Scripts (package.json):**

```json
{
  "test": "jest",
  "test:watch": "jest --watch",
  "test:coverage": "jest --coverage",
  "test:backend": "jest --testPathPattern=src",
  "test:frontend": "jest --testPathPattern=components",
  "test:e2e": "playwright test",
  "test:all": "npm run test && npm run test:e2e"
}
```

Provide complete testing setup with all configuration files and example tests.

```

---

## Phase 7: Deployment & Documentation

### 7.1: Build & Package Electron App

```text

Configure Electron Builder and deployment with:

**electron-builder.json Configuration:**

- App identity (name, version, description, author, homepage)
- Build for multiple platforms (Windows NSIS, macOS DMG, Linux AppImage)
- Bundle Node.js backend with app
- Asset directories and exclusions
- Code signing (placeholder for certificates)
- Auto-update configuration

**Build Scripts (package.json):**

```json
{
  "build:backend": "tsc --project tsconfig.backend.json",
  "build:frontend": "vite build",
  "build:electron": "electron-builder",
  "build:all": "npm run build:backend && npm run build:frontend && npm run build:electron",
  "pack": "electron-builder --dir",
  "dist": "electron-builder"
}
```

**Backend Bundling:**

- Compile TypeScript to JavaScript
- Bundle Node.js dependencies
- Minimize bundle size
- Include .env for backend configuration

**Auto-updates:**

- Electron-updater configuration
- Update server setup (GitHub Releases or custom server)
- Check for updates on app launch
- Download and install in background
- Restart app to apply update
- Show update notification with changelog

**Icon & Branding:**

- macOS: .icns format (512x512px minimum)
- Windows: .ico format (256x256px minimum)
- Linux: .png format (512x512px)
- Splash screen (optional)

**Installer Customization:**

- Windows NSIS installer (custom UI, license agreement)
- macOS DMG (drag-and-drop installation)
- Linux installation instructions

**File Signing:**

- macOS code signing certificate
- Windows certificate for installer
- Notarization for macOS (Apple requirement)

Provide complete electron-builder configuration, build scripts, and deployment setup.

```

### 7.2: Create Documentation Suite

```text

Create comprehensive documentation including:

**README.md:**

- Project overview (what it is, why it exists)
- Key features (5 core features with descriptions)
- Screenshots (main interfaces)
- Tech stack (frontend, backend, database, styling)
- Installation instructions:
  1. Prerequisites (Node.js 16+, PostgreSQL, etc.)
  2. Clone repository
  3. Install dependencies (npm install)
  4. Setup environment variables (.env)
  5. Setup database (npm run prisma:generate, npm run prisma:migrate, npm run prisma:seed)
  6. Run development (npm run dev)
  7. Build for production (npm run build:all)
- Project structure overview
- Contributing guidelines
- License

**ARCHITECTURE.md:**

- System architecture diagram
- Tech stack decisions and rationale
- Data flow diagram
- Frontend structure (folders, components, state management)
- Backend structure (routes, services, models)
- Database schema overview
- API structure and endpoints
- Real-time communication (WebSocket)
- Third-party integrations

**API_DOCUMENTATION.md:**

- Authentication flow
- API base URL and headers
- All endpoints organized by feature:
  - Contacts CRUD
  - Campaigns CRUD
  - Sequences CRUD
  - Workflows CRUD
  - Analytics endpoints
- Request/response examples for each endpoint
- Error codes and messages
- Rate limiting information
- Pagination details
- Filtering and sorting options

**USER_GUIDE.md:**

- Getting started (create first contact, send first campaign)
- Feature walkthroughs with screenshots:
  - CRM Contacts (create, edit, view, filter, bulk operations)
  - Email Campaigns (build campaign, schedule, view analytics)
  - Automation Workflows (create workflow, activate, test)
  - Prospection Sequences (create sequence, enroll contacts, track responses)
  - Analytics Dashboard (understand metrics, export data)
- Tips and best practices
- Keyboard shortcuts
- Troubleshooting common issues
- FAQ

**DEVELOPER_GUIDE.md:**

- Development setup (environment, dependencies, database)
- Code organization conventions
- How to add a new feature (step-by-step walkthrough)
- Testing guidelines
- Debugging tips
- Performance considerations
- Deployment process
- Updating the app

Provide all documentation files in Markdown format with proper formatting, examples, and diagrams.

```

### 7.3: Setup CI/CD Pipeline

```text

Create automated deployment pipeline using GitHub Actions:

**Workflow Files (.github/workflows/):**

1. **test.yml** - Run tests on every push:
   - Install dependencies
   - Run backend tests (Jest)
   - Run frontend tests (Jest)
   - Run E2E tests (Playwright)
   - Upload coverage to Codecov
   - Fail if tests don't pass

2. **build.yml** - Build app on every push:
   - Build backend (TypeScript compile)
   - Build frontend (Vite)
   - Build Electron for all platforms
   - Upload artifacts

3. **release.yml** - Deploy on tag push (v1.0.0):
   - Build for all platforms (Windows, macOS, Linux)
   - Sign code (macOS, Windows)
   - Create GitHub release
   - Upload build artifacts
   - Publish to update server
   - Send release notification

**Environment Variables:**

- Database URL (for testing)
- API keys (email service, etc.)
- Code signing certificates
- GitHub token (for releases)

**Deployment Environments:**

- Staging (test version, manual trigger)
- Production (released version, automatic on tag)

**Notifications:**

- Slack notifications on build success/failure
- GitHub release notes auto-generated from commits

Provide complete GitHub Actions workflow files with all setup.

```

---

## Phase 8: Community & Launch

### 8.1: Create Video Tutorial Scripts

```text

Write comprehensive tutorial video scripts for:

**Video 1: "Building a HubSpot Clone with AI (Complete Walkthrough)"**

- Duration: 15 minutes
- Hook, problem statement, overview of what you'll build
- Show final product in action
- Break down technical architecture (high level)
- Live coding/demo of key features
- Results and key learnings
- Call-to-action (download code, join community)

**Video 2: "How to Use AI to Build Complex SaaS Features"**

- Duration: 20 minutes
- Demonstrate the prompt engineering workflow
- Show how to break down a complex feature
- Example: Build automation workflow engine
- Show AI-generated code working
- Explain how to refine and iterate on AI outputs
- Key takeaways about AI-assisted development

**Video 3: "Designing Enterprise UX with Minimalist Principles"**

- Duration: 12 minutes
- Show before/after UI design
- Explain Linear's design philosophy
- Walk through dark mode implementation
- Demonstrate animations and interactions
- Tools and libraries used
- Design system creation process

For each script, provide:

- Exact narration to read
- On-screen overlays and text
- Code snippets to show
- Visual assets needed
- Timeline markers
- Suggested background music

```

### 8.2: Create Launch Announcement Template

```text

Create a launch announcement post for social media and communities:

**LinkedIn Post:**

- Hook that resonates with audience (problem statement)
- Challenge you undertook (building HubSpot clone)
- What you built (5 features, tech stack)
- Key accomplishments (production-ready, time invested)
- Learning outcome (what you learned about SaaS, AI, design)
- Offer (open source code, join community, tutorial series)
- Call-to-action (download, watch demo, join Discord)
- 200-300 words, professional tone

**Twitter/X Thread:**

- Tweet 1: Hook and announcement
- Tweet 2: What you built (features)
- Tweet 3: Tech stack and architecture
- Tweet 4: Design and UX approach
- Tweet 5: Key learning (AI-assisted development)
- Tweet 6: Offer (code + tutorials + community)
- Tweet 7: Call-to-action (link to GitHub)

**Dev.to Article:**

- Detailed writeup (1500-2000 words)
- Introduction (problem you solved)
- What you built (comprehensive feature overview with screenshots)
- Technical approach (architecture, tech choices, why)
- Design system (Linear-inspired, dark mode, animations)
- Key insights (challenges faced, how AI helped, what worked/didn't)
- Open sourcing decision
- Next steps (tutorials, community, improvements)
- Links (GitHub, Discord, YouTube)

**Product Hunt Launch:**

- Tagline (one sentence hook)
- Description (2-3 paragraph overview)
- Thumbnail/GIF showing app in action
- Gallery of screenshots (each feature)
- How it's made (tech stack)
- Discussion prompt (Ask users: What feature would you add next?)

Provide templates for each platform with fill-in sections and example text.

```

---

## Troubleshooting & Refinement

### T.1: When AI Output Doesn't Work

**Situation:** AI generated code that has syntax errors or doesn't integrate properly

**Prompt to Use:**

```text

The code you generated for [COMPONENT/FEATURE] has an issue:

[DESCRIBE THE ERROR: error message, unexpected behavior, etc.]

Here's what I tried:
[SHOW THE CODE OR THE CONTEXT]

The error occurs when:
[DESCRIBE THE SCENARIO THAT TRIGGERS THE ERROR]

Can you fix this by:

1. [Identifying the root cause]
2. [Explaining why the error happens]
3. [Providing corrected code with the fix]
4. [Testing approach to verify it works]

Please provide the complete corrected file(s) with all imports and exports.

```

### T.2: When You Don't Understand the Generated Code

**Situation:** AI generated code that works but you don't understand how

**Prompt to Use:**

```text

I'm not sure I understand this code you generated:

[PASTE THE CODE SECTION]

Can you explain:

1. What each part does (line by line)
2. Why this approach was chosen (vs. alternatives)
3. Key concepts I should understand (specific patterns, libraries, techniques)
4. How this integrates with the rest of the app
5. What I should watch out for when modifying this

Use analogies or simple examples if helpful. Assume I'm new to this pattern.

```

### T.3: When You Need to Modify Existing Code

**Situation:** You have working code but need to add a new feature or change behavior

**Prompt to Use:**

```text

I have this existing code that [DESCRIBE WHAT IT DOES]:

[PASTE THE CURRENT CODE]

I need to modify it to [DESCRIBE THE NEW REQUIREMENT]:
[SPECIFIC DETAILS ABOUT WHAT SHOULD CHANGE]

Please:

1. Explain what changes are needed
2. Show the minimal code changes required
3. Point out any potential side effects
4. Provide the complete updated code
5. Suggest any refactoring that would make it cleaner

Keep the existing structure and patterns - just add/modify what's necessary.

```

### T.4: When Performance Is Slow

**Situation:** Feature runs slow or app feels sluggish

**Prompt to Use:**

```text

The [COMPONENT/FEATURE] is running slowly. Here's what I notice:

[DESCRIBE THE SYMPTOM: "Contact list takes 5 seconds to load", etc.]

Current implementation:
[PASTE THE RELEVANT CODE]

Can you:

1. Identify the performance bottleneck
2. Suggest 3 optimization strategies (ranked by impact)
3. Implement the best approach with complete code
4. Explain the performance improvement (X% faster)
5. Provide testing code to measure improvements

Context: The app loads [NUMBER] contacts/records at once. React is [RENDERING APPROACH]. Database queries [DESCRIBE CURRENT QUERIES].

```

### T.5: When Features Don't Integrate

**Situation:** Two features don't communicate properly or share state incorrectly

**Prompt to Use:**

```text

I have two features that need to communicate:

**Feature A: [FEATURE_NAME]**
[DESCRIBE CURRENT CODE/IMPLEMENTATION]

**Feature B: [FEATURE_NAME]**
[DESCRIBE CURRENT CODE/IMPLEMENTATION]

**The Problem:**
[DESCRIBE WHAT ISN'T WORKING: state not syncing, events not firing, wrong data passed, etc.]

**What Should Happen:**
[DESCRIBE THE DESIRED BEHAVIOR]

Can you:

1. Identify the integration issue
2. Explain why they're not currently communicating
3. Redesign the integration approach
4. Provide updated code for both features showing how to connect them
5. Suggest a testing strategy to verify the integration works

Use our Zustand stores and Socket.io for real-time updates if applicable.

```

---

## Advanced Prompt Techniques

### Technique 1: Iterative Refinement

**Process:**

1. Start with a rough prompt describing what you want
2. AI generates initial code
3. Provide specific feedback on what needs to change
4. AI refines the code based on feedback
5. Repeat until satisfied

**Example:**

```text

First prompt: "Create a contact form component"
Feedback: "The form doesn't validate email. Add email validation and show error below the field."
AI refines: Adds email validation
Feedback: "The validation happens on submit. Make it happen as the user types (with debouncing)."
AI refines: Adds onChange handler with debouncing
Feedback: "The error color needs to match our design system (#EF4444). Also add a success state."
AI refines: Adds correct colors and success state

```

### Technique 2: Reference Existing Code

When asking for modifications or new features similar to existing ones:

```text

I have a working [FEATURE] component here:

[PASTE THE EXISTING CODE]

Can you create a similar [NEW_FEATURE] component that:

1. Follows the same patterns and structure
2. Uses the same styling approach
3. Integrates with Zustand store in the same way
4. [DESCRIBE NEW REQUIREMENTS SPECIFIC TO THIS FEATURE]

Keep it consistent with the existing code style.

```

### Technique 3: Ask for Alternatives

When you want to see different approaches:

```text

For [FEATURE/COMPONENT], generate 2 different implementation approaches:

**Approach A:** [DESCRIBE ONE WAY]
**Approach B:** [DESCRIBE ANOTHER WAY]

For each approach, provide:

1. Complete implementation
2. Pros and cons
3. Performance implications
4. Maintenance considerations
5. My recommendation and why

I'll choose based on your recommendation.

```

### Technique 4: Test-Driven Prompting

Ask AI to create tests before implementation:

```text

Create tests for [FEATURE] that verify:

1. [BEHAVIOR 1]
2. [BEHAVIOR 2]
3. [BEHAVIOR 3]

Then, implement the feature to pass these tests.

Provide:

1. Complete test file with multiple test cases
2. Implementation code that makes tests pass
3. Explanation of test-driven approach used

```

### Technique 5: Documentation-First Prompting

Ask AI to document before building:

```text

Create detailed documentation for [FEATURE] including:

1. API specification (endpoints, request/response)
2. Data models (properties, relationships)
3. User workflows (step-by-step user interactions)
4. Component structure (component tree, props)
5. State management approach

Then implement the feature based on this documentation.

```

---

## Checklist Before Submitting Prompts

Use this checklist to ensure high-quality prompts:

- ✅ **Clear Context** - AI understands what you're building and why
- ✅ **Specific Requirements** - Exactly what should be included
- ✅ **Tech Stack Reference** - Mentions relevant frameworks/libraries
- ✅ **Output Format** - Specifies complete code, file structure, comments
- ✅ **Design Constraints** - If applicable, mentions styling/theme
- ✅ **Error Handling** - Asks for proper error handling
- ✅ **TypeScript** - If applicable, asks for full type coverage
- ✅ **File Structure** - Specifies where code should go
- ✅ **Comments** - Asks for comments explaining complex logic
- ✅ **Integration Points** - Mentions how it connects to other features
- ✅ **Testing** - Optionally asks for test-ability
- ✅ **Performance** - Mentions if performance is critical
- ✅ **Accessibility** - If UI component, asks for a11y features

---

## Sample Complete Workflow

Here's how you'd use multiple prompts together for a real feature:

**Example: Building the Contact Import Feature**

1. **Start with meta-prompt** (establish context)
2. **Use 2.4 prompt** (design the database schema for import tracking)
3. **Use Phase 2 prompt** (build CSV import backend endpoint)
4. **Use T.2 prompt** (understand the generated code)
5. **Use 5.2 prompt** (build the import UI component)
6. **Use T.5 prompt** (integrate backend with frontend)
7. **Use 6.1 prompt** (write tests for the feature)
8. **Use 6.4 prompt** (optimize if performance issues)
9. **Document the feature** (update API_DOCUMENTATION.md)

This workflow ensures complete, tested, integrated features.

---

## Key Principles for Prompt Success

1. **Be Specific** - Vague prompts get vague results
2. **Provide Context** - More context = better outputs
3. **Ask for Complete Code** - Not snippets or pseudocode
4. **Iterate Ruthlessly** - First output rarely perfect
5. **Reference Similar Code** - Helps AI maintain consistency
6. **Test Immediately** - Verify AI outputs work before moving on
7. **Document as You Go** - Don't leave this for the end
8. **Save Successful Prompts** - Build your own prompt library
9. **Combine Prompts** - Use multiple prompts for complex features
10. **Always Understand** - Never paste AI code without understanding it

---

## Phase 0: ADVANCED - Reverse-Engineering HubSpot & Competitors

### A.1: Complete HubSpot Feature Reverse-Engineering

```

Conduct an exhaustive reverse-engineering analysis of HubSpot's platform focusing on these 5 core features.

For EACH feature below, provide a detailed specification document:

**FEATURE 1: CRM CONTACTS MODULE**

CRM Interface Analysis:

- Document the exact layout of the contacts page (left sidebar filters, main data area, right details panel)
- List all visible data fields in the table view (Name, Email, Company, Phone, Lifecycle Stage, Lead Score, Last Activity, etc.)
- Document the detail/record view layout when clicking a contact
- Analyze the sidebar on contact detail (properties section, activity timeline, related deals, etc.)
- Document all filter options (how many filters, filter types, multi-select capabilities)
- Analyze search functionality (does it search names/emails/companies? Real-time results?)

Contact Properties & Data Model:

- List all default contact properties (first_name, last_name, email, phone, company, etc.)
- Document custom fields capability (how to add, field types available, JSON structure)
- Analyze property types (text, email, phone, select, date, number, textarea, multi-select)
- Document lifecycle stages options (Subscriber, Lead, Marketing Qualified Lead, Sales Qualified Lead, Opportunity, Customer, Evangelist)
- Analyze lead scoring (what factors affect it, default ranges, custom scoring)
- Document tagging system (how tags work, tag colors, bulk tagging)
- Analyze list functionality (static lists vs. dynamic segments)

Contact Activities & Timeline:

- Analyze the activity timeline (types of activities: notes, emails, calls, meetings, tasks)
- Document activity creation (modal/inline form, required fields)
- Analyze email activity (shows subject, date, recipient, open/click status)
- Document call logging (duration, direction, notes)
- Analyze meeting creation and management
- Document task creation and assignment

Contact Interactions & Actions:

- List all buttons/actions on contact record (Send email, Create task, Schedule call, Enroll in workflow, etc.)
- Analyze quick actions (what can you do without leaving the contact view?)
- Document bulk operations (select multiple → actions available)
- Analyze contact import/export functionality

User Flows:

- Document the "Create Contact" flow (modal? inline form? required fields? validation?)
- Analyze the "Edit Contact" workflow (inline edit vs. modal vs. drawer?)
- Document "Delete Contact" (soft delete? confirmation? undo?)
- Analyze "Search & Filter" contacts workflow
- Document "View Contact Activity Timeline" (how is it accessed? what info shown?)
- Analyze "Enroll Contact in Workflow" (is there a modal? does workflow list show?)

**FEATURE 2: EMAIL CAMPAIGNS**

Campaign Interface Analysis:

- Document the campaigns list view (card view? table? metrics shown per campaign?)
- Analyze campaign status indicators (Draft, Scheduled, Sending, Sent, Paused)
- Document the campaign creation flow (is it multi-step wizard? linear or branching?)
- Analyze the campaign editing interface

Campaign Builder Steps (if multi-step):

- Step 1 analysis (template selection, template preview, template categories)
- Step 2 analysis (email editor interface, toolbar, preview mode)
- Step 3 analysis (recipient selection, list vs. segment, exclusion lists)
- Step 4 analysis (scheduling interface, timezone handling, recurring options)
- Step 5 analysis (review screen, test send option)

Email Editor:

- Document the rich text editor (toolbar buttons: bold, italic, underline, headings, etc.)
- Analyze the template system (pre-built templates, custom templates, template variables)
- Document personalization tokens (how are they inserted? what tokens available?)
- Analyze the preview functionality (mobile vs. desktop views)
- Document A/B testing setup (what can be tested? how to configure variants?)
- Analyze scheduling options (send now, schedule for specific time, recurring sends)

Campaign Analytics:

- List all metrics displayed (Sent, Delivered, Open Rate %, Click Rate %, Unsubscribe Rate %)
- Document the analytics timeline (how far back can you view? date selection?)
- Analyze charts (line chart for opens/clicks over time? engagement rate graphs?)
- Document click tracking (heatmap on email showing which links clicked?)
- Analyze recipient list (can you see who opened? who clicked? who unsubscribed?)
- Document export functionality (export analytics as CSV?)

**FEATURE 3: ANALYTICS DASHBOARD**

Dashboard Layout:

- Document the main dashboard sections (top metrics cards, middle charts, bottom reports)
- Analyze the date range selector (preset ranges available: 7d, 30d, 90d, 1y, custom?)
- List all metric cards visible (Total Contacts, Active Deals, Meetings Booked, etc.)
- Analyze the comparison functionality (period-over-period comparison available?)

Dashboard Metrics & KPIs:

- Document contact metrics (total contacts, new contacts this period, growth %)
- Analyze deal/opportunity metrics (total deals, deal value, deals won)
- Document email metrics (emails sent, open rate, click rate, reply rate)
- Analyze call metrics (calls logged, call duration, notes recorded)
- Document meeting metrics (meetings scheduled, meetings completed)
- Analyze engagement metrics (contacts with activity, interactions this period)

Dashboard Charts:

- List chart types used (line chart, bar chart, funnel, pie chart, etc.)
- Document the "Contacts Over Time" chart (when does it show new contacts? daily/weekly/monthly?)
- Analyze "Lifecycle Stage Distribution" (pie chart breakdown? funnel?)
- Document "Email Performance" chart (campaigns compared? performance trends?)
- Analyze "Deal Pipeline" chart (funnel showing deal progression?)
- Document any custom chart functionality

Dashboard Interactions:

- Analyze chart click behavior (click on data point → drill down detail?)
- Document filter behavior (change date range → all charts update?)
- Analyze export options (export individual charts? export full dashboard report?)
- Document real-time update behavior (do metrics update in real-time? how frequently?)
- Analyze tab navigation (different dashboard views/tabs available?)

**FEATURE 4: AUTOMATION BUILDER (Workflows)**

Workflow Builder Interface:

- Document the visual builder canvas (node-based? flow-chart style?)
- Analyze node types (Trigger, Condition, Action, Delay nodes visible?)
- Document the sidebar (workflow list? node picker? templates?)
- Analyze the toolbar (save, activate, test, duplicate, delete buttons?)

Workflow Components:

- Document trigger types (Contact Created, Email Opened, Form Submitted, Contact Property Changed, etc.)
- Analyze condition nodes (if/then logic? how are conditions configured?)
- Document action types available (Send Email, Create Task, Update Property, Add to List, etc.)
- Analyze delay nodes (wait X days? wait until specific date? wait for action?)
- Document branch/conditional routing (can flow split based on conditions?)

Workflow Configuration:

- Analyze trigger setup (click trigger node → what configuration panel shows?)
- Document condition builder (how to set up if/then conditions? operators available: equals, contains, greater than, etc.)
- Analyze action configuration (send email → select template from dropdown?)
- Document delay configuration (wait 2 days? business days? until specific time?)

Workflow Management:

- Document workflow list view (active/inactive toggle? creation date? enrollment count?)
- Analyze workflow templates (pre-built workflows available? template categories?)
- Document activation (how to activate/deactivate workflow? confirmation needed?)
- Analyze testing functionality (can you test workflow with sample contact?)
- Document workflow history/logs (can you see enrollments? execution status? which step stuck?)

**FEATURE 5: PROSPECTION / SEQUENCES**

Sequence Interface:

- Document the sequences list view (table or card view? metrics per sequence?)
- Analyze sequence creation flow (modal? multi-step? linear wizard?)
- Document sequence editing (how to edit steps? can you edit while active?)

Sequence Configuration:

- Analyze sequence steps (email step? task step? delay? what types available?)
- Document step ordering (can you reorder steps? add step anywhere or just at end?)
- Analyze email step config (select template? personalization preview?)
- Document task step config (task type: call, LinkedIn, email, custom? description field?)
- Analyze delay between steps (days to wait? business days? specific time?)

Enrollment & Execution:

- Document enrollment methods (manual select contacts? bulk upload? automatic based on criteria?)
- Analyze enrollment criteria (who auto-enrolls? is it based on lead score? company? custom properties?)
- Document the sequence timeline per contact (which step are they on? when will next step send?)
- Analyze unenrollment (what triggers unenrollment? reply detection? manual unenrollment option?)

Sequence Analytics:

- List metrics tracked (enrolled count, active count, completed count, response rate %)
- Analyze funnel visualization (shows contacts at each step? drop-off at each step?)
- Document response tracking (how does it detect replies? marks them?)
- Analyze meeting bookings (tracks meetings booked from sequence?)
- Document step performance (which step has highest response rate?)
- Analyze export functionality

**DESIGN PATTERNS OBSERVED:**

Visual Hierarchy:

- How does HubSpot establish visual hierarchy? (size, color, positioning?)
- What's the color scheme? (primary color, accent colors, semantic colors?)
- Typography choices (font family, font sizes, font weights for different elements)
- Spacing patterns (how much padding/margin between elements?)

Interactions:

- Hover states (what changes when you hover over buttons, rows, cards?)
- Click feedback (what happens immediately after click? loading state?)
- Loading states (skeleton screens? spinners? progress indicators?)
- Empty states (how does app look with no data? helpful text?)
- Error states (how are errors displayed? inline? toasts? modals?)

Navigation Patterns:

- Sidebar navigation (collapsible? icons + text? active state?)
- Top navigation (search bar? user menu? notifications?)
- Breadcrumbs (where used? how styled?)
- Tabs (where used? how selected tab indicated?)

Data Display:

- Table layouts (header styling? row hover? alternating row colors?)
- Pagination (how many per page? pagination controls where?)
- Modals (where used? size? backdrop blur?)
- Drawers/Sidepanels (when used instead of modals?)
- Popovers/tooltips (used for additional info? activation method?)

**OUTPUT FORMAT:**

For each feature, provide a detailed specification document (1500+ words) with:

1. Exact UI layout descriptions
2. Data models and properties
3. Complete user workflows (step-by-step)
4. All interaction points
5. Visual design patterns
6. Color/typography schemes observed
7. Animation/transition behaviors
8. Error handling patterns
9. Responsive behavior
10. ASCII or text-based wireframes showing layout

Format as a technical specification that a developer could use to build the feature from scratch.

```

### A.2: Competitive Analysis - Similar CRM Platforms

```

Compare HubSpot's design and functionality with these competitors:

**PLATFORMS TO ANALYZE:**

1. Salesforce (Sales Cloud)
2. Pipedrive
3. Zoho CRM
4. ActiveCampaign
5. Intercom
6. Close.com
7. Copper (formerly ProsperWorks)
8. Freshsales

**FOR EACH PLATFORM, DOCUMENT:**

1. **Core CRM Module:**
   - Contact record layout (what fields shown by default?)
   - List/table view (columns, filters, search)
   - Activity timeline (how activities tracked?)
   - Custom fields system (how flexible?)

2. **Unique Features:**
   - What does THIS platform do better than HubSpot?
   - What features are unique to this platform?
   - How is the UX different? (simpler? more complex? more intuitive?)

3. **Visual Design:**
   - Color palette (primary, accent, semantic colors)
   - Typography and spacing
   - Component styling (buttons, inputs, tables, modals)
   - Dark mode available? How implemented?

4. **UI/UX Patterns:**
   - Navigation approach (sidebar? top nav? both?)
   - How data-heavy features presented (dashboards, reports, tables)
   - Animation philosophy (lots of animation? minimal? smooth transitions?)
   - Responsiveness (desktop-first? mobile-friendly?)

5. **Feature Implementation Differences:**
   - Email campaigns (compared to HubSpot's approach)
   - Automation workflows (visual builder? JSON-based? templates?)
   - Analytics (real-time? what metrics prioritized?)
   - Prospection/sequences (how similar/different from HubSpot?)

**OUTPUT:**

Create a competitive analysis matrix showing:

1. Feature comparison (which platforms have which features)
2. UI/UX approach comparison (layout, navigation, interaction patterns)
3. Design philosophy differences (minimalist vs. feature-rich, etc.)
4. Best practices from each platform (what we should adopt)
5. Gaps/opportunities (what no one does well that we could do)
6. Design system recommendations based on competitive analysis

Highlight what makes each platform unique and what we can learn for our clone.

```

### A.3: Design System Deep Dive

```

Based on the reverse-engineering of HubSpot and competitors, create a comprehensive design system specification.

**COLOR SYSTEM:**

1. Primary Colors (used for main CTAs, active states)
   - HubSpot's primary color (what is it? hex code?)
   - Competitors' primary colors (are they similar?)
   - Our choice for the clone (justify selection)

2. Neutral Colors (grays for backgrounds, borders, text)
   - Document the full gray scale (10+ shades from almost black to almost white)
   - Dark mode grays (backgrounds that don't burn the eyes)
   - Light mode grays (optional, but document if supporting it)

3. Semantic Colors (success, error, warning, info)
   - Success color (green shade used across platforms)
   - Error color (red shade for errors)
   - Warning color (yellow/orange for warnings)
   - Info color (blue for informational messages)

4. Interactive States (how colors change)
   - Default state color
   - Hover state (usually darker/lighter?)
   - Active state (what indicates something is selected?)
   - Disabled state (usually grayed out?)
   - Focus state (for accessibility, how is focus indicated?)

**TYPOGRAPHY SYSTEM:**

1. Font Family Selection
   - Which font(s) does HubSpot use? (check inspection)
   - System font stack recommended for performance
   - Fallback fonts

2. Font Sizes & Scale
   - Document the type scale (body: 14px, 16px, or 18px base?)
   - Heading sizes (H1, H2, H3, H4, how large each?)
   - Small text size (captions, labels, helpers)
   - Create a ratios/formula for scaling (1.25 ratio? 1.5 ratio?)

3. Font Weights
   - Regular (body text)
   - Medium (labels, strong emphasis)
   - Semibold (subheadings)
   - Bold (main headings)
   - Which weights should be used where?

4. Line Heights & Letter Spacing
   - Line height for body text (1.5? 1.6?)
   - Line height for headings (1.2? 1.3?)
   - Letter spacing (any applications? usually 0 for most text)

**SPACING SYSTEM:**

1. Base Unit Selection
   - HubSpot seems to use 4px, 8px, or 16px base unit?
   - Define the spacing scale (0, 4, 8, 12, 16, 24, 32, 48, 64, etc.)

2. Padding (internal space)
   - Button padding (small, medium, large)
   - Card padding (consistent across all cards?)
   - Input field padding
   - Modal/drawer padding

3. Margins (external space)
   - Between sections
   - Between cards in a grid
   - Heading to content spacing

4. Gap/Gutter (between flex/grid items)
   - Column spacing in grids
   - Row spacing in tables
   - Item spacing in lists

**COMPONENT LIBRARY:**

Based on HubSpot's component patterns, document each:

1. **Buttons:**
   - Primary button (main CTA, what color?)
   - Secondary button (alternative action)
   - Ghost/tertiary button (lowest priority)
   - Danger button (destructive actions)
   - Size variants (small, medium, large)
   - States (default, hover, active, disabled, loading)
   - Icons in buttons (left-aligned? right-aligned?)
   - Text + icon combinations

2. **Input Fields:**
   - Text input (border style? thickness? color on focus?)
   - Email input (same as text? or different?)
   - Password input (with show/hide toggle?)
   - Textarea (how different from text input?)
   - Number input (with +/- buttons? or just spinner?)
   - Date input (native? custom picker?)
   - Select/Dropdown (open state? scroll behavior for long lists?)
   - Multi-select (tags? checkboxes? how to remove selected items?)
   - Label placement (above? inline?)
   - Help text placement (below? tooltip?)
   - Error text styling (red color? error icon?)
   - Required field indicator (asterisk? red dot?)
   - Disabled state styling
   - Focus/active state styling

3. **Form Elements:**
   - Checkbox (style? how does it look when checked?)
   - Radio button (style? grouped?)
   - Toggle switch (how does it animate? on/off colors?)
   - Slider/range input (track color? handle color? range limits?)

4. **Tables:**
   - Header styling (background color? text weight? sort indicators?)
   - Row styling (hover state? alternating row colors?)
   - Cell padding and alignment (left/center/right?)
   - Borders (between rows? between columns? subtle or visible?)
   - Sortable columns (how indicated? click behavior?)
   - Selectable rows (checkbox column? how many can select?)
   - Pagination controls (where placed? style?)
   - Empty state (what shows when no data?)
   - Loading state (skeleton rows? spinner?)

5. **Cards:**
   - Border (shadow? border line? combination?)
   - Padding/spacing inside card
   - Hover state (lift? shadow change? color change?)
   - Card title styling
   - Card content area
   - Card actions (buttons at bottom? action menu on hover?)

6. **Modals/Dialogs:**
   - Backdrop styling (blur? dark overlay? opacity?)
   - Modal positioning (centered? how much padding from screen edges?)
   - Header styling (title, close button placement)
   - Body content area (scrollable?)
   - Footer with action buttons
   - Size variants (small, medium, large)
   - Animation (how does it appear/disappear?)

7. **Alerts/Notifications:**
   - Alert banner (top of page? inline?)
   - Types (success, error, warning, info)
   - Icon (used? which icon per type?)
   - Close button (available? always?)
   - Styling (background color? text color? border?)
   - Toast notification (small, temporary popup)
   - Notification center bell (icon style? badge number?)

8. **Navigation:**
   - Sidebar styling (background color? text color? icons?)
   - Navigation item (padding? hover state? active state indicator?)
   - Collapsed sidebar (icon-only? animation speed?)
   - Top navigation bar (logo, search, user menu positioning)
   - Breadcrumb styling (separators? text styling?)
   - Tabs (how selected tab indicated? underline? background? border?)

9. **Data Visualization:**
   - Chart colors (are they branded colors? accessible?)
   - Chart legends (placement? font size?)
   - Chart tooltips (formatting? colors?)
   - Grid lines (visible? subtle? none?)
   - Axis labels (font size? color?)

**ANIMATION & MOTION:**

1. Page Transitions
   - How do pages appear when navigating? (fade? slide? instant?)
   - Duration (200ms? 300ms? 500ms?)
   - Easing function (cubic-bezier? ease-in-out?)

2. Interaction Animations
   - Button hover (scale? color change? both?)
   - Dropdown open (slide down? fade? pop up?)
   - Modal open (slide from right? fade in? scale from center?)
   - Form field focus (border animation? background animation?)
   - List item insertion (slide in? fade in? stagger multiple items?)

3. Loading & Progress
   - Loading spinner (style? color? rotation speed?)
   - Progress bar (height? color? animation for progress change?)
   - Skeleton screen (pulse animation? gradient animation?)

4. Feedback Animations
   - Success checkmark (appears? animation style?)
   - Error state (shake? color change? both?)
   - Delete animation (fade out? slide away?)

**DESIGN TOKENS (for implementation):**
Create CSS/Tailwind custom properties for:

- Colors (--color-primary, --color-error, etc.)
- Typography (--font-size-lg, --line-height-normal, etc.)
- Spacing (--space-sm, --space-md, --space-lg, etc.)
- Transitions (--duration-fast, --easing-smooth, etc.)
- Shadows (--shadow-sm, --shadow-lg, etc.)
- Border radius (--radius-sm, --radius-md, --radius-lg, etc.)

**PROVIDE:**

1. Color palette (hex codes)
2. Typography specification (fonts, sizes, weights)
3. Spacing scale (base unit and all sizes)
4. Complete component specifications (appearance, states, behavior)
5. Animation specifications (durations, easing, triggers)
6. Design tokens for implementation
7. Accessibility considerations for each component

```

---

## BONUS: Using Stitch Design Integration with Claude API

### B.1: Import Figma/Design into Claude Implementation

```

I have a complete design system created in Stitch (or Figma) that I want to provide to Claude API for implementation.

**MY DESIGN ASSETS:**
[DESCRIBE WHAT YOU HAVE]:

- Figma file with components (link: [FIGMA_LINK])
- Design tokens exported as JSON (attach or paste the JSON)
- Component screenshots (you can upload images)
- Design system documentation (paste or link)
- Color palette documentation
- Typography specifications
- Spacing/grid system rules
- Animation guidelines

**IMPLEMENTATION REQUEST:**

Using my design system, create the [FEATURE_NAME] component/page with:

1. **Design Adherence:**
   - Use exact colors from my design system
   - Match typography specifications (font family, sizes, weights)
   - Follow spacing/padding rules from design
   - Implement animations/transitions specified in design
   - Match component states shown in design (hover, active, disabled, error, etc.)

2. **Technical Implementation:**
   - Use React + TypeScript
   - Use Tailwind CSS with custom theme configuration matching design tokens
   - Use Framer Motion for animations (with exact timings from design)
   - Extract colors/spacing/fonts as CSS variables for reusability

3. **Deliverables:**
   - React component file(s) with full implementation
   - Tailwind theme configuration matching design tokens
   - Framer Motion animation configurations
   - Component exports and TypeScript types
   - Storybook stories (optional) showcasing all component states

**SPECIFIC REQUIREMENTS:**

- Primary color from design: [HEX]
- Secondary color: [HEX]
- Base font family: [FONT_NAME]
- Base font size: [SIZE]px
- Base spacing unit: [NUMBER]px
- Animation duration standard: [NUMBER]ms
- Border radius standard: [NUMBER]px
- [ADD ANY OTHER KEY DESIGN SPECS]

Please implement this component/page to exactly match my design system. If my design system is missing specification for something, use best practices from [DESIGN_PHILOSOPHY] (e.g., Linear's minimalism).

Provide complete, production-ready code with all styling, animations, and interactions implemented.

```

### B.2: Design System to Tailwind Config

```

I've created a design system with specific colors, typography, spacing, and animations.

**MY DESIGN SYSTEM SPECS:**

Colors:
[PASTE YOUR COLOR PALETTE - Either as JSON, CSS variables, or list]

Typography:

- Font family: [FONT_NAME]
- Body text size: [SIZE]px
- Heading 1: [SIZE]px, weight [WEIGHT]
- Heading 2: [SIZE]px, weight [WEIGHT]
- Heading 3: [SIZE]px, weight [WEIGHT]
- Small text: [SIZE]px
- Line height: [NUMBER]
- Letter spacing: [NUMBER]

Spacing:

- Base unit: [NUMBER]px
- Full spacing scale: [PROVIDE SCALE]

Border Radius:

- Small: [NUMBER]px
- Medium: [NUMBER]px
- Large: [NUMBER]px

Shadows:
[PROVIDE SHADOW DEFINITIONS]

Animations:

- Standard duration: [NUMBER]ms
- Easing function: [CUBIC_BEZIER or PRESET]

**REQUEST:**

Create a complete Tailwind CSS theme configuration (tailwind.config.js) that:

1. Maps all my colors to Tailwind color utilities
2. Configures typography to match my specifications
3. Sets up spacing scale
4. Configures border radius
5. Defines custom shadows
6. Sets up animation/transition configurations
7. Includes dark mode support (if applicable)

Also provide:

1. CSS variables file (/src/config/theme.css or similar) for fallback
2. Framer Motion animation variants config matching my animation specs
3. Example components showing how to use the theme
4. Guidelines for developers on using the design system

The resulting Tailwind config should be the single source of truth for all design decisions, so developers just use utility classes without thinking about colors/spacing/etc.

```

### B.3: Screenshot-to-Code with Design Context

```

I have screenshots of my designed UI from Stitch, and I want to implement them with my design system.

**SCREENSHOTS:**
[UPLOAD OR LINK TO SCREENSHOTS OF YOUR DESIGN]

**DESIGN SYSTEM CONTEXT:**

- Design system documentation (paste or link)
- Design tokens (colors, typography, spacing, animations)
- Component library specifications
- [Any other design context]

**IMPLEMENTATION REQUEST:**

Analyze my screenshot and create a React component that:

1. **Matches the Visual Design:**
   - Exact layout and component positioning
   - All colors from my design system
   - Typography matching my design specs
   - Spacing/padding from design
   - All visual elements shown in screenshot

2. **Implements All Interactive States:**
   - Hover states (if visible in design)
   - Active/selected states
   - Disabled states
   - Loading states
   - Error states
   - Empty states

3. **Adds Interactivity:**
   - Click handlers for buttons/links
   - Form submission for forms
   - Modal open/close if modals shown
   - Dropdown menus expand/collapse
   - Animations on user interaction (smooth transitions, etc.)

4. **Technical Requirements:**
   - React + TypeScript with full types
   - Tailwind CSS using my design system tokens
   - Framer Motion for all animations
   - Responsive design (mobile, tablet, desktop)
   - Accessibility (ARIA labels, semantic HTML, keyboard navigation)

5. **File Organization:**
   - Component file(s) organized logically
   - Separate hooks if needed (useForm, useDropdown, etc.)
   - Types file with interfaces
   - Constants file if there's hardcoded data

Provide complete, production-ready code that can be immediately integrated into the app. Include comments explaining complex sections.

```

### B.4: Batch Design-to-Code Implementation

```

I have a complete design system with multiple screens/components designed in Stitch.

**DESIGN DELIVERABLES:**

- Figma file (link: [LINK])
- Design system documentation
- Design tokens (colors, typography, spacing, animations)
- Screenshots of all screens/components
- Component specification document
- [Any other design artifacts]

**IMPLEMENTATION SCOPE:**

Create React components for these screens/features:

1. [FEATURE 1] - [BRIEF DESCRIPTION]
2. [FEATURE 2] - [BRIEF DESCRIPTION]
3. [FEATURE 3] - [BRIEF DESCRIPTION]
etc.

**PROJECT STRUCTURE:**
Create the following file organization:

```

/src
  /components
    /[FEATURE1]
      /[Component1].tsx
      /[Component2].tsx
      /[Component1].module.css (if needed)
    /[FEATURE2]
      ...
  /types
    /[FEATURE1].ts
    /[FEATURE2].ts
  /styles
    /tailwind.config.js (with design system theme)
    /globals.css
  /config
    /animations.ts (Framer Motion variants)
    /theme.ts (design tokens)

```

**FOR EACH COMPONENT:**

1. Analyze screenshot from design
2. Identify all visual elements and their styling
3. Identify interactive elements and their states
4. Create React component matching design exactly
5. Use Tailwind CSS with design system tokens
6. Add Framer Motion animations
7. Include TypeScript types
8. Add proper accessibility features
9. Implement responsive design

**DELIVERABLES:**

1. Complete React component files with all styling
2. Tailwind theme configuration
3. Framer Motion animation configurations
4. TypeScript types for all components
5. Component exports and documentation
6. Usage examples for each component

This should be a cohesive component library ready to use across the entire application.

```

---

**End of Reverse-Engineering & Design Integration Section**
