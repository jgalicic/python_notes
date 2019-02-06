---
tags:
  - python
  - python syntax
---

# Python Fundamentals

<br>

|         | Contents                |
| ------- | ----------------------- |
| [1](#1) | [Strings](#1)           |
| [2](#2) | [Data Types](#2)        |
| [3](#3) | [Conditionals](#3)      |
| [4](#4) | [Logical Operators](#4) |
| [5](#5) | [Loops](#5)             |
| [6](#6) | [Functions](#6)         |
| [7](#7) | [Classes](#7)           |

<br><a id="1"></a>

---

---

---

## 1. Strings

---

---

---

Printing a string:

```python
print("This is a string.") # This is a string.
```

String concatenation: (comma)

```python
name = "Zen"
print("My name is", name) # ('My name is', 'Zen')
```

String concatenation: (plus sign)

```python
name = "Zen"
print("My name is " + name) # My name is Zen
```

String Interpolation: (New style - use this)

```python
first_name = "Zen"
age = 27
print(f"My name is {first_name} and I am {age} years old.")
# My name is Zen and I am 27 years old.
```

%-Formatting: (Old style - don't use this)

```python
name = "Zen"
age = 27
print("My name is %s and I'm %d" % (name, age))
# My name is Zen and I am 27 years old.
```

String Methods:

```python
len(string)             # returns the length of the string
string.upper()          # returns a copy of the string in uppercase
string.lower()          # returns a copy of the string in lowercase
string.count(substr)    # returns num of occurrences of substring
string.split(char)      # splits string into list at given character
string.find(substr)     # finds and returns first matching index of substring
string.isalnum()        # returns boolean
string.isalpha()        # returns boolean
string.isdigit()        # returns boolean
string.islower()        # returns boolean
string.isupper()        # returns boolean
string.join(list)       # concatenates all strings passed into it
string.endswith(substr) # returns boolean
```

<br><a id="2"></a>

---

---

---

## 2. Data Types

---

---

---

Boolans

```python
is_hungry = True
is_full = False # Booleans are capitalized in Python!
```

Numbers

```python
age = 35 # storing an int
weight = 160.57 # storing a float
```

Strings

```python
name = "Joe Blue" # literal text
```

Tuples

```python
dog = ('Bruce', 'cocker spaniel', 19, False) # Tuples can contain mixed data types
print(dog[0]) # Bruce
dog[1] = 'dachshund' # ERROR: tuples are immutable and cannot be modified
```

Lists

```python
empty_list = []

numbers = ['One', 'Two', 'Three']
print(numbers[2]) # Three

numbers[0] = 'Zero'
print(numbers) # ['Zero', 'Two', 'Three']

numbers.append('Four')
print(numbers) # ['Zero', 'Two', 'Three', 'Four']

numbers.pop()
print(numbers) # ['Zero', 'Two', 'Three']

numbers.pop(1)
print(numbers) # ['Zero', 'Three']
```

Dictionaries

```python
empty_dict = {}

new_person = {
  'name': 'John',
  'age': 38,
  'weight': 160.2,
  'has_glasses': False
  }

new_person['name'] = 'Jack' # updates if the key exists
new_person['hobbies'] = ['climbing', 'coding']

print(new_person)
# {
#   'name': 'Jack',
#   'age': 38,
#   'weight': 160.2,
#   'has_glasses': False,
#   'hobbies': ['climbing', 'coding']
# }

w = new_person.pop('weight') # removes specified key and returns value
print(w) # 160.2

print(new_person)
# {
#   'name': 'Jack',
#   'age': 38,
#   'has_glasses': False,
#   'hobbies': ['climbing', 'coding']
# }

```

Type Methods

```python
type(True)    # <class 'bool'>
type(10))     # <class 'int'>
type(2.63))   # <class 'float'>
type("Hello") # <class 'str'>
type((1,2))   # <class 'tuple'>
type([1,2])   # <class 'list'>
type({'1':2}) # <class 'dict'>
```

Type Conversion

```python
print("Hello" + 42)       # TypeError
print("Hello " + str(42)) # Hello 42

total = 45
val = "2"
total = total + val       # TypeError
total = total + int(val)  # 47
```

<br><a id="3"></a>

---

---

---

## 3. Conditionals

---

---

---

If/else

```python
x = 5
if x > 10:
  print("bigger than 10")
else:
  print("smaller than 10") # smaller than 10
```

If/else-if/else

```python
y = 30
if y > 10:
  print("bigger than 10") # bigger than 10
elif y > 20:
  print("bigger than 20") # will not execute since the first statement was true
else:
  print("smaller than 20")
```

<br><a id="4"></a>

---

---

---

## 4. Logical Operators

---

---

---

<br>

| Operator | Description                                          |
| -------- | ---------------------------------------------------- |
| ==       | Equal to                                             |
| !=       | Not equal to                                         |
| >        | Greater than                                         |
| <        | Less than                                            |
| >=       | Greater than or equal to                             |
| <=       | Less than or equal to                                |
| and      | Checks if both expressions are true                  |
| or       | Checks if either expression is true                  |
| not      | Flips value of operand (true to false or vice versa) |

<br><a id="5"></a>

---

---

---

## 5. Loops

---

---

---

Basic For Loop

```python
for x in range(0, 5, 1):
  print(x) # 0, 1, 2, 3, 4
```

Shorthand variations

```python
for x in range(0, 5): # increment by +1 is implied
  print(x)             # 0, 1, 2, 3, 4

for x in range(5):    # increment by +1 & start at 0 is implied
  print(x)             # 0, 1, 2, 3, 4
```

Loop through a List

```python
my_list = ["1", 2, "3"]

for x in range(len(my_list)):
    print(x, my_list[x]) # 0 1, 1 2, 2 3

for v in my_list:
    print(v) # 1, 2, 3

```

Loop through a Dictionary

```python
my_dict = { "name": "Monty", "language": "Python" }
for k in my_dict:
    print(k) # name, language

for key, val in my_dict.items():
     print(key, " = ", val) # name = Monty, language = Python
```

While Loop

```python
num = 0

while num < 5:
    print(num)
    num += 1 # 0, 1, 2, 3, 4

print(num) # 5
```

While-Else Loop

```python
while num > 0:
    print(num)
    num -= 1
else:
    print("Done!") # 5, 4, 3, 2, 1, Done!
```

Break

```python
for val in "hello world":
  if val == "w":
    break
  print(val) # h, e, l, l, o
```

Continue

```python
for val in "hello world":
  if val == "l":
    continue
  print(val) # h, e, o, , w, o, r, d
```

<br><a id="6"></a>

---

---

---

## 6. Functions

---

---

---

Defining and calling a Function

```python
def add(a,b):
  return a + b

add(5,10) # 15
```

Default parameters

```python
def add(a=10, b=20):
  return a + b

add(5) # 25
```

<br><a id="7"></a>

---

---

---

## 6. Classes

---

---

---

Create a class:

```python
class User:
  def __init__(self, username, email_address):
    self.name = username
    self.email = email_address
    self.account_balance = 0

# create new instances of the class:
guido = User("Guido van Rossum", "guido@python.com")
monty = User("Monty Python", "monty@python.com")

# print name
print(guido.name)	# Guido van Rossum
print(monty.name)	# Monty Python
```

Using Methods:

```python
class User:
  def __init__(self, name, email):
    self.name = name
    self.email = email
    self.account_balance = 0
  def make_deposit(self, amount): # make_deposit method
    self.account_balance += amount

# run methods
guido.make_deposit(100)
guido.make_deposit(200)
monty.make_deposit(50)

# print account_balance
print(guido.account_balance) # 300
print(monty.account_balance) # 50

```

Association between classes

```python
# BankAccount will be encapsulated by the User class below
class BankAccount:
  def __init__(self, account_balance=0, interest_rate=.01):
    self.account_balance = account_balance
    self.interest_rate = interest_rate
  def deposit(self, amount):
    self.account_balance += amount
    return self

class User:
  def __init__(self, name, email):
    self.name = name
    self.email = email
    self.account = BankAccount(int_rate=0.02, balance=0)
  def example_method(self):
        self.account.deposit(100) # call the BankAccount instance's methods
    	print(self.account.account_balance)
```
