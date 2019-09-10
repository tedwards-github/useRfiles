---
title: "A `xtable` Table: Output as HTML"
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

## Default table using the package `xtable`

Note the default return is **.html** code.


```r
library(xtable)
print(xtable(f1), type ="html")
```

```
## <!-- html table generated in R 3.5.3 by xtable 1.8-4 package -->
## <!-- Mon Sep 09 19:23:12 2019 -->
## <table border=1>
## <tr> <th>  </th> <th> ospreysex </th> <th> fishspp </th> <th> count </th>  </tr>
##   <tr> <td align="right"> 1 </td> <td> Male </td> <td> Sunfish </td> <td align="right">  59 </td> </tr>
##   <tr> <td align="right"> 2 </td> <td> Female </td> <td> Sunfish </td> <td align="right">  72 </td> </tr>
##   <tr> <td align="right"> 3 </td> <td> Male </td> <td> Bass </td> <td align="right">  14 </td> </tr>
##   <tr> <td align="right"> 4 </td> <td> Female </td> <td> Bass </td> <td align="right">  21 </td> </tr>
##   <tr> <td align="right"> 5 </td> <td> Male </td> <td> Shad </td> <td align="right"> 189 </td> </tr>
##   <tr> <td align="right"> 6 </td> <td> Female </td> <td> Shad </td> <td align="right"> 138 </td> </tr>
##    </table>
```

By adding the option `results="asis"` to the **chunk** the table is now rendered into text.


```r
library(xtable)
# xtable(f1)  NOT RUN: would return a default table of LaTex code
print(xtable(f1), type = "html", include.rownames = F)  # rendered table in html format
```

<!-- html table generated in R 3.5.3 by xtable 1.8-4 package -->
<!-- Mon Sep 09 19:23:12 2019 -->
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

### The RMD code used to build the HTML output is in the box below

    ---
    title: "A `xtable` Table: Output as HTML"
    author: "Student R. Me"
    date: "`r format(Sys.time(), '%d %B, %Y')`"
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
    
    ## Default table using the package `xtable`
    
    Note the default return is **.html** code.
    
    ```{r}
    library(xtable)
    print(xtable(f1), type ="html")
    ```
    By adding the option `results="asis"` to the **chunk** the table is now rendered into text.

    ```{r, results="asis"}
    library(xtable)
    # xtable(f1)  NOT RUN: would return a default table of LaTex code
    print(xtable(f1), type = "html", include.rownames = F)  # rendered table in html format
    ```
    
    ---

