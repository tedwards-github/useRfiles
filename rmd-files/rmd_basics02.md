---
title: "Line Separators and Headers"
author: "Student R. Me"
date: "09 September, 2019"
output: 
    html_document:
        keep_md: true
    pdf_document: default
    word_document: default
---

---

---

Two line separators with a hard return between generates two lines, as above. 

\-\-\-

\-\-\-

Single line separators can be used to distinguish between sections in the document body, as below.

\-\-\-

---

These are headers:

# Header1
## Header2
### Header3
#### Header4
##### Header5
###### Header6

Compare Header6 to this text.  It's smaller, isn't it?

---

### The RMD code used to build the HTML output is in the box below.

    ---
    title: "Line Separators and Headers"
    author: "Student R. Me"
    date: "`r format(Sys.time(), '%d %B, %Y')`"
    html_document:
        keep_md: true
    pdf_document: default
    word_document: default  
    ---
    
    ---
    
    ---
    
    Two line separators with a hard return between generates two lines, as above. 
    
    \-\-\-
    
    \-\-\-
    
    Single line separators can be used to distinguish between sections in the document body, as below.
    
    \-\-\-
    
    ---
    
    These are headers:
    
    # Header1
    ## Header2
    ### Header3
    #### Header4
    ##### Header5
    ###### Header6
    
    Compare Header6 to this text.  It's smaller, isn't it?
    
    ---



