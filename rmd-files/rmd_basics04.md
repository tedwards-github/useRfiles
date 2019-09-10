---
title: "Lists"
author: "Student R. Me"
date: "09 September, 2019"
output: 
    html_document:
        keep_md: true
    pdf_document: default
    word_document: default
---

---

## Unordered Lists

* Build an unordered Markdown list using *
* Add a second list element
    * at least 4 spaces (or a tab) before the * results in indenting

---

## Ordered Lists

1. Build an ordered Markdown list using numbers
2. Add a second list element
    1. at least 4 spaces (or a tab) before an ordered sub-list

---

### The RMarkdown .rmd code used to build the HTML output is in the box below

    ---
    title: "Lists"
    author: "Student R. Me"
    date: "`r format(Sys.time(), '%d %B, %Y')`"
    html_document:
        keep_md: true
    pdf_document: default
    word_document: default  
    ---
    
    ---
    
    ## Unordered Lists
    
    * Build an unordered Markdown list using *
    * Add a second list element
        * at least 4 spaces (or a tab) before the * results in indenting
    
    ---
    
    ## Ordered Lists
    
    1. Build an ordered Markdown list using numbers
    2. Add a second list element
        1. at least 4 spaces (or a tab) before an ordered sub-list
    
    ---
