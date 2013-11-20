html-style-guide
================

MercadoLibre HTML Style Guide

## Overview

The main goal of this style guide is provide comprehensive guidelines to write valid, robust, and semantic html.


> "Comment"

## Index

- [Doctype](#doctype)
- [Anchors](#anchors)
- [Forms](#forms)
- [Tabular Data - Tables](#tables)
- [Lists](#lists) 

## Doctype

- We use HTML5 across all our pages EXCEPT for emails(1). Always use HTML5 doctype: 

        /* DON'T */
        
        XHTML 1.0 Transitional
        <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
        
        HTML 4.01 Transitional
        <!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">

        /* DO */

        HTML5
        <!DOCTYPE HTML5>


> (1) Find email guidelines [here](http://static.mlstatic.com/org-img//Manual/ManualEmails/index.html)
