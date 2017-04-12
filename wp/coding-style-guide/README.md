# Coding Style Guide

*WordPress & PHP coding style guide for Born Digital team*

## Table of Contents

  1. [Indentation](#indentation)
  2. [Variable Naming](#variable-naming)
  3. [Namespacing](#namespacing)
  4. [Class Naming](#class-naming)
  5. [Method Naming](#method-naming)
  6. [Method & Property Scopes](#method--property-scopes)
  7. [Function Naming](#function-naming)
  8. [Braces Style](#braces-style)
  9. [Commenting](#commenting)


## Contents

### Indentation

<sup>status: **optional**</sup>

You're free to choose the variation. But in terms of how many spaces (or tabs) constitutes indentation, it's **more important to be consistent** throughout your code than to use any specific tab stop value.

Below are some of the variations:

- #1: Tab for indentation, tab for alignment
  + (+) You save a lot of bytes.
  + (-) A tab could be a different number of columns depending on your environment/ editor, but a space is always one column.
- #2: Space for indentation, space for alignment
  + (+) Your codes become neat in whatever environment/ editor. So, team-interchange should not be a problem.
  + (-) This will increase the bytes of your file.
- #3: Tab for indentation, space for alignment
  + (+) Balance between bytes-saving & code cleanness.
  + (-) (Tobe defined)

### Variable Naming

<sup>status: **requirement**</sup>

Most of the team use underscore (`_`) for variable naming.

**Example**
```
$post_id = 3;
$user_id = get_current_user_id();
```

### Namespacing

<sup>status: **optional**</sup>

WordPress seems like didn't campaign the usage of namespace. You can follow [PSR-1](http://www.php-fig.org/psr/psr-1/) if you want.

**Example**
```
<?php
namespace Plugin\Email;

use Plugin\Messaging\Utility;

class Actions
{
    public function __construct()
    {
        // code
    }
}
```

### Class Naming

<sup>status: **requirement**</sup>

Due to team convention, we can use `Class_Name` style as used in WordPress core. Here is how it looks like:
```
<?php
class Fetch_Message
{
    public function __construct()
    {
        // code
    }
}
```

### Method Naming

<sup>status: **requirement**</sup>

Following the class naming, method name must uses underscore (`_`) style like `class_method_name` as used in WordPress. It could be like this:

```
<?php
class Fetch_Message
{
    public function by_id($msg_id)
    {
        // code
    }
}
```

### Method & Property Scopes

<sup>status: **requirement**</sup>

For readibility inside the class it self, use underscore (`_`) as prefix for **private** methods & properties.

**Example**
```
<?php
class Fetch_Message
{
    public $response = [];
    private $_item = [];

    private function _update($msg_id)
    {
        // code
    }
}
```

### Function Naming

<sup>status: **requirement**</sup>

Following the method naming, function name must uses underscore (`_`) style like `function_name` as used in WordPress. It could be like this:

```
<?php
function get_message() {
    // code
}
```

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

### Commenting

<sup>status: **requirement**</sup>

Always comment on unclear/ ambiguos code. This will help you in maintaining the project and it will help the others to understand your code.

> For one line comment, please use inline comment like `// your comment`

**Example of inline comment**
```
// $quiz_done is taken from user meta
$prev_quiz = $quiz_done - 1;
$next_quiz = $prev_quiz + 1;
```
**Example of multilines comment**
```
/**
 * Get message by id
 *
 * @since 1.0.0
 *
 * @param int $msg_id
 * @return object
 */
function get_message_by_id($msg_id) {
    return Messaging::get($msg_id);
}
```
