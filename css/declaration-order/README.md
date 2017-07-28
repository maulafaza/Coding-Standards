# Declaration Order Guide

*CSS declaration order guide for Born Digital team*

## Table of Contents

  1. [Declaration Order](#declaration-order)

## Contents

### Declaration Order

<sup>Status: **under discussion**   | Following WordPress: no</sup>

[@mdo](http://codeguide.co/#css-declaration-order) :

Related property declarations should be grouped together following the order:

<ol>
<li> Positioning </li>
<li> Box model </li>
<li> Typographic </li>
<li> Visual </li>
</ol>

Positioning comes first because it can remove an element from the normal flow of the document and override box model related styles. The box model comes next as it dictates a component's dimensions and placement.

Everything else takes place inside the component or without impacting the previous two sections, and thus they come last.

```
.declaration-order {
  /* Positioning */
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 100;

  /* Box-model */
  display: block;
  float: right;
  width: 100px;
  height: 100px;

  /* Typography */
  font: normal 13px "Helvetica Neue", sans-serif;
  line-height: 1.5;
  color: #333;
  text-align: center;

  /* Visual */
  background-color: #f5f5f5;
  border: 1px solid #e5e5e5;
  border-radius: 3px;

  /* Misc */
  opacity: 1;
}
```
