html-style-guide
================

MercadoLibre HTML Style Guide

## Overview

The main goal of this style guide is to provide comprehensive guidelines to write valid, robust, and semantic html.

## Index

- [Doctype](#doctype)
- [HTML Syntax](#html-syntax)
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

<!DOCTYPE html>
(HTML5 doctype)
```


> (1) Find email guidelines [here](http://static.mlstatic.com/org-img//Manual/ManualEmails/index.html)

> Related articles:

> - [HTML5 Doctype article](http://ejohn.org/blog/html5-doctype/) (John Resig's Blog)

> - [Fix Your Site With the Right DOCTYPE!](http://alistapart.com/article/doctype) (A list apart)

## Syntax

- We use XHTML syntax to ensure well formed code and backwards compatibility. 

```html
<!-- DON´T -->

<!-- You must not use mixed caps for tags names or attributes. Always use small caps -->
<iNPut ... />

<!-- HTML tags must be always closed -->
<br> 

<!-- Avoid the boolean attribute syntax -->
<input type="checkbox" name="myCheck" checked>
<!-- DO -->

<!-- Use small caps for html tags attributes and everything else, EXCEPT doctype -->
<input ....>

<!-- Close your html elements. ALWAYS -->
<br />

<img src="myimage.png" alt="myimage" />

<input type="radio" name="myRadio" />

<a href="#">Click here</a>

<strong>My bold text</strong>

<textarea>My text here</textarea>

<!-- Write your attributes following this sintax: attribute:"value" (Yes, double quoutes) -->
<input type="checkbox" name="myCheck" checked="checked">
```