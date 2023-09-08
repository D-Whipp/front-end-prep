# Questions taken from r/learnprogramming

## What are the different types of variables in JavaScript? How are they different from each other?

Answers taken from MDN web docs.

### var

The var statement declares function-scoped or globally-scoped variables, optionally initializing each to a value.

The var keyword is used to declare function-scoped variables and globally-scoped variables. If you use var inside a block, the variable will not be a block scoped. It will either be function scoped or globally scoped depending upon where the block is present.

-   var declarations can be in the same scope as a function declaration. In this case, the var declaration's initializer always overrides the function's value, regardless of their relative position. This is because function declarations are hoised before any initializer gets evaluated, so the initializer comes later and overrides the value.

    -   Example:
        -   var a = 1;
        -   function a() {};
        -   console.log(a);
        -   _1_

-   var declarations cannot be in the same scope as a let, const, class, oro import declarations.

    -   var a = 1;
    -   let a = 1;
    -   _SyntaxError: Identifier 'a' has already been declared_

-   Because var declarations are not scoped to blocks, this also applies to the following case:

    -   let a = 1;
        -   {
        -   var a = 1; _SyntaxError: Identifier 'a' has already been declared_
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
    -   _Logs 1_

### let

The let declaration declares re-assignable, block-scoped local variables, optionally initializing each to a value.

Example:

-   let x = 1;
-   if (x === 1) {
-   let x = 1;
-   console.log(x);
-   _Expected output: 2_
-   }
-   console.log(x);
-   _Expected output: 1_

Description:

The scope of a variable declared with _let_ is one of the following curly-brace-enclosed syntaxes that most closely contains the _let_ declaration.

-   Block statement
-   switch statement
-   try...catch statement
-   Body of one of the _for_ statements, if the _let_ is in the header of the statement
-   Function body
-   Static initialization block

_let_ differs from _var_ in the following ways:

-   _let_ declarations are scoped to blocks as well as functions.
-   _let_ declarations can only be accessed after the place of a declaration is reached.
    -   For this reason, _let_ declarations are commonly regarded as non-hoisted.
-   _let_ declarations do not create properties on globalThis when declared at the top level of a script.
-   _let_ declarations cannot be redeclared by any other declaration in the same scope.
-   _let_ begins delcarations, not statements. That means you cannot use a lone _let_ declaration as the body of a block.
    -   Example: if (true) let a = 1;
    -   _SyntaxError: Lexical declaration cannot appear in a single-statment context._

### Temporal Dead Zone (TDZ)

{
_TDZ starts at beginning of scope_
console.log(bar); _undefined_
console.log(foo); _ReferenceError: Cannot access 'foo' before initialization_
var bar = 1;
let foo = 2; _End of TDZ (for foo)_
}

The term "temporal" is used because the zone depends on the order of execution (time) rather than the order in which the code is written (position). For example, the code below works because, even though the function that uses the let variable appears before the variable is declared, the function is called outside the TDZ.

{
_TDZ starts at beginning of scope_
const func = () => console.log(letVar); _OK_

    _Within the TDZ access throws `ReferenceError`_

    let letVar = 3; _End of TDZ (for letVar)_
    func(); _Called outside TDZ!_

}

## What are some different ways to create an object in JavaScript?

## How can you get the type of a variable in JavaScript?

## Can you tell me the difference between == and ===?

## Do you know what arrow functions are?

## How are arrow functions different from traditional functions?

## What can you tell me about Callbacks?
