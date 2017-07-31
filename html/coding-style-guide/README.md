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

<sup>Status: **under discussion**  | Following WordPress: no</sup>

[Code Guide version](http://codeguide.co/#html) :
<ul>
<li>  </li>
<li> Don’t omit optional closing tags (e.g. &lt;/li&gt; or &lt;/body&gt;). </li>
</ul>

```
<!DOCTYPE html>
<html>
  <head>
    <title>Page title</title>
  </head>
  <body>
    <img src="images/company-logo.png" alt="Company">
    <h1 class="hello-world">Hello, world!</h1>
  </body>
</html>
```


### Self-closing Elements

<sup>Status: **under discussion**  | Following WordPress: yes</sup>

All tags must be properly closed. For tags that can wrap nodes such as text or other elements, termination is a trivial enough task. For tags that are self-closing, the forward slash should have exactly one space preceding it:

```
<br />;
```
rather than the compact but incorrect:
```
<br/>;
```
The W3C specifies that a single space should precede the self-closing slash [(source)](https://www.w3.org/TR/xhtml1/#C_2).


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
>###### WordPress version:
>As with PHP, HTML indentation should always reflect logical structure. Use tabs and not spaces.
>
>###### [Code Guide version](http://codeguide.co/#html-syntax):
>Use soft tabs with two spaces—they're the only way to guarantee code renders the same in any environment.
>
>###### Bagus proposal:
>To match our goal of **Uniformity** and **Compatibility**, indentation must use spaces. Because space based indentation will look the same in any editor on any setting.
>
>Do not manual spacing the indentation. Instead, set the editor to use *Tab* key represents *4 spaces*. HTML indentation should be 4 spaces (using *Tab* button, not manually ;) pressing the "space") to match PHP coding style.
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
