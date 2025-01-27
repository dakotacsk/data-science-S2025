Vis: Data Visualization Basics
================
Zach del Rosario
2020-05-03

# Vis: Data Visualization Basics

*Purpose*: The most powerful way for us to learn about a dataset is to
*visualize the data*. Throughout this class we will make extensive use
of the *grammar of graphics*, a powerful graphical programming *grammar*
that will allow us to create just about any graph you can imagine!

*Reading*: [Data Visualization
Basics](https://rstudio.cloud/learn/primers/1.1). *Note*: In RStudio use
`Ctrl + Click` (Mac `Command + Click`) to follow the link. *Topics*:
`Welcome`, `A code template`, `Aesthetic mappings`. *Reading Time*: ~ 30
minutes

### **q1** Inspect the `diamonds` dataset. What do the `cut`, `color`, and `clarity` variables mean?

*Hint*: We learned how to inspect a dataset in `e-data-00-basics`!

### **q2** Use your “standard checks” to determine what variables the dataset has.

Now that we have the list of variables in the dataset, we know what we
can visualize!

### **q3** Using `ggplot`, visualize `price` vs `carat` with points. What trend do

you observe?

*Hint*: Usually the language `y` vs `x` refers to the `vertical axis` vs
`horizontal axis`. This is the opposite order from the way we often
specify `x, y` pairs. Language is hard!

``` r
## TODO: Complete this code
ggplot(diamonds)
```

![](d05-e-vis00-basics-assignment_files/figure-gfm/q3-task-1.png)<!-- -->

**Observations**:

- (Write your observations here!)

## A note on *aesthetics*

The function `aes()` is short for *aesthetics*. Aesthetics in ggplot are
the mapping of variables in a dataframe to visual elements in the graph.
For instance, in the plot above you assigned `carat` to the `x`
aesthetic, and `price` to the `y` aesthetic. But there are *many more*
aesthetics you can set, some of which vary based on the `geom_` you are
using to visualize. The next question will explore this idea more.

### **q4** Create a new graph to visualize `price`, `carat`, and `cut`

simultaneously.

*Hint*: Remember that you can add additional aesthetic mappings in
`aes()`. Some options include `size`, `color`, and `shape`.

``` r
## TODO: Complete this code
ggplot(diamonds)
```

![](d05-e-vis00-basics-assignment_files/figure-gfm/q4-task-1.png)<!-- -->

**Observations**:

- (Write your observations here!)

<!-- include-exit-ticket -->

# Exit Ticket

<!-- -------------------------------------------------- -->

Once you have completed this exercise, make sure to fill out the **exit
ticket survey**, [linked
here](https://docs.google.com/forms/d/e/1FAIpQLSeuq2LFIwWcm05e8-JU84A3irdEL7JkXhMq5Xtoalib36LFHw/viewform?usp=pp_url&entry.693978880=e-vis00-basics-assignment.Rmd).
