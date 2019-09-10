---
title: "`kable` Table from Package `knitr`"
author: "Student R. Me"
date: "09 September, 2019"
output: 
    html_document:
        keep_md: true
    pdf_document: default
    word_document: default
---


<!-- set root directory here --> 


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

## Build a table using the `kable` function from package `knitr`

This table includes options for "readable" column header names, data alignments within columns, and a table caption.


```r
# build a table using fxn kable from package knitr
  library(knitr)  # load library: knitr
  kable(f1, col.names = c("Sex", "Fish Species", "Frequency"), align = c("l", "c", "r"),
    caption = "Fish capture freqeuncy by osprey sex")
```



Table: Fish capture freqeuncy by osprey sex

Sex       Fish Species    Frequency
-------  --------------  ----------
Male        Sunfish              59
Female      Sunfish              72
Male          Bass               14
Female        Bass               21
Male          Shad              189
Female        Shad              138

---

### The RMD code used to build the HTML output is in the box below

    ---
    title: "`kable` Table from Package `knitr`"
    author: "Student R. Me"
    date: "`r format(Sys.time(), '%d %B, %Y')`"
    html_document:
        keep_md: true
    pdf_document: default
    word_document: default  
    ---
    
    
    <!-- set root directory here --> 
    ```{r global_options, include=FALSE}
    knitr::opts_knit$set(root.dir = "~/words/classes/markdownR/markdown_html")
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
    
    ## Build a table using the `kable` function from package `knitr`
    
    This table includes options for "readable" column header names, data alignments within columns, and a table caption.
    
    ```{r}
    # build a table using fxn kable from package knitr
      library(knitr)  # load library: knitr
      kable(f1, col.names = c("Sex", "Fish Species", "Frequency"), align = c("l", "c", "r"),
        caption = "Fish capture freqeuncy by osprey sex")
    ```
    
    ---




