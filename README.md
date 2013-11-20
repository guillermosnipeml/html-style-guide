html-style-guide
================

MercadoLibre HTML Style Guide

## Overview

The main goal of this style guide is to provide comprehensive guidelines to write valid, robust, and semantic html.

## Index

- [Doctype](#doctype)
- [Anchors](#anchors)
- [Forms](#forms)
- [Tabular Data - Tables](#tables)
- [Lists](#lists) 

## Doctype

- We use HTML5 across all our pages EXCEPT for emails(1), so when coding html for our sites always use HTML5 doctype: 

```html
<!-- DON'T -->
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
(XHTML 1.0 Transitional doctype)

<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
(HTML 4.01 Transitional doctype)

<!-- DO -->

<!DOCTYPE HTML5>
(HTML5 doctype)
```


> (1) Find email guidelines [here](http://static.mlstatic.com/org-img//Manual/ManualEmails/index.html)
