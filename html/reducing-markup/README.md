# Coding Style Guide

*HTML reducing markup guide for Born Digital team*

## Table of Contents

  1. [Reducing Markup](#reducing-markup)
  
## Contents

### Reducing Markup

<sup>Status: **under discussion** </sup>

<a href="http://codeguide.co/#html-reducing-markup">@MDO:</a> <br>
Whenever possible, avoid superfluous parent elements when writing HTML. <br>
Many times this requires iteration and refactoring, but produces less HTML. <br>
Take the following example:

```
<!-- Not so great -->
<span class="avatar">
  <img src="...">
</span>

<!-- Better -->
<img class="avatar" src="...">
```
