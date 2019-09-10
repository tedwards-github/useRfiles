---
title: "A `xtable` Table"
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

## `xtable` table with `results="asis"`

By adding the option `results="asis"` to the **chunk** the table is now rendered into text.


```r
library(xtable)
# xtable(f1)  NOT RUN: would return a default table of LaTex code
print(xtable(f1), type="html", include.rownames=F)  # rendered table in html format
```

<!-- html table generated in R 3.5.3 by xtable 1.8-4 package -->
<!-- Mon Sep 09 19:50:37 2019 -->
<table border=1>
<tr> <th> ospreysex </th> <th> fishspp </th> <th> count </th>  </tr>
  <tr> <td> Male </td> <td> Sunfish </td> <td align="right">  59 </td> </tr>
  <tr> <td> Female </td> <td> Sunfish </td> <td align="right">  72 </td> </tr>
  <tr> <td> Male </td> <td> Bass </td> <td align="right">  14 </td> </tr>
  <tr> <td> Female </td> <td> Bass </td> <td align="right">  21 </td> </tr>
  <tr> <td> Male </td> <td> Shad </td> <td align="right"> 189 </td> </tr>
  <tr> <td> Female </td> <td> Shad </td> <td align="right"> 138 </td> </tr>
   </table>

---

Use of the `align =` option for left, right, and centered cell text.  It is simplest to change names outside of the `xtable` call.


```r
# add format:  alignment
  library(xtable)
  tab1 <- xtable(f1, align = "llrc")
  names(tab1) <- c("Sex", "Fish Species", "Frequency")
  print(tab1, type="html", include.rownames = F)  # rendered table in html format
```

<!-- html table generated in R 3.5.3 by xtable 1.8-4 package -->
<!-- Mon Sep 09 19:50:38 2019 -->
<table border=1>
<tr> <th> Sex </th> <th> Fish Species </th> <th> Frequency </th>  </tr>
  <tr> <td> Male </td> <td align="right"> Sunfish </td> <td align="center">  59 </td> </tr>
  <tr> <td> Female </td> <td align="right"> Sunfish </td> <td align="center">  72 </td> </tr>
  <tr> <td> Male </td> <td align="right"> Bass </td> <td align="center">  14 </td> </tr>
  <tr> <td> Female </td> <td align="right"> Bass </td> <td align="center">  21 </td> </tr>
  <tr> <td> Male </td> <td align="right"> Shad </td> <td align="center"> 189 </td> </tr>
  <tr> <td> Female </td> <td align="right"> Shad </td> <td align="center"> 138 </td> </tr>
   </table>

---

### The RMD code used to build the HTML output is in the box below

    ---
    title: "A `xtable` Table"
    author: "Student R. Me"
    date: "`r format(Sys.time(), '%d %B, %Y')`"
    output: html_document
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
    
    ## `xtable` table with `results="asis"`
    
    By adding the option `results="asis"` to the **chunk** the table is now rendered into text.
    
    ```{r, results="asis"}
    library(xtable)
    # xtable(f1)  NOT RUN: would return a default table of LaTex code
    print(xtable(f1), type="html", include.rownames=F)  # rendered table in html format
    ```
    
    ---
    
    Use of the `align =` option for left, right, and centered cell text.  It is simplest to change names outside of the `xtable` call.
    
    ```{r, results="asis"}
    # add format:  alignment
      library(xtable)
      tab1 <- xtable(f1, align = "llrc")
      names(tab1) <- c("Sex", "Fish Species", "Frequency")
      print(tab1, type="html", include.rownames = F)  # rendered table in html format
    ```
    
    ---



