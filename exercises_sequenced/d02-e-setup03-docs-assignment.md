Setup: Documentation
================
2020-05-05

# Setup: Documentation

*Purpose*: No programmer memorizes every fact about every function.
Expert programmers get used to quickly reading *documentation*, which
allows them to look up the facts they need, when they need them. Just as
you had to learn how to read English, you will have to learn how to
consult documentation. This exercise will get you started.

*Reading*: [Getting help with R](https://www.r-project.org/help.html)
(Vignettes and Code Demonstrations)

``` r
library(tidyverse)
```

    ## ── Attaching core tidyverse packages ──────────────────────── tidyverse 2.0.0 ──
    ## ✔ dplyr     1.1.4     ✔ readr     2.1.5
    ## ✔ forcats   1.0.0     ✔ stringr   1.5.1
    ## ✔ ggplot2   3.5.1     ✔ tibble    3.2.1
    ## ✔ lubridate 1.9.3     ✔ tidyr     1.3.1
    ## ✔ purrr     1.0.2     
    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()
    ## ℹ Use the conflicted package (<http://conflicted.r-lib.org/>) to force all conflicts to become errors

The `vignette()` function allows us to look up
[vignettes](https://stat.ethz.ch/R-manual/R-devel/library/utils/html/vignette.html);
short narrative-form tutorials associated with a package, written by its
developers.

### **q1** Use `vignette(package = ???)` (fill in the ???) to look up vignettes

associated with `"dplyr"`. What vignettes are available?

``` r
## TODO: Re-write the code above following the tidyverse style guide
vignette("dplyr", package = "dplyr")
```

Once we know *what* vignettes are available, we can use the same
function to read a particular vignette.

### **q2** Use `vignette(???, package = "dplyr")` to read the vignette on `dplyr`.

Read this vignette up to the first note on `filter()`. Use `filter()` to
select only those rows of the `iris` dataset where
`Species == "setosa"`.

*Note*: This should open up your browser.

``` r
## Filter the iris dataset
iris %>%
  as_tibble() %>%
  filter(Species == "setosa")
```

    ## # A tibble: 50 × 5
    ##    Sepal.Length Sepal.Width Petal.Length Petal.Width Species
    ##           <dbl>       <dbl>        <dbl>       <dbl> <fct>  
    ##  1          5.1         3.5          1.4         0.2 setosa 
    ##  2          4.9         3            1.4         0.2 setosa 
    ##  3          4.7         3.2          1.3         0.2 setosa 
    ##  4          4.6         3.1          1.5         0.2 setosa 
    ##  5          5           3.6          1.4         0.2 setosa 
    ##  6          5.4         3.9          1.7         0.4 setosa 
    ##  7          4.6         3.4          1.4         0.3 setosa 
    ##  8          5           3.4          1.5         0.2 setosa 
    ##  9          4.4         2.9          1.4         0.2 setosa 
    ## 10          4.9         3.1          1.5         0.1 setosa 
    ## # ℹ 40 more rows

Vignettes are useful when we only know *generally* what we’re looking
for. Once we know the verbs (functions) we want to use, we need more
specific help.

### **q3** Remember back to `e-setup02-functions`; how do we look up help for a specific function?

? or help()

Sometimes we’ll be working with a function, but we won’t *quite* know
how to get it to do what we need. In this case, consulting the
function’s documentation can be *extremely* helpful.

### **q4** Use your knowledge of documentation lookup to answer the following

question: How could we `filter` the `iris` dataset to return only those
rows with `Sepal.Length` between `5.1` and `6.4`?

``` r
## TODO: Consult the docs; Write your code here

#?filter

filter(iris, Sepal.Length < 6.4 & Sepal.Length > 5.1)
```

    ##    Sepal.Length Sepal.Width Petal.Length Petal.Width    Species
    ## 1           5.4         3.9          1.7         0.4     setosa
    ## 2           5.4         3.7          1.5         0.2     setosa
    ## 3           5.8         4.0          1.2         0.2     setosa
    ## 4           5.7         4.4          1.5         0.4     setosa
    ## 5           5.4         3.9          1.3         0.4     setosa
    ## 6           5.7         3.8          1.7         0.3     setosa
    ## 7           5.4         3.4          1.7         0.2     setosa
    ## 8           5.2         3.5          1.5         0.2     setosa
    ## 9           5.2         3.4          1.4         0.2     setosa
    ## 10          5.4         3.4          1.5         0.4     setosa
    ## 11          5.2         4.1          1.5         0.1     setosa
    ## 12          5.5         4.2          1.4         0.2     setosa
    ## 13          5.5         3.5          1.3         0.2     setosa
    ## 14          5.3         3.7          1.5         0.2     setosa
    ## 15          5.5         2.3          4.0         1.3 versicolor
    ## 16          5.7         2.8          4.5         1.3 versicolor
    ## 17          6.3         3.3          4.7         1.6 versicolor
    ## 18          5.2         2.7          3.9         1.4 versicolor
    ## 19          5.9         3.0          4.2         1.5 versicolor
    ## 20          6.0         2.2          4.0         1.0 versicolor
    ## 21          6.1         2.9          4.7         1.4 versicolor
    ## 22          5.6         2.9          3.6         1.3 versicolor
    ## 23          5.6         3.0          4.5         1.5 versicolor
    ## 24          5.8         2.7          4.1         1.0 versicolor
    ## 25          6.2         2.2          4.5         1.5 versicolor
    ## 26          5.6         2.5          3.9         1.1 versicolor
    ## 27          5.9         3.2          4.8         1.8 versicolor
    ## 28          6.1         2.8          4.0         1.3 versicolor
    ## 29          6.3         2.5          4.9         1.5 versicolor
    ## 30          6.1         2.8          4.7         1.2 versicolor
    ## 31          6.0         2.9          4.5         1.5 versicolor
    ## 32          5.7         2.6          3.5         1.0 versicolor
    ## 33          5.5         2.4          3.8         1.1 versicolor
    ## 34          5.5         2.4          3.7         1.0 versicolor
    ## 35          5.8         2.7          3.9         1.2 versicolor
    ## 36          6.0         2.7          5.1         1.6 versicolor
    ## 37          5.4         3.0          4.5         1.5 versicolor
    ## 38          6.0         3.4          4.5         1.6 versicolor
    ## 39          6.3         2.3          4.4         1.3 versicolor
    ## 40          5.6         3.0          4.1         1.3 versicolor
    ## 41          5.5         2.5          4.0         1.3 versicolor
    ## 42          5.5         2.6          4.4         1.2 versicolor
    ## 43          6.1         3.0          4.6         1.4 versicolor
    ## 44          5.8         2.6          4.0         1.2 versicolor
    ## 45          5.6         2.7          4.2         1.3 versicolor
    ## 46          5.7         3.0          4.2         1.2 versicolor
    ## 47          5.7         2.9          4.2         1.3 versicolor
    ## 48          6.2         2.9          4.3         1.3 versicolor
    ## 49          5.7         2.8          4.1         1.3 versicolor
    ## 50          6.3         3.3          6.0         2.5  virginica
    ## 51          5.8         2.7          5.1         1.9  virginica
    ## 52          6.3         2.9          5.6         1.8  virginica
    ## 53          5.7         2.5          5.0         2.0  virginica
    ## 54          5.8         2.8          5.1         2.4  virginica
    ## 55          6.0         2.2          5.0         1.5  virginica
    ## 56          5.6         2.8          4.9         2.0  virginica
    ## 57          6.3         2.7          4.9         1.8  virginica
    ## 58          6.2         2.8          4.8         1.8  virginica
    ## 59          6.1         3.0          4.9         1.8  virginica
    ## 60          6.3         2.8          5.1         1.5  virginica
    ## 61          6.1         2.6          5.6         1.4  virginica
    ## 62          6.3         3.4          5.6         2.4  virginica
    ## 63          6.0         3.0          4.8         1.8  virginica
    ## 64          5.8         2.7          5.1         1.9  virginica
    ## 65          6.3         2.5          5.0         1.9  virginica
    ## 66          6.2         3.4          5.4         2.3  virginica
    ## 67          5.9         3.0          5.1         1.8  virginica

On other occasions we’ll know a function, but would like to know about
other, related functions. In this case, it’s useful to be able to trace
the `function` back to its parent `package`. Then we can read the
vignettes on the package to learn more.

### **q5** Look up the documentation on `cut_number`; what package does it come

from? What about `parse_number()`? What about `row_number()`?

``` r
?cut_number # [Package ggplot2 version 3.5.1 Index]

?parse_number # [Package readr version 2.1.5 Index]

?row_number # [Package dplyr version 1.1.4 Index]
```

<!-- include-exit-ticket -->

# Exit Ticket

<!-- -------------------------------------------------- -->

Once you have completed this exercise, make sure to fill out the **exit
ticket survey**, [linked
here](https://docs.google.com/forms/d/e/1FAIpQLSeuq2LFIwWcm05e8-JU84A3irdEL7JkXhMq5Xtoalib36LFHw/viewform?usp=pp_url&entry.693978880=e-setup03-docs-assignment.Rmd).
