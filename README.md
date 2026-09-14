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
