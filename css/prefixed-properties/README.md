# Prefixed properties

*CSS prefixed properties guide for Born Digital team*

## Table of Contents

  1. [Prefixed properties](#prefixed-properties)
  
## Contents

### Prefixed properties

<sup>Status: **under discussion** | Following Wordpress: **no** </sup>

[@mdo:](http://codeguide.co/#css-prefixed-properties) <br>
When using vendor prefixed properties, indent each property such that the declaration's value lines up vertically for easy multi-line editing. <br>

In Textmate, use Text → Edit Each Line in Selection (⌃⌘A). In Sublime Text 2, use Selection → Add Previous Line (⌃⇧↑) and Selection → Add Next Line (⌃⇧↓). <br>

```
/* Prefixed properties */
.selector {
  -webkit-box-shadow: 0 1px 2px rgba(0,0,0,.15);
          box-shadow: 0 1px 2px rgba(0,0,0,.15);
}
```
