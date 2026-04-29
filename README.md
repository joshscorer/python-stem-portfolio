# Python Programming Portfolio

**Joshua Scorer**
**Bishop's Stortford College**
**Python for STEM**
**Year 12**

---
## About me 

I am a year 12 student and I have been doing a python for STEM course over the last few months. I study Maths, Further Maths, Economics and History. I hope to study economics at university.

---

## Course overview 

This portfolio documents my progress through a Python programming course designed for students preparing for STEM pathways at university and future life. The course covers:

- Python fundamentals (variables, input/output, data types)
- Control structures (loops and conditionals)
- Functions and modular code
- Data structures (lists, dictionary, tuples, sets)
- Validation and error handling
- File handling
- Object-Oriented Prograaming (OOP)
- Version control with Git and GitHub
- Working with Jupyter Notebooks

--- 

## Portfolio Projects

| # | Project | Key skills | Status |
|---|---|---|---|
| 1 | [Unit converter](#Unitconverter) | Variables, functions, input/output | ✅ Complete |
| 2 | Number Guessing Game | Loops, conditions, random | ✅ Complete |
| 3 | To-do List | Lists, functions, data structures | ✅ Complete |
| 4 | Student Grade Calculator | Dictionaries, validation, error handling | ✅ Complete |
| 5 | OOP Bank account | Classes, OOP principles | ✅ Complete |
| 6 | Data Analysis Notebook | Jupyter Notebooks, data exploration | ✅ Complete |

---

## Skills I have developed

**Programming Concepts**
- Writing clean, well-commented Python code
- Using functions to organise and reuse code 
- Handling use input safely with validation

**Tools and Technologies**
- Python 3 (Thonny IDE)
- Jupyter Notebook
- Git version control
- GitHub for code sharing and portfolio management
- Markdown for documentation

---

## Contact
- **Github:** [joshscorer]
- **Email** [joshua.scorer@outlook.com]

---
## Projects
- #Unit converter
``` Python
def celsiuis_to_fahrenheit(celsius):
    fahrenheit = (celsius * 9/5) + 32
    return fahrenheit

temp1 = celsiuis_to_fahrenheit(0)
temp2 = celsiuis_to_fahrenheit(25)
temp3 = celsiuis_to_fahrenheit(100)

print(f"0 Celsius = {temp1} Fahrenheit")
print(f"25 Celsius = {temp2} Fahrenheit")
print(f"100 Celsius = {temp3} Fahrenheit")
```
- Number Guessing Game
``` Python
def guessNumber():
    '''Randomly chooses a number between 1 and 10'''
    import random
    secret_number = random.randint(1, 10)
    print(secret_number)
    while True:
        guess = int(input("Enter your guess: "))
        
        if guess < 1 or guess > 10: 
            print("Please enter a number between 1 and 10.")
        elif guess < secret_number:
            print("Too low. Try again.")
        elif guess > secret_number:
            print("Too high. Try again.")
        else:
            print("Congratulations! You guessed it!")
          break 
guessNumber()
```
- To-do List Manager
``` Python

def show_tasks(tasks):
    """Display all tasks with their numbers."""
    if len(tasks) == 0:
        print("No tasks yet!")
        return
    
    print("\n=== Your Tasks ===")
    for i, task in enumerate(tasks, start=1):
        print(f"{i}. {task}")
    print()

def add_task(tasks):
    """Add a new task to the list."""
    new_task = input("Enter task: ")
    tasks.append(new_task)
    print(f"Added: '{new_task}'")

def remove_task(tasks):
    """Remove a task by number."""
    show_tasks(tasks)
    number = int(input("Enter task number to remove: "))
    if 1 <= number <= len(tasks):
        removed = tasks.pop(number - 1)
        print(f"Removed: '{removed}'")
    else:
        print("Invalid number.")

def main():
    tasks = []
    
    while True:
        print("=== To-Do List ===")
        print("1. View tasks")
        print("2. Add task")
        print("3. Remove task")
        print("4. Quit")
        
        choice = input("Choose: ")
        
        if choice == "1":
            show_tasks(tasks)
        elif choice == "2":
            add_task(tasks)
        elif choice == "3":
            remove_task(tasks)
        elif choice == "4":
            print("Goodbye!")
            break

main()
```


