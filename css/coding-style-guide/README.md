# Coding Style Guide

*CSS coding style guide for Born Digital team*

## Table of Contents

  1. [CSS Syntax](#css-syntax)
  2. [Structure](#structure)
  3. [Selectors](#selectors)
  4. [Properties](#properties)
  5. [Property Ordering](#property-ordering)
  6. [Vendor Prefixes](#vendor-prefixes)
  7. [Values](#values)
  8. [Media Queries](#media-queries)
  9. [Commenting](#commenting)
  10. [Best Practices](#best-practices)

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


### Selectors

<sup>Status: **under discussion**   | Following WordPress: yes</sup>

With specificity, comes great responsibility. Broad selectors allow us to be efficient, yet can have adverse consequences if not tested. Location-specific selectors can save us time, but will quickly lead to a cluttered stylesheet. Exercise your best judgement to create selectors that find the right balance between contributing to the overall style and layout of the DOM.
<ul>
<li> Similar to the WordPress PHP Coding Standards for file names, use lowercase and separate words with hyphens when naming selectors. </li> 
<li> Avoid camelcase and underscores. </li> 
<li> Use human readable selectors that describe what element(s) they style. </li> 
<li> Attribute selectors should use double quotes around values </li> 
<li> Refrain from using over-qualified selectors, div.container can simply be stated as .container </li> 
</ul>

Correct:
```
#comment-form {
    margin: 1em 0;
}
 
input[type="text"] {
    line-height: 1.1;
}
```

Incorrect:
```
#commentForm { /* Avoid camelcase. */
    margin: 0;
}
 
#comment_form { /* Avoid underscores. */
    margin: 0;
}
 
div#comment_form { /* Avoid over-qualification. */
    margin: 0;
}
 
#c1-xr { /* What is a c1-xr?! Use a better name. */
    margin: 0;
}
 
input[type=text] { /* Should be [type="text"] */
    line-height: 110% /* Also doubly incorrect */
}
```

### Properties

<sup>Status: **under discussion**   | Following WordPress: yes</sup>

Similar to selectors, properties that are too specific will hinder the flexibility of the design. Less is more. Make sure you are not repeating styling or introducing fixed dimensions (when a fluid solution is more acceptable).
<ul>
<li> Properties should be followed by a colon and a space. </li>
<li> All properties and values should be lowercase, except for font names and vendor-specific properties. </li>
<li> Use hex code for colors, or rgba() if opacity is needed. Avoid RGB format and uppercase, and shorten values when possible: #fff instead of #FFFFFF. </li>
<li> Use shorthand (except when overriding styles) for background, border, font, list-style, margin, and padding values as much as possible. (For a shorthand reference, see [CSS Shorthand](https://codex.wordpress.org/CSS_Shorthand).) </li>
</ul>

Correct:
```
#selector-1 {
    background: #fff;
    display: block;
    margin: 0;
    margin-left: 20px;
}
```

Incorrect:
```
#selector-1 {
    background:#FFFFFF;
    display: BLOCK;
    margin-left: 20PX;
    margin: 0;
}
```

### Property Ordering

<sup>Status: **under discussion**   | Following WordPress: yes</sup>

Above all else, choose something that is meaningful to you and semantic in some way. Random ordering is chaos, not poetry. In WordPress Core, our choice is logical or grouped ordering, wherein properties are grouped by meaning and ordered specifically within those groups. The properties within groups are also strategically ordered to create transitions between sections, such as background directly before color. The baseline for ordering is:

<ul>
<li> Display </li>
<li> Positioning </li>
<li> Box model </li>
<li> Colors and Typography </li>
<li> Other  </li>
</ul>

Things that are not yet used in core itself, such as CSS3 animations, may not have a prescribed place above but likely would fit into one of the above in a logical manner. Just as CSS is evolving, so our standards will evolve with it.

Top/Right/Bottom/Left (TRBL/trouble) should be the order for any relevant properties (e.g. margin), much as the order goes in values. Corner specifiers (e.g. border-radius-*-*) should be top-left, top-right, bottom-right, bottom-left. This is derived from how shorthand values would be ordered.

Example:
```
#overlay {
    position: absolute;
    z-index: 1;
    padding: 10px;
    background: #fff;
    color: #777;
}
```

Another method that is often used, including by the Automattic/WordPress.com Themes Team, is to order properties alphabetically, with or without certain exceptions.

Example:
```
#overlay {
    background: #fff;
    color: #777;
    padding: 10px;
    position: absolute;
    z-index: 1;
}
```

### Vendor Prefixes

<sup>Status: **under discussion**   | Following WordPress: yes</sup>

We use Autoprefixer as a pre-commit tool to easily manage necessary browser prefixes, thus making the majority of this section moot. For those interested in following that output without using Grunt, vendor prefixes should go longest (-webkit-) to shortest (unprefixed). All other spacing remains as per the rest of standards.

```
.sample-output {
    -webkit-box-shadow: inset 0 0 1px 1px #eee;
    -moz-box-shadow: inset 0 0 1px 1px #eee;
    box-shadow: inset 0 0 1px 1px #eee;
}
```

### Values

<sup>Status: **under discussion**   | Following WordPress: yes</sup>

There are numerous ways to input values for properties. Follow the guidelines below to help us retain a high degree of consistency.
<ul>
<li> Space before the value, after the colon </li>
<li> Do not pad parentheses with spaces </li>
<li> Always end in a semicolon </li>
<li> Use double quotes rather than single quotes, and only when needed, such as when a font name has a space. </li>
<li> Font weights should be defined using numeric values (e.g. 400 instead of normal, 700 rather than bold). </li>
<li> 0 values should not have units unless necessary, such as with transition-duration. </li>
<li> Line height should also be unit-less, unless necessary to be defined as a specific pixel value. This is more than just a style convention, but is worth mentioning here. More information: http://meyerweb.com/eric/thoughts/2006/02/08/unitless-line-heights/  </li>
<li> Use a leading zero for decimal values, including in rgba(). </li>
<li> Multiple comma-separated values for one property should be separated by either a space or a newline, including within rgba(). </li> <li> Newlines should be used for lengthier multi-part values such as those for shorthand properties like box-shadow and text-shadow </li> 
 <li> Each subsequent value after the first should then be on a new line, indented to the same level as the selector and then spaced over to left-align with the previous value. </li>
</ul>

Correct:
```
.class { /* Correct usage of quotes */
    background-image: url(images/bg.png);
    font-family: "Helvetica Neue", sans-serif;
    font-weight: 700;
}
 
.class { /* Correct usage of zero values */
    font-family: Georgia, serif;
    line-height: 1.4;
    text-shadow: 0 -1px 0 rgba(0, 0, 0, 0.5),
                 0 1px 0 #fff;
}
```

Incorrect:
```
.class { /* Avoid missing space and semicolon */
    background:#fff
}
 
.class { /* Avoid adding a unit on a zero value */
    margin: 0px 0px 20px 0px;
}
 
.class {
    font-family: Times New Roman, serif; /* Quote font names when required */
    font-weight: bold; /* Avoid named font weights */
    line-height: 1.4em;
}
```

### Media Queries

<sup>Status: **under discussion**   | Following WordPress: yes</sup>

Media queries allow us to gracefully degrade the DOM for different screen sizes. If you are adding any, be sure to test above and below the break-point you are targeting.

<ul>
<li> It is generally advisable to keep media queries grouped by media at the bottom of the stylesheet. </li>
<li> An exception is made for the wp-admin.css file in core, as it is very large and each section essentially represents a stylesheet of its own. Media queries are therefore added at the bottom of sections as applicable. </li>
<li> Rule sets for media queries should be indented one level in. </li>
</ul> 

Example:
```
@media all and (max-width: 699px) and (min-width: 520px) {
 
        /* Your selectors */
}
```


### Commenting

<sup>Status: **under discussion**   | Following WordPress: yes</sup>

<ul>
<li> Comment, and comment liberally. If there are concerns about file size, utilize minified files and the SCRIPT_DEBUG constant. Long comments should manually break the line length at 80 characters. </li>
<li> A table of contents should be utilized for longer stylesheets, especially those that are highly sectioned. Using an index number (1.0, 1.1, 2.0, etc.) aids in searching and jumping to a location. </li>
<li> Comments should be formatted much as PHPDoc is. The [CSSDoc](http://web.archive.org/web/20070601200419/http://cssdoc.net/) standard is not necessarily widely accepted or used but some aspects of it may be adopted over time. Section/subsection headers should have newlines before and after. Inline comments should not have empty newlines separating the comment from the item to which it relates. </li>
</ul>

For sections and subsections:
```
/**
* #.# Section title
*
* Description of section, whether or not it has media queries, etc.
*/
 
.selector {
    float: left;
}
```

For inline:
```
/* This is a comment about this selector */
.another-selector {
    position: absolute;
    top: 0 !important; /* I should explain why this is so !important */
}
```


### Best Practices

<sup>Status: **under discussion**   | Following WordPress: yes</sup>

Stylesheets tend to get long in length. Focus slowly gets lost whilst intended goals start repeating and overlapping. Writing smart code from the outset helps us retain the overview whilst remaining flexible throughout change.

<ul>
<li> If you are attempting to fix an issue, attempt to remove code before adding more. </li>
<li> Magic Numbers are unlucky. These are numbers that are used as quick fixes on a one-off basis. Example: .box { margin-top: 37px }. </li>
<li> DOM will change over time, target the element you want to use as opposed to “finding it” through its parents. Example: Use .highlight on the element as opposed to .highlight a (where the selector is on the parent) </li>
<li> Know when to use the height property. It should be used when you are including outside elements (such as images). Otherwise use line-height for more flexibility. </li>
<li> Do not restate default property & value combinations (for instance display: block; on block-level elements). </li>
</ul>



