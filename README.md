# Complete Python Tutorial for Absolute Beginners

## Table of Contents
1. [Terminal/Bash Basics](#terminal-bash-basics)
2. [Package Managers: pip vs uv](#package-managers-pip-vs-uv)
3. [Virtual Environments](#virtual-environments)
4. [Python Data Types](#python-data-types)
5. [Printing and Variables](#printing-and-variables)
6. [Taking User Input](#taking-user-input)
7. [Type Conversion](#type-conversion)
8. [Running Python Files](#running-python-files)
9. [Next Steps](#next-steps)

---

## Terminal/Bash Basics

### Essential Terminal Commands

Before we start coding, you need to know how to navigate your computer using the terminal (Git Bash).

| Command | Purpose | Example |
|---------|---------|---------|
| `ls` | List files and folders in current directory | `ls` |
| `cd foldername` | Change into a specific folder | `cd Documents` |
| `cd ..` | Go back one folder (parent directory) | `cd ..` |
| `cd ../..` | Go back two folders | `cd ../..` |
| `cd ~` | Go to home directory | `cd ~` |
| `clear` | Clear the terminal screen | `clear` |
| `rm filename` | Remove/delete a file | `rm myfile.txt` |
| `rm -rf foldername` | Remove folder and all contents | `rm -rf myfolder` |
| `mkdir foldername` | Create a new folder | `mkdir python_projects` |

### ⚠️ **Important Warning**
- `rm` permanently deletes files - they don't go to trash!
- `rm -rf *` will delete EVERYTHING in the current folder - be very careful!

### Navigation Examples
```bash
# Check where you are
pwd

# See what's in current folder
ls

# Go into a folder called "projects"
cd projects

# Go back to parent folder
cd ..

# Go to your home directory
cd ~

# Clear the screen
clear
```

---

## Package Managers: pip vs uv

### What is a Package Manager?
A package manager is a tool that helps you install, update, and manage software libraries (packages) for your programming language.

### pip vs uv Comparison

| Feature | pip | uv |
|---------|-----|-----|
| **Speed** | Slower | Much faster (10-100x) |
| **Default in Python** | Yes | No (needs installation) |
| **Dependency Resolution** | Basic | Advanced |
| **Disk Usage** | Higher | Lower |
| **Learning Curve** | Easier | Slightly steeper |
| **Compatibility** | Universal | Modern Python versions |

### When to Use Each

| Situation | Use pip | Use uv |
|-----------|---------|---------|
| Just starting Python | ✅ | ❌ |
| Large projects | ❌ | ✅ |
| Working in team | ❌ | ✅ |
| Need maximum speed | ❌ | ✅ |
| Simple scripts | ✅ | ✅ |

**Recommendation for beginners**: Start with `pip`, then try `uv` later when you're comfortable.

---

## Virtual Environments

### Why Use Virtual Environments?
- Keep different projects separate
- Avoid conflicts between package versions
- Make projects portable

### Creating Virtual Environments

#### Using pip (venv)
```bash
# Create virtual environment
python -m venv .venv

#### Using uv
```bash
# Install uv first (if not installed)
pip install uv

# Create virtual environment
uv venv .venv
```

### Activating Virtual Environment

**For Git Bash (Windows):**
```bash
# Activate the virtual environment
. .venv/Scripts/activate
```


### How to Know if Virtual Environment is Active

| Indicator | What to Look For |
|-----------|------------------|
| **Command Prompt** | Shows `(.venv)` at the beginning |
| **Python Path** | `which python` points to .venv folder |

```bash
# Check if active - you should see (.venv) before your prompt
(.venv) user@computer:~/project$ 

# Verify python location
which python
# Should show: /path/to/your/project/.venv/Scripts/python
```

### Deactivating Virtual Environment
```bash
deactivate
```

---

## Python Data Types

### Basic Data Types with Examples

| Data Type | Description | Example | Python Code |
|-----------|-------------|---------|-------------|
| **Integer** | Whole numbers | 42, -17, 0 | `age = 25` |
| **Float** | Decimal numbers | 3.14, -2.5, 0.0 | `price = 19.99` |
| **String** | Text | "Hello", 'Python' | `name = "Alice"` |
| **Boolean** | True/False | True, False | `is_student = True` |
| **List** | Ordered collection | [1, 2, 3] | `numbers = [1, 2, 3]` |

### Example Code
```python
# Integer
age = 25
student_count = 100

# Float
price = 29.99
temperature = -5.5

# String
name = "John"
message = 'Hello World!'

# Boolean
is_active = True
has_license = False

# List
fruits = ["apple", "banana", "orange"]
numbers = [1, 2, 3, 4, 5]

# Check type of variable
print(type(age))        # <class 'int'>
print(type(price))      # <class 'float'>
print(type(name))       # <class 'str'>
print(type(is_active))  # <class 'bool'>
```

---

## Printing and Variables

### Basic Printing
```python
# Simple print
print("Hello World!")
print('Single quotes work too!')

# Printing variables
name = "Alice"
age = 30

print(name)
print(age)

# Printing multiple items
print("Name:", name, "Age:", age)

# Using f-strings (modern way)
print(f"My name is {name} and I am {age} years old")

# Using .format() method
print("My name is {} and I am {} years old".format(name, age))
```

### Variable Examples
```python
# Numbers
score = 95
average = 87.5

# Text
first_name = "John"
last_name = "Doe"
full_name = first_name + " " + last_name

# Boolean
is_passing = True
is_weekend = False

# Print everything
print(f"Student: {full_name}")
print(f"Score: {score}")
print(f"Average: {average}")
print(f"Passing: {is_passing}")
```

---

## Taking User Input

### Basic Input
```python
# Basic input (always returns string)
name = input()
print(f"Hello {name}!")

# Input with custom prompt
name = input("What is your name? ")
print(f"Nice to meet you, {name}!")

age = input("How old are you? ")
print(f"You are {age} years old")
```

### Input Examples
```python
# Getting different types of information
name = input("Enter your name: ")
favorite_color = input("What's your favorite color? ")
hobby = input("What's your hobby? ")

# Display the information
print("\n--- Your Information ---")
print(f"Name: {name}")
print(f"Favorite Color: {favorite_color}")
print(f"Hobby: {hobby}")

# Note: input() always returns a string!
age_string = input("Enter your age: ")
print(f"Type of age: {type(age_string)}")  # <class 'str'>
```

---

## Type Conversion

### Common Type Conversions

| From | To | Function | Example |
|------|----|---------|---------| 
| String | Integer | `int()` | `int("42")` → `42` |
| String | Float | `float()` | `float("3.14")` → `3.14` |
| Integer | String | `str()` | `str(42)` → `"42"` |
| Float | String | `str()` | `str(3.14)` → `"3.14"` |
| Integer | Float | `float()` | `float(42)` → `42.0` |
| Float | Integer | `int()` | `int(3.14)` → `3` |
| String | Boolean | `bool()` | `bool("hello")` → `True` |
| Any | Boolean | `bool()` | `bool(0)` → `False` |

### Conversion Examples
```python
# String to number conversion
age_string = input("Enter your age: ")
age_number = int(age_string)
print(f"Next year you'll be {age_number + 1}")

# Number to string conversion
score = 95
message = "Your score is " + str(score)
print(message)

# Float conversions
price_string = "19.99"
price_float = float(price_string)
print(f"Price with tax: {price_float * 1.1}")

# Integer to float
whole_number = 10
decimal_number = float(whole_number)
print(decimal_number)  # 10.0

# Float to integer (loses decimal part)
decimal = 3.99
whole = int(decimal)
print(whole)  # 3
```

### Common Conversion Errors
```python
# These will cause errors:
# int("hello")      # ValueError
# int("3.14")       # ValueError (use float() first)
# float("abc")      # ValueError

# Safe conversion example
user_input = input("Enter a number: ")
try:
    number = int(user_input)
    print(f"Your number doubled: {number * 2}")
except ValueError:
    print("That's not a valid number!")
```

---

## Running Python Files

### Step-by-Step Process

1. **Navigate to the correct folder**
   ```bash
   # Check where you are
   pwd
   
   # See available files
   ls
   
   # Go to your project folder
   cd my_python_project
   ```

2. **Create a Python file**
   ```bash
   # Create a new Python file (using text editor)
   # Or just create it in your code editor
   ```

3. **Write your Python code**
   ```python
   # Save this as hello.py
   print("Hello World!")
   name = input("What's your name? ")
   print(f"Nice to meet you, {name}!")
   ```

4. **Run the Python file**
   ```bash
   # Make sure you're in the right folder
   ls
   # Should show: hello.py
   
   # Run the file
   python hello.py
   
   # Alternative (if python doesn't work)
   python3 hello.py
   ```

### Complete Example Workflow
```bash
# 1. Clear terminal and check location
clear
pwd

# 2. Create project folder and navigate
mkdir my_first_python_project
cd my_first_python_project

# 3. Create virtual environment
python -m venv .venv

# 4. Activate virtual environment
. .venv/Scripts/activate

# 5. Check if activated (should see (.venv) in prompt)
# (.venv) user@computer:~/my_first_python_project$ 

# 6. Create and run Python file
ls  # check files
python calculator.py  # run your file

# 7. When done, deactivate
deactivate
```

### Sample Python File to Try
Create a file called `first_program.py`:
```python
# first_program.py
print("=== My First Python Program ===")

# Get user information
name = input("What's your name? ")
age_string = input("How old are you? ")

# Convert age to number
age = int(age_string)

# Calculate and display info
next_year = age + 1
print(f"\nHello {name}!")
print(f"You are currently {age} years old")
print(f"Next year you will be {next_year} years old")

# Fun fact
days_lived = age * 365
print(f"You have lived approximately {days_lived} days!")
```

Run it with:
```bash
python first_program.py
```

---

## Next Steps

### What You've Learned
- ✅ Terminal navigation and file management
- ✅ Package managers (pip and uv)
- ✅ Virtual environments
- ✅ Python data types
- ✅ Variables and printing
- ✅ User input
- ✅ Type conversion
- ✅ Running Python programs


### Practice Exercises
Try creating these simple programs:

1. **Age Calculator**: Ask birth year, calculate current age
2. **Simple Calculator**: Add, subtract, multiply, divide two numbers
3. **Temperature Converter**: Convert Celsius to Fahrenheit
4. **Shopping List**: Take multiple items and display them

### Useful Commands to Remember
```bash
# Terminal shortcuts
clear              # Clear screen
ls                # List files
cd folder_name    # Change directory
cd ..             # Go back
python file.py    # Run Python file

# Virtual environment
python -m venv .venv              # Create
. .venv/Scripts/activate          # Activate (Git Bash)
deactivate                        # Deactivate
```

---

**Remember**: Programming is learned by doing! Don't worry about memorizing everything - focus on understanding the concepts and practicing with code. The more you practice, the more natural it becomes.

Good luck with your Python journey! 🐍
