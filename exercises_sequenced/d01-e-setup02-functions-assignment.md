Setup: Function Basics
================
2020-05-03

# Setup: Function Basics

*Purpose*: Functions are our primary tool in carrying out data analysis
with the `tidyverse`. It is unreasonable to expect yourself to memorize
every function and all its details. To that end, we’ll learn some basic
*function literacy* in R; how to inspect a function, look up its
documentation, and find examples on a function’s use.

*Reading*: [Programming
Basics](https://rstudio.cloud/learn/primers/1.2). *Topics*: `functions`,
`arguments` *Reading Time*: ~ 10 minutes

### **q1** How do you find help on a function? Get help on the built-in `rnorm` function.

``` r
## Your code here
?rnorm
```

### **q2** How do you show the source code for a function?

``` r
## Your code here
help
```

    ## function (topic, package = NULL, lib.loc = NULL, verbose = getOption("verbose"), 
    ##     try.all.packages = getOption("help.try.all.packages"), help_type = getOption("help_type")) 
    ## {
    ##     types <- c("text", "html", "pdf")
    ##     help_type <- if (!length(help_type)) 
    ##         "text"
    ##     else match.arg(tolower(help_type), types)
    ##     if (!missing(package)) 
    ##         if (is.name(y <- substitute(package))) 
    ##             package <- as.character(y)
    ##     if (missing(topic)) {
    ##         if (!is.null(package)) {
    ##             if (interactive() && help_type == "html") {
    ##                 port <- tools::startDynamicHelp(NA)
    ##                 if (port <= 0L) 
    ##                   return(library(help = package, lib.loc = lib.loc, 
    ##                     character.only = TRUE))
    ##                 browser <- if (.Platform$GUI == "AQUA") {
    ##                   get("aqua.browser", envir = as.environment("tools:RGUI"))
    ##                 }
    ##                 else getOption("browser")
    ##                 browseURL(paste0("http://127.0.0.1:", port, "/library/", 
    ##                   package, "/html/00Index.html"), browser)
    ##                 return(invisible())
    ##             }
    ##             else return(library(help = package, lib.loc = lib.loc, 
    ##                 character.only = TRUE))
    ##         }
    ##         if (!is.null(lib.loc)) 
    ##             return(library(lib.loc = lib.loc))
    ##         topic <- "help"
    ##         package <- "utils"
    ##         lib.loc <- .Library
    ##     }
    ##     ischar <- tryCatch(is.character(topic) && length(topic) == 
    ##         1L, error = function(e) FALSE)
    ##     if (!ischar) {
    ##         reserved <- c("TRUE", "FALSE", "NULL", "Inf", "NaN", 
    ##             "NA", "NA_integer_", "NA_real_", "NA_complex_", "NA_character_")
    ##         stopic <- deparse1(substitute(topic))
    ##         if (!is.name(substitute(topic)) && !stopic %in% reserved) 
    ##             stop("'topic' should be a name, length-one character vector or reserved word")
    ##         topic <- stopic
    ##     }
    ##     paths <- index.search(topic, find.package(if (is.null(package)) 
    ##         loadedNamespaces()
    ##     else package, lib.loc, verbose = verbose))
    ##     try.all.packages <- !length(paths) && is.logical(try.all.packages) && 
    ##         !is.na(try.all.packages) && try.all.packages && is.null(package) && 
    ##         is.null(lib.loc)
    ##     if (try.all.packages) {
    ##         for (lib in .libPaths()) {
    ##             packages <- .packages(TRUE, lib)
    ##             packages <- packages[is.na(match(packages, .packages()))]
    ##             paths <- c(paths, index.search(topic, file.path(lib, 
    ##                 packages)))
    ##         }
    ##         paths <- paths[nzchar(paths)]
    ##     }
    ##     structure(unique(paths), call = match.call(), topic = topic, 
    ##         tried_all_packages = try.all.packages, type = help_type, 
    ##         class = "help_files_with_topic")
    ## }
    ## <bytecode: 0x1392222b0>
    ## <environment: namespace:utils>

### **q3** Using either the documentation or the source, determine the arguments for `rnorm`.

rnorm(n, mean = 0, sd = 1) args: n, mean, sd

### **q4** Scroll to the bottom of the help for the `library()` function. How do you

list all available packages?

Code ran:

``` r
?library
```

Answer:

``` r
library()                   # list all available packages
```

The **examples** in the help documentation are often *extremely* helpful
for learning how to use a function (or reminding yourself how its used)!
Get used to checking the examples, as they’re a great resource.

<!-- include-exit-ticket -->

# Exit Ticket

<!-- -------------------------------------------------- -->

Once you have completed this exercise, make sure to fill out the **exit
ticket survey**, [linked
here](https://docs.google.com/forms/d/e/1FAIpQLSeuq2LFIwWcm05e8-JU84A3irdEL7JkXhMq5Xtoalib36LFHw/viewform?usp=pp_url&entry.693978880=e-setup02-functions-assignment.Rmd).
