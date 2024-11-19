# R-programming

## What is R?
R is a programming language, often used for statistical computing and graphical presentation to analyze and visualize data.

## Why Use R?
- It is a great resource for data analysis, data visualization, data science and machine learning
- It provides many statistical techniques (such as statistical tests, classification, clustering and data reduction)
- It is easy to draw graphs in R, like pie charts, histograms, box plot, scatter plot, etc++
- It works on different platforms (Windows, Mac, Linux)
- It is open-source and free
- It has a large community support
- It has many packages (libraries of functions) that can be used to solve different problems

### R Syntax
Unlike many other programming languages, you can output code in R without using a print function. However, R does have a print() function available if you want to use it.
```
5+5
"Hello World!"
```
```
for (x in 1:10) {
  print(x)
}
```

### R Comments
Comments starts with a **#**. There are no syntax in R for multiline comments. However, we can just insert a # for each line to create multiline comments:
```
# This is a comment
"Hello World!" # This is a comment

# This is a comment
# written in
# more than just one line
"Hello World!"
```

### R Variables
- **Creating Variables in R:**
R does not have a command for declaring a variable. A variable is created the moment you first assign a value to it. To assign a value to a variable, use the <- sign.
```
name <- "John"
age <- 40

name   # auto-print the value of the name variable
age    # output 40
```
- **R Multiple Variables:**
R allows you to assign the same value to multiple variables in one line:
```
name <- "John"
age <- 40

name   # output "John"
age    # output 40
```

- **R Concatenate Elements:**
You can also concatenate, or join, two or more elements, by using the `paste()` function. To combine both text and a variable, R uses comma (,):
```
text <- "awesome"

paste("R is", text)
```
```
text1 <- "R is"
text2 <- "awesome"

paste(text1, text2)
```

- **R Variable Names (Identifiers):**
A variable can have a short name (like x and y) or a more descriptive name (age, carname, total_volume). Rules for R variables are:
  - A variable name must start with a letter and can be a combination of letters, digits, period(.)
and underscore(_). If it starts with period(.), it cannot be followed by a digit.
  - A variable name cannot start with a number or underscore (_)
  - Variable names are case-sensitive (age, Age and AGE are three different variables)
  - Reserved words cannot be used as variables (TRUE, FALSE, NULL, if...)

### R Data Types
Basic data types in R can be divided into the following types:
- **numeric** - (10.5, 55, 787)
- **integer** - (1L, 55L, 100L, where the letter "L" declares this as an integer)
- **complex** - (9 + 3i, where "i" is the imaginary part)
- **character** (a.k.a. string) - ("k", "R is exciting", "FALSE", "11.5")
- **logical** (a.k.a. boolean) - (TRUE or FALSE)

We can use the `class()` function to check the data type of a variable:

```
# numeric
x <- 10.5
class(x)

# integer
x <- 1000L
class(x)

# complex
x <- 9i + 3
class(x)

# character/string
x <- "R is exciting"
class(x)

# logical/boolean
x <- TRUE
class(x)
```

### R Numbers
There are three number types in R:
- numeric
- integer
- complex

You can convert from one type to another with the following functions:
- as.numeric()
- as.integer()
- as.complex()
```
x <- 1L # integer
y <- 2 # numeric

# convert from integer to numeric:
a <- as.numeric(x)

# convert from numeric to integer:
b <- as.integer(y)

# print values of x and y
x
y

# print the class name of a and b
class(a)
class(b)
```

### R Math
R also has many built-in math functions that allows you to perform mathematical tasks on numbers.
For example:
- the `min()` and `max()` functions can be used to find the lowest or highest number in a set:
```
max(5, 10, 15)
min(5, 10, 15)
```
- `sqrt()` function returns the square root of a number:
```
sqrt(16)
```
- `abs()` function returns the absolute (positive) value of a number:
```
abs(-4.7)
```
- `ceiling() and floor()`: The ceiling() function rounds a number upwards to its nearest integer, and the floor() function rounds a number downwards to its nearest integer, and returns the result:
```
ceiling(1.4)

floor(1.4)
```

### R Strings
- **String Literals:**
Strings are used for storing text.
A string is surrounded by either single quotation marks, or double quotation marks: "hello" is the same as 'hello':

- **Assign a String to a Variable:**
```
str <- "Hello"
str # print the value of str
```

- **Multiline Strings:**
```
str <- "Lorem ipsum dolor sit amet,
consectetur adipiscing elit,
sed do eiusmod tempor incididunt
ut labore et dolore magna aliqua."

str # print the value of str
```
However, note that R will add a "\n" at the end of each line break. This is called an escape character, and the n character indicates a new line.

If you want the line breaks to be inserted at the same position as in the code, use the cat() function:
```
str <- "Lorem ipsum dolor sit amet,
consectetur adipiscing elit,
sed do eiusmod tempor incididunt
ut labore et dolore magna aliqua."

cat(str)
```
- **String Length:**
For example, to find the number of characters in a string, use the nchar() function:
```
str <- "Hello World!"

nchar(str)
```

- **Check a String:**
Use the grepl() function to check if a character or a sequence of characters are present in a string:
```
str <- "Hello World!"

grepl("H", str)
grepl("Hello", str)
grepl("X", str)
```
- **Combine Two Strings:**
Use the paste() function to merge/concatenate two strings:
```
str1 <- "Hello"
str2 <- "World"

paste(str1, str2)
```

- **Escape Characters:**
To insert characters that are illegal in a string, you must use an escape character.
An escape character is a backslash \ followed by the character you want to insert.

The escape character allows you to use double quotes when you normally would not be allowed:
```
str <- "We are the so-called \"Vikings\", from the north."

str
cat(str)
```
Note that auto-printing the str variable will print the backslash in the output. You can use the cat() function to print it without backslash.

### R Booleans / Logical Values
In programming, you often need to know if an expression is true or false.
You can evaluate any expression in R, and get one of two answers, TRUE or FALSE.
When you compare two values, the expression is evaluated and R returns the logical answer:
```
10 > 9    # TRUE because 10 is greater than 9
10 == 9   # FALSE because 10 is not equal to 9
10 < 9    # FALSE because 10 is greater than 9
```
You can also run a condition in an if statement
```
a <- 200
b <- 33

if (b > a) {
  print ("b is greater than a")
} else {
  print("b is not greater than a")
}
```

### R Operators
Operators are used to perform operations on variables and values.
R divides the operators in the following groups:
- Arithmetic operators: used with numeric values to perform common mathematical operations:


- Assignment operators: used to assign values to variables:
```
my_var <- 3
my_var <<- 3

3 -> my_var
3 ->> my_var

my_var # print my_var
```
**Note:** <<- is a global assigner. You will learn more about this in the Global Variable chapter.
It is also possible to turn the direction of the assignment operator (x <- 3 is equal to 3 -> x)

- Comparison operators: used to compare two values.

- Logical operators: combine conditional statements.

- Miscellaneous operators: used to manipulate data.

### R If ... Else

- An "if statement" is written with the if keyword, and it is used to specify a block of code to be executed if a condition is TRUE:
- The else if keyword is R's way of saying "if the previous conditions were not true, then try this condition":
- The else keyword catches anything which isn't caught by the preceding conditions:
```
a <- 200
b <- 33

if (b > a) {
  print("b is greater than a")
} else if (a == b) {
  print("a and b are equal")
} else {
  print("a is greater than b")
}
```
- You can also have if statements inside if statements, this is called nested if statements.
```
x <- 41

if (x > 10) {
  print("Above ten")
  if (x > 20) {
    print("and also above 20!")
  } else {
    print("but not above 20.")
  }
} else {
  print("below 10.")
}
```
- R - AND OR Operators
The & symbol (and) is a logical operator, and is used to combine conditional statements:
```
a <- 200
b <- 33
c <- 500

if (a > b & c > a) {
  print("Both conditions are true")
}
```
The | symbol (or) is a logical operator, and is used to combine conditional statements:
```
a <- 200
b <- 33
c <- 500

if (a > b | a > c) {
  print("At least one of the conditions is true")
}
```

### Loops
Loops can execute a block of code as long as a specified condition is reached.
Loops are handy because they save time, reduce errors, and they make code more readable.
R has two loop commands:
- while loops: execute a set of statements as long as a condition is TRUE. With the break statement, we can stop the loop even if the while condition is TRUE.
```
i <- 1
while (i < 6) {
  print(i)
  i <- i + 1
  if (i == 4) {
    break
  }
}
```
With the next statement, we can skip an iteration without terminating the loop:
```
i <- 0
while (i < 6) {
  i <- i + 1
  if (i == 3) {
    next
  }
  print(i)
}
```

- for loops: used for iterating over a sequence:
```
fruits <- list("apple", "banana", "cherry")

for (x in fruits) {
  if (x == "cherry") {
    break
  }
  print(x)
}
```

```
fruits <- list("apple", "banana", "cherry")

for (x in fruits) {
  if (x == "banana") {
    next
  }
  print(x)
}
```

```
dice <- 1:6

for(x in dice) {
  if (x == 6) {
    print(paste("The dice number is", x, "Yahtzee!"))
  } else {
    print(paste("The dice number is", x, "Not Yahtzee"))
  }
}
```
:
- Nested Loops: It is also possible to place a loop inside another loop.
```
adj <- list("red", "big", "tasty")

fruits <- list("apple", "banana", "cherry")
  for (x in adj) {
    for (y in fruits) {
      print(paste(x, y))
  }
}
```

### R Functions
A function is a block of code which only runs when it is called.
You can pass data, known as parameters, into a function.
A function can return data as a result.

- Creating a Function: use the function() keyword
```
my_function <- function() { # create a function with the name my_function
  print("Hello World!")
}
my_function() # call the function named my_function
```

- Arguments: Information can be passed into functions as arguments.
Arguments are specified after the function name, inside the parentheses. You can add as many arguments as you want, just separate them with a comma.
The following example has a function with one argument (fname). When the function is called, we pass along a first name, which is used inside the function to print the full name:

```
my_function <- function(fname) {
  paste(fname, "Griffin")
}

my_function("Peter")
my_function("Lois")
my_function("Stewie")
```


```
```

