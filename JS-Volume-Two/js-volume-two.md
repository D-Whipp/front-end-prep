# Questions taken from r/learnprogramming

## What are the different types of variables in JavaScript? How are they different from each other?

var

-   The var statement declares function-scoped or globally-scoped variables, optionally initializing each to a value.
-   var declarations can be in the same scope as a function declaration. In this case, the var declaration's initializer always overrides the function's value, regardless of their relative position. This is because function declarations are hoised before any initializer gets evaluated, so the initializer comes later and overrides the value.

    -   Example:
        -   var a = 1;
        -   function a() {};
        -   console.log(a);
        -   //1

-   var declarations cannot be in the same scope as a let, const, class, oro import declarations.

    -   var a = 1;
    -   let a = 1;
    -   // SyntaxError: Identifier 'a' has already been declared

-   Because var declarations are not scoped to blocks, this also applies to the following case:

    -   let a = 1;
        -   {
        -   var a = 1; // SyntaxError: Identifier 'a' has already been declared
        -   }
        -   This does not apply to the following case, where let is in a child scope of var, not the same scope:
        -   var a = 1;
        -   {
        -   let a = 1;
        -   }

-   A var declaration within a function's body can have the same name as a parameter.
    -   function foo(a) {
    -   var a = 1;
    -   console.log(a);
    -   }
    -   foo(2);
    -   // Logs 1

## What are some different ways to create an object in JavaScript?

## How can you get the type of a variable in JavaScript?

## Can you tell me the difference between == and ===?

## Do you know what arrow functions are?

## How are arrow functions different from traditional functions?

## What can you tell me about Callbacks?
