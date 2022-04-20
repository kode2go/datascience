# Welcome to the kode2r wiki!

Here we will be learning the basics of R programming.

# What is R

It is popular programming language for data analysis, data visualization, data science and machine learning.
It provides many statistical techniques (such as statistical tests, classification, clustering and data reduction).
It is easy to draw graphs in R, like pie charts, histograms, box plot, scatter plot, etc++.

# Installation

Two options are provided. Either will way will provide the say outcome. For these lessons, option 1 was chosen.

## Option 1 - Installing R and RStudio through Anaconda

Download and install Anaconda from here:
https://www.anaconda.com/products/individual

Open the Anaconda Navigator and select R studio.

![image](https://user-images.githubusercontent.com/29664888/159347897-a818fa0b-b155-4089-8d43-cf1b5cebc801.png)

It will take a while to download the necessary files (20min), then it might say this:

![image](https://user-images.githubusercontent.com/29664888/159347955-8a379e29-b9b9-4641-9047-63fed7b3411f.png)

Just say create and it will install correctly.

Remember to always be on this one selected:

![image](https://user-images.githubusercontent.com/29664888/159348646-91c5864f-a058-443c-ba57-cf1fe0edcc06.png)

## Option 2 - R and R Studio Website
Download and install R (https://cran.r-project.org/) - use precompiled binary distributions, not
source code. Then download and install RStudio Desktop (https://rstudio.com/products/rstudio/download/) - free
version, not Pro.

# The Basics

We will cover the base of R and using RStudio in this lesson

# RStudio Environment 

![image](https://user-images.githubusercontent.com/29664888/159349153-137fe785-6b04-40da-b803-1559cfccb239.png)

You can use your console as an interactive environment to basic calculations, display text and more. It is like your scratch pad area, to try out things in R before you put it in a file.

# Simple Calculations and Variables:

We will be using the console, note to clear it at any more point do `ctrl + l`. Now go ahead a perform a few math calculations like `10+10` as shown below:

![image](https://user-images.githubusercontent.com/29664888/159349652-e4404c7b-f81b-4d06-a5de-abafd69e356d.png)

You see as soon as you add the numbers you get the answer, just like a calculator.

You can also store variables like:

```r
x <- 40
y <- 10
sum <- x + y
sum
```

![image](https://user-images.githubusercontent.com/29664888/159350143-fa175e48-5fcc-4aff-870d-315f28c3d81c.png)

Notice that the `<-` symbol is used to assign values to a variable. Note, when I made an error with `<` while it should have been `<-`.

Also note our variables are stored in memory and you can see what they are at all times by your top right window:

![image](https://user-images.githubusercontent.com/29664888/159350319-0dc236b6-d8d6-4f0e-a187-3ec503f30652.png)

Also note, that you can call variables whatever you want. There just can't be any spaces or dashes in between characters and it can't start with a number.

Lastly, if you want to add comments to you code you just use the `#` symbol at the
start of the line and R will read as just a comment and not use it like:

```r
# This line will do nothing in R, try it out! 
# 1+1
```

## Data Types

Like all programming languages you get various data types. It allows us to store data of different types. And different types of data can do different things. For example you can 
add two numbers together but you can't add two names together!

So we have seen the number or numeric data type before:

```r
myvar <- 10
myvar2 <- 0.5123
```

We can also store text:

```r
myname <- "bob"
```

We store text by using `" "` double quotes around the text. Note, it can be made up of multiple words like:

```r
my_full_name <- "bob jones"
```

Note, text based data types are called `characters` or `strings`.

You can get the length of string variables using:

```r
my_full_name <- "bob jones"
nchar(my_full_name )
```

You can combine two strings:

```r
firstname <- "bob"
lastname <- "jones"
paste(firstname,lastname)
```

You can also check if a character is in a variable:

```r
my_full_name <- "bob jones"
grepl("jo",my_full_name)
```

We can convert between data types. For example if we have a text file that has numbers in it, we may want to convert those text based numbers to actual numbers that we can use `as.numeric()` like:

```r
line_in_file <- "40.94"
num <- as.numeric(line_in_file)
num = num + 1
num
```

You can also print or display text to the console using the `print()` function:

```r
print("Hi are you enjoying R so far?")
```

If you want to print or display text with variables you can use the `cat()` function:

```r
thisyear = 2000
mystring = "this year is"

cat(mystring,thisyear)
```

**Note, you can do all the same code in a script file and then run it. The problem with the console is that you can't make edits
to your code if you made a mistake. The console is really only used as a test area for a 1 or 2 lines of code and to display the output of 
your code.**

## Math Functions:

We saw we can do basic math operations, now for more advanced ones we used built in features like:

```r
# Square root
sqrt(16)

# Absolute
abs(-5)

# Ceiling - round up
ceiling(1.4)

# Floor - round down
floor(1.4)

# Exponent:
3^2
```

# Logical Operators, Conditional Statements and Loops:

Sometimes we need to know if something is True or False like:

```r
# Will give True
10 > 9
# Used for checking if two values are equal, will give False
10 == 9
# Will give False
10 < 9
# Will give False
10 >=9

# Will give False
10 <= 9

# Will give True
10 != 9
```

A custom way to get a True and False comparison between two variables and then output certain code is using a `if` statement:

```r
a <- 10
b <- 9

if (a > b)
{
print("a is bigger than b")
}
else
{
print("b is bigger than a")
}
```

In the example above we use two variables, a and b, which are used as a part of the if statement to test whether a is greater than b. As a is 10, and b is 9, we know that 10 is greater than 9, and so we print to screen that "a is greater than b".

R uses curly brackets { } to define the scope in the code. Scope just means we are blocking out a few lines of code to perform some code that is only known within these lines.

We can add further conditions adding another `if` statement:

```r
a <- 33
b <- 33

if (b > a) {
  print("b is greater than a")
} else if (a == b) {
  print ("a and b are equal")
} 
else
{
 print("nothing else?")
}
```

In this example a is equal to b, so the first condition is not true, but the else if condition is true, so we print to screen that "a and b are equal".

You can use as many else if statements as you want in R.
Note, the `else` keyword catches anything which isn't caught by the preceding condition.

You can combine conditions using `&` which stands for and so all these conditions must be true:

```r
a <- 200
b <- 33
c <- 500

if (a > b & c > a){
  print("Both conditions are true")
} 
```

Lastly, the `|` symbol is used to check either or:

```r
a <- 200
b <- 33
c <- 500

if (a > b | a > c){
  print("At least one of the conditions is true")
} 
```

# Extra Features: Loops and Functions

The last useful feature of R is the `for` loop. And its used to iterate or loop
over a sequence of numbers or variables like:

```r
for (x in 1:10) {
  print(x)
}
```

or:

```r
for (x in 1:10) {
  print(x)
  if (x == 5){
  print("Number found")
  break
  }
}
```

The loop will stop at the number 5.

On to functions, a function is a block of code which only runs when it is called.
You can pass data, known as parameters, into a function. A function can return data as a result. See the example below:

```r
my_function <- function(x) {
  return (5 * x)
}

print(my_function(3))
print(my_function(5))
print(my_function(9))
```

*** CODING ADVICE - ALWAYS DOUBT YOURSELF YOUR PC ONLY DOES WHAT YOU TELL IT - ALWAYS DOUBLE CHECK ***

***
And that is yet to R, you have learnt the basics. Now on to more in-depth aspects of R with the next lesson.
***


# Data Structures

In this section we look at various ways to store multiple data values in a single variable.

## Vector

A vector is simply a list of items that are of the **same type.**

To combine the list of items to a vector, use the `c()` function and separate the items by a comma.

In the example below, we create a vector variable called fruits, that combine strings:

```r
# Vector of strings
fruits <- c("banana", "apple", "orange")

# Print fruits
fruits 
```

In this example, we create a vector that combines numerical values:

```r
# Vector of numerical values
numbers <- c(1, 2, 3)

# Print numbers
numbers 
```

To create a vector with numerical values in a sequence, use the `:` operator:

```r
# Vector with numerical values in a sequence
numbers <- 1:10

numbers 
```

You can also create numerical values with decimals in a sequence, but note that if the last element does not belong to the sequence, it is not used:

```r
# Vector with numerical decimals in a sequence
numbers1 <- 1.5:6.5
numbers1

```

To find out how many items a vector has, use the length() function:

```r
fruits <- c("banana", "apple", "orange")

length(fruits) 
```

To sort items in a vector alphabetically or numerically, use the sort() function:

```
fruits <- c("banana", "apple", "orange", "mango", "lemon")
numbers <- c(13, 3, 5, 7, 20, 2)

sort(fruits)  # Sort a string
sort(numbers) # Sort numbers 
```

You can access the vector items by referring to its index number inside brackets []. The first item has index 1, the second item has index 2, and so on:

```r
fruits <- c("banana", "apple", "orange")

# Access the first item (banana)
fruits[1] 
```

You can also access multiple elements by referring to different index positions with the c() function:

```r
fruits <- c("banana", "apple", "orange", "mango", "lemon")

# Access the first and third item (banana and orange)
fruits[c(1, 3)] 
```

You can also use negative index numbers to access all items except the ones specified:

```r
fruits <- c("banana", "apple", "orange", "mango", "lemon")

# Access all items except for the first item
fruits[c(-1)] 
```

To change the value of a specific item, refer to the index number:

```r
fruits <- c("banana", "apple", "orange", "mango", "lemon")

# Change "banana" to "pear"
fruits[1] <- "pear"

# Print fruits
fruits 
```

To make bigger or smaller steps in a sequence, use the seq() function:
```r
numbers <- seq(from = 0, to = 100, by = 20)

numbers 
```

Note: The seq() function has three parameters: from is where the sequence starts, to is where the sequence stops, and by is the interval of the sequence.

You can also remove items from a vector. If you have a sequence of numbers from 1 to 30 and we want to remove numbers 3 to 10:

```r
x <- 1:30
x2 <- x[!x %in% 3:10]
```

Remember: 

A vector is simply a list of items that are of the **same type.**

## Lists

A list in R can contain many different data types inside it. A list is a collection of data which is ordered and changeable.

To create a list, access, change items, get length of a list() function is the same as with a vector c():

```r
# List of strings
thislist <- list("apple", "banana", "cherry")

# Print the list
thislist 

# Access list
thislist[1] 

# Change Value
thislist[1] <- "blackcurrant"

# Print the updated list
thislist 

# Length of list
length(thislist) 
```

To find out if a specified item is present in a list, use the %in% operator:

```r
thislist <- list("apple", "banana", "cherry")

"apple" %in% thislist 
```

To add an item to the end of the list, use the append() function:

```r
thislist <- list("apple", "banana", "cherry")

append(thislist, "orange") 
```

To add an item to the right of a specified index, add "after=index number" in the append() function:

```r
thislist <- list("apple", "banana", "cherry")

append(thislist, "orange", after = 2) 
```

You can specify a range of indexes by specifying where to start and where to end the range, by using the `:` operator:

```r
thislist <- list("apple", "banana", "cherry", "orange", "kiwi", "melon", "mango")

(thislist)[2:5] 
```



Note: The search will start at index 2 (included) and end at index 5 (included).

Remember that the first item has index 1.

You can loop through the list items by using a for loop:

```r
thislist <- list("apple", "banana", "cherry")

for (x in thislist) {
  print(x)
} 
```

There are several ways to join, or concatenate, two or more lists in R.

The most common way is to use the c() function, which combines two elements together:

```r
list1 <- list("a", "b", "c")
list2 <- list(1,2,3)
list3 <- c(list1,list2)

list3 
```





