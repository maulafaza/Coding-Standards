# Media Query Placement Guide

*CSS media query placement guide for Born Digital team*

## Table of Contents

  1. [Media Query Placement](#media-query-placement)

## Contents

### Media Query Placement

<sup>Status: **under discussion**   | Following WordPress: no</sup>

[@mdo](http://codeguide.co/#css-media-queries) :

Place media queries as close to their relevant rule sets whenever possible. 
Don't bundle them all in a separate stylesheet or at the end of the document. 
Doing so only makes it easier for folks to miss them in the future. Here's a typical setup.

```
.element { ... }
.element-avatar { ... }
.element-selected { ... }

@media (min-width: 480px) {
  .element { ...}
  .element-avatar { ... }
  .element-selected { ... }
}
```
