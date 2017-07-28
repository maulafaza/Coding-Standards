# Coding Style Guide

*CSS coding style guide for Born Digital team*

## Table of Contents

  1. [CSS Syntax](#css-syntax)
  2. [Structure](#structure)

## Contents

### CSS Syntax

<sup>Status: **under discussion**   | Following WordPress: no</sup>

[@mdo](http://codeguide.co/#css) :

<ul>
<li> Use soft tabs with two spaces—they're the only way to guarantee code renders the same in any environment. </li>
<li> When grouping selectors, keep individual selectors to a single line. </li>
<li> Include one space before the opening brace of declaration blocks for legibility. </li>
<li> Place closing braces of declaration blocks on a new line. </li>
<li> Include one space after : for each declaration. </li>
<li> Each declaration should appear on its own line for more accurate error reporting. </li>
<li> End all declarations with a semi-colon. The last declaration's is optional, but your code is more error prone without it. </li>
<li> Comma-separated property values should include a space after each comma (e.g., box-shadow). </li>
<li> Don't include spaces after commas within rgb(), rgba(), hsl(), hsla(), or rect() values. This helps differentiate multiple color values (comma, no space) from multiple property values (comma with space). </li>
<li> Don't prefix property values or color parameters with a leading zero (e.g., .5 instead of 0.5 and -.5px instead of -0.5px). </li>
<li> Lowercase all hex values, e.g., #fff. Lowercase letters are much easier to discern when scanning a document as they tend to have more unique shapes. </li>
<li> Use shorthand hex values where available, e.g., #fff instead of #ffffff. </li>
<li> Quote attribute values in selectors, e.g., input[type="text"]. They’re only optional in some cases, and it’s a good practice for consistency. </li>
<li> Avoid specifying units for zero values, e.g., margin: 0; instead of margin: 0px;. </li>
</ul>

```
/* Bad CSS */
.selector, .selector-secondary, .selector[type=text] {
  padding:15px;
  margin:0px 0px 15px;
  background-color:rgba(0, 0, 0, 0.5);
  box-shadow:0px 1px 2px #CCC,inset 0 1px 0 #FFFFFF
}

/* Good CSS */
.selector,
.selector-secondary,
.selector[type="text"] {
  padding: 15px;
  margin-bottom: 15px;
  background-color: rgba(0,0,0,.5);
  box-shadow: 0 1px 2px #ccc, inset 0 1px 0 #fff;
}
```


### Structure

<sup>Status: **under discussion**   | Following WordPress: yes</sup>

There are plenty of different methods for structuring a stylesheet. With the CSS in core, it is important to retain a high degree of legibility. This enables subsequent contributors to have a clear understanding of the flow of the document.
<ul>
<li> Use tabs, not spaces, to indent each property. </li>
<li> Add two blank lines between sections and one blank line between blocks in a section. </li>
<li> Each selector should be on its own line, ending in either a comma or an opening curly brace. Property-value pairs should be on their own line, with one tab of indentation and an ending semicolon. The closing brace should be flush left, using the same level of indentation as the opening selector. </li>
</ul>
Correct:

```
#selector-1,
#selector-2,
#selector-3 {
    background: #fff;
    color: #000;
}
```

Incorrect:
```
#selector-1, #selector-2, #selector-3 {
    background: #fff;
    color: #000;
    }
 
#selector-1 { background: #fff; color: #000; }
```
