# Nesting In Less And SASS Guide

*CSS Nesting In Less And SASS guide for Born Digital team*

## Table of Contents

  1. [Nesting In Less And SASS](#nesting-in-less-and-sass)

## Contents

### Nesting In Less And SASS

<sup>Status: **under discussion**   | Following WordPress: no</sup>

[@mdo](http://codeguide.co/#css-nesting) :

Avoid unnecessary nesting. Just because you can nest, doesn't mean you always should. 
Consider nesting only if you must scope styles to a parent and if there are multiple elements to be nested.

Additional reading:

[Nesting in Sass and Less](http://markdotto.com/2015/07/20/css-nesting/)


```
// Without nesting
.table > thead > tr > th { … }
.table > thead > tr > td { … }

// With nesting
.table > thead > tr {
  > th { … }
  > td { … }
}
```
