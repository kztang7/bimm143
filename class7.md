class7
================

``` r
source("http://tinyurl.com/rescale-R")

# write a both_na() function
x <- c( 1, 2, NA, 3, NA)
y <- c(NA, 3, NA, 3, 4)
is.na(x) #finds which are 'na'
```

    ## [1] FALSE FALSE  TRUE FALSE  TRUE

``` r
is.na(y)
```

    ## [1]  TRUE FALSE  TRUE FALSE FALSE

``` r
is.na(x) & is.na(y) #finds which are 'na' in both
```

    ## [1] FALSE FALSE  TRUE FALSE FALSE

``` r
sum(is.na(x) & is.na(y)) #how many are 'na' in same position
```

    ## [1] 1

``` r
# function for NA finding
both_na <- function(x, y) {
  sum( is.na(x) & is.na(y) )
}
both_na(x,y)
```

    ## [1] 1

``` r
x <- c(NA, NA, NA)
y1 <- c( 1, NA, NA)
y2 <- c( 1, NA, NA, NA)

# Find matching genes (intersect of two data.frames)
# Simplify further to single vectors
# Simplify further to single vectors
x <- df1$IDs
y <- df2$IDs
intersect(x,y)
```

    ## [1] "gene2" "gene3"

``` r
inds <- x %in% y # tests if values of x are in y
x[inds]
```

    ## [1] "gene2" "gene3"

``` r
y[y %in% x]
```

    ## [1] "gene2" "gene3"

``` r
df1[df1$IDs %in% df2$IDs, ] 
```

    ##     IDs exp
    ## 2 gene2   1
    ## 3 gene3   1

``` r
df2[df2$IDs %in% df1$IDs, ]
```

    ##     IDs exp
    ## 1 gene2  -2
    ## 3 gene3   1
