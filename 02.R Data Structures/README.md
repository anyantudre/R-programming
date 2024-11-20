## R Vectors

#### Vectors
A vector is simply a list of items that are of the same type.
To combine the list of items to a vector, use the c() function and separate the items by a comma.

```
# Vector of strings
fruits <- c("banana", "apple", "orange")

# Print fruits
fruits

# Vector of numerical values
numbers <- c(1, 2, 3)

# Print numbers
numbers
```
To create a vector with numerical values in a sequence, use the : operator:
```
# Vector with numerical values in a sequence
numbers <- 1:10

numbers
```
You can also create numerical values with decimals in a sequence, but note that if the last element does not belong to the sequence, it is not used:
```
# Vector with numerical decimals in a sequence
numbers1 <- 1.5:6.5
numbers1

# Vector with numerical decimals in a sequence where the last element is not used
numbers2 <- 1.5:6.3
numbers2
```

#### Vector Length
To find out how many items a vector has, use the length() function:
```
fruits <- c("banana", "apple", "orange")

length(fruits)
```

#### Sort a Vector
To sort items in a vector alphabetically or numerically, use the sort() function:
```
fruits <- c("banana", "apple", "orange", "mango", "lemon")
numbers <- c(13, 3, 5, 7, 20, 2)

sort(fruits)  # Sort a string
sort(numbers) # Sort numbers
```
#### Access Vectors
You can access the vector items by referring to its index number inside brackets []. The first item has index 1, the second item has index 2, and so on:
```
fruits <- c("banana", "apple", "orange")

# Access the first item (banana)
fruits[1]
```
You can also access multiple elements by referring to different index positions with the c() function:
```
fruits <- c("banana", "apple", "orange", "mango", "lemon")

# Access the first and third item (banana and orange)
fruits[c(1, 3)]
```
You can also use negative index numbers to access all items except the ones specified:
```
fruits <- c("banana", "apple", "orange", "mango", "lemon")

# Access all items except for the first item
fruits[c(-1)]
```

#### Change an Item
To change the value of a specific item, refer to the index number:
```
fruits <- c("banana", "apple", "orange", "mango", "lemon")

# Change "banana" to "pear"
fruits[1] <- "pear"

# Print fruits
fruits
```

#### Repeat Vectors
To repeat vectors, use the rep() function:
```
# Repeat each value:
repeat_each <- rep(c(1,2,3), each = 3)
repeat_each

# Repeat the sequence of the vector:
repeat_times <- rep(c(1,2,3), times = 3)
repeat_times

# Repeat each value independently:
repeat_indepent <- rep(c(1,2,3), times = c(5,2,1))
repeat_indepent
```

#### Generating Sequenced Vectors
One of the examples on top, showed you how to create a vector with numerical values in a sequence with the : operator:
```
numbers <- 1:10
numbers
```
To make bigger or smaller steps in a sequence, use the seq() function:
```
numbers <- seq(from = 0, to = 100, by = 20)
numbers
```
**Note:** The seq() function has three parameters: from is where the sequence starts, to is where the sequence stops, and by is the interval of the sequence.

## R Lists
#### Lists

A list in R can contain many different data types inside it. A list is a collection of data which is ordered and changeable.  
To create a list, use the list() function:
```
# List of strings
thislist <- list("apple", "banana", "cherry")

# Print the list
thislist

# access the list firs item
thislist[1]
```
#### Change Item Value
To change the value of a specific item, refer to the index number:
```
thislist <- list("apple", "banana", "cherry")
thislist[1] <- "blackcurrant"

# Print the updated list
thislist

# how many items a list has
length(thislist)
```

#### Check if Item Exists
To find out if a specified item is present in a list, use the %in% operator:
```
thislist <- list("apple", "banana", "cherry")

"apple" %in% thislist
```

#### Add List Items
To add an item to the end of the list, use the append() function:
```
thislist <- list("apple", "banana", "cherry")

append(thislist, "orange")
```
To add an item to the right of a specified index, add "after=index number" in the append() function:
```
thislist <- list("apple", "banana", "cherry")

append(thislist, "orange", after = 2)
```
#### Remove List Items
You can also remove list items. The following example creates a new, updated list without an "apple" item:
```
thislist <- list("apple", "banana", "cherry")

newlist <- thislist[-1]

# Print the new list
newlist
```

#### Range of Indexes
You can specify a range of indexes by specifying where to start and where to end the range, by using the : operator:
```
thislist <- list("apple", "banana", "cherry", "orange", "kiwi", "melon", "mango")

(thislist)[2:5]
```

#### Loop Through a List
You can loop through the list items by using a for loop:
```
thislist <- list("apple", "banana", "cherry")

for (x in thislist) {
  print(x)
}
```
#### Join Two Lists
There are several ways to join, or concatenate, two or more lists in R.

The most common way is to use the c() function, which combines two elements together:
```
list1 <- list("a", "b", "c")
list2 <- list(1,2,3)
list3 <- c(list1,list2)

list3
```

## R Matrices

```
```


```
```








