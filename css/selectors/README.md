# Selectors

*CSS Selectors notation guide for Born Digital team*

## Selectors

  1. [Selectors](#selectors)
  
## Contents

### Selectors

<sup>Status: **under discussion** | Following Wordpress: **no** </sup>

[@mdo:](http://codeguide.co/#css-selectors) <br>
<ul>
<li>Use classes over generic element tag for optimum rendering performance.</li>
<li>Avoid using several attribute selectors (e.g., [class^="..."]) on commonly occuring components. Browser performance is known to be impacted by these.</li>
<li>Keep selectors short and strive to limit the number of elements in each selector to three.</li>
<li>Scope classes to the closest parent <b>only</b> when necessary (e.g., when not using prefixed classes).</li>
</ul>

Additional reading:

<ul>
<li>Scope CSS classes with prefixes</li>
<li>Stop the cascade</li>
</ul>

```
/* Bad example */
span { ... }
.page-container #stream .stream-item .tweet .tweet-header .username { ... }
.avatar { ... }

/* Good example */
.avatar { ... }
.tweet-header .username { ... }
.tweet .avatar { ... }
```
