Coding Style Guide
===

### 1. Indentation

- 1.1 **Status**: *optional*
- 1.2 **Description**:  You're free to choose the variation. But in terms of how many spaces (or tabs) constitutes indentation, it's **more important to be consistent** throughout your code than to use any specific tab stop value.
- **Variations**
  + **Tab for indentation, tab for alignment**
    - (+): *You save a lot of bytes.*
    - (-): *A tab could be a different number of columns depending on your environment/ editor, but a space is always one column.*
  +  **Space for indentation, space for alignment**
  - (+): *Your codes become neat in whatever environment/ editor. So, team-interchange should not be a problem.*
  - (-): Cons: *This will increase the bytes of your file.*
  + **Tab for indentation, space for alignment**
 - (+): *Balance between bytes-saving & code cleanness.*
 - (-): (Tobe defined)

### 2. Variable Naming

> status: **requirement**

Most of team use underscore (`_`) for variable naming.

### 3. Namespacing

> status: **optional**

WordPress seems doesn't campaign the usage of namespacing. You can follow [PSR-1](http://www.php-fig.org/psr/psr-1/) if you want.

### 4. Class Naming

> status: **requirement**

Due to team convention, we can use `Class_Name` as used in WordPress core.

### 5. Method Naming

> status: **requirement**

Following the class naming, method name must uses underscore (`_`) style like `class_method_name` as used in WordPress & CodeIgniter.

### 6. Function Naming

> status: **requirement**

Following method naming, function name must uses underscore (`_`) style like `function_name` as used in WordPress & CodeIgniter.

### 7. Braces Style

> status: **optional**

You're free to choose the variation. You can follow either WordPress or [PSR-2](http://www.php-fig.org/psr/psr-2/) style.

**Variation 1**:

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

**Variation 2**:

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

### 7. Code Commenting

> status: **requirement**

Always comment on un-clear/ ambiguos code. This will help you in maintaining the project and help the others to understand your code.
