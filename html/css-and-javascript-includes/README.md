# Coding Style Guide

*HTML => CSS and JavaScript includes guide for Born Digital team*

## Table of Contents

  1. [CSS and JavaScript includes](#css-and-javascript-includes)
  
## Contents

### CSS and JavaScript includes

<sup>Status: **under discussion** </sup>

[@mdo:](http://codeguide.co/#html-style-script 
Per HTML5 spec, typically there is no need to specify a type when including CSS and JavaScript files as text/css and text/javascript are their respective defaults.

HTML5 spec links
<ul>
<li><a href="http://www.w3.org/TR/2011/WD-html5-20110525/semantics.html#the-link-element">Using link</a></li>
<li><a href="http://www.w3.org/TR/2011/WD-html5-20110525/semantics.html#the-style-element">Using style</a></li>
<li><a href="http://www.w3.org/TR/2011/WD-html5-20110525/scripting-1.html#the-script-element">Using script</a></li>
</uL

<b> External CSS </b>

```
<link rel="stylesheet" href="code-guide.css">
```

<b> In-document CSS </b>

```
<style>
  /* ... */
</style>
```

<b> JavaScript </b>
```
<script src="code-guide.js"></script>
```
