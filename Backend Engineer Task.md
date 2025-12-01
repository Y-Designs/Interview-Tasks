# Backend Engineer Task

**Time Limit:** 6-12 Hours
**Preferred Stack:** Node.js (TypeScript optional), PostgreSQL (or MySQL), REST APIs
**Bonus:** Python, Redis, Docker, AWS knowledge

---

# **Problem Statement — “Mini Project Management API”**

Build a small backend service that allows users to manage **Projects**, **Tasks**, and **Comments**.

This system should support:

* User creation
* Project creation
* Task management within projects
* Comments on tasks
* Assigning users to tasks
* Listing tasks with filters
* A clean REST API structure
* SQL relationships & joins
* Pagination & validation

---

# **Data Model (Minimum Required)**

### **1. users**

| Field      | Type            |
| ---------- | --------------- |
| id         | UUID            |
| name       | string          |
| email      | string (unique) |
| created_at | timestamp       |

---

### **2. projects**

| Field       | Type                 |
| ----------- | -------------------- |
| id          | UUID                 |
| name        | string               |
| description | text                 |
| owner_id    | UUID (FK → users.id) |
| created_at  | timestamp            |

---

### **3. tasks**

| Field       | Type                                |
| ----------- | ----------------------------------- |
| id          | UUID                                |
| project_id  | UUID (FK → projects.id)             |
| title       | string                              |
| description | text                                |
| status      | enum("todo", "in_progress", "done") |
| assigned_to | UUID (FK → users.id, nullable)      |
| created_at  | timestamp                           |

---

### **4. comments**

| Field      | Type                 |
| ---------- | -------------------- |
| id         | UUID                 |
| task_id    | UUID (FK → tasks.id) |
| user_id    | UUID (FK → users.id) |
| message    | text                 |
| created_at | timestamp            |

---

# **Required APIs (Node.js / Express / Fastify / NestJS)**

## **1. Create User**

**POST /users**

```json
{
  "name": "John Doe",
  "email": "john@example.com"
}
```

Requirements:

* Validate email format
* Unique email constraint

---

## **2. Create Project**

**POST /projects**

Body:

```json
{
  "name": "Project Apollo",
  "description": "Internal product build",
  "owner_id": "UUID"
}
```

Requirements:

* Validate user exists
* Return the created project

---

## **3. Create Task under a Project**

**POST /tasks**

Body:

```json
{
  "project_id": "UUID",
  "title": "Setup CI/CD",
  "description": "Configure pipeline",
  "assigned_to": "UUID"
}
```

Requirements:

* Validate project exists
* Optionally validate assigned user exists
* Set default status = `"todo"`

---

## **4. Add Comment to Task**

**POST /tasks/:id/comments**

Body:

```json
{
  "user_id": "UUID",
  "message": "CI/CD pipeline deployed successfully."
}
```

Requirements:

* Validate task + user exist

---

## **5. List Tasks with Filters**

**GET /tasks?project_id=UUID&status=todo&assigned_to=UUID&page=1&limit=10**

Requirements:

* Filter by:

  * `project_id`
  * `status`
  * `assigned_to`
* Pagination
* Return each task with:

  * Project info
  * Assigned user info
  * Latest comment (optional but preferred)

This tests **JOIN queries, pagination, and performance**.

---

# **Optional Python Task (20–30 mins)**

Create a Python script that:

1. Reads a JSON file `tasks.json`
2. Summarizes:

   * total tasks
   * count by status
   * count by assigned user
3. Writes `summary.json` containing:

```json
{
  "summary": { ... },
  "tasks": [ ...original array... ]
}
```

This tests basic scripting & data-handling.

---

# **Bonus (Optional — Not Required)**

Candidates can earn extra points by implementing:

### Authentication (JWT)

Basic login + token validation.

### Redis Caching

Cache **task list results** for 30 seconds.

### Background Worker

Simulate task reminders or due-date notifications.

### Docker Setup

`docker-compose.yml` with API + PostgreSQL.

### Tests

Basic unit/integration tests using Jest / Mocha.

---

# **Expected Submission**

The candidate should submit:

### **1. GitHub Repository**

Containing:

* Node.js code
* SQL migrations or schema
* Python script (optional)
* Postman collection (optional)

### **2. README File**

Explaining:

* How to run the project
* DB setup
* Available APIs
* Bonus features (if implemented)
