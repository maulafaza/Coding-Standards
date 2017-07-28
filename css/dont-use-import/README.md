# Don't Use Import

*CSS <i>Don't Use Import</i> guide for Born Digital team*

## Table of Contents

  1. [Do Not Use Import](#do-not-use-import)

## Contents

### Do Not Use Import

<sup>Status: **under discussion** | Following WordPress: no</sup>

[@mdo](http://codeguide.co/#css-import) :

Compared to &lt;link&gt;s, @import is slower, adds extra page requests, and can cause other unforeseen problems. Avoid them and instead opt for an alternate approach:

<ul>
<li> Use multiple &lt;link&gt; elements </li>
<li> Compile your CSS with a preprocessor like Sass or Less into a single file </li>
<li> Concatenate your CSS files with features provided in Rails, Jekyll, and other environments </li>
</ul>

```
<!-- Use link elements -->
<link rel="stylesheet" href="core.css">

<!-- Avoid @imports -->
<style>
  @import url("more.css");
</style>
```
