# Coding Style Guide

*HTML reducing markup guide for Born Digital team*

## Table of Contents

  1. [Reducing Markup](#reducing-markup)
  
## Contents

### Reducing Markup

Whenever possible, avoid superfluous parent elements when writing HTML. Many times this requires iteration and refactoring, but produces less HTML. Take the following example:

<sup>Status: **unnder discussion** </sup>

```
<!-- Not so great -->
<span class="avatar">
  <img src="...">
</span>

<!-- Better -->
<img class="avatar" src="...">
```
