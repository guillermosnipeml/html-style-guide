MercadoLibre HTML Style Guide
================

This style guide will guide you follow through the standards of the code used among our web pages. If you notice that some important info is missing, or you want to contribute with it, just let us know.

## Overview

The main goal of this style guide is to provide comprehensive guidelines to write valid, robust, and semantic html.

## Index

- [Doctype](#doctype)
- [HTML Syntax](#syntax)
- [New HTML5 markup tags](#new-html5-markup-tags)
- [Anchors](#anchors)
- [Forms](#forms)
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



> [Go back to Style guide index](#index) 

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
> [Go back to Style guide index](#index) 


## New HTML5 markup tags

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

### Support for IE8
IE8 does not recognize the new HTML5 elements (article, section, etc.), so you must include the HTML5 Shiv script as shown below, if you want to support IE8:
````html
<!-- The HTML5 Shiv (https://github.com/aFarkas/html5shiv) -->
<!--[if lt IE 9]>
    <script src="http://static.mlstatic.com/org-img/ch/vendor/html5shiv/html5shiv-3.7.0.js"></script>
<![endif]-->
````
> [Go back to Style guide index](#index) 

## Anchors

### Description
* Defines an anchor and can be used as a link to another document, such as a marker, or both.


### Attributes
<a href="#href">`href`</a>
<a href="#title">`title`</a>
<a href="#id">`id`</a>
<a href="#name">`name`</a>
<a href="#class">`class`</a>
<a href="#target">`target`</a>
<a href="#type">`type`</a>
<a href="#rel">`rel`</a>


### Basic implementation
Specific `href` and `title` attributes
```html
<a href="https://github.com/mercadolibre/html-style-guide" title="Go to html style guide" >html-style-guide</a>
```

### Implementing data attributes
```html
<a href="http://url.original" data-some-data="sting-data" title="link with data attr"></a>
```

### Good Practices
Anchors don't have auto close tag
```html
<!-- DON'T -->
<a href="url" title="title-text" />
```

```html
<!-- DO -->
<a href="url" title="title-text"></a>
```

<a name="title"></a>
Always specific a title attribute
```html
<!-- DON'T -->
<a href="url"></a>
```

```html
<!-- DO -->
<a href="url" title=""></a>
```

Never use other element if you want link any info
```html
<!-- DON'T -->
<span id="link" onclick="window.open('url')" ></span>
```

```html
<!-- DO -->
<a href="url" title="title-link" target="_blank"></a>
```

Always define a url and prevent it from javascript
```html
<!-- DON'T -->
<a href="javscript:void();" ></a>
```

```html
<!-- DO -->
<a href="http://www.url.bla" title="title-link"></a>
and prevent event on click this
```

<a name="id"></a>
Link info inside our content example
```html
<a href="#idReference" title="Go to Reference">Go to Reference</a>
(...our html content...)
<section id="idReference"></section>
```
Or
<a name="name"></a>
```html
<a href="#nameReference" title="Go to Reference">Go to Reference</a>
(...our html content...)
<a name="nameReference"></a>
<section id="reference"></section>
```


### Attributes description

#### Target
<span id="target"></span>

######Possible values

* `_blank` - *Open linked document in new windows or tab*
* `_self` - *It's a default, open linked document in the same context*
* `_parent` - *Open linked document in the parent frame*
* `_top` - *Open linked document in the top level of current context frame*



#### Source:
http://www.htmlquick.com/es/reference/tags/a.html
http://www.htmlquick.com/es/reference/mime-types.html
http://www.htmlquick.com/es/reference/types.html#frame-target
http://stackoverflow.com/questions/11009597/correct-implementation-of-anchor-tag
http://line25.com/articles/10-html-tag-crimes-you-really-shouldnt-commit
http://stackoverflow.com/questions/134845/href-attribute-for-javascript-links-or-javascriptvoid0
http://moz.com/learn/seo/anchor-text
http://www.w3.org/TR/html4/types.html#h-6.16
http://stackoverflow.com/questions/4964130/target-blank-vs-target-new
http://www.w3.org/html/wg/drafts/html/master/Overview.html

> [Go back to Style guide index](#index) 

## Forms

### Generic FORM example

#### _Code_
```html
<form action="/processData.php" method="post">
    <fieldset>
        <legend>Personal information</legend>
        <div>
            <label for="firstName">First name:</label>
            <input id="firstName" name="firstname" type="text">
        </div>
        <div>
            <label for="lastName">Last name:</label>
            <input id="lastName" name="lastname" type="text">
        </div>
        <div>
            <label for="male">Sex:</label>
            <input id="male" name="sex" value="male" type="radio">
            <label for="male">Male</label>
            <input id="female" name="sex" value="female" type="radio">
            <label for="female">Female</label>
        </div>
        <div>
            <label for="birthDate">Birth date:</label>
            <input id="birthDate" name="birthdate" type="date">
        </div>
    </fieldset>
    <fieldset>
        <legend>Other Information</legend>
        <div>
            <label for="someInfo">Some info:</label>
            <input id="someInfo" name="someinfo" type="text">
        </div>
        <div>
            <label for="selectEg">Select example:</label>
            <select id="selectEg" name="selecteg">
                <option>option 1</option>
                <option>option 2</option>
                <option>option 3</option>
                <optgroup label="optgroup 1">
                    <option>option 4.1</option>
                    <option>option 4.2</option>
                    <option>option 4.3</option>
                </optgroup>
                <option>option 5</option>
                <option>option 6</option>
                <optgroup label="optgroup 2 disabled" disabled><!-- In XHTML, attribute minimization is forbidden, and the disabled attribute must be defined as <optgroup disabled="disabled"> -->
                    <option>option 7.1</option>
                    <option>option 7.2</option>
                    <option>option 7.3</option>
                    <option>option 7.4</option>
                </optgroup>
            </select>
        </div>
        <div>
            <input id="check1" name="checkbox1" value="example1" type="checkbox">
            <label for="check1">checkbox 1:</label>
            <input id="check2" name="checkbox2" value="example2" type="checkbox">
            <label for="check2">checkbox 2:</label>
            <input id="check3" name="checkbox3" value="example4" type="checkbox">
            <label for="check3">checkbox 3:</label>
        </div>
    </fieldset>
    <fieldset>
        <legend>Action Buttons</legend>
        <input value="Send" type="submit">
        <input value="reset form" type="reset">
    </fieldset>
</form>
```


### New attributes

* `autocomplete` - *(only if the type attr isn't `hidden` `checkbox` `radio` `file` or button type `button` `submit` `reset` `image`)*
* `pattern` - A regular expression. Validate the input content when is used with tel, search, url, and email input types
* `placeholder` - A hint to the user of what can be entered in the control
* `required` - This attribute specifies that the user must fill in a value before submitting a form. *(not apply for hidden, image, submit, reset or button types)*

__Inputs__

* `list` - The value must be the id of a `<datalist>` element in the same document
*(This attribute is ignored when the type attribute's value is hidden, checkbox, radio, file, or a button type)*
* `form` - A *String* indicating which `<form>` element this input is part of. An input can only be in one form. *(The value must be the id of a form)*
* `formmethod` - A *String* define which method (get/post) should be used when submitting. __It overrides the form method__, if defined. *(only applies for type image or submit, when the form attribute has been set)*
* `formaction` - A *String* define the URI should be used to processes the information. __It overrides the form action__, if defined. *(only applies for type image or submit, when the form attribute has been set)*

[Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#Browser_compatibility)

### New attributes values


>For `type` attr  
>`email` `date` `datetime` `number` `range` `search` `tel` `url`

>For `accept` attr *(if type attr is `file`)*  
>`audio` `image` `video`

[Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#Browser_compatibility)

### Good practices

* Don't use form elements outside from this context

```html
<!-- DON'T -->
<body>
    <input value="someValue" type="hidden">
</body>
```

```html
<!-- DO -->
<body>
    <form>
        <input value="someValue" type="hidden">
    </form>
</body>
```

* Specify form action

```html
<!-- DON'T -->
<form>...</form>
```

```html
<!-- DO -->
<form action="form-process.php">...</form>
```

* Specify form method

```html
<!-- DON'T -->
<form action="form-process.php">...</form>
```

```html
<!-- DO -->
<form action="form-process.php" method="post">...</form>
```
_Methods_ `post get `


* Use submit input to send form data

```html
<!-- DON'T -->
<input type="button" value="Send" onclick="sendForm();">
```

```html
<!-- DO -->
<input type="submit" value="Send">
```

* Use reset input to clear form

```html
<!-- DON'T -->
<input type="button" value="Clear" onclick="resetForm();">
```

```html
<!-- DO -->
<input type="reset" value="Clear">
```

* Use *labels* to describe the role of the form element

```html
<!-- DON'T -->
name: <input type="text">
```

```html
<!-- DO -->
<label>name:</label><input type="text">
```

* Asociate a label with the corresponding field

```html
<!-- DON'T -->
<label>name:</label><input type="text">
```

```html
<!-- DO -->
<label for="name">name:</label><input id="name" type="text">
```

* Add names to fields that will be sending in the submit action

```html
<!-- DON'T -->
<input class="name" id="userName" type="text">
```

```html
<!-- DO -->
<input class="name" id="userName" name="userName" type="text">
```

* Don't add names to the fields that will not be sending in the submit action

```html
<!-- DON'T -->
<input class="pass" id="userPass" name="userPass" type="password">
```

```html
<!-- DO -->
<input class="pass" id="userPass" type="text">
```

* Separate content by context

```html
<!-- DON'T -->
<label>name:</label><input name="userName" type="text">
<label>sex:</label><input name="userSex" type="radio"><input name="userSex" type="radio">
<label>Transaction Number:</label><input name="productNumTransaction" type="text">
<label>Transaction Date:</label><input name="productDateTransaction" type="date">
```

```html
<!-- DO -->
<fieldset name="userData">
    <label>name:</label><input name="name" type="text">
    <label>sex:</label><input name="sex" type="radio"><input name="sex" type="radio">
</fieldset>
<fieldset name="productData">
    <label>Transaction Number:</label><input name="numTransaction" type="text">
    <label>Transaction Date:</label><input name="dateTransaction" type="date">
</fieldset>
```

#### Sources:
*[https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/)*
*[https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Forms](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Forms)*
*[http://www.w3.org/TR/html401/interact/forms.html](http://www.w3.org/TR/html401/interact/forms.html)*
*[http://www.tutorialspoint.com/html5/](http://www.tutorialspoint.com/html5/)*
*[http://html5doctor.com/](http://html5doctor.com/)*

> [Go back to Style guide index](#index) 


## Lists

Used to enumerate(list) information, which determines the type of list used.

### Types
- `<ul>` - unorderer list
- `<ol>` - orderer list
- `<dl>` - description list

#### Unordered Lists

Used to list information that does not require a particular order.

Eg. List of payment methods.

html structure
```
<ul>
  <li>MercadoPago<li>
  <li>Efectivo<li>
  <li>Transferencia bancaria<li>
</ul>
```
Result
* MercadoPago
* Efectivo
* Transferencia bancaria


#### Ordered Lists

Used to list items that need an order.

Eg: Steps to buying.

html structure
```
<ol>
  <li>Offert<li>
  <li>Select a payment method</li>
  <li>Select a shipment method</li>
</ol>
```
Result
1. Offert
2. Select a payment method
3. Select a shipment method

#### Definition Lists

This list is recommended for use when the information has a relevant title or concept, in addition to its content.
It has a title `<dt>` and description `<dd>`.

html structure
```
<dl>
    <dt>Tipo de artículo:</dt>
       <dd>Artículo nuevo</dd>
    <dt>Vendidos:</dt>
        <dd>1 vendido</dd>
</dl>
```
Result

···· __Tipo de artículo:__

···· ···· Artículo nuevo

···· __Vendidos:__

···· ···· 1 vendido


> [Go back to Style guide index](#index) 
