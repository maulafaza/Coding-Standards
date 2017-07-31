# Reducing Markup

## Table of Contents

  1. [Introduction](#introduction)

## Contents

### Introduction

<sup>Status: **under discussion**</sup>

Whenever possible, avoid superfluous parent elements when writing HTML. <br>
Many times this requires iteration and refactoring, but produces less HTML. <br>
Take the following example:

```
<!-- Not so great -->
<span class="avatar">
    <img src="...">
</span>

<!-- Better -->
<img class="avatar" src="...">
```
