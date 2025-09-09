# Python Intermediate Guide: Conditionals, Loops & Functions

## Table of Contents
1. [Conditional Statements (if/else)](#conditional-statements)
2. [Loops](#loops)
3. [Functions](#functions)
4. [Practice Projects](#practice-projects)

---

## Conditional Statements

Conditional statements allow your program to make decisions based on certain conditions. Think of them as "if this happens, do that" instructions.

### Basic if Statement

```python
age = 18

if age >= 18:
    print("You can vote!")
```

**How it works:** The code after `if` only runs when the condition is `True`.

### if-else Statement

```python
age = 16

if age >= 18:
    print("You can vote!")
else:
    print("You're too young to vote.")
```

### if-elif-else Statement

When you have multiple conditions to check:

```python
score = 85

if score >= 90:
    print("Grade: A")
elif score >= 80:
    print("Grade: B")
elif score >= 70:
    print("Grade: C")
else:
    print("Grade: F")
```

### Comparison Operators

- `==` Equal to
- `!=` Not equal to
- `>` Greater than
- `<` Less than
- `>=` Greater than or equal to
- `<=` Less than or equal to

### Logical Operators

- `and` - Both conditions must be True
- `or` - At least one condition must be True
- `not` - Reverses the condition

```python
age = 25
has_license = True

if age >= 18 and has_license:
    print("You can drive!")

weather = "sunny"
if weather == "sunny" or weather == "cloudy":
    print("Good day for a walk!")
```

### Use Cases for Conditionals

1. **User Input Validation**
```python
password = input("Enter password: ")
if len(password) >= 8:
    print("Strong password!")
else:
    print("Password too short!")
```

2. **Game Logic**
```python
player_choice = "rock"
computer_choice = "scissors"

if player_choice == computer_choice:
    print("It's a tie!")
elif (player_choice == "rock" and computer_choice == "scissors") or \
     (player_choice == "paper" and computer_choice == "rock") or \
     (player_choice == "scissors" and computer_choice == "paper"):
    print("You win!")
else:
    print("Computer wins!")
```

---

## Loops

Loops allow you to repeat code multiple times without writing it over and over again.

### for Loops

Use `for` loops when you know how many times you want to repeat something or when iterating through a collection.

#### Basic for Loop with range()

```python
# Print numbers 0 to 4
for i in range(5):
    print(i)

# Print numbers 1 to 5
for i in range(1, 6):
    print(i)

# Print even numbers from 0 to 10
for i in range(0, 11, 2):
    print(i)
```

#### Looping Through Lists

```python
fruits = ["apple", "banana", "orange"]

for fruit in fruits:
    print(f"I like {fruit}")
```

#### Looping Through Strings

```python
word = "Python"

for letter in word:
    print(letter)
```

### while Loops

Use `while` loops when you want to repeat something until a condition becomes False.

```python
count = 0

while count < 5:
    print(f"Count is: {count}")
    count += 1  # Same as count = count + 1
```

#### User Input with while Loop

```python
answer = ""

while answer != "yes":
    answer = input("Do you want to continue? (yes/no): ").lower()
    
print("Great! Continuing...")
```

### Loop Control Statements

#### break - Exit the loop early

```python
for i in range(10):
    if i == 5:
        break  # Stop the loop when i equals 5
    print(i)
```

#### continue - Skip to next iteration

```python
for i in range(5):
    if i == 2:
        continue  # Skip printing when i equals 2
    print(i)
```

### Use Cases for Loops

1. **Processing Data**
```python
numbers = [1, 2, 3, 4, 5]
total = 0

for num in numbers:
    total += num

print(f"Sum: {total}")
```

2. **Menu Systems**
```python
while True:
    print("\n1. Play Game")
    print("2. View Scores")
    print("3. Exit")
    
    choice = input("Choose an option: ")
    
    if choice == "1":
        print("Starting game...")
    elif choice == "2":
        print("Showing scores...")
    elif choice == "3":
        print("Goodbye!")
        break
    else:
        print("Invalid choice!")
```

---

## Functions

Functions are reusable blocks of code that perform specific tasks. They help organize your code and avoid repetition.

### Defining Functions

```python
def greet():
    print("Hello, World!")

# Call the function
greet()
```

### Functions with Parameters

```python
def greet_person(name):
    print(f"Hello, {name}!")

greet_person("Alice")
greet_person("Bob")
```

### Functions with Multiple Parameters

```python
def add_numbers(a, b):
    result = a + b
    print(f"{a} + {b} = {result}")

add_numbers(5, 3)
add_numbers(10, 7)
```

### Functions that Return Values

```python
def multiply(x, y):
    return x * y

result = multiply(4, 5)
print(result)  # Output: 20

# You can use the returned value directly
print(f"Double of 6 is: {multiply(6, 2)}")
```

### Default Parameters

```python
def greet_with_title(name, title="Mr."):
    print(f"Hello, {title} {name}!")

greet_with_title("Smith")           # Uses default title "Mr."
greet_with_title("Johnson", "Dr.")  # Uses provided title "Dr."
```

### Functions with Variable Arguments

```python
def calculate_average(*numbers):
    if len(numbers) == 0:
        return 0
    return sum(numbers) / len(numbers)

print(calculate_average(1, 2, 3, 4, 5))  # Can pass any number of arguments
print(calculate_average(10, 20))
```

### Local vs Global Variables

```python
global_var = "I'm global"

def my_function():
    local_var = "I'm local"
    print(global_var)  # Can access global variable
    print(local_var)   # Can access local variable

my_function()
# print(local_var)  # This would cause an error - local_var doesn't exist here
```

### Use Cases for Functions

1. **Input Validation**
```python
def is_valid_email(email):
    return "@" in email and "." in email

user_email = input("Enter your email: ")
if is_valid_email(user_email):
    print("Valid email!")
else:
    print("Invalid email!")
```

2. **Calculations**
```python
def calculate_tip(bill_amount, tip_percentage=15):
    tip = bill_amount * (tip_percentage / 100)
    total = bill_amount + tip
    return tip, total

bill = 50.00
tip_amount, total_amount = calculate_tip(bill, 20)
print(f"Tip: ${tip_amount:.2f}")
print(f"Total: ${total_amount:.2f}")
```

3. **Data Processing**
```python
def count_vowels(text):
    vowels = "aeiouAEIOU"
    count = 0
    for char in text:
        if char in vowels:
            count += 1
    return count

sentence = "Hello World"
vowel_count = count_vowels(sentence)
print(f"'{sentence}' has {vowel_count} vowels")
```

---

## Practice Projects

### Project 1: Number Guessing Game

Create a game where the computer picks a random number and the user has to guess it.

**Requirements:**
- Use `import random` and `random.randint(1, 100)` to generate a random number
- Use a while loop to keep asking for guesses
- Use if/elif/else to give hints (too high, too low, correct)
- Keep track of the number of attempts
- Use functions to organize your code

**Starter Code Structure:**
```python
import random

def get_user_guess():
    # Function to get and validate user input
    pass

def check_guess(guess, target):
    # Function to compare guess with target number
    pass

def play_game():
    # Main game logic
    pass

# Start the game
play_game()
```

### Project 2: Simple Calculator

Build a calculator that can perform basic operations.

**Requirements:**
- Use functions for each operation (add, subtract, multiply, divide)
- Use a while loop to keep the calculator running
- Use if/elif/else to handle different operations
- Handle division by zero
- Allow user to exit the program

### Project 3: Student Grade Manager

Create a program to manage student grades.

**Requirements:**
- Store student names and grades in lists
- Use functions to add students, calculate averages, and find highest/lowest grades
- Use loops to process all students
- Use conditionals to assign letter grades
- Create a menu system using while loops

### Project 4: Word Counter

Build a program that analyzes text.

**Requirements:**
- Create functions to count words, characters, and sentences
- Use loops to process each character/word
- Use conditionals to identify different types of characters
- Allow user to input text or read from a string
- Display statistics in a formatted way

### Practice Tips

1. **Start Small:** Begin with simple versions of each project and add features gradually
2. **Test Frequently:** Run your code often to catch errors early
3. **Use Print Statements:** Add `print()` statements to debug and understand what your code is doing
4. **Break Down Problems:** Divide complex problems into smaller, manageable functions
5. **Practice Daily:** Spend at least 30 minutes coding each day to build muscle memory

### Common Beginner Mistakes to Avoid

1. **Forgetting Colons:** Always end if/for/while/def statements with `:`
2. **Inconsistent Indentation:** Python is sensitive to indentation - be consistent
3. **Infinite Loops:** Make sure your while loop conditions will eventually become False
4. **Not Returning Values:** Remember to use `return` in functions when you need the result
5. **Comparing vs Assignment:** Use `==` for comparison, `=` for assignment

Remember: Programming is learned by doing! Start with these concepts, practice with the projects, and don't be afraid to experiment and make mistakes. Each error is a learning opportunity!
