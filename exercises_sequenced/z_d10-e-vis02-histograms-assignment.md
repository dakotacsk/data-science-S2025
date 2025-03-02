Vis: Histograms
================
Zach del Rosario
2020-05-22

# Vis: Histograms

*Purpose*: *Histograms* are a key tool for EDA. In this exercise we’ll
get a little more practice constructing and interpreting histograms and
densities.

*Reading*: [Histograms](https://rstudio.cloud/learn/primers/3.3)
*Topics*: (All topics) *Reading Time*: ~20 minutes

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

### **q1** Using the graphs generated in the chunks `q1-vis1` and `q1-vis2` below, answer:

- Which `class` has the most vehicles?
- Which `class` has the broadest distribution of `cty` values?
- Which graph—`vis1` or `vis2`—best helps you answer each question?

``` r
## NOTE: No need to modify
mpg %>%
  ggplot(aes(cty, color = class)) +
  geom_freqpoly(bins = 10)
```

![](d10-e-vis02-histograms-assignment_files/figure-gfm/q1-vis1-1.png)<!-- -->

``` r
## NOTE: No need to modify
mpg %>%
  ggplot(aes(cty, color = class)) +
  geom_density()
```

![](d10-e-vis02-histograms-assignment_files/figure-gfm/q1-vis2-1.png)<!-- -->

In the previous exercise, we learned how to *facet* a graph. Let’s use
that part of the grammar of graphics to clean up the graph above.

### **q2** Modify `q1-vis2` to use a `facet_wrap()` on the `class`. “Free” the vertical axis with the `scales` keyword to allow for a different y scale in each facet.

``` r
mpg %>%
  ggplot(aes(cty, color = class)) +
  geom_density() +
  facet_wrap(~class, scales = "free_y")
```

![](d10-e-vis02-histograms-assignment_files/figure-gfm/q2-task-1.png)<!-- -->

In the reading, we learned that the “most important thing” to keep in
mind with `geom_histogram()` and `geom_freqpoly()` is to *explore
different binwidths*. We’ll explore this idea in the next question.

### **q3** Analyze the following graph; make sure to test different binwidths. What patterns do you see? Which patterns remain as you change the binwidth?

``` r
## TODO: Run this chunk; play with differnet bin widths
diamonds %>%
  filter(carat < 1.1) %>%

  ggplot(aes(carat)) +
  geom_histogram(binwidth = 0.005, boundary = 0.005) +
  scale_x_continuous(
    breaks = seq(0, 1, by = 0.1)

  )
```

![](d10-e-vis02-histograms-assignment_files/figure-gfm/q3-task-1.png)<!-- -->

**Observations** - Write your observations here!

<!-- include-exit-ticket -->

# Exit Ticket

<!-- -------------------------------------------------- -->

Once you have completed this exercise, make sure to fill out the **exit
ticket survey**, [linked
here](https://docs.google.com/forms/d/e/1FAIpQLSeuq2LFIwWcm05e8-JU84A3irdEL7JkXhMq5Xtoalib36LFHw/viewform?usp=pp_url&entry.693978880=e-vis02-histograms-assignment.Rmd).
