---
title: 'At DataFest 2019, I Learned...'
author: 'Edward A. Roualdes'
date: '2019-04-09'
slug: learnings
categories: []
tags: []
description: ''
---

# Introduction

During [CSU, Chico's DataFest 2019](https://csudsi.netlify.com/2019/02/17/2019-02-17-asa-datafest-2019/), two questions from different teams provided me (Edward, not Dr. Donatello) an excellent learning experience.  This blog post attempts to describe the problems these teams faced and then offer up some solutions.  This post is about my own learnings during DataFest and does not even pretend to claim that these are the only, nor the best, solutions to these problems.

# Team Re(sps)

The physics team asked me about transforming multiple, specific columns within a Python $\texttt{pandas.DataFrame.groupby}$ operation.  It took me a minute, but here's what I came up with.  Three specific variables are standardized and then checked to ensure that the correct thing happened.


```python
import pandas as pd

# setup
df = pd.read_csv("~/data/finches.csv")
vars = ['winglength', 'taillength', 'middletoelength']
zvars = ['z' + x for x in vars]

# solution
df[zvars] = df.groupby('island')[vars].transform(lambda x: (x - x.mean())/x.std())

# check
df.groupby('island')[zvars].agg({'mean', 'std'})
```

```
##                zwinglength        ztaillength      zmiddletoelength     
##                       mean  std          mean  std             mean  std
## island                                                                  
## floreana     -8.710981e-16  1.0 -6.148928e-16  1.0    -1.340808e-15  1.0
## sancristobal  1.513193e-15  1.0  1.940834e-15  1.0    -1.233581e-15  1.0
## santacruz    -7.401487e-16  1.0 -4.144833e-16  1.0    -1.657933e-15  1.0
```

## Team Data Strikes Back

Team Data Strikes Back wanted to number the levels of a categorical variable.  Here's some made up data to represent the idea.  Our goal is to index the levels of $f$.


```r
suppressMessages(library(dplyr))
df <- tibble(f = sample(letters, 20, replace=TRUE))
```
The solution I came up with relies on sorting the data, so let's do that first.

```r
o <- order(df$f)
df <- df[o,,drop=FALSE]
df$nf <- match(df$f, unique(df$f))

# check
head(df)
```

```
## # A tibble: 6 x 2
##   f        nf
##   <chr> <int>
## 1 a         1
## 2 d         2
## 3 g         3
## 4 g         3
## 5 g         3
## 6 i         4
```

Surely there's other ways to do this; R ~~probably~~ has a function for it.  But I ~~don't~~ didn't know which function.  Moreover, this solution is general enough to be used within a broader grouping variable $g$ and does not require any variable to be a factor.

```r
number_levels <- function(x) {
  x <- sort(x)
  match(x, unique(x))
}
df$g <- as.character(gl(4, 5, labels=sample(LETTERS, 4)))

df <- df %>%
  group_by(g) %>%
  mutate(gf = number_levels(f))
```
It requires some extra work if you want the numbered levels to be increasing across the levels of some grouping variable $g$, but we can manage with some help from a rarely used assignment operator.

```r
index_grouped_levels <- function() {
  idx <- 0
  nl <- function(x) {
    levels <- number_levels(x) + idx
    idx <<- max(levels)
    levels
  }
  nl
}

igrp_levels <- index_grouped_levels()
df <- df %>%
  arrange(g, f) %>%
  group_by(g) %>%
  mutate(ngf = igrp_levels(f))
```
### A Simpler Solution

On the Tuesday after DataFest, I show off my work to Dr. Donatello, and she looks at me like I'm crazy.  She says, "What about $\texttt{as.numeric(f)}$ called on a factor?"  I respond, "Ffa, sha, wha?"  Then she shows me, and we worked out this gem.

```r
df <- tibble(f = sample(letters, 20, replace=TRUE))
df$g <- as.character(gl(4, 5, labels=sample(LETTERS, 4)))

# as.numeric() on a concatenated factor
df <- df %>%
  arrange(desc(g), f) %>%
  mutate(gf = paste0(g, f)) %>%
  mutate(mgf = as.numeric(as.factor(gf)))

# my strategy
igrp_levels <- index_grouped_levels()
df <- df %>%
  group_by(g) %>%
  mutate(ngf = igrp_levels(f))

all(df$mgf == df$ngf)
```

```
## [1] TRUE
```

# Conclusion

Dr. D's solution is much simpler, but at least I came up with a solution and learned something along the way.  DataFest 2019 was great, and it's my opinion that all involved gained a lot from the event. Thanks, Dr. D.
