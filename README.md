# Principles of writing consistent, idiomatic HTML

The following document outlines a reasonable style guide for HTML development.
These guidelines strongly encourage the use of existing, common, sensible
patterns. They should be adapted as needed to create your own style guide.

This is a living document and new ideas are always welcome. Please
contribute.


## Table of contents

1. [General principles](#general-principles)
2. [Format](#format)
3. [Attribute order](#attribute-order)
4. [Naming](#naming)
4. [Semantics](#semantics)

[License](#license)


<a name="general-principles"></a>
## General principles

* All code in any code-base should look like a single person typed it, no
  matter how many people contributed.
* Strictly enforce the agreed upon style.
* If in doubt when deciding upon a style, use existing, common patterns.


<a name="format"></a>
## Format

* Use soft-tabs with 4 spaces for indentation.
* Nested elements should be indented once.
* Always use double quotes to quote attribute values.
* Don't include a trailing slash in self-closing elements.

Example:

```html
<div class="tweet">
    <a href="path/to/somewhere">
      <img src="path/to/image.png" alt="">
    </a>
    <p>[tweet text]</p>
</div>
```


<a name="html-attribute-order"></a>
## Attribute order

HTML attributes should come in this particular order for easier reading of code.

* `class`
* `id`
* `data-*`
* `for`|`type`|`href`

Example:

````html
<a class="" id="" data-name="" href="">[link text]</a>
````


<a name="naming"></a>
## Naming

Naming is hard, but very important. It's a crucial part of the process of
developing a maintainable code base, and ensuring that you have a relatively
scalable interface between your HTML and CSS/JS.

* Use clear, thoughtful, and appropriate names for HTML classes. The names
  should be informative both within HTML and CSS files.
* Avoid _systematic_ use of abbreviated class names. Don't make things
  difficult to understand.

Example with bad names:

```html
<div class="cb s-scr"></div>
```

```css
.s-scr {
  overflow: auto;
}

.cb {
  background: #000;
}
```

Example with better names:

```html
<div class="column-body is-scrollable"></div>
```

```css
.is-scrollable {
    overflow: auto;
}

.column-body {
    background: #000;
}
```


<a name="semantics"></a>
## Semantics

Trying to find the appropriate element to use is often difficult, but doing 
so can result in cleaner, more maintainable code. Another, often overlooked 
advantage, is this increases accessibility, particularly with screen readers.

* Always try to use the most appropriate elements for the required field.
* Try to avoid unnecessary declarations of elements purely for _wrapper_ purposes.

Example with unneccesary and innapropriate elements:

```html
<div class="tweet">
    <div class="tweet-avatar">
        <a href="path/to/somewhere">
            <img src="path/to/image.png" alt="">
        </a>
    </div>
    <div class="tweet-message">
         <span class="tweet-inner-text">[tweet text]</span>
    </div>
</div>
```

A more semantic example:

```html
<div class="tweet">
    <a href="path/to/somewhere">
      <img src="path/to/image.png" alt="">
    </a>
    <p>[tweet text]</p>
</div>
```

<a name="license"></a>
## License

_Principles of writing consistent, idiomatic HTML_ by Nicolas Gallagher is
licensed under the [Creative Commons Attribution 3.0 Unported
License](http://creativecommons.org/licenses/by/3.0/). This applies to all
documents and translations in this repository.

Based on a work at
[github.com/necolas/idiomatic-html](https://github.com/necolas/idiomatic-html).
