
# 📝 Simple To-Do List Application — Day 8

## 📌 Project Overview
A beginner-friendly command-line To-Do List application developed using Python. It allows users to add, view, update, and delete tasks through an interactive menu.

## 🎯 Objectives
- Understand Python lists and list methods.
- Practice `while` and `for` loops.
- Use conditional statements for menu selection.
- Implement CRUD operations.
- Handle invalid menu choices and task numbers.
- Build a menu-driven command-line application.

## 🛠️ Technologies Used
- Python 3
- Visual Studio Code

## ✨ Features
- **Add Task:** Add a new task to the list.
- **View Tasks:** Display all tasks with numbered entries.
- **Update Task:** Modify an existing task.
- **Delete Task:** Remove a selected task.
- **Input Validation:** Handle empty task descriptions and invalid task numbers.
- **Exit:** Close the application using the menu.

## 📂 Project Structure
```text
Day8-To-Do-List/
├── todo_list.py
└── README.md
```

## 💻 Source Code
```python

tasks = []

menu = ("Add task", "View task", "Update task", "Delete task", "Exit")

while True:
    print("\n===== TO-DO LIST MENU =====")

    for i in range(len(menu)):
        print(f"{i + 1}. {menu[i]}")

    user_input = input("Enter a menu number: ")

    if user_input == "1":
        task = input("Enter a task: ")

        if task.strip():
            tasks.append(task)
            print("Task added successfully!")
        else:
            print("Task cannot be empty.")

    elif user_input == "2":
        if len(tasks) == 0:
            print("No tasks available.")
        else:
            print("\nYour tasks:")
            for i in range(len(tasks)):
                print(f"{i + 1}. {tasks[i]}")

    elif user_input == "3":
        if len(tasks) == 0:
            print("No tasks available to update.")
        else:
            for i in range(len(tasks)):
                print(f"{i + 1}. {tasks[i]}")

            try:
                task_number = int(input("Enter task number to update: "))

                if 1 <= task_number <= len(tasks):
                    new_task = input("Enter the new task: ")

                    if new_task.strip():
                        tasks[task_number - 1] = new_task
                        print("Task updated successfully!")
                    else:
                        print("Task cannot be empty.")
                else:
                    print("Invalid task number.")

            except ValueError:
                print("Enter a valid whole number.")

    elif user_input == "4":
        if len(tasks) == 0:
            print("No tasks available to delete.")
        else:
            for i in range(len(tasks)):
                print(f"{i + 1}. {tasks[i]}")

            try:
                task_number = int(input("Enter task number to delete: "))

                if 1 <= task_number <= len(tasks):
                    deleted_task = tasks.pop(task_number - 1)
                    print(f"Deleted task: {deleted_task}")
                else:
                    print("Invalid task number.")

            except ValueError:
                print("Enter a valid whole number.")

    elif user_input == "5":
        print("Exiting To-Do List. Goodbye!")
        break

    else:
        print("Invalid menu choice. Enter a number from 1 to 5.")

```

## ⚙️ How It Works
1. An empty list stores all tasks.
2. A tuple stores the menu labels.
3. A `while` loop keeps displaying the menu.
4. The user selects an operation using numbers 1–5.
5. `append()` adds new tasks.
6. A `for` loop displays tasks with their numbers.
7. List indexing updates the selected task.
8. `pop()` removes the selected task.
9. `try` and `except` handle invalid task-number input.
10. `break` exits the application.

## ▶️ How to Run
1. Install Python 3.
2. Save the program as `todo_list.py`.
3. Open a terminal in the project directory.
4. Run the following command:

```bash
python todo_list.py
```

On Windows, you can also use:

```bash
py todo_list.py
```

## 🧪 Sample Execution
```text
===== TO-DO LIST MENU =====
1. Add task
2. View task
3. Update task
4. Delete task
5. Exit

Enter a menu number: 1
Enter a task: Learn Python lists
Task added successfully!

Enter a menu number: 2
Your tasks:
1. Learn Python lists
```

## ✅ Test Cases

| Test | Expected Result |
|---|---|
| Add a task | Task is added successfully |
| View an empty list | Displays no tasks available |
| View existing tasks | Displays numbered tasks |
| Update a task | Replaces the selected task |
| Delete a task | Removes the selected task |
| Enter an invalid menu choice | Displays an error message |
| Enter letters for a task number | Displays a validation message |
| Select Exit | Program terminates |

## 📚 Concepts Learned
- Python lists and tuples
- `append()` and `pop()`
- `while` and `for` loops
- `range()` and `len()`
- Conditional statements
- User input and type conversion
- Exception handling
- CRUD operations

## ⚠️ Limitations
Tasks are stored in memory and disappear when the program closes. The application does not currently save tasks permanently to a file or database.

## 🚀 Future Improvements
- Save tasks to a file.
- Add task completion status.
- Add task priorities and due dates.
- Create a graphical user interface.
- Store tasks in a database.

## 👨‍💻 Author
**Akash Adepu**

Python Programming Internship — Day 8 of 45

---
⭐ Built to practice Python fundamentals through hands-on coding.
