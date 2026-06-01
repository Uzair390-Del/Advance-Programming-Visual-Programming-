# Visual Programming (C# / ASP.NET) Open-Book Assessment

## Title
**Skill Exchange Portal**

## Duration
3 Hours

## Assessment Type
Open-Book Practical Assessment

---

## Scenario

A university wants a web-based platform where students can offer skills they can teach (e.g., Graphic Design, Python, Public Speaking, Video Editing) and request skills they want to learn.

Students can create profiles, post skill offers, browse available skills, and send learning requests.

---

# Objective

Develop a web application that allows students to share knowledge and connect with peers through a skill-exchange system.

Students may use:

- ASP.NET Core MVC
- ASP.NET Core Razor Pages
- ASP.NET MVC
- C#
- SQL Server or SQLite
- Entity Framework Core (Recommended)

---

# Functional Requirements

## 1. User Management

The system should allow users to:

- Register a new account
- Login and Logout
- View their profile

---

## 2. Skill Management

Users should be able to:

- Add a new skill offer
- Edit an existing skill offer
- Delete a skill offer
- View all available skill offers

Each skill should contain:

- Skill Title
- Category
- Description
- Skill Level (Beginner, Intermediate, Expert)
- Availability Hours per Week

---

## 3. Search and Filtering

Provide:

- Search by skill title
- Filter by category
- Filter by skill level

---

## 4. Learning Requests

A logged-in user can:

- Request to learn a skill
- Add a short message with the request

The skill owner should be able to:

- View received requests
- Accept or reject requests

---

## 5. Dashboard

Display:

- Total Skills Posted
- Total Requests Sent
- Total Requests Received
- Accepted Requests

---

## 6. Validation

Implement server-side validation for:

- Required fields
- Skill title length
- Description length
- Valid availability hours

---

## 7. User Interface

Provide:

- Responsive layout
- Navigation menu
- Proper forms
- Data tables or card-based views

---

# Minimum Database Design

## Users

| Field |
|---------|
| UserId |
| Name |
| Email |
| Password |

## Skills

| Field |
|---------|
| SkillId |
| Title |
| Category |
| Description |
| Level |
| HoursPerWeek |
| UserId |

## Requests

| Field |
|---------|
| RequestId |
| SkillId |
| RequestedBy |
| Message |
| Status |
| RequestDate |

---

# Bonus Features (+10 Marks)

Implement any one of the following:

- Profile picture upload
- Dark mode
- Skill ratings
- AJAX search
- Pagination
- Bookmark favorite skills
- Email notification simulation

---

# Marking Rubric (100 Marks)

| Component | Marks |
|------------|---------|
| Database Design | 15 |
| CRUD Operations | 25 |
| Authentication | 15 |
| Search & Filtering | 10 |
| Validation | 10 |
| Dashboard | 10 |
| UI/UX Design | 10 |
| Code Quality | 5 |
| **Total** | **100** |

---

# Submission Requirements

Students must submit:

1. Complete source code.
2. Database script or migration files.
3. Screenshots of major application pages.
4. A short README describing:
   - Project overview
   - Technologies used
   - Instructions to run the application

---

# Assessment Notes

- This is an individual assessment.
- Students may consult books, notes, and online resources.
- Copying complete solutions from others is prohibited.
- The application must be functional and demonstrate understanding of Visual Programming concepts using C# and ASP.NET technologies.
