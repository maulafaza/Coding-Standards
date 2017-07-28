# Class Names Guide

*CSS Class Names guide for Born Digital team*

## Table of Contents

  1. [Class Names](#class-names)

## Contents

### Class Names

<sup>Status: **under discussion**   | Following WordPress: no</sup>

[@mdo](http://codeguide.co/#css-classes) :

<ul>
<li> Keep classes lowercase and use dashes (not underscores or camelCase). Dashes serve as natural breaks in related class (e.g., .btn and .btn-danger). </li>
<li> Avoid excessive and arbitrary shorthand notation. .btn is useful for button, but .s doesn't mean anything. </li>
<li> Keep classes as short and succinct as possible. </li>
<li> Use meaningful names; use structural or purposeful names over presentational. </li>
<li> Prefix classes based on the closest parent or base class. </li>
<li> Use .js-* classes to denote behavior (as opposed to style), but keep these classes out of your CSS. </li>
</ul>

It's also useful to apply many of these same rules when creating Sass and Less variable names.

```
/* Bad example */
.t { ... }
.red { ... }
.header { ... }

/* Good example */
.tweet { ... }
.important { ... }
.tweet-header { ... }
```
