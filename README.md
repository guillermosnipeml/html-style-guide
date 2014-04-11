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

<!-- You must not use mixed caps for tags names or attributes. -->
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

<!-- Write your attributes following this sintax: attribute:"value" -->
<input type="checkbox" name="myCheck" checked="checked">
```

###Elements
The HTML5 markup incorporates some new tags designed to make web pages structure more logical and functional.
http://www.w3.org/TR/html5/dom.html#elements
*Always use the class of the element 
*Use ARIA attribute

####Header
Represents the header of a section, and it is assumed to be given more importance than the rest, especially if the section is an ítem.


````html
<header class="ml-header">  
    <a href="http://www.mercadolibre.com.ar">
        <h1 class="ml-logo">
            MercadoLibre - Donde compras y vendes de todo
        </h1>
    </a>
    <!-- Header content -->
</header>
````

####Main
The ```` <div> ```` with the class or id ```` main or content```` we replace by class ```` <main> ```` .

````html
<!-- DON´T -->
<div id="main" role="main">
    <!-- Content -->
</div>
````
````html
<!-- DO -->
<main role="main">
    <!-- Content -->
</main>
````

####Nav
Represents a section dedicated to the navigation of the site.
*Within the header
````html
<!-- DON´T -->
<div>
    <ul>
        <li><a href="#">Item of menu</a></li>
    </ul>
</div>
````
````html
<!-- DO -->
<nav class="ml-navigation" role="navigation">
    <ul>
        <li><a href="index.html">Home</a></li>
        <li><a href="/about/">About</a></li>
    </ul>
</nav>
````
####Article
Allows to declare a part of the content which is independent of this, such as reviews.
*Use in the Main
````html
<!-- DO -->
<article class="review" itemprop="review" itemscope itemtype="http://schema.org/Review">
    <header>
        <h4 itemprop="name">
            Excellent product
        </h4>
        by <a href="/user/..." itemprop="author">USERNAME...</a>
        <span class="reviewRating" itemprop="reviewRating" itemscope itemtype="http://schema.org/Rating">
            <meta itemprop="worstRating" content="1">
            <span itemprop="ratingValue">5</span>
            <meta itemprop="bestRating" content="5">
        </span>
        <time itemprop="datePublished" datetime="2013-08-29T13:58Z">August 29th, 2013 at 13:58</time>
    </header>
    <p itemprop="description">Review content ...</p>
</article>
````
####Section
Represents a general section inside a document or an application.  It can contain subsections and if we accompany with h1-h6 we could structure better the entire page.
````html
<!-- DO -->
<section>
    <h2>Promotions</h2>
    <p>Promo description</p>
</section>
````

####Aside
It is essential to define the “important content" from the “support content", giving more importance to the first that the second.

````html
<!-- DO -->
<aside>
    <h2>Blogroll</h2>
    <ul>
        <li><a href="#">My Friend</a></li>
        <li><a href="#">My Other Friend</a></li>
        <li><a href="#">My Best Friend</a></li>
    </ul>
</aside>
````

The content of the ```` aside ```` element is related directly with the article.
````html
<!-- DO -->
<article>
    <h2>My Blog Post</h2>
    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do
    eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
    <aside>
        <h3>Glossary</h3>
        <p>ipsum dolor sit amet</p>
    </aside>
</article>
````

The ```` aside ```` element can be out of the article. Its content is related to the page, but not so closely to the article.
````html
<!-- DO -->
<article>
    <h2>Products Apple</h2>
    <p>The <b>apple</b> is the pomaceous fruit of the apple tree...</p>
    ...
</article>
<aside>
    <h3>Oder products</h3>
    <ul>
        <li><a href="#">AMD</a></li>
        <li><a href="#">Intel</a></li>
        ...
    </ul>
</aside>
````
####Footer
Represents the bottom of a section with information about the page/section that has little to do with the content itself but has data like the author, copyright or the year.

````html
<!-- DON´T -->
<div id="footer">
    <ul>
        <li>copyright</li>
        <li>More information</li>
        ...
    </ul>
<div>
````

````html
<!-- DO -->
<footer class="ml-footer" role="contentinfo">
    <ul>
        <li>copyright</li>
        <li>More information</li>
        ...
    </ul>
</footer>
````
#####The footer inside another element
######Section
````html
<!-- DO -->
<section>
   Section content appears here.
   <footer>
   Footer information for section.
   </footer>
</section>
````

######Article
````html
<!-- DO -->
<article>
   Article content appears here.
   <footer>
   Footer information for article.
   </footer>
</article>
````

###Basic structure of elements
````html
<!-- DO -->
<body>
    <header class="ml-header">
        <nav class="ml-navigation">...</nav>
    </header>
    <main class="ml-main" role="main">
        <aside>...</aside>
        <article>
            <section>...</section>
        </article>
    </main>
    <footer  class="ml-footer">...</footer>
</body>
````
![Alt text](/files/structure-html5.png "Basic structure of elements in MeLi")

### Use HTML5 Shiv
IE does not recognize the new HTML5 elements (article, section, etc.)
````html
<!-- The HTML5 Shiv (https://github.com/aFarkas/html5shiv) -->
<!--[if lt IE 9]>
    <script src="http://static.mlstatic.com/org-img/ch/vendor/html5shiv/html5shiv-3.7.0.js"></script>
<![endif]-->
````