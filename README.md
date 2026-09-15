<!-- badges: start -->
[![Project Status](https://www.repostatus.org/badges/latest/wip.svg)](https://www.repostatus.org/#wip)
[![CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-brightgreen)](https://raw.githubusercontent.com/inbo/citeme/refs/heads/main/inst/licenses/cc_by_4_0.md)
![GitHub repo size](https://img.shields.io/github/repo-size/wlangera/futurize-talk-2026)
<!-- badges: end -->

# futurize talk 2026

Presentation as part of the monthly talks by BMK for the Research Institute for Nature and Forest (INBO).

The presentation is a summary of the workshop:

**"Introduction to Parallel Processing in R using Futureverse - Easier than Ever Before"**
Henrik Bengtsson, useR! conference, 6 July 2026.

These slides are condensed notes based on the original workshop and are intended as a short introduction for an INBO audience.
They do not replace the original workshop materials.
The original futureverse tutorials and workshop materials are available at:

<https://www.futureverse.org/tutorials.html>

## Preparation

### Step 1: Install packages

```r
install.packages("futureverse")
```

### Step 2: Make sure everything is up to date

```r
futureverse::futureverse_update()
#> All futureverse packages up-to-date
```

### Step 3: Verify that it works

```r
library(futurize)

plan(multisession, workers = 2)
plan(sequential)
```

## Some functions used during the talk

```r
# Take the slow sum of numeric values
slow_sum <- function(x) {
  sum <- 0
  for (value in x) {
    Sys.sleep(1)    # one-second slowdown per value
    sum <- sum + value
  }
  sum
}

# Take the square root of numeric value
slow_sqrt <- function(x) {
  Sys.sleep(0.5)  # half-second delay per item
  sqrt(x)
}
```

```r
# Functions to verify run time
tic <- futureverse:::tic
toc <- futureverse:::toc
```
