# Coding Style Guide

*HTML coding style guide for Born Digital team*

## Table of Contents

  1. [HTML Tags](#html-tags)
  2. [Self-closing Elements](#self-closing-elements)
  3. [Attributes and Tags](#attributes-and-tags)
  4. [Quotes](#quotes)
  5. [Indentation](#indentation)


## Contents

### HTML Tags

<sup>Status: **under discussion**</sup>

All tags must be properly closed. Don’t omit [optional closing tags](https://www.w3.org/TR/html5/syntax.html#optional-tags) (e.g. &lt;/li&gt; or &lt;/p&gt;).

**Correct**
```
<ul>
    <li>First</li>
    <li>Second</li>
</ul>

<article>
    <p>First</p>
    <p>Second</p>
</article>
```

**Incorrect**
```
<ul>
    <li>First
    <li>Second
</ul>

<article>
    <p>First
    <p>Second
</article>
```


### Self-closing Elements

<sup>Status: **under discussion**  | Following WordPress: -</sup>

>
>#### Discussions
>###### WordPress version (using old [2002th XHTML 1 source](https://www.w3.org/TR/xhtml1/#C_2) as reference):
>All tags must be properly closed. For tags that are self-closing, the forward slash should have exactly one space preceding it: `<br />` instead of `<br/>`
>
>###### [Code Guide version](http://codeguide.co/#html-syntax) (using [HTML 5 source](https://dev.w3.org/html5/spec-author-view/syntax.html#syntax-start-tag) as reference):
>Don't include a trailing slash in self-closing elements—the [HTML5 spec](https://dev.w3.org/html5/spec-author-view/syntax.html#syntax-start-tag) says they're optional.
>
>###### Discussion proposal (Think about practical & readability):
>The HTML 5 spec says: "_Then, if the element is one of the void elements, or if the element is a foreign element, then there may be a single U+002F SOLIDUS character (/). This character has no effect on void elements, but on foreign elements it marks the start tag as self-closing._"
>
>Optional is optional (not even a recommendation) which means you can whether say "Yes" or "No". The trailing slash has no effect on: `area, base, br, col, command, embed, hr, img, input, keygen, link, meta, param, source, track, wbr` tags.
>
>But our editor maybe use <tag /> as autocomplete, or maybe our habbits use it.
>
>Bagus wants make this as really *optional*. He wants to ommit the closing tags (since it has no-effect on void elements) but his editor auto do this (but don't worry, Atom is editable :D).
>


### Attributes and Tags

<sup>Status: **under discussion**  | Following WordPress: yes</sup>

All tags and attributes must be written in lowercase. Additionally, attribute values should be lowercase when the purpose of the text therein is only to be interpreted by machines. For instances in which the data needs to be human readable, proper title capitalization should be followed.

For machines:

```
<meta http-equiv="content-type" content="text/html; charset=utf-8" />
```
For humans:

```
<a href="http://example.com/" title="Description Here">Example.com</a>
```

### Quotes

<sup>Status: **under discussion**  | Following WordPress: yes</sup>

According to the W3C specifications for XHTML, all attributes must have a value, and must use double- or single-quotes (source). The following are examples of proper and improper usage of quotes and attribute/value pairs.

Correct:

```
<input type="text" name="email" disabled="disabled" />
<input type='text' name='email' disabled='disabled' />
```

Incorrect:

```
<input type=text name=email disabled>
```

In HTML, attributes do not all have to have values, and attribute values do not always have to be quoted. While all of the examples above are valid HTML, failing to quote attributes can lead to security vulnerabilities. Always quote attributes.

Always use double quotes, never single quotes, on HTML attributes.



### Indentation

<sup>Status: **under discussion**  | Following WordPress: partially</sup>

>
>#### Discussions
>###### WordPress version (tab):
>As with PHP, HTML indentation should always reflect logical structure. Use tabs and not spaces.
>
>###### [Code Guide version](http://codeguide.co/#html-syntax) (tab button represent 2 spaces):
>Use soft tabs with two spaces—they're the only way to guarantee code renders the same in any environment.
>
>###### Bagus proposal (tab button represent 4 spaces):
>To match our goal of **Uniformity** and **Compatibility**, indentation must use spaces. Because space based indentation will look the same in any editor on any setting.
>
>HTML indentation should be 4 spaces (using *Tab* button, not manually ;) pressing the "space") to match PHP coding style.
>


When mixing PHP and HTML together, indent PHP blocks to match the surrounding HTML code. Closing PHP blocks should match the same indentation level as the opening block.

Correct:

```
<?php if ( ! have_posts() ) : ?>
    <div id="post-1" class="post">
        <h1 class="entry-title">Not Found</h1>
        <div class="entry-content">
            <p>Apologies, but no results were found.</p>
            <?php get_search_form(); ?>
        </div>
    </div>
<?php endif; ?>
```

Incorrect:

```
        <?php if ( ! have_posts() ) : ?>
        <div id="post-0" class="post error404 not-found">
            <h1 class="entry-title">Not Found</h1>
            <div class="entry-content">
            <p>Apologies, but no results were found.</p>
<?php get_search_form(); ?>
            </div>
        </div>
<?php endif; ?>
```
