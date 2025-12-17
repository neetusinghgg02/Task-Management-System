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

## Notes

* Entity Framework **Code First approach** is used
* Session-based authentication (no ASP.NET Identity)
* Follows clean and maintainable MVC architecture

---

## Author

**Neetu Singh**
