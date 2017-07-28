# Organization Guide

*CSS Organization guide for Born Digital team*

## Table of Contents

  1. [Organization](#organization)

## Contents

### Organization

<sup>Status: **under discussion**   | Following WordPress: no</sup>

[@mdo](http://codeguide.co/#css-organization) :

<ul>
<li> Organize sections of code by component. </li>
<li> Develop a consistent commenting hierarchy. </li>
<li> Use consistent white space to your advantage when separating sections of code for scanning larger documents. </li>
<li> When using multiple CSS files, break them down by component instead of page. Pages can be rearranged and components moved. </li>
</ul>

```
/*
 * Component section heading
 */

.element { ... }


/*
 * Component section heading
 *
 * Sometimes you need to include optional context for the entire component. Do that up here if it's important enough.
 */

.element { ... }

/* Contextual sub-component or modifer */
.element-heading { ... }
```
