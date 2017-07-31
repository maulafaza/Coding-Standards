# CSS and JavaScript Includes

## Table of Contents

  1. [Introduction](#introduction)

## Contents

### Introduction

<sup>Status: **under discussion** </sup>

Per HTML5 spec, typically there is no need to specify a type when including CSS and JavaScript files as text/css and text/javascript are their respective defaults.

HTML5 spec links
* [Using link](http://www.w3.org/TR/2011/WD-html5-20110525/semantics.html#the-link-element)
* [Using style](http://www.w3.org/TR/2011/WD-html5-20110525/semantics.html#the-style-element)
* [Using script](http://www.w3.org/TR/2011/WD-html5-20110525/scripting-1.html#the-script-element)

**External CSS**

```
<link rel="stylesheet" href="code-guide.css">
```

**In-document CSS**

```
<style>
    /* ... */
</style>
```

**External JavaScript**
```
<script src="code-guide.js"></script>
```
