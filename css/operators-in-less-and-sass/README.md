# Operator In Less And SASS Guide

*CSS Operator In Less And SASS guide for Born Digital team*

## Table of Contents

  1. [Operator In Less And SASS](#operator-in-less-and-sass)

## Contents

### Operator In Less And SASS

<sup>Status: **under discussion**   | Following WordPress: no</sup>

[@mdo](http://codeguide.co/#css-operators) :

For improved readability, wrap all math operations in parentheses with a single space between values, variables, and operators.

```
// Bad example
.element {
  margin: 10px 0 @variable*2 10px;
}

// Good example
.element {
  margin: 10px 0 (@variable * 2) 10px;
}
```
