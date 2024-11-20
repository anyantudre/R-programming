## R Data Set
A data set is a collection of data, often presented in a table.
There is a popular built-in data set in R called "mtcars" (Motor Trend Car Road Tests), which is retrieved from the 1974 Motor Trend US Magazine.
In the examples below (and for the next chapters), we will use the mtcars data set, for statistical purposes:

```
# Print the mtcars data set
mtcars
```

#### Information About the Data Set
You can use the question mark (`?`) to get information about the `mtcars` data set:
```
# Use the question mark to get information about the data set
?mtcars
```

#### Get Information
Use the dim() function to find the dimensions of the data set, and the names() function to view the names of the variables:
```
Data_Cars <- mtcars # create a variable of the mtcars data set for better organization

# Use dim() to find the dimension of the data set
dim(Data_Cars)

# Use names() to find the names of the variables from the data set
names(Data_Cars)
```
Use the rownames() function to get the name of each row in the first column, which is the name of each car:
```
Data_Cars <- mtcars

rownames(Data_Cars)
```

#### Print Variable Values
If you want to print all values that belong to a variable, access the data frame by using the $ sign, and the name of the variable (for example cyl (cylinders)):
```
Data_Cars <- mtcars

Data_Cars$cyl

# To sort the values, use the sort() function:
sort(Data_Cars$cyl)
```

#### Analyzing the Data
Now that we have some information about the data set, we can start to analyze it with some statistical numbers.

For example, we can use the summary() function to get a statistical summary of the data:
```
Data_Cars <- mtcars

summary(Data_Cars)
```
The summary() function returns six statistical numbers for each variable:
- Min
- First quantile (percentile)
- Median
- Mean
- Third quantile (percentile)
- Max
We will cover all of them, along with other statistical numbers in the next chapters.


#### R Max and Min
The min() and max() functions can be used to find the lowest or highest value in a set:
```
Data_Cars <- mtcars

max(Data_Cars$hp)
min(Data_Cars$hp)
```
Now we know that the largest horsepower value in the set is 335, and the lowest 52.
We could take a look at the data set and try to find out which car these two values belongs to:

We can use the which.max() and which.min() functions to find the index position of the max and min value in the table:
```
Data_Cars <- mtcars

which.max(Data_Cars$hp)
which.min(Data_Cars$hp)
```
Or even better, combine which.max() and which.min() with the rownames() function to get the name of the car with the largest and smallest horsepower:
```
Data_Cars <- mtcars

rownames(Data_Cars)[which.max(Data_Cars$hp)]
rownames(Data_Cars)[which.min(Data_Cars$hp)]
```

#### Outliers
Max and min can also be used to detect outliers. An outlier is a data point that differs from rest of the observations.
Example of data points that could have been outliers in the mtcars data set:
- If maximum of forward gears of a car was 11
- If minimum of horsepower of a car was 0
- If maximum weight of a car was 50 000 lbs

## R Mean
#### Mean
To calculate the average value (mean) of a variable from the mtcars data set, find the sum of all values, and divide the sum by the number of values.
Luckily for us, the mean() function in R can do it for you:
```
Data_Cars <- mtcars

mean(Data_Cars$wt)
```

## R Median
The median value is the value in the middle, after you have sorted all the values.
Note: If there are two numbers in the middle, you must divide the sum of those numbers by two, to find the median.

Luckily, R has a function that does all of that for you: Just use the median() function to find the middle value:
```
Data_Cars <- mtcars

median(Data_Cars$wt)
```
## R Mode
The mode value is the value that appears the most number of times.
R does not have a function to calculate the mode. However, we can create our own function to find it.

```
Data_Cars <- mtcars

names(sort(-table(Data_Cars$wt)))[1]
```

## R Percentiles
#### Percentiles
Percentiles are used in statistics to give you a number that describes the value that a given percent of the values are lower than.
```
Data_Cars <- mtcars

# c() specifies which percentile you want
quantile(Data_Cars$wt, c(0.75))
```
If you run the quantile() function without specifying the c() parameter, you will get the percentiles of 0, 25, 50, 75 and 100:
```
Data_Cars <- mtcars

quantile(Data_Cars$wt)
```

#### Quartiles
Quartiles are data divided into four parts, when sorted in an ascending order:

The value of the first quartile cuts off the first 25% of the data
The value of the second quartile cuts off the first 50% of the data
The value of the third quartile cuts off the first 75% of the data
The value of the fourth quartile cuts off the 100% of the data



