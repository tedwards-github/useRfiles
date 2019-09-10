---
title: "`pander` Tables with Data and Analytical Output"
author: "Student R. Me"
date: "09 September, 2019"
output: 
    html_document:
        keep_md: true
    pdf_document: default
    word_document: default
---


<!-- set root directory here --> 
<!-- your directory will be specific to you -->


---

---

## Data for table construction


```r
# import data and examine dataframe characteristics
  f1 <- read.csv("data/ospreypreybysex.csv", header = T)
  f1
```

```
##   ospreysex fishspp count
## 1      Male Sunfish    59
## 2    Female Sunfish    72
## 3      Male    Bass    14
## 4    Female    Bass    21
## 5      Male    Shad   189
## 6    Female    Shad   138
```

---

## Table using the package `pander`


```r
# built a table using pander
  library(pander)
  names(f1)=c("Sex", "Fish Species", "Frequency")  # rename columns
  pander(f1, caption = "Fish capture frequency by osprey sex", 
   justify = c("right", "center", "center"))  # rendered table in html format
```


-----------------------------------
     Sex  Fish Species   Frequency 
-------- -------------- -----------
    Male    Sunfish         59     

  Female    Sunfish         72     

    Male      Bass          14     

  Female      Bass          21     

    Male      Shad          189    

  Female      Shad          138    
-----------------------------------

Table: Fish capture frequency by osprey sex

---

## Analytical output for table construction


```r
# import data and examine dataframe characteristics
  f1 <- read.csv("data/ospreypreybysex.csv", header = T)
# chi-sq test
  f2 <- xtabs(count ~ ospreysex + fishspp, data = f1)  # cross-tab the data
  f3 <- chisq.test(f2)  # chisq test
  f3
```

```
## 
## 	Pearson's Chi-squared test
## 
## data:  f2
## X-squared = 8.7294, df = 2, p-value = 0.01272
```

---

## `pander` table of analytical output


```r
# render statsical output as a table: chi-sq test from above
  library(pander)
  pander(f3, caption = "$\\chi^2$ test of fish capture frequency by osprey sex")
```


---------------------------------
 Test statistic   df    P value  
---------------- ---- -----------
     8.729        2    0.01272 * 
---------------------------------

Table: $\chi^2$ test of fish capture frequency by osprey sex

---

### The RMD code used to build the HTML output is in the box below

    ---
    title: "`pander` Tables with Data and Analytical Output"
    author: "Student R. Me"
    date: "`r format(Sys.time(), '%d %B, %Y')`"
    output: 
        html_document:
            keep_md: true
        pdf_document: default
        word_document: default
    ---
    
    
    <!-- set root directory here --> 
    <!-- your directory will be specific to you -->
    ```{r global_options, include=FALSE}
    knitr::opts_knit$set(root.dir = "~/words/github/useRfiles/rmd-files")
    knitr::opts_chunk$set(warning=FALSE)
    ```
    
    ---
    
    ---
    
    ## Data for table construction
    
    ```{r}
    # import data and examine dataframe characteristics
      f1 <- read.csv("data/ospreypreybysex.csv", header = T)
      f1
    ```
    
    ---
    
    ## Table using the package `pander`
    
    ```{r}
    # built a table using pander
      library(pander)
      names(f1)=c("Sex", "Fish Species", "Frequency")  # rename columns
      pander(f1, caption = "Fish capture frequency by osprey sex", 
       justify = c("right", "center", "center"))  # rendered table in html format
    ```
    
    ---
    
    ## Analytical output for table construction
    
    ```{r}
    # import data and examine dataframe characteristics
      f1 <- read.csv("data/ospreypreybysex.csv", header = T)
    # chi-sq test
      f2 <- xtabs(count ~ ospreysex + fishspp, data = f1)  # cross-tab the data
      f3 <- chisq.test(f2)  # chisq test
      f3
    ```
    
    ---
    
    ## `pander` table of analytical output
    
    ```{r}
    # render statsical output as a table: chi-sq test from above
      library(pander)
      pander(f3, caption = "$\\chi^2$ test of fish capture frequency by osprey sex")
    ```
    
    ---



