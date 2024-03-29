# Soft JavaScript Interview Questions

JavaScript is used to add user interaction to an application. The following section targets the commonly asked JavaScript Frontend Developer Interview Questions.

## What are the various Data Types in JavaScript?

JavaScript has many data types to provide the basic functionality needed for a web application. They are mentioned in this table.
![Data Types Images](./images/JavaScript_DataTypes.png)

## What is Callback in JavaScript?

![Calllback Image](./images/JavaScript_CallBack.png)

A callback is a JavaScript function that is sent as an argument or parameter to another function.
You call this function whenever the function to which it is provided is called.

## What’s the difference between Function Declaration and Function Expression?

### Function Declaration

function abc(){

    return 5;

}

Within the main JavaScript code, it declares this as a separate statement. It is possible to invoke it before the function has been defined. It provides improved code readability.

### Function Expression

var a = function abc(){

    return

}

It is created inside an expression or some other construct. It is generally used when there is a need for a conditional declaration of a function.

## What do you understand about Cookies in JavaScript?

A cookie is a little piece of data sent by a website and kept on the user's computer by the web browser that was used to access the page.

Cookies are used to remember information for later use and to keep track of a website's browsing activities.

The simplest approach to make a cookie with JavaScript is to do it as follows:

document.cookie = "key1 = value1; key2 = value2; expires = date";

To delete a cookie, you can just set an expiration date and time; specifying the correct path of the cookie is a good practice.

function delete_cookie(name) {

      document.cookie = name + "=; Path=/; Expires=Thu, 01 Jan 1970 00:00:01 GMT;";

    }

## What are Closures in JavaScript?

Closures in JavaScript are a feature where an inner function has access to the outer function’s variables.

function outer_func()

{

    var b =10;

    function inner_func(){

        var a =20;

        console.log(a+b);

    }

    return inner;

}

A closure has three scope chains:

- Has access to the variable defined within its curly braces, which is its scope.
- Has access to the outer functions' variables.
- Has the ability to access global variables.

## What are Imports and Exports in JavaScript?

### Export

export const sqrt = Math.sqrt;

export function square(x) {

return x \* x;

}

export function diag(x, y) {

return sqrt(square(x) + square(y));

}

This file exports two functions that calculate the squares and diagonal of the input respectively.

### Import

import { square, diag } from "calc";

console.log(square(4)); // 16

    console.log(diag(4, 3)); // 5

Here you import those functions and pass input to those functions to calculate square and diagonal.

## What is the difference between Undefined, Undeclared, and Null in JavaScript?

var x

console.log(x) //Undefined variable

var y=NULL

console.log(y) //Null Variable

console.log(z) //Undeclared Variable

Undefined - Undefined means a variable has been declared but a value has not yet been assigned to that variable.

Null - Null is an assignment value that you can assign to any variable that is meant to contain no value.

Undeclared - Variables that are not declared or that do not exist in a program or application.

## What is the best way to remove Duplicates from a JavaScript Array?

You can delete duplicates from a JavaScript array in one of two ways:

By employing the filtering technique - Three arguments are required to call the filter() function. These are the array, current element, and current element index.

The For loop is used to store all the repeated elements in an empty array.
