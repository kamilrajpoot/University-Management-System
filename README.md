# 🎓 University Management System (C++)

A console-based University Management System built in C++ using OOP principles. It manages **Students**, **Faculty**, and **Courses**, and supports enrolling students into courses and assigning faculty to teach them.

## Features

- Add students, faculty, and courses
- Enroll a student into a course
- Assign a course to a faculty member
- Display full details of all students and faculty (including their courses)
- Duplicate-safe: prevents duplicate IDs, course codes, enrollments, and assignments
- Robust input handling (invalid/non-numeric input won't crash or infinite-loop the program)

## Tech / Concepts Used

- Object-Oriented Programming (encapsulation, composition)
- `std::deque` for stable pointer storage (avoids dangling pointers on reallocation)
- Pointer-based relationships between `Student`/`Faculty` and `Course`
- Menu-driven console interface

## Project Structure

```
.
├── university_management_fixed.cpp   # Main source file
└── README.md
```

## Classes

| Class        | Responsibility                                              |
|--------------|---------------------------------------------------------------|
| `Course`     | Stores course code, name, and credit hours                    |
| `Student`    | Stores student info and list of enrolled courses              |
| `Faculty`    | Stores faculty info and list of courses taught                |
| `University` | Manages all students, faculty, and courses; handles operations |

## Getting Started

### Prerequisites

- A C++ compiler supporting C++17 (e.g., `g++`, `clang++`, or MSVC)

### Compile & Run

```bash
g++ -std=c++17 -Wall -o university university_management_fixed.cpp
./university
```

On Windows (MSVC), you can also just open the `.cpp` file in Visual Studio and build/run.

## Usage

Once running, you'll see a menu:

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

Enter the number corresponding to the action you want to perform, then follow the prompts.

## Known Fixes Applied

This version resolves several issues found in the original implementation:

- **Dangling pointer bug** — courses are now stored in a `std::deque` instead of `std::vector`, so pointers to existing courses stay valid even when new courses are added.
- **Infinite loop on bad input** — non-numeric input for menu choices or IDs is now caught and handled gracefully.
- **Duplicate records** — adding a student/faculty/course with an ID or code that already exists is now blocked with an error message.
- **Duplicate enrollment/assignment** — a student can't be enrolled twice in the same course, and a faculty member can't be assigned twice to the same course.

## Possible Future Improvements

- Persist data to a file or database instead of in-memory storage
- Add ability to remove/update students, faculty, or courses
- Add course capacity limits and prerequisite checks
- Unit tests for core University operations

## License

This project is open source and available for personal or educational use.
