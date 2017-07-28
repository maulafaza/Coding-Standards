# IE compatibility mode

*HTML IE compatibility mode guide for Born Digital team*

## Table of Contents

  1. [IE compatibility mode](#ie-compatibility-mode)
  
## Contents

### IE compatibility mode

<sup>Status: **under discussion** </sup>

[@mdo:](http://codeguide.co/#html-ie-compatibility-mode) <br>
Internet Explorer supports the use of a document compatibility <meta> tag to specify what version of IE the page should be rendered as. Unless circumstances require otherwise, it's most useful to instruct IE to use the latest supported mode with edge mode. <br>

For more information, <a href="http://stackoverflow.com/questions/6771258/whats-the-difference-if-meta-http-equiv-x-ua-compatible-content-ie-edge-e">read this awesome Stack Overflow article</a>.

```
<meta http-equiv="X-UA-Compatible" content="IE=Edge">
```
