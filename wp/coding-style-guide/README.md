# Coding Style Guide

*WordPress & PHP coding style guide for Born Digital team*

## Table of Contents

  1. [Indentation](#indentation)
  2. [Variable Naming](#variable-naming)
  3. [Namespacing](#namespacing)
  4. [Class Naming](#class-naming)
  5. [Method Naming](#method-naming)
  6. [Function Naming](#function-naming)
  7. [Braces Style](#braces-style)
  8. [Commenting](#commenting)


## Contents

### Indentation

<sup>status: **optional**</sup>

 You're free to choose the variation. But in terms of how many spaces (or tabs) constitutes indentation, it's **more important to be consistent** throughout your code than to use any specific tab stop value.

Variations:

- Tab for indentation, tab for alignment
  + (+) You save a lot of bytes.
  + (-) A tab could be a different number of columns depending on your environment/ editor, but a space is always one column.
- Space for indentation, space for alignment
  + (+) Your codes become neat in whatever environment/ editor. So, team-interchange should not be a problem.
  + (-) This will increase the bytes of your file.
- Tab for indentation, space for alignment
  + (+) Balance between bytes-saving & code cleanness.
  + (-) (Tobe defined)

### Variable Naming

<sup>status: **requirement**</sup>

Most of the team use underscore (`_`) for variable naming.

### Namespacing

<sup>status: **optional**</sup>

WordPress seems doesn't campaign the usage of namespacing. You can follow [PSR-1](http://www.php-fig.org/psr/psr-1/) if you want.

### Class Naming

<sup>status: **requirement**</sup>

Due to team convention, we can use `Class_Name` as used in WordPress core.

### Method Naming

<sup>status: **requirement**</sup>

Following the class naming, method name must uses underscore (`_`) style like `class_method_name` as used in WordPress & CodeIgniter.

### Function Naming

<sup>status: **requirement**</sup>

Following method naming, function name must uses underscore (`_`) style like `function_name` as used in WordPress & CodeIgniter.

### Braces Style

<sup>status: **optional**</sup>

You're free to choose the variation. You can follow either WordPress or [PSR-2](http://www.php-fig.org/psr/psr-2/) style.

**variation 1**:

```
if ( condition ) {
    // code
}

foreach ( condition ) {
    // code
}

function the_function( $param ) {
    // code
}

```

**variation 2**:

```
if (condition) {
    // code
}

foreach (condition) {
    // code
}

function the_function($param) {
    // code
}

```

### Code Commenting

<sup>status: **requirement**</sup>

Always comment on un-clear/ ambiguos code. This will help you in maintaining the project and help the others to understand your code.
