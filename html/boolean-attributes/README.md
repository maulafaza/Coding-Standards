# Boolean Attributes

## Table of Contents

  1. [Introduction](#introduction)


## Contents

### Boolean Attributes

<sup>Status: **under discussion**</sup>

A boolean attribute is one that needs no declared value. XHTML required you to declare a value, but HTML5 has no such requirement.

For further reading, consult the [WhatWG section on boolean attributes:](https://html.spec.whatwg.org/multipage/common-microsyntaxes.html#boolean-attributes)

<i>The presence of a boolean attribute on an element represents the true value, and the absence of the attribute represents the false value.</i>

If you must include the attribute's value, and you don't need to, follow this WhatWG guideline:

<i>If the attribute is present, its value must either be the empty string or [...] the attribute's canonical name, with no leading or trailing whitespace.
In short, don't add a value. </i>


```
<input type="text" disabled>

<input type="checkbox" value="1" checked>

<select>
    <option value="1" selected>1</option>
</select>
```
