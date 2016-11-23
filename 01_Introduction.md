# Introduction
Steve Pederson  
23 November 2016  






## Who Am I? | Steve Pederson

- R User for >10 years
- Co-ordinator, Bioinformatics Hub  
    - Level 4, Santos Petroleum Engineering Building

Also helping today:

- Alastair Ludington (Bioinformatics Hub)

## Today's Outline | Four 90 minute Sessions

1. How does R even work?

2. Loading Data into R

3. What have we really done?

4. The Genomics Era


# How Does R Even Work?

## What is R

- Began as a statistical tool in the 1990s (Ross Ihaka & Robert Gentleman)
- Evolved far beyond it's original design
- Primarly used for analysis & graphics
- Current estimates are 1 - 2 million users




## What is R? 

- Can be treated as a simple calculator:


```r
1 + 2
```

```
## [1] 3
```


## What is R? 

- Contains all standard mathematical functions `+`, `-`, `*`, `/`, `^`


```r
2^3
```

```
## [1] 8
```

```r
1 + 2 - 3 * 4 / 5
```

```
## [1] 0.6
```

## What is R? 

- Built-in functions for common transformations like `log` or $\sqrt{~}$ 
- Place the values inside the round braces after the function name


```r
sqrt(2)
```

```
## [1] 1.414214
```

```r
log(10)
```

```
## [1] 2.302585
```

## What is R? 

- Trigonometric Functions `sin()`, `cos()`, `tan()`
- Other common functions like `abs()` for the absolute value


```r
abs(-1)
```

```
## [1] 1
```

## What is R? 

- Two common log transforms are also included


```r
log2(0.5)
```

```
## [1] -1
```

```r
log10(0.001)
```

```
## [1] -3
```

## What is R? 

- There is no `inverse()` function. 

### How would we find the inverse of a number?

# Creating Objects In R

## Creating Objects in R

- In `R` we can save objects and give them a name
- We type the desired name, folowed by `<-`, then the value


```r
x <- 3
```

### 2 Key points!!!
1. The value was not "_printed_" to the screen
2. The _assignment operator_ (`<-`) acts like an arrow **placing the value** in the object `x`

## Creating Objects in R

Yes we could have written:


```r
x = 3
```

- The standard convention is to use `<-` 
- It makes it clearer that you are placing a value into an object

### What other use might the `=` sign have?

## Creating Objects in R

We could also have written


```r
3 -> x
```

But no-one ever does...

## Using R objects

- To see the value(s) that `x` contains, we just type it's name:


```r
x
```

```
## [1] 3
```

- We occasionally like to be _very specific_ and use the `print()` command


```r
print(x)
```

```
## [1] 3
```

## Using R objects

- We can pass this value to any function, or do math on it


```r
sqrt(x)
x^2
x + 1
```

# Using R Studio

## Using R Studio

- RStudio is the most common way of interacting with `R`
- We can save all of our commands in a single file
- We can view a summary of our objects, make plots, import & export data etc.

## Using R Studio | R Projects

- R Projects are not compulsory, but are VERY useful!
- Just a simple wrapper to help keep an analysis/workshop organised
- When we open an R Project, we go back to the last state (i.e. where we were last time)
- Also great for interacting with version control (e.g. git)

## Using R Studio | R Projects

Let's set one up for this course: `File > New Project`

<img src="images/Project.png" width="540" style="display: block; margin: auto;" />

## Using R Studio | R Projects

- Choose either a `New` or `Existing` Directory
- Navigate to where you think is suitable for keeping the course notes
- The project name will _automatically be assigned_ as the directory name




<div class="footer" style="text-align:center;width:25%">
[Home](http://uofabioinformaticshub.github.io/RAdelaide-July-2016/)
</div>
