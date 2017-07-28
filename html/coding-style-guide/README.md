# Coding Style Guide

*HTML coding style guide for Born Digital team*

## Table of Contents

  1. [HTML Tags](#html-tags)
  2. [Self-closing Elements](#self-closing-elements)
  3. [Attributes and Tags](attributes-and-tags)


## Contents

### HTML Tags

<sup>Status: **under discussion**</sup>

[@mdo](http://codeguide.co/#html) :
<ul>
<li> Use soft tabs with two spaces—they're the only way to guarantee code renders the same in any environment. </li>
<li> Nested elements should be indented once (two spaces). </li>
<li> Always use double quotes, never single quotes, on attributes. </li>
<li> Don't include a trailing slash in self-closing elements—the HTML5 spec says they're optional. </li>
<li> Don’t omit optional closing tags (e.g. &lt;/li&gt; or &lt;/body&gt;). </li>
</ul>

### Self-closing Elements

<sup>Status: **under discussion**</sup>

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

<sup>Status: **under discussion**</sup>

All tags and attributes must be written in lowercase. Additionally, attribute values should be lowercase when the purpose of the text therein is only to be interpreted by machines. For instances in which the data needs to be human readable, proper title capitalization should be followed.

For machines:

```
<meta http-equiv="content-type" content="text/html; charset=utf-8" />
```
For humans:

```
<a href="http://example.com/" title="Description Here">Example.com</a>
```




  
