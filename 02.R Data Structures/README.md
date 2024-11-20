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
A matrix is a two dimensional data set with columns and rows.

A matrix can be created with the matrix() function. Specify the nrow and ncol parameters to get the amount of rows and columns:
```
# Create a matrix
thismatrix <- matrix(c(1,2,3,4,5,6), nrow = 3, ncol = 2)
thismatrix

# create a matrix with strings
thismatrix <- matrix(c("apple", "banana", "cherry", "orange"), nrow = 2, ncol = 2)
thismatrix
```
You can access the items by using [ ] brackets. The first number "1" in the bracket specifies the row-position, while the second number "2" specifies the column-position:

```
thismatrix <- matrix(c("apple", "banana", "cherry", "orange"), nrow = 2, ncol = 2)
thismatrix[1, 2]

# The whole row can be accessed if you specify a comma after the number in the bracket
thismatrix <- matrix(c("apple", "banana", "cherry", "orange"), nrow = 2, ncol = 2)
thismatrix[2,]

# The whole column can be accessed if you specify a comma before the number in the bracket
thismatrix <- matrix(c("apple", "banana", "cherry", "orange"), nrow = 2, ncol = 2)
thismatrix[,2]
```

#### Access More Than One Row/Column
More than one row/column can be accessed if you use the c() function:
```
# acces rows
thismatrix <- matrix(c("apple", "banana", "cherry", "orange","grape", "pineapple", "pear", "melon", "fig"), nrow = 3, ncol = 3)
thismatrix[c(1,2),]

# access columns
thismatrix <- matrix(c("apple", "banana", "cherry", "orange","grape", "pineapple", "pear", "melon", "fig"), nrow = 3, ncol = 3)
thismatrix[, c(1,2)]
```

#### Add Rows and Columns
- Use the cbind() function to add additional columns in a Matrix. 
```
thismatrix <- matrix(c("apple", "banana", "cherry", "orange","grape", "pineapple", "pear", "melon", "fig"), nrow = 3, ncol = 3)

newmatrix <- cbind(thismatrix, c("strawberry", "blueberry", "raspberry"))

# Print the new matrix
newmatrix
```
- Use the rbind() function to add additional rows in a Matrix:
```
thismatrix <- matrix(c("apple", "banana", "cherry", "orange","grape", "pineapple", "pear", "melon", "fig"), nrow = 3, ncol = 3)

newmatrix <- rbind(thismatrix, c("strawberry", "blueberry", "raspberry"))

# Print the new matrix
newmatrix
```

#### Remove Rows and Columns
Use the c() function to remove rows and columns in a Matrix:
```
thismatrix <- matrix(c("apple", "banana", "cherry", "orange", "mango", "pineapple"), nrow = 3, ncol =2)

#Remove the first row and the first column
thismatrix <- thismatrix[-c(1), -c(1)]
thismatrix

# Check if an Item Exists
"apple" %in% thismatrix

# find the number of rows and columns
dim(thismatrix)

# find the dimension of a Matrix (Total cells)
length(thismatrix)
```

#### Loop Through a Matrix
You can loop through a Matrix using a for loop. The loop will start at the first row, moving right:
```
thismatrix <- matrix(c("apple", "banana", "cherry", "orange"), nrow = 2, ncol = 2)

for (rows in 1:nrow(thismatrix)) {
  for (columns in 1:ncol(thismatrix)) {
    print(thismatrix[rows, columns])
  }
}
```
#### Combine two Matrices
Again, you can use the rbind() or cbind() function to combine two or more matrices together:
```
# Combine matrices
Matrix1 <- matrix(c("apple", "banana", "cherry", "grape"), nrow = 2, ncol = 2)
Matrix2 <- matrix(c("orange", "mango", "pineapple", "watermelon"), nrow = 2, ncol = 2)

# Adding it as a rows
Matrix_Combined <- rbind(Matrix1, Matrix2)
Matrix_Combined

# Adding it as a columns
Matrix_Combined <- cbind(Matrix1, Matrix2)
Matrix_Combined
```


## R Arrays
Compared to matrices, arrays can have more than two dimensions.

We can use the array() function to create an array, and the dim parameter to specify the dimensions:
```
# An array with one dimension with values ranging from 1 to 24
thisarray <- c(1:24)
thisarray

# An array with more than one dimension
multiarray <- array(thisarray, dim = c(4, 3, 2))
multiarray
```
#### Access Array Items
You can access the array elements by referring to the index position. You can use the [] brackets to access the desired elements from an array:
```
thisarray <- c(1:24)
multiarray <- array(thisarray, dim = c(4, 3, 2))

multiarray[2, 3, 2]
```
You can also access the whole row or column from a matrix in an array, by using the c() function:
```
thisarray <- c(1:24)

# Access all the items from the first row from matrix one
multiarray <- array(thisarray, dim = c(4, 3, 2))
multiarray[c(1),,1]

# Access all the items from the first column from matrix one
multiarray <- array(thisarray, dim = c(4, 3, 2))
multiarray[,c(1),1]
```

#### Basic Operations
```
thisarray <- c(1:24)
multiarray <- array(thisarray, dim = c(4, 3, 2))

# find out if a specified item is present in an array
2 %in% multiarray

# find the amount of rows and columns in an array
dim(multiarray)

# find the dimension of an array
length(multiarray)

# loop through the array items by using a for loop
for(x in multiarray){
  print(x)
}
```

## R Data Frames
Data Frames are data displayed in a format as a table.

Data Frames can have different types of data inside it. While the first column can be character, the second and third can be numeric or logical. However, each column should have the same type of data.

Use the data.frame() function to create a data frame
```
# Create a data frame
Data_Frame <- data.frame (
  Training = c("Strength", "Stamina", "Other"),
  Pulse = c(100, 150, 120),
  Duration = c(60, 30, 45)
)

# Print the data frame
Data_Frame
```
- Use the summary() function to summarize the data from a Data Frame:
```
summary(Data_Frame)
```
- Use single brackets [ ], double brackets [[ ]] or $ to access columns from a data frame:
```
Data_Frame[1]

Data_Frame[["Training"]]

Data_Frame$Training
```
- Use the rbind() function to add new rows in a Data Frame:
```
# Add a new row
New_row_DF <- rbind(Data_Frame, c("Strength", 110, 110))

# Print the new row
New_row_DF
```
- Use the cbind() function to add new columns in a Data Frame:
```
# Add a new column
New_col_DF <- cbind(Data_Frame, Steps = c(1000, 6000, 2000))

# Print the new column
New_col_DF
```

- Use the c() function to remove rows and columns in a Data Frame:
```
# Remove the first row and column
Data_Frame_New <- Data_Frame[-c(1), -c(1)]

# Print the new data frame
Data_Frame_New
```

- Use the dim() function to find the amount of rows and columns in a Data Frame:
```
dim(Data_Frame)
```

- use the ncol() function to find the number of columns and nrow() to find the number of rows:
```
ncol(Data_Frame)
nrow(Data_Frame)
```

- Use the length() function to find the number of columns in a Data Frame (similar to ncol()):
```
length(Data_Frame)
```

- Use the rbind() function to combine two or more data frames in R vertically:
```
New_Data_Frame <- rbind(Data_Frame1, Data_Frame2)
New_Data_Frame
```

- use the cbind() function to combine two or more data frames in R horizontally:
```
New_Data_Frame1 <- cbind(Data_Frame3, Data_Frame4)
New_Data_Frame1
```


## R Factors
Factors are used to categorize data. Examples of factors are:
- Demography: Male/Female
- Music: Rock, Pop, Classic, Jazz
- Training: Strength, Stamina
To create a factor, use the factor() function and add a vector as argument:
```
# Create a factor
music_genre <- factor(c("Jazz", "Rock", "Classic", "Classic", "Pop", "Jazz", "Rock", "Jazz"))

# Print the factor
music_genre
```
You can see from the example above that that the factor has four levels (categories): Classic, Jazz, Pop and Rock.

To only print the levels, use the levels() function:
```
music_genre <- factor(c("Jazz", "Rock", "Classic", "Classic", "Pop", "Jazz", "Rock", "Jazz"))

levels(music_genre)
```
You can also set the levels, by adding the levels argument inside the factor() function:
```
music_genre <- factor(c("Jazz", "Rock", "Classic", "Classic", "Pop", "Jazz", "Rock", "Jazz"), levels = c("Classic", "Jazz", "Pop", "Rock", "Other"))

levels(music_genre)

# find out how many items there are in the factor
length(music_genre)
```

#### Access Factors/Change Item Value
- To access the items in a factor, refer to the index number, using [] brackets:
```
music_genre <- factor(c("Jazz", "Rock", "Classic", "Classic", "Pop", "Jazz", "Rock", "Jazz"))

music_genre[3]
```
- To change the value of a specific item, refer to the index number:
```
music_genre <- factor(c("Jazz", "Rock", "Classic", "Classic", "Pop", "Jazz", "Rock", "Jazz"))

music_genre[3] <- "Pop"

music_genre[3]
```
Note that you cannot change the value of a specific item if it is not already specified in the factor. The following example will produce an error:

However, if you have already specified it inside the levels argument, it will work:
```
music_genre <- factor(c("Jazz", "Rock", "Classic", "Classic", "Pop", "Jazz", "Rock", "Jazz"), levels = c("Classic", "Jazz", "Pop", "Rock", "Opera"))

music_genre[3] <- "Opera"

music_genre[3]
```
