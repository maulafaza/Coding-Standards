# Attribute Order Guide

## Table of Contents

  1. [Attribute Order](#attribute-order)


## Contents

### Attribute Order

<sup>Status: **under discussion**</sup>

HTML attributes should come in this particular order for easier reading of code.
<ul>
<li> class </li>
<li> id, name </li>
<li> data-* </li>
<li> src, for, type, href, value </li>
<li> title, alt </li>
<li> role, aria-* </li>
<li> Classes make for great reusable components, so they come first. Ids are more specific and should be used sparingly (e.g., for in-page bookmarks), so they come second. </li>
</ul>

```
<a class="..." id="..." data-toggle="modal" href="#">
  Example link
</a>

<input class="form-control" type="text">

<img src="..." alt="...">
```
