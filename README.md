# 🌿 Agri-Energy Connect

Agri-Energy Connect is a web-based application built using ASP.NET Core MVC (.NET 9) and designed to streamline the relationship between agricultural employees and farmers. Employees can manage farmer profiles, while farmers can add and manage their own product listings — all within a secure, role-based platform.

---

## 📌 Project Overview

Agri-Energy Connect was developed to address common issues in digital access for farmers. Many farmers are unable to register or manage data themselves, so the application introduces an employee-assisted onboarding process. 

Once an employee registers and approves a farmer, that farmer can log in to:

- Add products with details such as name, category, and production date.
- View and manage their product listings.
- Update their profile.

Meanwhile, employees can:

- Register or log in as staff.
- Add, edit, and manage farmer records.
- View all products submitted by farmers.
- Filter product listings by category or date range.

---

## 👥 User Roles

- 👨‍🌾 Farmer:
  - Must be registered and approved by an employee.
  - Can log in and manage their products.
  - Can edit their own profile details.

- 🧑‍💼 Employee:
  - Can register directly and log in.
  - Can add and manage farmer accounts.
  - Can view all products and apply filters.

---

## 🧱 Architecture & Design Pattern

The application follows the Model-View-Controller (MVC) design pattern, promoting separation of concerns:

- Model: Defines database entities like Farmer and Product.
- View: Razor pages styled with Bootstrap for responsive UI.
- Controller: Handles request routing, logic, and interactions between models and views.

🔧 Technologies:

- Language & Framework: C# and ASP.NET Core (.NET 9)
- Architecture: MVC Pattern
- UI: Razor Pages with Bootstrap
- ORM: Entity Framework Core
- Authentication: ASP.NET Core Identity (with role-based access)

✅ Design Integrity: No changes were made to the original architecture outlined in Part 1. The MVC pattern proved ideal for a maintainable and scalable web application.

---

## 🗄️ Database Usage

The application uses Microsoft SQL Server (SSMS) for data storage. All data — including users, products, and farmer profiles — is stored and accessed via Entity Framework Core.

🛠 Why SQL Server?

- Convenient local development and management using SSMS.
- Easy to integrate with Visual Studio and EF Core.
- Familiar tooling for database administration and queries.

💾 Migrations are used to create and update the schema from within the codebase, ensuring consistency between models and the underlying database.

---

## ✨ Key Features

🎯 Authentication

- Secure login and registration for both roles using ASP.NET Core Identity.
- Farmers cannot log in until approved by an employee.

🌾 Farmer Features

- Add product listings (name, category, date).
- View and edit their own listings.
- Update personal profile information.

🧑‍💼 Employee Features

- Register and log in.
- Add new farmer profiles.
- View and filter all product listings:
  - By date range
  - By category

---

## 💡 Implementation Highlights

- Role-based routing and access implemented in Startup.cs and controllers.
- Views rendered conditionally based on the logged-in user’s role.
- EF Core used for data persistence and LINQ queries for filtering logic.
- Bootstrap 5 ensures modern, mobile-responsive UI.

---

## 🎨 UI/UX Design

- Clean and minimalist design for ease of use.
- Responsive layout with clear role separation.
- Dynamic navigation menus based on user role.
- Validation and feedback on all forms.

---

## ⚙ Setup Instructions

Follow these steps to run the application locally:

1. Clone this repository in Visual Studio.
2. Install NuGet dependencies:

   - Microsoft.EntityFrameworkCore
   - Microsoft.EntityFrameworkCore.SqlServer
   - Microsoft.EntityFrameworkCore.Tools
   - Microsoft.AspNetCore.Identity.EntityFrameworkCore

3. Create a database in SQL Server Management Studio (SSMS) called AgriEnergyDB.
4. Locate your connection string in SSMS (right-click the DB → Properties) and update appsettings.json:

   ```json
   "ConnectionStrings": {
     "DefaultConnection": "Server=.;Database=AgriEnergyDB;Trusted_Connection=True;MultipleActiveResultSets=true"
   }
## 🧪 Sample Data

You can either add seed data for demo purposes or use the app’s interface to perform the following actions:
1. **Register as an Employee.**
2. Use the **Employee panel** to **add and activate Farmers.**
3. Log in as a **Farmer** to **start posting products.**

## 🛠 Challenges and Resolutions

- **UI Complexity**: 
  - Built a consistent layout that adapts to both Employee and Farmer roles, ensuring a seamless user experience for both.

- **Role Restrictions**: 
  - Implemented guards in controllers and views to restrict actions based on roles. This ensures that only authorized users can access or perform specific actions.

- **Filtering**: 
  - Wrote custom **LINQ queries** to enable dynamic filtering of products by **date** and **category**, allowing Farmers and Employees to efficiently browse and manage products.

## 🎥 Video Demonstration

**YouTube Link (Unlisted)**: [Add your video link here]

The video walkthrough includes:
- **Application Overview**
- **Role-based UI and Routing**: Demonstrates how the platform adapts to different roles.
- **Product Management**: Walkthrough of how products are added, viewed, and filtered.
- **Database Setup and Filtering**: Explanation of the underlying database structure and dynamic filtering.
- **Technical and UX Design Decisions**: A discussion of the decisions made during development.

