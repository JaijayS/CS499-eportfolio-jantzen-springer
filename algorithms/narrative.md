# Course Planner – Algorithms and Data Structure Enhancement

Original: https://github.com/JaijayS/CS-300-DSA-Analysis-and-Design

Enhanced: https://github.com/JaijayS/cs499-enhanced-algorithms


## 1. Briefly describe the artifact. What is it? When was it created?

This artifact differs from the previous one but aligns much better with the focus of algorithms and data structures. The project is a Course Planner application originally written in a single C++ source file. It was developed to load and manage course data for a university advising system, including support for prerequisites and course searching.

As part of the enhancement, the code was refactored to better demonstrate algorithmic design and data structure usage. I:
- Modularized the code
- Implemented a custom hash table to store course information
- Replaced the default `std::sort` with a custom QuickSort algorithm

The original version relied on the C++ Standard Library’s `std::sort`, which internally uses a hybrid sorting algorithm (QuickSort, HeapSort, and InsertionSort) [GeeksforGeeks, 2022]. My enhancements provided better performance control, deeper understanding, and clearer presentation of how data is processed.

---

## 2. Why did you choose this artifact?

I included this artifact because it demonstrates my ability to design, implement, and evaluate custom algorithmic solutions. It reflects my growth in structuring efficient systems using foundational data structures and shows clear evidence of strategic problem-solving.

Key Components and Improvements:
- Custom Hash Map: Built from scratch using chaining for collision handling to store course records efficiently.
- QuickSort Algorithm: Implemented manually to sort courses by ID, title, or teacher—replacing reliance on STL sort.
- CSV Parsing Improvements: Expanded logic to read multiple prerequisites and instructor names from structured data.
- Dynamic CLI Output: Cleanly formatted output for improved usability and better communication of results.

Through this enhancement, I applied algorithmic thinking and hands-on development to simulate a system that supports real-world advising workflows.

---

## 3. Did you meet your planned goals from Module One?

Yes — and I enhanced the project significantly beyond my initial plan.

Updates and Enhancements:
- Refactored the original monolithic `.cpp` into modular files (`main.cpp`, `HashMap.h/cpp`, `Sort.h/cpp`)
- Designed reusable Sort class and implemented abstraction for sorting by various fields
- Manually implemented recursive QuickSort, managing edge cases and testing performance
- Built comparison logic for complex course records (multiple instructors/prerequisites)
- Enhanced terminal output formatting for alignment and readability
- Incorporated peer feedback and iterative testing for refinement

These enhancements improved clarity, performance, scalability, and user control, while directly showcasing my understanding of data structures and algorithm design.

---

## 4. Reflection: What did you learn and what were the challenges?

Enhancing this artifact taught me about the importance of modularity and abstraction in algorithm-heavy applications.

Lessons Learned:
- Deepened my understanding of recursive logic, especially in QuickSort
- Learned to balance performance, maintainability, and readability
- Experienced the trade-offs of custom implementations vs. standard libraries

Challenges Faced:
- Managing multi-field comparison logic with non-uniform data (e.g., multiple instructors)
- Preventing regressions in output formatting while refactoring display code
- Debugging recursive partitioning and pointer handling in QuickSort
- Designing a flexible sorting interface while maintaining clean code separation

This project allowed me to design and evaluate a computing solution that uses algorithmic principles and clean architecture. It’s scalable, fast, and effective for supporting decision-making in a course planning context.

Although security wasn’t a focus here, I acknowledge that data validation and error handling are essential in real-world systems. Future improvements would include better input sanitation and defensive programming techniques.

---

## Project Files Overview

| File           | Description |
|----------------|-------------|
| `Main.cpp`     | Main program handling UI and logic |
| `Course.h`     | Defines Course struct: ID, title, prerequisites |
| `HashMap.h`    | HashMap interface for insert/search/print |
| `HashMap.cpp`  | Hashing and collision handling logic |
| `Courses.csv`  | Source course data with prerequisites and teachers |
| `Sort.h`       | Sorting interface for ID, title, or teacher |
| `Sort.cpp`     | QuickSort implementation with field comparison logic |

---

## Enhancement Log

| # | Change Description              | Impact                                           |
|---|--------------------------------|--------------------------------------------------|
| 1 | Modularized Code Structure     | Improved maintainability, readability, scalability |
| 2 | Added teacher support          | Enhanced realism of data                         |
| 3 | Implemented custom sort algo   | Reduced reliance on STL, improved learning       |
| 4 | Dynamic sorting options        | Gave user more control over presentation         |
| 5 | Reformatted console output     | Improved user experience                         |
| 6 | Improved CSV parser            | Increased flexibility and real-world compatibility |

---

## References

GeeksforGeeks. (2022, December 22). Introsort - C++’s sorting weapon.  
https://www.geeksforgeeks.org/dsa/introsort-cs-sorting-weapon/
