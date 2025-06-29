# Milestone Four: Enhancement Three - Databases

Original: https://github.com/JaijayS/CS-255-System-Analysis-Design

Enhanced: https://github.com/JaijayS/cs499-enhanced-database


## 1. What is the artifact? When was it created?

This artifact is the backend system of my **DriverPass web application**. It was originally built during **CS-255: System Analysis & Design** and later expanded during the **CS-499 Capstone** course.

It simulates the backend operations of a driving school, including:

- Account registration  
- Course scheduling  
- Student evaluations  
- Vehicle checkout  

The system is built using **Java Spring Boot** and **MySQL**.

Initially, the project functioned more like a prototype. As part of this enhancement, I:

- Redesigned the database schema to reflect real-world workflows
- Added new tables such as `CourseOutcome` and `Appointment`
- Restructured backend logic to support dynamic updates
- Ensured smooth, two-way communication between the frontend and backend

The project prompt allowed for a web application to demonstrate database work, so I focused on building a **robust backend** as the foundation of the application.

---

## 2. Why did you choose this artifact? What database skills does it demonstrate?

I chose this artifact because it showcases my ability to **design, build, and manage real database systems**, going far beyond writing basic SQL queries. It reflects thoughtful data architecture and full-cycle integration between UI and database layers.

### Key Skills Demonstrated

- **Entity Relationships**  
  Used JPA annotations like `@ManyToMany` and `@OneToMany` to connect students, teachers, courses, and outcomes.

- **Normalized Data Structures**  
  Replaced scattered boolean flags with a centralized `CourseOutcome` table to track evaluation results.

- **Role-Based Access Control**  
  Implemented student/teacher-specific views and access using custom repository and service-layer logic.

- **Form and Data Flow Integration**  
  All form submissions (enrollments, outcomes, appointments) are stored in the database and reflected in real time in the UI.

- **DTO and Service Layers**  
  Introduced Data Transfer Objects (DTOs) and separated business logic from controller logic, improving maintainability.

- **Test and Seed Data**  
  Built realistic sample data for users, vehicles, courses, and appointments to allow for full end-to-end testing.

These enhancements result in a **production-ready backend** suitable for a real or prototype educational management system.

---

## 3. Did you meet your planned goals from Module One?

Yes — and I exceeded them.

My original plan was to clean up a few entity relationships and improve some of the form logic. However, as I worked on the project, I realized there were deeper architectural improvements needed.

###  Additional Enhancements Completed:

- Built a `CourseOutcome` system to store evaluation results
- Implemented an `Appointment` system with constraints (e.g., weekdays only, one student per course per day)
- Improved session handling and custom login redirect logic
- Filtered course list so students can’t re-enroll in already completed courses
- Refactored controller logic into the service layer to improve modularity

These updates resulted in a **cleaner, more maintainable, and scalable system** that better simulates real-world backend workflows.

---

## 4. What did you learn from working on this enhancement? What were the challenges?

One major takeaway was how **early database design decisions significantly impact future flexibility and scalability**.

For example:
- Initially, course progress was tracked with simple booleans.
- Replacing those with a full `CourseOutcome` model required **refactoring multiple services, views, and controllers**, but the final structure was much more consistent and clean.

### Challenges Encountered:

- **Regression**: Adding features like appointment scheduling broke course availability logic — teaching the importance of **full regression testing** after every feature update.
- **Security Complexity**: Spring Security configuration was tricky. Handling user roles, session logic, and login redirects required **careful integration** with the rest of the application.
- **Cross-Layer Coordination**: Making sure changes in the frontend, controller, service, and repository layers stayed in sync took **careful versioning and testing**.

---

## Outcome

This project solidified my understanding of:

- Backend development using **Spring Boot**
- SQL and relational modeling in **MySQL**
- Authentication and authorization with **Spring Security**
- Clean separation of concerns using **DTOs** and **Service layers**
- Real-world system simulation and UI↔DB communication

It also reinforced the importance of designing systems that are **modular, testable, and easy to evolve** as needs change.

---

## Design Screenshots

 **Login Page**:
 
 ![Login Page](https://github.com/JaijayS/CS499-eportfolio-jantzen-springer/blob/main/images/driver-pass-login-page.png)
 
 **Registration Page**:
 
![Registration Page](https://github.com/JaijayS/CS499-eportfolio-jantzen-springer/blob/main/images/driver-pass-registration-page.png)

 **Admin Page**:
 
![Admin Page with CRUD Operations](https://github.com/JaijayS/CS499-eportfolio-jantzen-springer/blob/main/images/driver-pass-admin-page.png) 

 **Teacher Page**:
 
 ![Teacher Page](https://github.com/JaijayS/CS499-eportfolio-jantzen-springer/blob/main/images/driverpass-teacher-page.png)
 
 **Student Page**:
 
 ![Student Page with Scheduling and Enrollment](https://github.com/user-attachments/assets/357bcace-9c08-4dd5-9ce4-b5bc4cafc4fe)

