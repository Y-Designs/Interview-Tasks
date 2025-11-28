# **Frontend Engineer (2–5 Years) — Assessment Task**

**Time to complete:** 6–8 hours

**Tech:** React (with or without Next.js), TypeScript preferred, any CSS method, GitHub

**Optional:** Testing, charts, local JSON server, mock APIs

---

# **Project Goal: Build a Mini “User Management + Analytics Dashboard”**

You need to build a small **admin-style dashboard** with:

1. **Users List Page** (table + pagination + filters)
2. **User Details Page**
3. **Analytics Overview Page** (simple charts)
4. Clean component structure, reusable UI, and state management

---

# **Features & Requirements**

---

## **1. Users List Page**

**Route:** `/users`

Show a list of users with the following columns:

* Avatar
* Name
* Email
* Status (Active / Inactive)
* Created Date
* Actions (View button)

**Requirements:**

* Server-side or client-side pagination (`page`, `limit`)
* Filtering by:

  * Name (text search)
  * Status (dropdown)
* Sorting by:

  * Name
  * Created Date

**Data Source Options (Candidate's Choice):**

* Mock API using **JSON Server**
* Using a static JSON
* A simple JS array inside the project
* Using mock REST API tools like MockAPI.io or ReqRes

---

## **2. User Details Page**

**Route:** `/users/:id`

Show:

* User profile card (avatar, name, email, status)
* Activity summary (mock data)
* Last 5 actions (static list is fine)
* Edit user button → opens a modal

**Modal Requirements:**

* Update user name & status
* Basic form validation
* Should visually update UI (no real backend needed; local state update is fine)

---

## **3. Analytics Overview Page**

**Route:** `/analytics`

Show any **two simple charts** (candidate can use any chart library):

### Required Charts:

1. **User Signup Trend (Last 7 Days)** — Line or Bar
2. **Active vs Inactive Users** — Pie or Donut

Candidate can:

* Use mock data
* Use any chart library: Recharts / Chart.js / ECharts / Victory

---

# **UI Expectations**

* Clean layout
* Responsive design (mobile/tablet-friendly)
* Reusable components such as:

  * Table
  * Pagination
  * Filters
  * Cards
  * Buttons
  * Modal
* Consistent spacing, typography, and colors

Candidate may use:

* TailwindCSS
* SCSS
* Styled Components
* CSS Modules
* Or any preferred styling system

---

# **State Management Requirements**

Use either:

* React Context
* Redux Toolkit
* Zustand
* Jotai
* Recoil

Should be used for at least 1 of the following:

* User list filters
* User detail state
* Theme state
* Global loading state

---

# Optional but Great to Have (Bonus)

* Implement dark mode toggle
* Add React Query for API caching
* Add basic tests (Jest + React Testing Library)
* Add skeleton loaders
* Debounced search
* Add proper folder architecture (`components/`, `hooks/`, `pages/`, etc.)
* Use TypeScript instead of JS
* Add form validation using Zod/Yup
* Add lazy loading + code splitting

---

# **Expected Submission**

Candidate must submit:

### GitHub Repo Link

Should include:

* Source code
* README
* Any mock data or JSON files

### README must include:

* How to run the project
* Libraries used
* Short explanation of architecture choices
* Screenshots (optional, but appreciated)
