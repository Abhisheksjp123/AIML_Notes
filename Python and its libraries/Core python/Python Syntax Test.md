Answer these questions to revise all the major syntaxes in python. Unveil the answer to


## Print Function
Q1. How do you print multiple values in a single print statement?
```
name = "Alice"
age = 25
# Print both name and age
```

>[!Ans]- 
>Print(name, age)
>We can print multiple values in print function

Q2. How would you change the separator in the print statement to use a hyphen (-) instead of space?
```
print("apple", "banana", "cherry")
```
>[!Ans]- 
>print("apple", "banana", "cherry", sep = "-")
>sep attribute determines separator in multi print

Q3. What does this code print?
```
print("Hello", end="")
print("World")
```
>[!Ans]-
>HelloWorld
>End attribute defines how a print statement ends
>Its Default value is "\n" that is new line

Q4. What will this code output?
```
items = ["apple", "banana", "cherry"] 
print(*items)
```
>[!Ans]-
>apple banana cherry
>The asterisk (`*`) is the **unpacking operator**.
>`*items` unpacks the list and passes each element as a separate argument to the `print()`function.
>print(*items, sep=", ")

Q5. Complete using f-strings:
```
name = "Emma" 
score = 95.5 
print(f"?") # Output: "Emma scored 95.5 points"
```

>[!Ans]-
>print(f"{name} scored {score}points")
>To complete the f-string in your code, you can insert the variables `name` and `score` directly inside the curly braces `{}` within the string.
>

Q6. What's the output?
```
price = 19.99 
print(f"Price: ${price:.1f}")
```
>[!Ans]-
>`f"..."` is an **f-string**.
>`{price:.1f}` means:
> Format the `price` value as a **floating-point number** with **1 digit after the decimal point**.
> So `19.99` becomes `20.0` (due to rounding).

Q7. How do you print quotes inside a string?
```
# Print: She said "Hello World"
```
>[!Ans]-
>Option 1: Using single quotes to wrap the string
>print('She said "Hello World"')
>Option 2: Encapsulating double quotes inside the string with backward slash
>print("She said \"Hello World\"")


Q8. What happens with this code?
```
print("First line\nSecond line\tTabbed")
```
>[!Ans]-
>First line
>Second line    Tabbed
>Backward slash prompts python to use operation after that


# Data Types
### Basic Data type
Q1. Which of the following is NOT a basic data type in Python?
- a) int
- b) float
- c) char
- d) bool

>[!Ans]-
>C
>While Python has many built-in data types, there are **four primary or “basic” data types** that are most fundamental and frequently used:
>1. **int** – used for integers (e.g., 10, -3)
>2. **float** – used for decimal or real numbers (e.g., 3.14, 0.0)
>3. **bool** – used for boolean values (True, False)
>4. **str** – used for strings or text (e.g., "hello", 'A')

Q2. What is the output of `type(3.14)`?
- a) `<class 'int'>`
- b) `<class 'float'>`
- c) `<class 'decimal'>`
- d) `<class 'number'>`

>[!Ans]-
>b
>The type() function in Python is used to **determine the data type** of a value or variable.


### Strings
Q3. - Which of the following creates a multi-line string in Python?
    - a) 'Hello\nWorld'
    - b) """Hello World"""
    - c) 'Hello' + 'World'
    - d) All of the above
>[!Ans]-
>a
>n after backward slash \n is an indicator for change line in string


Q4. What is the output of `"Python"[2]`?

- a) P
- b) y
- c) t
- d) h

>[!Ans]-
>c
>indexing in python starts from 0
>[] can be used to access values in the string just like list


Q5. Which method converts a string to uppercase?
- a) upper()
- b) uppercase()
- c) toUpper()
- d) capitalize()

>[!Ans]-
>a
>.upper() is a method/function of sting class

## Container Datatype
### Lists

Q6. Which of the following correctly creates an empty list?
    - a) list = {}
    - b) list = []
    - c) list = ()
    - d) list = ""

>[!Ans]-
>b

Q7. What is the output of `[1, 2, 3] + [4, 5]`?

- a) [1, 2, 3, 4, 5]
- b) [5, 7, 8]
- c) Error
- d) [1, 2, 3][4, 5]

>[!Ans]-
>a
>.append() method can be used to add any single value as an element to the list
>lst = [1, 2, 3]
>lst.append([4, 5])
>print(lst)
>[1, 2, 3, [4, 5]]
>.extend() method can be used similar to the question to extend a list
>lst = [1, 2, 3]
>lst.extend([4, 5])
>print(lst)
>[1, 2, 3, 4, 5]

### Tuples
Q1. What makes tuples different from lists?
    - a) Tuples are mutable
    - b) Tuples are immutable
    - c) Tuples can only store numbers
    - d) Tuples are slower than lists

>[!Ans]-
>b
>- **Tuples** are **immutable**, meaning **you cannot change, add, or remove** elements once the tuple is created.

Q2. Which of the following creates a tuple with one element?
- a) (5)
- b) (5,)
- c) [5]
- d) {5}

>[!Ans]-
>a
>() is used to create a tuple


### Dictionary
Q1. Which of the following creates an empty dictionary?

- a) dict = []
- b) dict = {}
- c) dict = ()
- d) dict = ""

>[!Ans]-
>{} Creates a Dict


Q2. What happens if you try to access a key that doesn't exist in a dictionary?

- a) Returns None
- b) Returns empty string
- c) Raises KeyError
- d) Returns 0

>[!Ans]-
>In Python, if you try to access a dictionary using a key that **does not exist**, it will raise a **KeyError**.
>You can use the .get() method, which **returns None** (or a default value you provide) **instead of raising an error**:


Q3. Which method returns all keys in a dictionary?

- a) keys()
- b) getKeys()
- c) allKeys()
- d) keyList()

>[!Ans]-
> a
> the **keys()** method is used to **return a view of all the keys** in a dictionary.
> my_dict = {'name': 'Alice', 'age': 25}
> print(my_dict.keys())
> dict_keys(['name', 'age'])
> list(my_dict.keys())  # ➝ ['name', 'age'] you can convert to list if needed


### Sets
Q1. What is a key characteristic of sets in Python?

- a) They store duplicate values
- b) They are ordered
- c) They store unique values only
- d) They can only store numbers

>[!Ans]-
>C
> A **set** in Python is a **collection of unordered and unique elements**. This means:
> **No duplicate values** are allowed.
> The order of elements is **not guaranteed**.>
> Sets can contain **any [[hashable type]]** (numbers, strings, tuples, etc.), **not just numbers**.


Q2. Which operator finds the intersection of two sets?

- a) +
- b) &
- c) |
- d) -
>[!Ans]-
>b
>- **a) +** – Invalid for sets; causes a TypeError 
>- **c) |** – Performs **union** (all elements from both sets)
>- **d) -** – Performs **difference** (elements in one set but not the other)


Q3. How do you add an element to a set?

- a) append()
- b) insert()
- c) add()
- d) push()

>[!Ans]-
> C Add, To add a single element to a **set** in Python, you use the **add()** method.
>- **a) append()** – Used for **lists**, not sets.
>- **b) insert()** – Also a **list method** (adds at a specific index).  
>- **d) push()** – Not a Python method; used in stack operations in other languages.

Q4. Which creates an empty set?** 
a) `{}`  
b) `set()`  
c) `[]`  
d) `()`
### Type Conversion

Q1. Which function converts a number to a string?

- a) string()
- b) str()
- c) toString()
- d) convert()

>[!Ans]-
>b
>In Python, the **str()** function is used to **convert numbers (and other data types) into strings**.


## Variables
Q1. Which of the following is a valid variable name in Python?

- a) 2variable
- b) variable-2
- c) variable_2
- d) variable 2

>[!Ans]-
>c
>In Python, a valid variable name:
>Must start with a letter (A–Z or a–z) or an underscore (_)
>Can be followed by letters, numbers (0–9), or underscores
>Cannot contain spaces or special characters like `-`
   Cannot start with a digit

Q2. What is the output
```
a, b, c = 1, 2, 3 
print(a + b + c)
```
>[!Ans]-
> We can define multiple variables in a single line in python as
> a, b, c = 1, 2, 3 
> Or 
> a=1; b=2; c=3
## Keywords
**Keywords** in Python are special **reserved words** that have specific meanings and purposes within the language's syntax. These words form the core of Python's structure and logic and cannot be used for any other purpose, such as naming variables, functions, classes, or any identifiers
Q1. How many keywords are there in Python 3.9+?

- a) 33
- b) 35
- c) 37
- d) 39

>[!Ans]-
>C
>import keyword
>print(leyword.kwlist)
>False, True, None, and, or, not, if, elif, else, while, for, break, continue, return, is, in, def, class,
> try, except, raise, finally, import, from, as, global, nonlocal, lambda, yield, assert, pass, del, with, await, async


## Identifiers
A Python identifier is a name used to identify a variable, function, class, module or other object.
Rules for setting Identifiers
• can only start with an alphabet or
• Followed by 0 or more letter,_ and digits
• keywords cannot be used as an Identifiers

Q1. A variable that starts with double underscore (Ex.` __varname`) is called a _______ variable.

>[!Ans]-
>A variable that starts with double underscore (`__`) is called a **name-mangled variable** or a **private variable** in Python (often referred to as a _name-mangled_ or _"pseudo-private"_variable)
>When you define a variable or method inside a class with a double leading underscore (e.g., `__varname`), the Python interpreter automatically performs **name mangling**: it internally renames the attribute to `_ClassName__varname` to help avoid accidental access and override in subclasses
>The main purpose is **to avoid naming conflicts in subclasses** and to make the variable less accessible from outside the class, simulating privacy
>class MyClass: 
>	def __init__(self): 
>		self.__private = 42 
>obj = MyClass()
># obj.__private # AttributeError 
>print(obj._MyClass__private) # 42
>Note: This is different from variables with double underscores at both the start and end (e.g., `__init__`), which are called _special methods_ or _dunder methods_, not name-mangled variables

## Input in python

Q1. Which function is used to take input from the user in Python 3?

- a) input()
- b) raw_input()
- c) get_input()
- d) read()

>[!Ans]-
> a, input()

Q2. What data type does the `input()` function always return?

- a) int
- b) float
- c) str
- d) depends on input

>[!Ans]-
>C Str


Q3. How do you display a prompt message when taking input?

- a) input("Enter value: ")
- b) input() + "Enter value: "
- c) prompt("Enter value: ")
- d) input.prompt("Enter value: ")
>[!Ans]-
>a)input("Enter value: ")

Q4. Which module is used for password input (hidden input)?

- a) password
- b) getpass
- c) hidden
- d) secure

>[!Ans]-
>**b) getpass**
>The module used for password input (hidden input) in Python is **getpass**. The `getpass` module allows you to prompt the user for a password without echoing what they type, keeping the input hidden for security purposes
### Input validation
Q1. Which method checks if a string contains only digits?

- a) isdigit()
- b) isnumber()
- c) isint()
- d) isnumeric()

>[!Ans]-
>The method that checks if a string contains only digits in Python is **`isdigit()`**.
>**`isdigit()`** returns `True` if all characters in the string are digits (0-9) and the string is not empty, otherwise it returns `False`


Q2. How do you check if input is a valid float?

- a) isfloat()
- b) try-except with float()
- c) input().isreal()
- d) validate_float()

>[!Ans]-
>**b) try-except with float()**
>Python does **not** have a built-in method like `isfloat()` to directly check if a string input is a valid float
>The recommended way is to use a `try-except` block: try converting the input to a float using `float(input())`. If it **succeeds**, the input is a valid float; if it raises a `ValueError`, it is not

## Literal
Literal are basically raw data given to a variable. 
In python there are 4 types of literals
- Numeric
- String
- Boolean
- Special
### Numeric literal
Q1. Which of the following represents the number 255 in hexadecimal?
a) 0x255  
b) 0xFF  
c) 0o255  
d) 0b255

>[!Ans]-


Q2. **4. Which literal represents a complex number?**
a) 3.14i  
b) 3 + 4j  
c) complex(3,4)  
d) Both b and c

### String Literal
Q1. ## String Literals

Q1. Which of these creates a raw string?** 
a) `"C:\new\folder"`  
b) `r"C:\new\folder"`  
c) `raw"C:\new\folder"`  
d) `\r"C:\new\folder"`

**Q2. What type is `b"hello"`?** 
a) str  
b) bytes  
c) bytearray  
d) binary

Q**3. Which is NOT a valid way to create a multi-line string?** 
a) `"""line1\nline2"""`  
b) `'''line1\nline2'''`  
c) `"line1\nline2"`  
d) `""line1\nline2""`

Q4. Which literal creates the largest number?** a) `1e6`  
b) `1000000`  
c) `0x100000`  
d) All are equal

Q5. Which is equivalent to `[0, 0, 0, 0, 0]`?
a) `[0] * 5`  
b) `0 * [5]`  
c) `[0 * 5]`  
d) `list(0, 5)`