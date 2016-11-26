# Introduction to R
Steve Pederson  
27 November 2016  






## Who Am I? | Steve Pederson

- R User for >10 years
- Co-ordinator, Bioinformatics Hub  
    - Level 4, Santos Petroleum Engineering Building

Also helping today:

- Alastair Ludington 
- Jimmy Breen (morning) & Hien To (afternoon)

## Today's Outline | Four 90 minute Sessions

1. Introduction to R and RStudio

2. Loading Data Into R

3. What have we really done?

4. The Genomics Era


# Introduction

## Why use R?

- Began as a statistical tool in the 1990s (Ross Ihaka & Robert Gentleman)
- Evolved far beyond it's original design
- Current estimates are ~2 million users



## Why use R?

- The main software/language used for analysis and visualisation of biological data (along with Python)
- Can handle extremely large datasets  
- We can easily perform complex analytic procedures
- Many processes come as inbuilt functions  
- Huge user base of biological researchers

## Why use R? | Other Key Reasons

- Avoids common Excel pitfalls
- Reproducible Research

## Automatic Conversion | A common Excel problem

**Excel is notorious for converting values from one thing to another inappropriately.**

- Gene names are often converted to dates (e.g. _SEPT9_)

- Genotypes can be converted into numeric values (e.g. the homozygote "1/1")
    
- In `R` we generally work with plain text files.
    
## Reproducible Research

- Research is littered with mistakes from Excel
- Studies have made Phase III trials
- _We have code to record and exactly repeat our analysis_
- We can find and correct errors more easily than if they are copy/paste errors

## Using R

>__With power comes great responsibility - Uncle Ben__
  
With the extra capability R offers, we need to understand a little about:

1. Data Types  
2. Data Structures  

We'll get to that later...

_First, we'll just explore the `R` Console_


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

- Two common log transforms are also included
- `log2(0.5)` $\equiv$` `log(0.5, base = 2)`


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

- Trigonometric Functions `sin()`, `cos()`, `tan()`
- Other common functions like `abs()` for the absolute value


```r
abs(-1)
```

```
## [1] 1
```


## What is R? 

- There is no `inverse()` function. 

### How would we find the inverse of a number?

# Creating Objects In R

## Creating Objects in R

- In `R` we can save objects and give them a name
- We type the desired name, folowed by `<-`, then the value


```r
x <- 5
```

### 2 Key points!!!
1. The value was not "_printed_" to the screen
2. The _assignment operator_ (`<-`) acts like an arrow **placing the value** in the object `x`

## Creating Objects in R

Yes we could have written:


```r
x = 5
```

- The standard convention is to use `<-` 
- This is specific to creation of a new `R` object.
- It makes it clear **to all readers** that you are placing a value into an object

### What other use might the `=` sign have?

## Creating Objects in R

We could also have written


```r
5 -> x
```

But no-one ever does...

## Using R objects

- To see the value(s) that `x` contains, we just type it's name:


```r
x
```

```
## [1] 5
```

- We occasionally like to be _very specific_ and use the `print()` command


```r
print(x)
```

```
## [1] 5
```

## Using R objects

- We can now pass this value to any function, or do math on it


```r
sqrt(x)
x^2
x + 1
```

# Vectors

## A Brief Introduction To Vectors

- In `R` we can combine many numbers together into a `vector`
- Use the function `c()` (for _combine_)
- One of the most common functions in `R`


```r
x <- c(1, 2, 4)
x
```

```
## [1] 1 2 4
```

## A Brief Introduction To Vectors



- We can now apply lots of functions to this vector
- Similar to working with a column in Excel


```r
min(x)
mean(x)
sd(x)
range(x)
```

## A Brief Introduction To Vectors

- We can also perform mathematical operations on every value in the `vector` with _one command_


```r
x + 1
sqrt(x)
log2(x)
```

### This is one of the great strengths of `R`!

## A Brief Introduction To Vectors

- In `R`, everything is a vector
- A key property of a vector is it's `length`


```r
length(x)
```

- A single value in `R` is considered a vector of length 1


## The 4 Atomic Vector Types

- *Atomic Vectors* are the building blocks for everything in `R`
- There are four main types

## The 4 Atomic Vector Types | Logical Vectors

1. **logical**

Can only hold the values `TRUE` or `FALSE`


```r
logi_vec <- c(TRUE, TRUE, FALSE)
print(logi_vec)
```


## The 4 Atomic Vector Types | Integer Vectors

1. logical
2. **integer**

Useful for counts, ranks or indexing positions (e.g. column 3; nucleotide 254731)


```r
int_vec <- 1:5
print(int_vec)
```


## The 4 Atomic Vector Types | Double (i.e. Double Precision) Vectors

1. logical
2. integer
3. **double**

Often (& *lazily*) referred to as numeric


```r
dbl_vec <- c(0.618, 1.414, 2)
print(dbl_vec)
```

## The 4 Atomic Vector Types | Character Vectors

1. integer
2. logical
3. double
4. **character**


```r
char_vec <- c("blue", "red", "green")
print(char_vec)
```

```
## [1] "blue"  "red"   "green"
```

## The 4 Atomic Vector Types

These are the basic building blocks for all `R` objects

1. logical
2. integer
3. double
4. character

- Many other vector types built on these
- There are two more rare types we'll ignore: `complex` & `raw`

## The 4 Atomic Vector Types

To find what type of vector we have


```r
typeof(char_vec)
```

## The 4 Atomic Vector Types

### Importantly: _Every element of a vector is of the same type_

For example, if there is one number amongst some character values, it will also be _coerced_ to a character


```r
simp_vec <- c(742, "Evergreen", "Terrace")
simp_vec
```

Notice how the `742` now has quotation marks


```r
typeof(simp_vec)
```

## The 4 Atomic Vector Types

### Can numbers be coerced to characters?

### Can characters be coerced to numbers


```r
as.numeric(simp_vec)
```

You will see this error many times...

## The 4 Atomic Vector Types

Vectors can be coerced up the hierarchy with no information loss

- `logical` $\rightarrow$ `integer` $\rightarrow$ `numeric` $\rightarrow$ `character`


```r
as.integer(logi_vec)
as.character(logi_vec)
```

## The 4 Atomic Vector Types

Information will be lost going the other way


```r
as.integer(dbl_vec)
as.logical(c(2, 1, 0))
```


## Named Vectors

- We can specify a name for each element of a vector


```r
names(x) <- c("a", "b", "c")
x
```

- Notice that the names form a `character` vector

# Subsetting Vectors

## Subsetting Vectors

- The elements of a vector can be called using `[]`


```r
x[2]
x[c(1, 3)]
```

## Subsetting Vectors

- Double brackets (`[[]]`) can be used to return __single elements__ only


```r
x[[2]]
```

- If you tried `x[[c(1,3)]]` you would receive an error message
- Note that the names were also not returned by this method

## Subsetting Vectors

If a vector has `names` attributes, we can call values by name


```r
x[c("a", "c")]
x[["b"]]
```

1. Using `[]` returned the vector with the identical structure
2. Using `[[]]` removed the `attributes` & just gave the value

## Subsetting Vectors 

### Discussion Question

__Is it better to call by position, or by name?__

Things to consider:

- Which is easier to read?
- Which is more robust to undocumented changes in an object?


## Vector Operations

We can combine the above logical test and subsetting


```r
dbl_vec
dbl_vec > 1
dbl_vec[dbl_vec > 1]
```


## Vector Operations

An additional logical test: `%in%`  
(read as: "*is in*")


```r
dbl_vec %in% int_vec
```

Returns `TRUE/FALSE` for each value in `dbl_vec` if it **is in** or **is not in** `int_vec`

NB: `int_vec` was coerced silently to a `double` vector


---

<div class="footer" style="text-align:center;width:25%">
[Home](https://uofabioinformaticshub.github.io/Intro_R_Genomics_Dec_2016/)
</div>
