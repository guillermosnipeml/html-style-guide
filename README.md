MercadoLibre HTML Style Guide
================
## Overview

The main goal of this style guide is to provide comprehensive guidelines to write valid, robust, and semantic html.

## Table of Contents

- [Doctype](#doctype)
- [HTML Syntax](#syntax)
- [New HTML5 markup tags](#new-html5-markup-tags)
- [Links](#links)
- [Forms](#forms)
- [Lists](#lists)

## Doctype

- Use HTML5 doctype across all our pages EXCEPT for emails(1): 

```html
<!-- DO -->

<!DOCTYPE html>
(HTML5 doctype)
```


> (1) Find email guidelines [here](http://static.mlstatic.com/org-img//Manual/ManualEmails/index.html)

> Related articles:

> - [HTML5 Doctype article](http://ejohn.org/blog/html5-doctype/) (John Resig's Blog)

> - [Fix Your Site With the Right DOCTYPE!](http://alistapart.com/article/doctype) (A list apart)



> [Go back to Summary](#table-of-contents) 

## Syntax

- Use XHTML syntax to ensure well formed code and backwards compatibility.

- Use small caps for html tags attributes and everything else, EXCEPT doctype

```html
<!-- DON´T -->
<iNPut ... />

<!-- DO -->
<input ....>

```

- Close your html elements. ALWAYS

```html
<!-- DON´T -->
<br>

<!-- DO -->
<br />

<img src="myimage.png" alt="myimage" />

<input type="radio" name="myRadio" />

<a href="#">Click here</a>

<strong>My bold text</strong>

<textarea>My text here</textarea>

```

- Write your attributes following this sintax: attribute:"value"

```html
<!-- DON´T -->
<input type="checkbox" name="myCheck" checked>

<!-- DO -->
<input type="checkbox" name="myCheck" checked="checked">
```

[Go back to summary](#table-of-contents)


## New HTML5 markup tags

The HTML5 markup incorporates some new tags designed to make web pages structure more logical and functional.


####Header
Represents the header of a section, and it is assumed to be given more importance than the rest, especially if the section is an item.


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
        <li><a href="#">Item of menu</a></li>
    </ul>
</nav>

<nav class="ml-navigation" role="navigation">
    <a href="#">Item of menu</a>
</nav>

````
####Article
Allows to declare a part of the content which is independent of this, such as reviews.
*Use in the Main
````html
<!-- DO -->
<article class="review">
    <header>
        <h4>
            Excellent product
        </h4>
        by <a href="/user/...">USERNAME...</a>
        <span class="reviewRating">
            5
        </span>
        <time datetime="2013-08-29T13:58Z">August 29th, 2013 at 13:58</time>
    </header>
    <p>Review content ...</p>
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

<section>
    <section>Promotions 1</section>
    <section>Promotions 2</section>
</section>
````

####Aside
It is essential to define the “important content" from the “support content", giving more importance to the first that the second.

````html
<!-- DON´T -->
<section class="main-content">
    <article>...</article>
</section>
<section class="aux-content"></section>

<!-- DO -->
<section class="content"> </section>
<aside>
    <span>Your purchase is protected. <a href="">See conditions</a>.</span>
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
<footer>
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

###An example of the basic structure of an html
````html
<!-- DO -->
<body>
    <header>
        <nav>...</nav>
    </header>
    <main>
        <aside>...</aside>
        <article>
            <section>...</section>
        </article>
    </main>
    <footer>...</footer>
</body>
````
![Alt text](/files/structure-html5.png "Basic structure")

> [HTML5 elements] (http://www.w3.org/TR/html5/dom.html#elements)


### HTML5 support for IE8
IE8 does not recognize the new HTML5 elements (article, section, etc.), so you must include the HTML5 Shiv script as shown below, if you want to support IE8:
````html
<!-- The HTML5 Shiv (https://github.com/aFarkas/html5shiv) -->
<!--[if lt IE 9]>
    <script src="http://static.mlstatic.com/org-img/ch/vendor/html5shiv/html5shiv-3.7.0.js"></script>
<![endif]-->
````
[Go back to summary](#table-of-contents)

## Links

#### Anchors

The ```<a>``` tag defines a hyperlink, the most important attribute of the ```<a>``` element is the href attribute.

- The link don't have auto close tag
- Always specific a title attribute
- Never use other element if you want link any info
- Always define a url and prevent it from javascript

```html
<!-- DON'T -->
<a href="url" />

<!-- DON'T -->
<span id="link" onclick="window.open('url')" ></span>

<!-- DON'T -->
<a href="javscript:void();" ></a>

<!-- DO -->
<a href="http://www.url.bla" title="title-link"></a>
and prevent event on click this
```

- Link info inside our content example

```html
<a href="#idReference" title="Go to Reference">Go to Reference</a>
(...our html content...)
<section id="idReference"></section>

<!-- Or -->

<a href="#nameReference" title="Go to Reference">Go to Reference</a>
(...our html content...)
<a name="nameReference"></a>
<section id="reference"></section>
```

#### Links

The ```<link>``` tag it's a void element and specifies relationships between the current document and external resource. This Element is most used, for example, to link to style sheets.

_Basic code_
```html
<link href="http://url" type="text/css" rel="stylesheet" media="screen" />
```
- `href` - specifies the URL of the linked resource
- `type` - defined the type (MIME type) of the content that has been linked
- `rel` - names a relationship between the linked document and the current document
- `media` - specifies the media which the linked resource applies to. Its value must be a _media types and groups_ in HTML4, and extend thist o any kind of _media queries_ in HTML5

> - [MIME types](http://www.htmlquick.com/es/reference/mime-types.html)
> - [Anchor attibutes](http://www.htmlquick.com/es/reference/tags/a.html)
> - [`target` values](http://www.w3.org/TR/html4/types.html#h-6.16)
> - [Anchors bad implementeation examples](http://line25.com/articles/10-html-tag-crimes-you-really-shouldnt-commit)
> - [SEO - anchor](http://moz.com/learn/seo/anchor-text)
> - [Link attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link)
> - [`rel` link_types](https://developer.mozilla.org/en-US/docs/Web/HTML/Link_types)
> - [`media` values](http://www.w3schools.com/tags/att_link_media.asp)

[Go back to summary](#table-of-contents)

## Forms

### Generic FORM example

#### _Basic code_
```html
<form action="/processData.php" method="post">
    <fieldset>
        <legend>Personal information</legend>
        <div>
            <label for="firstName">First name:</label>
            <input id="firstName" name="firstname" type="text">
        </div>
        <div>
            <label for="male">Sex:</label>
            <input id="male" name="sex" value="male" type="radio">
            <label for="male">Male</label>
            <input id="female" name="sex" value="female" type="radio">
            <label for="female">Female</label>
        </div>
    </fieldset>
    <fieldset>
        <legend>Other Information</legend>
        <div>
            <label for="someInfo">Some info:</label>
            <input id="someInfo" name="someinfo" type="text">
        </div>
        <div>
            <label for="check1">checkbox 1:</label>
            <input id="check1" name="checkbox1" value="example1" type="checkbox">
            <label for="check2">checkbox 2:</label>
            <input id="check2" name="checkbox2" value="example2" type="checkbox">
            <label for="check3">checkbox 3:</label>
            <input id="check3" name="checkbox3" value="example4" type="checkbox">
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

>- _[html5doctor](http://html5doctor.com/html5-forms-introduction-and-new-attributes/#attributes)_
>- _[w3c](http://www.w3.org/TR/html5/forms.html)_
>- _[Check Browser Compatibility of this feature](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#Browser_compatibility)_

### New attributes values


>For `type` attr  
>`email` `date` `datetime` `number` `range` `search` `tel` `url`

>For `accept` attr *(if type attr is `file`)*  
>`audio` `image` `video`

[Check Browser Compatibility of this feature](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#Browser_compatibility)

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

> [Go back to summary](#table-of-contents)


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
```html
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
```html
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

### Good practices

- Use lists to create lists, don`t use other elements to this purpose

```html
<!-- DON'T -->
<ul>
    <!-- simple link -->
    <li>
        <a href="#">...</a>
    </li>
    <li>
        <!-- Breadcrumb  -->
        <span>... &gt;</span>
        <span>... &gt;</span>
        <span>... &gt;</span>
        <span>...</span>
    </li>
</ul>
```
```html
<!-- DO -->
<div>
    <!-- simple link -->
    <a href="#">...</a>
    <ul>
        <!-- Breadcrumb -->
        <li>...</li>
        <li>...</li>
        <li>...</li>
        <li>...</li>
    <ul>
</div>
```

- Using the correct type of list, according to the needs of the information

```html
<!-- DON'T -->
<ul>
    <li>
        <span class="title">...</span>
        <span class="data">...</span>
    </li>
    <li>
        <span class="title"></span>
        <span class="data"></span>
    </li>
</ul>
```
```html
<!-- DO -->
<dl>
    <dt>...<dt>
    <dd>...</dd>
    <dt>...<dt>
    <dd>...</dd>
</dl>
```

```html
<!-- DON'T -->
<ul>
    <li>
        <span class="num">1</span>
        ...
    </li>
    <li>
        <span class="num">2</span>
        ...
    </li>
<ul>
```
```html
<!-- DO -->
<ol>
    <li>...</li>
    <li>...</li>
<ol>
```


[Go back to summary](#table-of-contents)