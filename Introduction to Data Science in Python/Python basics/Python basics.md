# Python Basics
![image](https://github.com/fatihilhan42/Data_Science_Journey/assets/63750425/cf6e5e32-47c5-4d1f-b066-1bd1c1576430)


Welcome to the "Python Basics" study of the "Introduction to Data Science in Python" folder of the Data Science Journey repository! In this study, you will learn the fundamentals of the Python programming language. Specifically, you will learn about:

## Variables
A variable is a named location in memory where you can store a value. In Python, you can create a variable by assigning a value to it using the assignment operator (=). For example:

```Python
x = 10
y = "Hello, World!"
```

In the above example, x is a variable of type int (integer) with a value of 10, and y is a variable of type str (string) with a value of 
"Hello, World!". Python is a dynamically-typed language, which means that the type of a variable is determined by the value it is assigned.

## Data types
Python has several built-in data types, including:

int: An integer is a whole number, such as 0, 1, or -42.
float: A float is a number with a decimal point, such as 3.14 or -2.718.
str: A string is a sequence of characters, such as "hello" or "goodbye".
bool: A boolean is a value that can be either True or False.
NoneType: The value None represents the absence of a value and is of type NoneType.
You can check the type of a value using the type function:

```Python
print(type(10))       # int
print(type(3.14))     # float
print(type("hello"))  # str
print(type(True))     # bool
print(type(None))     # NoneType
```

## Operators
Python has several built-in operators that you can use to perform various operations on values. Some common operators include:

- Arithmetic operators: +, -, *, /, % (modulo), and ** (exponentiation).
- Comparison operators: == (equal to), != (not equal to), > (greater than), < (less than), >= (greater than or equal to), and <= (less than or equal to).
- Logical operators: and, or, and not.


Here are some examples of using these operators:
```Python

print(2 + 3)       # 5
print(5 - 3)       # 2
print(2 * 3)       # 6
print(6 / 3)       # 2.0
print(5 % 3)       # 2
print(2 ** 3)      # 8

print(2 == 3)      # False
print(2 != 3)      # True
print(2 > 3)       # False
print(2 < 3)       # True
print(2 >= 3)      # False
print(2 <= 3)      # True

print(True and False)  # False
print(True or False)   # True
print(not True)       # False
```
## Control structures

Control structures are statements that control the flow of execution of a program. Python has several built-in control structures, including:

- if statements: An if statement allows you to execute a block of code only if a certain condition is true. For example:

```Python
x = 10
if x > 5:
    print("x is greater than 5")
```

You can also use elif clauses to check for multiple conditions, and an else clause to specify a default action:

```Python
x = 10
if x > 15:
    print("x is greater than 15")
elif x > 5:
    print("x is greater than 5 but less than or equal to 15")
else:
    print("x is less than or equal to 5")

- for loops: A for loop allows you to iterate over a sequence of values, such as a list or a string. For example:

for i in range(5):
    print(i)
```
The above code will print the numbers 0 through 4. You can also iterate over a list:
```Python
colors = ['red', 'green', 'blue']
for color in colors:
    print(color)
```
- while loops: A while loop allows you to execute a block of code repeatedly as long as a certain condition is true. For example:

```Python
x = 0
while x < 5:
    print(x)
    x += 1
```
The above code will print the numbers 0 through 4.


## Functions

A function is a block of code that performs a specific task and can be reused multiple times. In Python, you can define a function using the def keyword, followed by the function name and a list of arguments in parentheses. For example:

```Python

def greet(name):
    print("Hello, " + name + "!")

greet("Alice")  # prints "Hello, Alice!"
greet("Bob")    # prints "Hello, Bob!"
```

You can also specify default values for arguments, which allows the caller to omit those arguments if they wish:

```Python

def greet(name, greeting="Hello"):
    print(greeting + ", " + name + "!")

greet("Alice")       # prints "Hello, Alice!"
greet("Bob", "Hi")   # prints "Hi, Bob!"
```

## Modules

A module is a file containing Python definitions and statements that can be imported into other Python files. You can use the import statement to import a module, and then access its definitions and statements using the . operator. For example:

```Python
import math

x = math.sqrt(4)  # x is 2.0
y = math.sin(0)   # y is 0.0
```

You can also use the from statement to import specific definitions and statements from a module, like this:

```Python

from math import sqrt

x = sqrt(4)  # x is 2.0
```


## Exception handling

Exception handling allows you to handle errors and exceptions that occur in your code. In Python, you can use the try and except statements to catch and handle exceptions. For example:


```Python

try:
    x = int("foo")
except ValueError:
    print("Could not convert string to integer")
```

The above code will print "Could not convert string to integer" because the string "foo" cannot be converted to an integer. You can also catch multiple exception types by specifying multiple except clauses:

```Python
try:
    x = int("foo")
except ValueError:
    print("Could not convert string to integer")
except TypeError:
    print("Invalid type for conversion")
```

You can also use the finally clause to specify a block of code that will always be executed, regardless of whether an exception occurs:

```Python
try:
    x = int("foo")
except ValueError:
    print("Could not convert string to integer")
finally:
    print("This will always be executed")
```

That concludes the **"Python Basics"** study. 
I hope you have learned the fundamentals of the Python programming language and are ready to start using it for data science tasks.



