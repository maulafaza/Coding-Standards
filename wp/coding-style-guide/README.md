# Coding Style Guide

*WordPress & PHP coding style guide for Born Digital team*

## Table of Contents

  1. [PHP Tags](#php-tags)
  2. [Quotes Usage](#quotes-usage)
  3. [Indentation](#indentation)
  4. [Braces Style](#braces-style)
  5. [Ternary Operator](#ternary-operator)
  6. [Conditional Style](#conditional-style)
  7. [Yoda Condition](#yoda-condition)
  8. [Files](#files)
  9. [Lines](#lines)
  10. [Space Usage](#space-usage)
  11. [Variable Naming](#variable-naming)
  12. [Namespacing](#namespacing)
  13. [Class Naming](#class-naming)
  14. [Method Naming](#method-naming)
  15. [Method & Property Scopes](#method--property-scopes)
  16. [Function Naming](#function-naming)
  17. [Commenting](#commenting)
  18. [Readibility, Maintainability](#readibility-maintainability)


## Contents

### PHP Tags

<sup>Status: **requirement** | Following WordPress: **no**</sup>

Opening tags MUST use the long tags `<?php ?>` while variable echo MUST use short-echo `<?= $var ?>` or `<?=$var?>`

### Quotes Usage

<sup>Status: **optional**</sup>

You are FREE to follow or don't follow [WordPress quotes guide](https://make.wordpress.org/core/handbook/best-practices/coding-standards/php/#single-and-double-quotes).

```
echo '<a href="#" title="Link Title">Link name</a>';
echo "<a href='$link' title='$linktitle'>$linkname</a>";
```

### Indentation

<sup>Status: **optional**</sup>

You're FREE to choose the variation. But in terms of how many spaces (or tabs) constitutes indentation, it's **more important to be consistent** throughout your code than to use any specific tab stop value.

Below are some of the variations:

- #1: Tab for indentation, tab for alignment
  + (+) You save lot of bytes.
  + (-) A tab could be a different number of columns depending on your environment/ editor, but a space is always one column.
- #2: Space for indentation, space for alignment
  + (+) Your codes become neat in whatever environment/ editor. So, team-interchange should not be a problem.
  + (-) This will increase the bytes of your file.
- #3: Tab for indentation, space for alignment
  + (+) Balance between bytes-saving & code cleanness.
  + (-) (Tobe defined)

### Braces Style

<sup>Status: **optional** | Following WordPress: **partially**</sup>

if you have a really long block, consider whether it can be broken into two or more shorter blocks or functions.

If you consider such a long block unavoidable, please put a short comment at the end so people can tell at glance what that ending brace ends – typically this is appropriate for a logic block, longer than about 35 rows, but any code that’s not intuitively obvious can be commented.

> **Shorthand conditional:**
> WordPress advises to always use the braces even when they're not required.
>
>*Please follow that advice.*

#### Don't do this:
```
// conditional for single statement using multilines but without braces
if (condition)
    // code
```

#### You may use these:
```
// simple conditional with single/ multi statements
if (condition) {
    //
}

// inline conditional with single statement
if (condition) // code

// longer conditional
if (condition) {

} elseif (condition) {

} else {

}

```
You can also use the alternative syntax for *Control Structures* (e.g. `if`/`endif`, `while`/`endwhile`)—especially in your templates where PHP code is embedded within HTML, for instance:
```
<?php if (have_posts()) : ?>
    <ul>
        <?php while (have_post()) : the_post(); ?>
            <li><?php the_content(); ?></li>
        <?php endwhile; ?>
    </ul>
<?php endif; ?>
```

### Ternary Operator

<sup>Status: **optional** | Following WordPress: **yes**</sup>

Ternary operators are fine, but always have them test if the statement is true, not false. Otherwise, it just gets confusing.

(An **exception** would be using `!empty()`, as testing for false here is generally more intuitive.)

```
// (if statement is true) ? (do this) : (else, do this);

$skin = ($user_role === 'admin') ? 'dark' : 'light';

$skin = $user_role === 'admin' ? 'dark' : 'light';

// (if statement is false) ? (do this) : (else, do this);
```

### Conditional Style

<sup>Status: **recommendation** | Following WordPress: **yes**</sup>

The keyword `elseif` SHOULD be used instead of `else if` so that all control keywords look like single words.

WordPress also said that `else if` is not compatible with the colon syntax for `if|elseif` blocks. For this reason, use `elseif` for conditionals.

### Yoda Condition

<sup>Status: **optional**</sup>

WordPress advices [Yoda Conditions](https://make.wordpress.org/core/handbook/best-practices/coding-standards/php/#yoda-conditions) which you're FREE to use it or not.

Some peoples would like to follow this, but some others are not comfortable with this, due to *strange-readibility*.

```
if ( 'admin' == $user_role ) {
    //you have access
}
```

### Files

<sup>Status: **requirement** | Following WordPress: **yes**</sup>

The closing `?>` tag MUST be omitted from files containing only PHP/ *non-direct-outputting*.

### Lines

<sup>Satus: **requirement** | Following WordPress: **yes**</sup>

There MUST NOT be trailing whitespace at the end of non-blank lines. Remove trailing whitespace at the end of each line of code.

### Space Usage

#### On Operators

<sup>Status: **requirement** | Following WordPress: **partially**</sup>

ALWAYS put spaces after commas, and on both sides of logical, comparison, string and assignment operators. Except for *negation*, you are FREE to use `! $condition` or `!$condition`:

```
$id === 3
$condition1 && $condition2
$condition1 || $condition2
! $condition
!$condition
$output .= '';
$items = ['Laravel', 'CodeIgniter 4', 'SlimPHP'];
```

#### On Blocks

<sup>Status: **optional**</sup>

You are FREE to put or omit spaces on both sides of the opening and closing parenthesis of: `if`, `elseif`, `foreach`, `for`, and `switch` blocks.

**variation 1**:

```
// conditional
if ( condition ) {

} elseif ( condition ) {

} else {

}

// looping
foreach ( condition ) {

}

// regular function
function get_member_url( $param ) {

}

// anonymous function
function ( $param ) {

}

```

**variation 2**:

```
// conditional
if (condition) {

} elseif (condition) {

} else {

}

// looping
foreach (condition) {

}

// regular function
function get_member_url($param) {

}

// anonymous function
function ($param) {

}

```

### Variable Naming

<sup>status: **requirement** | Following WordPress: **yes**</sup>

Most of the team use underscore (`_`) for dividing words in variable naming. So, underscore MUST be used to divide words instead of using `camelCase` style.

**Example**
```
$post_id = 3;
$user_id = get_current_user_id();
```

Variables that contain/ represent array MUST use **plural/ plural-like** style.
```
$users = [];
$posts = get_posts();
```

### Namespacing

<sup>status: **optional**</sup>

WordPress seems like didn't campaign the usage of namespace. You can follow [PSR-1](http://www.php-fig.org/psr/psr-1/) if you want.

**Example**
```
<?php
namespace Plugin\Messaging;

use Plugin\Members\User;

class Tool
{
    public function __construct()
    {
        // code
    }
}
```

### Class Naming

<sup>status: **requirement** | Following WordPress: **yes**</sup>

Due to team convention and WordPres's nature, class MUST uses `Class_Name` style in an *internal component/ module* that is not a *composer-package*. Here is how it looks like:
```
<?php
class Inbox_Utility
{
    public function __construct()
    {
        // code
    }
}
```

### Method Naming

<sup>status: **requirement** | Following WordPress: **yes**</sup>

Following the class naming, method name MUST uses underscore (`_`) style like `class_method_name` in an *internal component/ module* that is not a *composer-package*. It looks like this:

```
<?php
class Inbox_Utility
{
    public function set_unread($msg_id)
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
class Submit_Message
{
    public $response = [];
    private $_item = [];

    private function _send($args)
    {
        // code
    }
}
```

### Function Naming

<sup>status: **requirement** | Following WordPress: **yes**</sup>

Following the method naming, function name MUST uses underscore (`_`) style like `function_name` as used in WordPress. It could be like this:

```
<?php
function get_user_profiles() {
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
```

**Example of multilines comment**
```
/**
 * Activate member after:
 * - Admin approve the registration
 * - User click activation link from received email
 */
activate_member($user_id);
```

**Example of function commenting**
```
<?php
/**
 * Get message by id
 *
 * @since 1.0.0
 *
 * @param int $msg_id
 * @return object
 */
function get_message($msg_id) {
    return Messaging::get($msg_id);
}
```

### Readibility, Maintainability

<sup>Status: **requirement**</sup>

In general, readability is more important than cleverness or brevity. Good readibility and maintainability would help your partner and next maintainer.
