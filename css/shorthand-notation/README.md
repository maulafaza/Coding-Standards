# Shorthand notation

*CSS shorthand notation guide for Born Digital team*

## Table of Contents

  1. [Shorthand notation](#shorthand-notation)
  
## Contents

### Shorthand notation

<sup>Status: **under discussion** | Following Wordpress: **under discussion** </sup>

[@mdo:](http://codeguide.co/#html-reducing-markup) <br>
Strive to limit use of shorthand declarations to instances where you must explicitly set all the available values. <br>
Common overused shorthand properties include: <br>

<ul>
<li>padding</li>
<li>margin</li>
<li>font</li>
<li>background</li>
<li>border</li>
<li>border-radius</li>  
</ul>

Often times we don't need to set all the values a shorthand property represents. <br>
For example, HTML headings only set top and bottom margin, so when necessary, only override those two values. <br>
Excessive use of shorthand properties often leads to sloppier code with unnecessary overrides and unintended side effects. <br> <br>

The Mozilla Developer Network has a great article on shorthand properties for those unfamiliar with notation and behavior. <br>

```
/* Bad example */
.element {
  margin: 0 0 10px;
  background: red;
  background: url("image.jpg");
  border-radius: 3px 3px 0 0;
}

/* Good example */
.element {
  margin-bottom: 10px;
  background-color: red;
  background-image: url("image.jpg");
  border-top-left-radius: 3px;
  border-top-right-radius: 3px;
}
```
