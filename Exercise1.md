# Exercise 1 -- A Random Walk

## Requirements

Create a similar plot as the one produced above, but instead meet the following specifications.

* Increase the minimum and maximum limits of your area from 1 to 1000 in both the x & y dimension.
* Randomly place 50 dwelling units throughout the 1000 x 1000 dimensioned area. Size each square appropriately.
* Randomly place 40 small circles (trees) throughout the 1000 x 1000 dimensioned area. Set the radius of each circle to the same or approximately the same as the width of each home.
* Randomly place 12 large trees throughout the defined area, such that each tree has almost twice the radius as each home's width.
* Randomly select 7 homes from the 50 total, and use a dashed spline to describe the path between each labeled dwelling unit.
* Title your plot.

## Code

```R

rm(list=ls())

x <- 1:1000
y <- 1:1000

east <- sample(x,size=50,replace=TRUE)
north <- sample(y,size=50,replace=TRUE)

symbols(east,north, 
        squares = rep(7.5,50), 
        inches = FALSE)

symbols(sample(x, 40, replace = TRUE), 
        sample(y, 40, replace = TRUE), 
        circles = rep(7.5,40), 
        inches = FALSE,
        fg = "blue",
        bg = "beige",
        add = TRUE)

symbols(sample(x, 12, replace = TRUE), 
        sample(y, 12, replace = TRUE), 
        circles = rep(15,12), 
        inches = FALSE,
        fg = "green",
        bg = "beige",
        add = TRUE)

dwellings <- cbind.data.frame(id=1:50, east,north)
locs <- sample(1:50, 7, replace = FALSE)

xspline(x = dwellings[locs,2],
        y = dwellings[locs,3],
        shape = -1,
        lty = 2)

text(x = dwellings[locs,2], 
     y = dwellings[locs,3]+20,
     labels = dwellings[locs, ]$id)

title(main="A Person's path between Homes")

```
