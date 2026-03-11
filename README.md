# 🎓 University Management System

A console-based C++ application to manage students, faculty, and courses within a university. It supports enrollment, course assignment, and detailed record display through an interactive menu.

---

## 📋 Features

- Add and manage **students**, **faculty**, and **courses**
- **Enroll students** into courses
- **Assign courses** to faculty members
- **Display** all student and faculty details, including enrolled/taught courses
- Simple, interactive **menu-driven interface**

---

## 🏗️ Class Structure

### `Course`
Represents a university course.

| Member | Type | Description |
|---|---|---|
| `courseCode` | `string` | Unique identifier for the course |
| `courseName` | `string` | Full name of the course |
| `creditHours` | `int` | Number of credit hours |

---

### `Student`
Represents a student enrolled in the university.

| Member | Type | Description |
|---|---|---|
| `name` | `string` | Student's full name |
| `age` | `int` | Student's age |
| `studentId` | `int` | Unique student ID |
| `enrolledCourses` | `vector<Course*>` | List of enrolled courses |

---

### `Faculty`
Represents a faculty member.

| Member | Type | Description |
|---|---|---|
| `name` | `string` | Faculty member's full name |
| `age` | `int` | Faculty member's age |
| `facultyId` | `int` | Unique faculty ID |
| `department` | `string` | Department name |
| `coursesTaught` | `vector<Course*>` | List of courses assigned |

---

### `University`
The central class that manages all entities.

| Method | Description |
|---|---|
| `addStudent()` | Registers a new student |
| `addFaculty()` | Registers a new faculty member |
| `addCourse()` | Adds a new course to the system |
| `enrollStudent()` | Enrolls a student into a course by ID and course code |
| `assignCourse()` | Assigns a course to a faculty member |
| `displayAllDetails()` | Prints all student and faculty records |

---

## 🚀 Getting Started

### Prerequisites
- A C++ compiler supporting **C++11** or later (e.g., `g++`, `clang++`)

### Compilation

```bash
g++ -std=c++11 -o university_system main.cpp
```

### Running

```bash
./university_system
```

---

## 🖥️ Menu Options

```
************ University Management System ************
1. Add Student
2. Add Faculty
3. Add Course
4. Enroll Student in a Course
5. Assign Course to Faculty
6. Display All Details
0. Exit
******************************************************
```

---

## 📌 Usage Example

```
Enter your choice: 3
Enter course code: CS101
Enter course name: Introduction to Programming
Enter credit hours: 3
Course added successfully.

Enter your choice: 1
Enter student name: Alice Johnson
Enter student age: 20
Enter student ID: 1001
Student added successfully.

Enter your choice: 4
Enter student ID: 1001
Enter course code: CS101
Course enrolled successfully.

Enter your choice: 6
Student Details:
Student Name: Alice Johnson
Age: 20
Student ID: 1001
Enrolled Courses:
-------------------------------------
Course Code: CS101
Course Name: Introduction to Programming
Credit Hours: 3
-------------------------------------
```

---

## ⚠️ Notes

- Student IDs and Faculty IDs must be **unique integers**.
- Course codes must be **unique strings** (e.g., `CS101`, `MATH201`).
- If an invalid ID or course code is entered during enrollment or assignment, an error message is shown and no changes are made.
- The application runs entirely **in-memory** — data is not persisted after the program exits.

---

## 📁 File Structure

```
.
└── main.cpp      # All source code (Course, Student, Faculty, University classes + main)
```

---

## 📄 License

This project is open-source and free to use for educational purposes.
