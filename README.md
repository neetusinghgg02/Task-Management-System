# Task Management System

## Overview

A complete Task Management System developed using **ASP.NET Core MVC (.NET 9)**
as part of the **Oritso Private Limited – Screening Assignment**.

The application enables users to manage tasks efficiently with full CRUD operations, search functionality, and audit tracking.

---

## Features

* User login using **Session-based authentication**
* Create, view, update, and delete tasks
* Search tasks by **title** or **status**
* Track **CreatedAt** and **UpdatedAt** timestamps
* Track **CreatedBy** and **UpdatedBy** users
* Clean and professional UI

---

## Tech Stack

* **ASP.NET Core MVC (.NET 9)**
* **Entity Framework Core 9 (Code First)**
* **SQL Server**
* **Visual Studio 2022**
* **Bootstrap 5**

---

## Database Design

* **User** (1) → (M) **TaskItem**
* Indexes on **TaskTitle** and **Status** for faster search performance

---

## How to Build & Run

1. Open the solution in **Visual Studio 2022**
2. Update the **connection string** in `appsettings.json`
3. Open **Package Manager Console**
4. Run the following commands:

   ```powershell
   Add-Migration Initial
   Update-Database
   ```
5. Press **F5** or click **Run** to start the application

---

## Architecture & Design Decisions

### Application Structure

* The application is built using **ASP.NET Core MVC** following the standard **Model–View–Controller** pattern.
* Server-side rendering (MPA) is used instead of SPA to keep the solution simple, maintainable, and aligned with enterprise MVC applications.

### MVC vs SPA Choice

* **Standard MVC (MPA)** approach is used.
* Razor Views handle UI rendering on the server.
* This approach was chosen for:

  * Faster development
  * Clear separation of concerns
  * Easier debugging and maintainability

---

## Database Design

### ER Diagram (Logical Representation)

```
User (UserId, UserName, Email)
   |
   | 1-to-Many
   v
TaskItem (TaskItemId, TaskTitle, TaskDescription, DueDate,
          Status, Remarks, CreatedOn, UpdatedOn,
          CreatedByUserId, UpdatedByUserId)
```

### Data Dictionary

| Column Name     | Data Type | Description                                 |
| --------------- | --------- | ------------------------------------------- |
| TaskItemId      | int (PK)  | Unique task identifier                      |
| TaskTitle       | nvarchar  | Title of the task                           |
| TaskDescription | nvarchar  | Task details                                |
| DueDate         | datetime  | Task due date                               |
| Status          | nvarchar  | Task status (Pending/In Progress/Completed) |
| Remarks         | nvarchar  | Additional remarks                          |
| CreatedOn       | datetime  | Record creation timestamp                   |
| UpdatedOn       | datetime  | Record last updated timestamp               |
| CreatedByUserId | int (FK)  | User who created the task                   |
| UpdatedByUserId | int (FK)  | User who last updated the task              |

---

### Indexes Used

* Index on **TaskTitle** for faster title-based search
* Index on **Status** for optimized filtering

Indexes improve query performance during search operations.

---

### Database Approach

* **Entity Framework Core – Code First** approach is used
* Reason:

  * Better version control through migrations
  * Easy schema evolution
  * Strong alignment with domain models

---

## Frontend Design

* Web-based frontend using **Razor Views**
* **Bootstrap 5** used for responsive and clean UI
* Pages implemented:

  * Login
  * Task List
  * Create Task
  * Edit Task
  * Delete Task

---

## Build & Run Instructions

1. Open the solution in **Visual Studio 2022**
2. Update the connection string in `appsettings.json`
3. Open **Package Manager Console**
4. Run:

   ```powershell
   Add-Migration Initial
   Update-Database
   ```
5. Press **F5** to run the project

---

## Notes

* Entity Framework **Code First approach** is used
* Session-based authentication (no ASP.NET Identity)
* Designed as a screening-level enterprise MVC application

---

## Author

**Neetu Singh**
