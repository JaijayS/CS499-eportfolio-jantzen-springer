# Milestone Four: Enhancement Three - Databases

## 1. Artifact Overview

This artifact is the backend system for a project titled **DriverPass**, built using **Java Spring Boot** and **MySQL**. The system supports a driving school platform and handles everything from user registration, course enrollment, and vehicle checkout to teacher evaluations and student progress tracking. It was originally created in **CS-255: System Analysis & Design** and expanded in this capstone with a focus on **database integration** and **backend logic**.

As part of the database enhancement, I cleaned up and normalized relationships between entities, added `CourseOutcome` and `Appointment` tables, and built out the logic to store and retrieve dynamic, real-world data (like enrollments, test results, and appointments). I also made sure the data flows cleanly from the backend into the frontend views, so things like completed courses, appointment history, and student-teacher interactions all update live from the database.

With this updated setup, the system now reflects real workflows used in actual driving schools and supports more complex use cases while staying organized, relational, and scalable.

---

## 2. Justification for Inclusion

I picked this artifact because it shows what I can do when it comes to building a **real backend with a working database** behind it. It started out as a basic setup but became something much more detailed, with full relational logic and real user interaction.

### Improvements that Show My Database Work:
- **Entity Relationships**: Students, teachers, and courses are all connected using proper JPA annotations, and relationships are set up as many-to-many or one-to-many where needed.
- **CourseOutcome Table**: I replaced a few scattered booleans with a dedicated outcome model to track whether a student passed or failed a course. It’s cleaner and more flexible.
- **Live Student and Teacher Dashboards**: I added service methods (`findCoursesByStudent`, `findCoursesNotEnrolledByStudent`, `findByTeacher`) to give each user role their own data pulled from the DB. So students only see courses they’re in or can join, and teachers only see their students and appointments.
- **DTOs and Repositories**: I used DTOs to keep the controller data clean, and custom repo methods to return the right data without hardcoding logic into the views.
- **Form Handling and Data Storage**: The forms on the site (scheduling appointments, checking course progress, enrolling in classes) all save their results straight into the relational database and reflect changes immediately.
- **Seeding and Sample Data**: I created realistic test data to work with and validate that the logic, especially with enrollment, vehicles, and course outcomes, actually holds up.

The end result is a **real backend** with logic that supports student tracking, role-based dashboards, evaluations, and more — all through a clean **MySQL schema** and **Spring JPA**.

---

## 3. Course Outcome Alignment

Yes — and then some. I initially planned to clean up a few database issues and maybe add one or two new entities. But I ended up going further by:

- Adding a full `CourseOutcome` system to record pass/fail decisions
- Creating appointment tracking with cancel/reschedule support
- Reworking how courses connect to users so that everything is handled through real-time database-driven logic
- Updating the `StudentController` and `TeacherController` so they return only the relevant courses and appointments tied to that logged-in user
- Expanding `CourseService` to let me grab only the courses a student is in or not in, which makes the frontend more personalized and secure

This not only hit my goals but made the system feel more like a **real product** instead of a class project. All updates now reflect **relational logic** with no hardcoded values on the frontend.

---

## 4. Reflection

Working on this showed me how important it is to think through **relationships early**. A lot of the problems came from originally treating things like `attended`, `writtenTest`, and `drivingTest` as individual booleans. Replacing that with a proper outcome model forced me to rethink how I structure and store results.

### Challenges and Lessons Learned:
- Refactoring logic and UI to use a single `CourseOutcome` model instead of several flags
- Making sure students and teachers are synced when enrolled or removed from courses (many-to-many bidirectional logic)
- Updating the UI templates with Thymeleaf to show dynamic lists like enrolled/available courses, course outcomes, and upcoming appointments
- Getting controllers to stay clean by pushing most of the logic into services and repositories
- Making sure that every form — whether it’s an enrollment or a test result — actually stores values in the database the right way

This taught me how to keep a system **maintainable as it grows** and how to wire up a UI to **live data** through controllers and services without cutting corners. I also got better at working with **Spring’s transaction handling**, **fetch strategies**, and how to structure **repository queries** for clean code.
