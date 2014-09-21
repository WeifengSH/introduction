---
title       : Dectector for Species for Iris
subtitle    : 
author      : Weifeng
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Fisher's Iris Data Set

- The `Iris flower data set` or `Fisher's Iris data set` is a multivariate data set introduced by **Sir Ronald Fisher** (1936) as an example of **discriminant analysis**.
- It is sometimes called `Anderson's Iris data set` because **Edgar Anderson** collected the data to quantify the morphologic variation of Iris flowers of three related species.
- The data set consists of 50 samples from each of three species of Iris. Four features were measured from each sample: the length and the width of the sepals and petals, in *centimeters*.

---

## Getting Data Set in R Language

- `Fisher's Iris data set` has been included in R language.


```r
data(iris)
head(iris)
```

```
##   Sepal.Length Sepal.Width Petal.Length Petal.Width Species
## 1          5.1         3.5          1.4         0.2  setosa
## 2          4.9         3.0          1.4         0.2  setosa
## 3          4.7         3.2          1.3         0.2  setosa
## 4          4.6         3.1          1.5         0.2  setosa
## 5          5.0         3.6          1.4         0.2  setosa
## 6          5.4         3.9          1.7         0.4  setosa
```

- The first four variables represent the length and the width of the sepals and petals (in *centimeters*).
- The last variables represent the species of the specific Iris flower.

---

## Distribution of Species of Iris

Create a plot according to the relationship between the species and the width of the sepal, width.

![plot of chunk plot](assets/fig/plot.png) 

---

## Prediction Using Decision Tree

According to the plot demonstrated previously, algorithm **decision tree** can be used to predict the species based on other groups of parameters.

- **Decision tree** iteratively split variables into groups, evaluate "homogeneity" within each group, and split again if necessary.
- Pros:
  - Easy to interpret
  - Better performance in nonlinear settings
- Use method `rpart` in the package `caret` to perform this algorithm as below.

```
train(Species ~ ., method = "rpart", data = training)
```

- Find the result as a [ShinyApps](https://klaith.shinyapps.io/shiny/ "Detector for Species of Iris on ShinyApps.io").
