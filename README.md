# Python Programming Portfolio

**Joshua Scorer**
**Bishop's Stortford College**
**Python for STEM**
**Year 12**

---
## About me 

I am a year 12 student and I have been doing a python for STEM course over the last few months. I study Maths, Economics and History. I hope to study economics at university.

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
| 1 | [Unit converter](#Unit-converter-portfolio-projects) | Variables, functions, input/output | ✅ Complete |
| 2 | [Number Guessing Game](#Number-Guessing-Game-portfolio-projects) | Loops, conditions, random | ✅ Complete |
| 3 | [To do List](#To-do-List-portfolio-projects) | Lists, functions, data structures | ✅ Complete |
| 4 | [Student Grade Calculator](#Student-Grade-Calculator-portfolio-projects) | Dictionaries, validation, error handling | ✅ Complete |
| 5 | [OOP Bank account](#OOP-Bank-account-portfolio-projects) | Classes, OOP principles | ✅ Complete |
| 6 | [Contact book with file saving](#Contact-book-with-file-saving-portfolio-projects) | Jupyter Notebooks, data exploration | ✅ Complete |
| 7 | [Movie list with ratings](#Movie-list-with-ratings-portfolio-projects) | Using database, removing, adding, showing | ✅ Complete |

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
- ## Unit converter |[Portfolio Projects](#Portfolio-Projects)
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

<img width="202" height="41" alt="image" src="https://github.com/user-attachments/assets/4eea34cd-3c0c-4376-86ca-c8263f602f4c" />


- ## Number Guessing Game |[Portfolio Projects](#Portfolio-Projects)
``` Python
def guessNumber():
    '''Randomly chooses a number between 1 and 10'''
    import random
    secret_number = random.randint(1, 10)
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

<img width="215" height="29" alt="image" src="https://github.com/user-attachments/assets/59c0f91d-3333-49a5-b287-715846bb7db1" />

- ## To-do List |[Portfolio Projects](#Portfolio-Projects)
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

<img width="236" height="394" alt="image" src="https://github.com/user-attachments/assets/da3e0158-2322-4268-849c-d25a1573febd" />

- ## Student Grade Calculator |[Portfolio Projects](#Portfolio-Projects)
``` Python
def get_grade(average):
    """Return a letter grade based on average percentage."""
    if average >= 70:
        return "A"
    elif average >= 60:
        return "B"
    elif average >= 50:
        return "C"
    elif average >= 40:
        return "D"
    else:
        return "U"

def get_valid_score(subject):
    """Ask for a score and keep asking until a valid number is entered."""
    while True:
        try:
            score = float(input(f"Enter score for {subject} (0-100): "))
            if 0 <= score <= 100:
                return score
            else:
                print("Score must be between 0 and 100.")
        except ValueError:
            print("Please enter a number.")

def calculate_results():
    """Collect scores and display results."""
    name = input("Student name: ")
    subjects = ["Maths", "English", "Science"]
    scores = {}
    
    for subject in subjects:
        scores[subject] = get_valid_score(subject)
    
    average = sum(scores.values()) / len(scores)
    grade = get_grade(average)
    
    print(f"\n=== Results for {name} ===")
    for subject, score in scores.items():
        print(f"  {subject}: {score:.1f}")
    print(f"Average: {average:.1f}%")
    print(f"Grade: {grade}")

calculate_results()
```

<img width="227" height="123" alt="image" src="https://github.com/user-attachments/assets/04ce5267-ab44-42df-a64b-826a193d9352" />

- ## OOP Bank Account |[Portfolio Projects](#Portfolio-Projects)
``` Python
class BankAccount:
    """A simple bank account class."""
    
    def __init__(self, owner, initial_balance=0):
        """Set up the account with an owner name and starting balance."""
        self.owner = owner
        self.balance = initial_balance
        self.transactions = []
    
    def deposit(self, amount):
        """Add money to the account."""
        if amount > 0:
            self.balance += amount
            self.transactions.append(f"Deposit: +£{amount:.2f}")
            print(f"Deposited £{amount:.2f}. New balance: £{self.balance:.2f}")
        else:
            print("Deposit amount must be positive.")
    
    def withdraw(self, amount):
        """Remove money from the account if funds are available."""
        if amount <= 0:
            print("Withdrawal amount must be positive.")
        elif amount > self.balance:
            print(f"Insufficient funds. Balance is only £{self.balance:.2f}")
        else:
            self.balance -= amount
            self.transactions.append(f"Withdrawal: -£{amount:.2f}")
            print(f"Withdrew £{amount:.2f}. New balance: £{self.balance:.2f}")
    
    def show_balance(self):
        """Display the current balance."""
        print(f"\nAccount holder: {self.owner}")
        print(f"Current balance: £{self.balance:.2f}")
    
    def show_history(self):
        """Display all transactions."""
        print(f"\n=== Transaction History for {self.owner} ===")
        for t in self.transactions:
            print(f"  {t}")
        print(f"  Current balance: £{self.balance:.2f}")


# --- Using the class ---
def main():
    name = input("Enter account holder name: ")
    opening = float(input("Enter opening balance: £"))
    
    account = BankAccount(name, opening)
    
    while True:
        print("\n1. Deposit")
        print("2. Withdraw")
        print("3. Check balance")
        print("4. View history")
        print("5. Exit")
        
        choice = input("Choose: ")
        
        if choice == "1":
            amount = float(input("Amount to deposit: £"))
            account.deposit(amount)
        elif choice == "2":
            amount = float(input("Amount to withdraw: £"))
            account.withdraw(amount)
        elif choice == "3":
            account.show_balance()
        elif choice == "4":
            account.show_history()
        elif choice == "5":
            print("Thank you for banking with us.")
            break

main()
```

<img width="314" height="358" alt="image" src="https://github.com/user-attachments/assets/2329ba1a-7204-44dc-aa09-332cc59e8f7a" />

- ## Contact Book with File Saving |[Portfolio Projects](#Portfolio-Projects)
``` Python
import os

FILENAME = "contacts.txt"

def load_contacts():
    """Load contacts from file. Return empty list if file doesn't exist."""
    contacts = []
    if os.path.exists(FILENAME):
        with open(FILENAME, "r") as f:
            for line in f:
                parts = line.strip().split(",")
                if len(parts) == 2:
                    contacts.append({"name": parts[0], "phone": parts[1]})
    return contacts

def save_contacts(contacts):
    """Save all contacts to file."""
    with open(FILENAME, "w") as f:
        for c in contacts:
            f.write(f"{c['name']},{c['phone']}\n")
    print("Contacts saved.")

def add_contact(contacts):
    name = input("Name: ")
    phone = input("Phone: ")
    contacts.append({"name": name, "phone": phone})
    save_contacts(contacts)

def view_contacts(contacts):
    if not contacts:
        print("No contacts saved.")
        return
    print("\n=== Contacts ===")
    for i, c in enumerate(contacts, 1):
        print(f"{i}. {c['name']} — {c['phone']}")

def main():
    contacts = load_contacts()
    print(f"Loaded {len(contacts)} contact(s).")
    
    while True:
        print("\n1. View contacts  2. Add contact  3. Exit")
        choice = input("Choose: ")
        if choice == "1":
            view_contacts(contacts)
        elif choice == "2":
            add_contact(contacts)
        elif choice == "3":
            break

main()
```

<img width="272" height="134" alt="image" src="https://github.com/user-attachments/assets/6641f603-8d37-4ba6-b3f9-46f62800b23c" />


- ## Student Records Database |[Portfolio Projects](#Portfolio-Projects)
``` Python
import sqlite3

def create_database():
    """Create the database and table if they don't exist."""
    conn = sqlite3.connect("students.db")
    cursor = conn.cursor()
    cursor.execute("""
        CREATE TABLE IF NOT EXISTS students (
            id INTEGER PRIMARY KEY AUTOINCREMENT,
            name TEXT NOT NULL,
            score REAL NOT NULL
        )
    """)
    conn.commit()
    conn.close()

def add_student(name, score):
    conn = sqlite3.connect("students.db")
    cursor = conn.cursor()
    cursor.execute("INSERT INTO students (name, score) VALUES (?, ?)", (name, score))
    conn.commit()
    conn.close()
    print(f"Added {name} with score {score}.")

def view_all_students():
    conn = sqlite3.connect("students.db")
    cursor = conn.cursor()
    cursor.execute("SELECT id, name, score FROM students ORDER BY score DESC")
    rows = cursor.fetchall()
    conn.close()
    
    if not rows:
        print("No records found.")
        return
    
    print("\n=== All Students ===")
    print(f"{'ID':<5} {'Name':<20} {'Score':<10}")
    print("-" * 35)
    for row in rows:
        print(f"{row[0]:<5} {row[1]:<20} {row[2]:<10}")

def search_student(name):
    conn = sqlite3.connect("students.db")
    cursor = conn.cursor()
    cursor.execute("SELECT * FROM students WHERE name LIKE ?", (f"%{name}%",))
    results = cursor.fetchall()
    conn.close()
    
    if not results:
        print(f"No student found with name '{name}'.")
    else:
        for r in results:
            print(f"ID: {r[0]}, Name: {r[1]}, Score: {r[2]}")

def main():
    create_database()
    
    while True:
        print("\n=== Student Records ===")
        print("1. View all  2. Add student  3. Search  4. Exit")
        choice = input("Choose: ")
        
        if choice == "1":
            view_all_students()
        elif choice == "2":
            name = input("Name: ")
            score = float(input("Score: "))
            add_student(name, score)
        elif choice == "3":
            name = input("Search name: ")
            search_student(name)
        elif choice == "4":
            break

main()
```

<img width="317" height="268" alt="image" src="https://github.com/user-attachments/assets/0889f7d6-eea8-4653-af99-0b355c1c3970" />



