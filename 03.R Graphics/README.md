## R Plotting
#### Plot
The `plot()` function is used to **draw points (markers) in a diagram**.
The function takes parameters for specifying points in the diagram.
- **Param 1:** points on the x-axis.
- **Param 2:** points on the y-axis.

At its simplest, you can use the `plot()` function to plot two numbers against each other:
```
plot(1, 3)  # Draw one point in the diagram, at position (1) and position (3)

plot(c(1, 8), c(3, 10))  # Draw two points in the diagram, one at position (1, 3) and one in position (8, 10)
```

#### Multiple Points
You can plot as many points as you like:
```
plot(c(1, 2, 3, 4, 5), c(3, 7, 8, 9, 12))

# For better organization, it is better to use variables
x <- c(1, 2, 3, 4, 5)
y <- c(3, 7, 8, 9, 12)
plot(x, y)
```

#### Sequences of Points or Line
- If you want to **draw dots in a sequence**, on both the x-axis and the y-axis, use the `: operator`:
```
plot(1:10)
```
- The `plot()` function also takes a `type` parameter with the value `l` to draw a **line to connect all the points** in the diagram:
```
plot(1:10, type="l")
```

#### Graph Appearance
There are many parameters you can use to change the appearance of the points.
- **`main`, `xlab` and `ylab`:** to customize the graph with a **main title and different labels for the x and y-axis**:
```
plot(1:10, main="My Graph", xlab="The x-axis", ylab="The y axis")
```
- **`col="color"`:** to add a color to the points:
```
plot(1:10, col="red")
```
- **`cex=number`:** to change the size of the points (1 is default, while 0.5 means 50% smaller, and 2 means 100% larger).
```
plot(1:10, cex=2)
```
- **`pch`:** with a value from 0 to 25 to change the point shape format:
```
plot(1:10, pch=25, cex=2)
```
The values of the pch parameter ranges from 0 to 25, which means that we can choose up to 26 different types of point shapes:
![]()


## R Line
#### Line Graphs
A line graph has a line that connects all the points in a diagram.   
To create a line, use the plot() function and add the type parameter with a value of "l":
```
plot(1:10, type="l")
```

#### Line Graphs Appearence & Style
- To change the color, use the `col` parameter:
```
plot(1:10, type="l", col="blue")
```
- To change the width of the line, use the `lwd` parameter (1 is default, while 0.5 means 50% smaller, and 2 means 100% larger):
```
plot(1:10, type="l", lwd=2)
```
- Use the `lty` parameter with a **value from 0 to 6** to specify the line format.  
For example, lty=3 will display a dotted line instead of a solid line:
```
plot(1:10, type="l", lwd=5, lty=3)
```
Available parameter values for `lty`:
  - 0 removes the line
  - 1 displays a solid line
  - 2 displays a dashed line
  - 3 displays a dotted line
  - 4 displays a "dot dashed" line
  - 5 displays a "long dashed" line
  - 6 displays a "two dashed" line

#### Multiple Lines
To display more than one line in a graph, use the plot() function together with the `lines()` function:
```
line1 <- c(1,2,3,4,5,10)
line2 <- c(2,5,7,8,9,10)

plot(line1, type="l", col = "blue")
lines(line2, type="l", col = "red")
```


## R Scatter Plot
#### Scatter Plots
A "scatter plot" is a type of plot used to **display the relationship between two numerical variables**, and plots one dot for each observation.
```
x <- c(5,7,8,7,2,2,9,4,11,12,9,6)
y <- c(99,86,87,88,111,103,87,94,78,77,85,86)

# The observation in the example above should show the result of 12 cars passing by.
plot(x, y, main="Observation of Cars", xlab="Car age", ylab="Car speed")
```
To recap, the observation in the example above is the result of 12 cars passing by.
- The x-axis shows how old the car is.
- The y-axis shows the speed of the car when it passes.

**Are there any relationships between the observations?**
It seems that the newer the car, the faster it drives, but that could be a coincidence, after all we only registered 12 cars.

#### Compare Plots
In the example above, there seems to be a relationship between the car speed and age, but what if we plot the observations from another day as well? Will the scatter plot tell us something else?  
To compare the plot with another plot, use the `points()` function:
```
# day one, the age and speed of 12 cars:
x1 <- c(5,7,8,7,2,2,9,4,11,12,9,6)
y1 <- c(99,86,87,88,111,103,87,94,78,77,85,86)

# day two, the age and speed of 15 cars:
x2 <- c(2,2,8,1,15,8,12,9,7,3,11,4,7,14,12)
y2 <- c(100,105,84,105,90,99,90,95,94,100,79,112,91,80,85)

plot(x1, y1, main="Observation of Cars", xlab="Car age", ylab="Car speed", col="red", cex=2)
points(x2, y2, col="blue", cex=2)
```
**Conclusion of observation:** By comparing the two plots, I think it is safe to say that they both gives us the same conclusion: the newer **the car, the faster it drives.**


## R Pie Charts
#### Pie Charts
A pie chart is a circular graphical view of data.
Use the `pie()` function to draw pie charts:
```
# Create a vector of pies
x <- c(10,20,30,40)

# Display the pie chart
pie(x)
```
**Example Explained:** As you can see the pie chart draws one pie for each value in the vector (in this case 10, 20, 30, 40).
By default, the plotting of the first pie starts from the x-axis and move counterclockwise.

#### Start Angle
You can change the start angle of the pie chart with the `init.angle` parameter.
The value of `init.angle` is defined with angle in degrees, where default angle is 0.
```
# Create a vector of pies
x <- c(10,20,30,40)

# Display the pie chart and start the first pie at 90 degrees
pie(x, init.angle = 90)
```

#### Labels and Header
Use the `label` parameter to add a label to the pie chart, and use the main parameter to add a header:
```
# Create a vector of pies
x <- c(10,20,30,40)

# Create a vector of labels
mylabel <- c("Apples", "Bananas", "Cherries", "Dates")

# Display the pie chart with labels
pie(x, label = mylabel, main = "Fruits")
```

#### Colors
You can add a color to each pie with the col parameter:
```
# Create a vector of colors
colors <- c("blue", "yellow", "green", "black")

# Display the pie chart with colors
pie(x, label = mylabel, main = "Fruits", col = colors)
```

#### Legend
To add a list of explanation for each pie, use the `legend()` function:
```
# Create a vector of labels
mylabel <- c("Apples", "Bananas", "Cherries", "Dates")

# Create a vector of colors
colors <- c("blue", "yellow", "green", "black")

# Display the pie chart with colors
pie(x, label = mylabel, main = "Pie Chart", col = colors)

# Display the explanation box
legend("bottomright", mylabel, fill = colors)
```
The legend can be positioned as either: **bottomright, bottom, bottomleft, left, topleft, top, topright, right, center.**


## R Bar Charts
#### Bar Charts
A bar chart uses rectangular bars to visualize data. The height or length of the bars are proportional to the values they represent.  
Use the `barplot()` function to draw a vertical bar chart:
```
# x-axis values
x <- c("A", "B", "C", "D")

# y-axis values
y <- c(2, 4, 6, 8)

barplot(y, names.arg = x)
```
Example Explained
- The x variable represents values in the x-axis (A,B,C,D)
- The y variable represents values in the y-axis (2,4,6,8)
- Then we use the barplot() function to create a bar chart of the values
- names.arg defines the names of each observation in the x-axis

#### Bar Customizations
- Use the `col` parameter to change the color of the bars:
```
x <- c("A", "B", "C", "D")
y <- c(2, 4, 6, 8)

barplot(y, names.arg = x, col = "red")
```

- Use the `density` parameter to change the bar texture:
```
x <- c("A", "B", "C", "D")
y <- c(2, 4, 6, 8)

barplot(y, names.arg = x, density = 10)
```

- Use the `width` parameter to change the width of the bars:
```
x <- c("A", "B", "C", "D")
y <- c(2, 4, 6, 8)

barplot(y, names.arg = x, width = c(1,2,3,4))
```

- **`horiz=TRUE`:** the bars to be displayed horizontally instead of vertically.
```
x <- c("A", "B", "C", "D")
y <- c(2, 4, 6, 8)

barplot(y, names.arg = x, horiz = TRUE)
```








