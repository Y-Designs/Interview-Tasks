# **Associate Backend Developer Skills Assessment Task**

**Time Limit:** 6 hours

**Tech Required:** Node.js, Express.js (or Nest.js), PostgreSQL, GitHub

**Optional:** TypeScript (bonus), AWS S3 (bonus)

---

# **Problem Statement**

You need to build a small backend service for managing **Creators** and their **Videos** for an OTT-style system.

The task should use the following entities:

### **1. Creator**

| Field      | Type            |
| ---------- | --------------- |
| id         | UUID            |
| name       | string          |
| email      | string (unique) |
| created_at | timestamp       |

### **2. Video**

| Field       | Type                    |
| ----------- | ----------------------- |
| id          | UUID                    |
| creator_id  | UUID (FK to creator.id) |
| title       | string                  |
| description | text                    |
| video_url   | string                  |
| created_at  | timestamp               |

---

# **Requirements**

## **A. Build 4 APIs using Node.js + Express/Nest**

### **1. Create Creator**

**POST /creators**
Body:

```json
{
  "name": "John Doe",
  "email": "john@example.com"
}
```

Requirements:

* Validate email format
* Throw error if email already exists
* Return created record

---

### **2. Create Video**

**POST /videos**
Body:

```json
{
  "creator_id": "UUID",
  "title": "My First Video",
  "description": "Description here",
  "video_url": "https://example.com/sample.mp4"
}
```

Requirements:

* Validate `creator_id` exists
* Validate `video_url` format
* Return created record

---

### **3. List Videos of a Creator**

**GET /creators/:id/videos?page=1&limit=10**

Requirements:

* Pagination
* Should show creator info + list of videos

---

### **4. Get Video Details**

**GET /videos/:id**

Return:

* Video details
* Creator details (joined via SQL)

---

## **B. PostgreSQL Requirements**

* Create proper tables with keys, indexes
* Use UUID as primary keys
* Use SQL queries or ORM (Sequelize/Prisma/Knex)
* Show migrations if possible

---

## **C. Code Quality Requirements**

* Use `.env` for DB credentials
* Proper folder structure
* Error handling
* Validation
* Use Git and push to GitHub

---

## **D. Bonus (Optional but Great to See)**

These are optional but help the candidate stand out:

### **1. Upload video file to AWS S3**

Provide an **upload URL** (even mock AWS SDK usage is acceptable).

### **2. Add TypeScript instead of JS**

### **3. Add simple logging middleware**

---

# **Expected Submission**

Candidate must submit:

### 1. GitHub Repo Link

Containing:

* Source code
* Package.json
* README
* SQL/migration files
* Postman Collection (optional)

### 2. README explaining:

* How to run the project
* DB setup
* APIs
* Any assumptions
