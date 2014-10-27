---
tags: variables, integers, strings, operators, primitives, floats
language: JavaScript, JS
resources: 5
---

#JavaScript Basics:
JavaScript is the de facto language of the internet.  It's a tool that once mastered will allow you to interact with your users via your app in fun and interesting ways.  It is a dynamically typed, prototypical, functional programming language.  What that exactly means will come more apparent in class and through exposure to the language.  But here are the basics.

## Variables, Primitives, and Operators
Welcome to JavaScript! First thing first, let's get the absolute basics down before you do anything else. In this lab we'll explore variables, primitives (strings, integers, floats, and booleans), and operators.

### Variables
  In JavaScript you can declare a variable in two ways but each have different consequences.

  The best way is to use the key word `var` before the variable.  This ensures that the variable is set to the current scope.  If var is not used in defining a new variable it becomes global and is accessible throughout the program.  This happens because it becomes attached to the global object, which in most cases is `window`.

  ex.
  ```javascript
  var someLocalNumber = 10; // can only be accessed within the current scope
  someGlobalNumber = 42; // is now window.someGlobalNumber and can be accessed anywhere
  ```

  Variables can also be declared, but not necessarily assigned a value.  The following two are equivalent.

  ex.
  ```javascript
  var someNumber; // returns undefined
  someNumber = 10;  // returns 10
  var theSameNumber = 10; // returns 10
  ```

  Variables can also be assigned at once with multiple lines, using commas to delimit each.You must terminate the assignment with a semicolon.

  ex.
  ```javascript
  var someVariable,
      someNumber = 10,
      aString = 'Hello World';
  ```
### Strings
  Strings are very straight forward in JS.  They are collections of characters.  Plus signs are used to concatenated strings.  JS does not support string interpolation like some other languages. Concatenating strings coerces the types of the objects into strings if they are not already.

  ex.
  ```javascript
  'Hello ' + 'World'; // returns 'Hello World'
  'High ' + 5 + '!!!'; // returns 'High 5!!!'
  ```

### Numbers
  Unlike most programming languages JS uses floats by default. And creating literal numbers uses the Number Constructor. New numbers can optionally have decimal points with trailing zeros, but keep in mind they are floats either way.

  Sometimes this can lead to unexpected consequences, which can generally be solved with `Math.floor`.  Note when comparing integers to unknown numbers it is best practice to floor the unknown because some floats are equal to the integer.

  ex.
  ```javascript
  4 === 4.0; // returns true
  Math.floor(4.00001); // returns 4
  4.0000000000000001 === 4; // returns true
  Math.floor(4.0000000000000001); === true // safer!
  ```

### Booleans
  Booleans are fairly straight forward in JS; however, there are some quirks.  Booleans can be cast into numbers.  1 and 0 also follow boolean logic, so 1 is loosely equal to true and 0 is loosely equal to false. (1 and 0 can also be cast into true and false respectively.)

  ex.
  ```javascript
  + true // returns 1
  0 == false // returns true
  !!1 // returns true
  !!0 // returns false
  ```

### Operators
  For the most part operators are the same in JS as they are in any other language except for loose and strict equals.  `==` and `!=` are loose comparisions and convert type to match one another. `===` and `!==` are strict comparisons, they compare both type and value.

  ex.
  ```javascript
  1 != true // returns false
  1 == '1' // returns true
  1 !== true // returns true
  1 === '1' // returns false
  ```

### Undefined, Null, and NaN
  Undefined represents the absence of a primitve value, and Null represents the absence of an object.

  NaN represents an error from the improper use of a math operator.  NaN is the only thing in JS that is not equal to itself. To check for NaN us the `isNaN()` function.

  ex.
  ```javascript
  1 - 'three' // returns NaN
  NaN === NaN // returns false
  isNaN(NaN) // returns true
  ```

####Resources:
* [A Larger (optional) tutorial by Mozilla](https://developer.mozilla.org/en-US/docs/Web/JavaScript/A_re-introduction_to_JavaScript)
* [String Constructor](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)
* [Number Constructor](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)
* [Arithmetic Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators)
* [Undefined, Null, NaN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference)
