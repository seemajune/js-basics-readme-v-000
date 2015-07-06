---
tags: variables, integers, strings, operators, primitives, floats, beginner
language: JavaScript, JS
resources: 8
---

# JavaScript Basics

JavaScript is the de facto language of the internet.  It's a tool that once mastered will allow you to interact with your users via your app in fun and interesting ways.  It is a dynamically typed, prototypical, functional programming language.  What that exactly means will come more apparent in class and through exposure to the language.  But here are the basics.

## Objectives

1. Gain a basic understanding of JavaScript syntax

2. Become comfortable reading, understanding, and writing basic JavaScript code

## Syntax Basics

Welcome to JavaScript! First thing first, let's get the absolute basics down before you do anything else.

**A simple variable declaration**

```javascript
var greeting = 'hello world';
```

**Whitespace has no meaning outside of quotation marks**

```javascript
var greeting =         'hello world';
```

**Parentheses indicate precedence**

```javascript
2 * 3 + 5;    // returns 11; multiplication happens first

2 * (3 + 5);  // returns 16; addition happens first
```

**Tabs enhance readability, but have no special meaning**

```javascript
var tvShows = {
    "ABC": [
        "The Bachelorette",
        "Grey's Anatomy"
    ],
    "FOX": [
        "Bones",
        "Empire"
    ]
};
```

## Data Types

JavaScript has a small set of primitive data types:
  1. Number
    - Examples include: 1, 3.14, 0.13, 100, ...
    - The largest number in JavaScript is 9007199254740992. Similarly, the smallest number is -9007199254740992 (see [here](http://stackoverflow.com/a/307200/2890716) for more info.

  2. String
    - Examples include:  "a", "World Wide Web"

  3. Boolean
    - Only two examples: true and false

  4. Undefined
    - Refers to an absent or unknown value

  5. Null
    - This is a special keyword that means one of two things: no value or empty.  The difference from undefined is that when a variable is null, it is still defined.

## Truthy and Falsely Things

We make a lot of assumptions when we write computer programs. In order to make the right assumtions, we need to understand what values in our program evaluate to `truthy` values and which evaluate to `falsely` values.

  ** Values that evaluate to `true`**

  ```javascript
  'all strings';  
  
  'all number strings'; // for example '0', '5', '0.2', '-3.14'  
  
  []; // an empty array  
  
  {}; // an empty object  
  
  1; // any non-zero number
  ```

  **Values that evaluate to 'false'**
  ```javascript
  0; // the number zero  
  
  '';  // an empty string  
  
  NaN;  
  
  null; 
  
  undefined;
  ```
## Return Values in JS
  Unless you use the `return` keyword or call a function that explicitly returns a value, the implicit return value in JavaScript is  `undefined`.
    > Undefined represents the absence of a primitive value

  Other special return values in JavaScript are `null`
    > Null represents the absence of an object

  and `NaN`
    > NaN represents an error from the improper use of a math operator.

## Variables

### Declaring Variables

As in Ruby, variables in JavaScript are used to store information/data that will be used in our program.  A variable can point to almost any type of value including numbers, strings, arrays, and hashes.

In JavaScript, variables are assigned values using the `=` operator. Variable names are typically all lower case, and in the case of multiple words, the words are joined together using [lower camelCase](http://c2.com/cgi/wiki?LowerCamelCase).

You can declare a variable in two ways  but each have different consequences:
- declaring a variable **using** the `var` keyword
  ```javascript
    var someLocalNumber = 10; // can only be accessed within the current scope
  ```
  <br>
- declaring a variable **without using** the `var` keyword

  ```javascript
    someGlobalNumber = 42; // is now window.someGlobalNumber and can be accessed anywhere
  ```

It is best to use the key word `var` before declaring a variable.  This ensures that the variable is set to the current scope.  If `var` is not used in defining a new variable it becomes global and is accessible throughout the program.  This happens because it becomes attached to the global object, which in most cases is `window`.

Variables can also be declared, but not necessarily assigned a value.  The following two are equivalent:

```javascript
  someNumber  = 10; // declares a global variable and returns 10  
  
  var someNumber = 10; // declares a non-global variable and returns 10
```
<br>
Variables can also be assigned at once with multiple lines, using commas to delimit each. You must terminate the assignment with a semicolon.
- ex:
  ```javascript
    var someVariable, someNumber = 10, aString = 'Hello World';
  ```

## Booleans

Booleans (**true** or **false** values) are fairly straight forward in JS; however, there are some quirks that you should be aware of.

Unlike in Ruby, booleans in JavaScript can be cast into numbers. The numbers 1 and 0 also follow boolean logic, so 1 is loosely equal to true and 0 is loosely equal to false. (1 and 0 can also be cast into true and false respectively). For example:
  ```javascript
  !!0 // returns false  
  
  + true // returns 1 
  
  0 == false // returns true  
  
  !!1 // returns true

  ```

## Strings

Strings are very straight forward in JS.  They are collections of characters.  Plus signs are used to concatenated strings.

JS does not support string interpolation like some other languages (i.e. Ruby). Concatenating strings coerces the types of the objects into strings if they are not already.

  ```javascript
  'Hello ' + 'World'; // returns 'Hello World'  
  
  'High ' + 5 + '!!!'; // returns 'High 5!!!'
  ```

## Numbers

Unlike most programming languages JS uses floats by default. And creating literal numbers uses the Number Constructor. New numbers can optionally have decimal points with trailing zeros, but keep in mind they are floats either way.

Sometimes this can lead to unexpected consequences, which can generally be solved with `Math.floor`.  Note when comparing integers to unknown numbers it is best practice to floor the unknown because some floats are equal to the integer.

  ```javascript  
  
  4 === 4.0; // returns true  
  
  Math.floor(4.00001); // returns 4  
  
  4.0000000000000001 === 4; // returns true  
  
  Math.floor(4.0000000000000001); === true // safer!
  ```

## Operators

### Basic Operators

  Basic operators allow you to manipulate values.

  **Concatenation**
  ```javascript
  var foo = "Hello";  
  
  var bar = "World!"  
  
  console.log(foo + ' ' + bar); // 'Hello World!'
  ```

  **Multiplication and division**
  ```javascript
  2 * 3;  
  
  2 / 3;
  ```

  **Incrementing and decrementing**
  ```javascript
  var i = 1;
  var j = ++i; // pre-increment: j equals 2; i equals 2
  var k = i++; // post-increment: k equals 2; i equals 3
  ```
  ### Operations on Numbers & Strings
  
  In JavaScript, numbers and strings will occasionally behave in ways you might not expect.

  **Addition vs. concatenation**

  ```javascript
  var foo = 1;
  var bar = '2';

  console.log(foo + bar);  // 12. uh oh
  ```

  **Forcing a string to act as a number**

  ```javascript
  var foo = 1;
  var bar = '2';

  // coerce the string to a number
  console.log(foo + Number(bar));
  ```

  The Number constructor, when called as a function (like above) will have
  the effect of casting its argument into a number. You could also use the
  unary plus operator, which does the same thing:

  **Forcing a string to act as a number (using the [unary-plus operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Unary_plus_()))**

  ```javascript
  console.log(foo + +bar);
  ```

## Logical Operators

  Operators are the same in JS as in other programming languages.

  - **logical OR (||) operator**
      * returns value of first truthy operand it encounters
      * if both operands are falsely, returns value of last operand
      
      ```javascript
      var bar = 0;
      var foo = 1;
      var moo = 2;

      bar || foo; // returns 1
      foo || moo; // returns 1
      ```


  - **logical AND (&&) operator**
     * returns first falsely operand it encounters
     * if both operands are truthy, returns value of last operand
     
     ```javascript
     var bar = 0;
     var foo = 1;
     var moo = 2;

     bar && foo; // returns 0
     foo && moo; // returns 2
     ```

## Comparison Operators

Recall that Comparison operators allow you to test the relationship (equality and identity) between objects. By now you know about the following comparison operators:  

| Operator      | Description   | Example |
| ------------- | ------------- |-------- |
| ==            | checks if calue of two operands are equal or not. If yes then returns true  | (10 == 20) is not true; hence returns false |
| !=            |checks if the value of 2 operands are equal. If values are not equal, returns true| (a != b) is true; hence returns true |
| >             | checks if value of left operand is greater than value of right operand. If left operand is greater than right operand, returns true  | (10 > 20) is not true hence returns false         |  
| <  | checks if value of left operand is less than value of right operand. If left operand is less than righ operand, returns true | (10 < 20) is true        |  
| >=   | checks if value of left operand is greater than or equal to value of right operand. If it is, returns true; else returns false  | (10 >= 20 ) is false         |  
| <=  | checks if value of left operand is less than or equal to right operand. If left operamd is less than or equal to righ operand, returns true; else returns false  |  (10 <= 20) is true       |  


In JavaScript, in addition to the regular comparison operators, we have **strict comparison operators**; which are strict equals  (`===`) and strict not-equals (`!==`).

**Loose comparison operators** ( `==` and `!=` ) are quite liberal - they convert type to match one another. This means that values may be considered equal even if they are different types, since the operator will force coercion of one or both operators into a single type (usually a number) before performing a comparison.

```javascript
var bar = 0;
var foo = 1;

var yoo = "1";
var zee = 2;

// does 1 equal 0?
foo == bar; // returns false
foo != bar; // returns true

// does  1 equal "1"?
foo == yoo; // returns true. Why? Because == opertor forces coercion of string 1 ("1") into number 1 (1)
```

On the other hand, **strict comparison operators** (`===` and `!==` ) compare both type and value equality.

```javascript
var bar = 0;
var foo = 1;

var yoo = '1';
var zee = 2;

foo === yoo; // returns false because though 0 and 1 are of the same type (both are numbers = identities match) they are not equal

foo === parseInt(yoo); returns true because `parseInt` converts string 1 to integer(number) 1
```

### Undefined, Null, and NaN

Undefined represents the absence of a primitve value, and Null represents the absence of an object.

NaN represents an error from the improper use of a math operator.  NaN is the only thing in JS that is not equal to itself. To check for NaN use the `isNaN()` function.

```javascript
1 - 'three' // returns NaN
NaN === NaN // returns false
isNaN(NaN) // returns true
```

## Flow Control  && Conditional Logic

Flow Control allows the excution of code only under certain conditions.

  1. ** IF Statements**
    * evaluates to either true or false:  
    ```javascript
      if ( conditionToTestIsTrue) {
        // code to be executed here
      }
    ```
    
    * You will often see an `If` statement used in combination with an  `else` clause. An `else` clause is a fallback to an `if` statement and will only get executed if the previous `if` statement is false.  
    ```javascript
      if (conditionToTestIsTrue) {
        // codition is false hence code is not executed
      } else {
        // code to be executed because previous `if` condition is false
      }
    ```  
    
    * `if` statements can also be combined with an `else if` clause. This is like an else statement, but with its own condition. It will only run if its condition is true, and the previous statement's condition was false.
    ```javascript
      if (conditionToTestIsTrue){
          // codition is false hence code is not executed
      } else if (thisCondionIsTrue) {
        // excute this code if previous `if` statement is false
      } else {
        // excute this code if the 2 conditions above are false
      }
    ```

  2. ** Ternary Operator**
    - used as a shortcut for the `if-else` statement
    - tests a condition; if the condition is true, it returns a certain value, otherwise it returns a different value
    ```javascript
      conditionToTest ? valueToBeReturnedIfTrue : valueToBeReturnedIfFalse
    ```

  3. ** SWITCH Statements**
    - acts like a big if / else if / else chain
    - the switch expression is evaluated once
    - the value of the expression is compared with the values of each case
    - if there is a match, the associated block of code is executed
    ```javascript
      switch (expression) {
        case n:
            // code to be executed if case n is true
            break; // break out of switch statement once code executed
        case m:
            // code to be executed if case m is true
            break; // break out of switch statement once code executed
        default:  // all other cases
            // code to be executed if case n and case m false
      }
    ```

## Loops

Loops are used to execute the same block of code a specified number of times.

1. **`for` loop**: made up of four statements and has the following structure:
      ```javascript
        for ( [initialization]; [condition]; [iteration] ) {
        [loopBody]
        }
      ```
  - initialization
    An expression (including assignment expressions) or variable declaration. Typically used to initialize a counter variable. This expression may optionally declare new variables with the var keyword

  - condition
    An expression evaluated before each loop iteration. If this expression evaluates to true, statement is executed

  - iteration
    A statement executed at the end of each iteration. Typically, this will involve incrementing or decrementing a counter and thus bringing the loop ever closer to its end

  - loopBody
    code which runs on every iteration as long as condition evaluates to true

    > Use `for` loop when you know how many times you want the loop to run

    Example:
    The code belong will print the string "Hello World!" 99 times
    ```javascript
      // i is set to equal to 0; as long as i is less than 100 execute the code in the loopBody - which is print "Hello World"; increment i each time code in loopBody is executed
      for (var i = 0, i < 100, i++) {
        console.log( "Hello World! for the " + i + " time" );
      }
    ```

2. **`while` loop**: similar to an if statement, except that its body will keep executing until the condition evaluates to false. Has the following structure:
  ```javascript
    while ([condition]) {
      [loopBody]
    }
  ```
  - condition
    An expression evaluated before each pass through the loop (each pass is either an increment or a decrement). If this condition evaluates to true, statement is executed

    > Use `while` loop when you don't know how many times your loop needs to run - that is your condition is dependent on some a dynamic function/return value

    Example:
    ```javascript
      // i is set to Zero
      var i = 0;

      // while i is less than Zero
      while ( i < 100) {
        console.log( "Hello World! for the " + i + " time");

        //  instruction for each pass through loop
        ++i;
      }
    ```

3. **`do-while` loop**: almost exactly the same as the while loop, except for the fact that the loop’s body is executed at least once before the condition is tested. Has the following structure:
  ```javascript
    do {
      [loopBody];
    } while ([condition]);
  ```
    > rarely see `do-while` used since very few situations require a loop that blindly executes at least once.

####Resources:

* [String Constructor](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)
* [Number Constructor](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)
* [Arithmetic Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators)
* [Undefined, Null, NaN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference)
* [Truth and Equality in JavaScript](https://javascriptweblog.wordpress.com/2011/02/07/truth-equality-and-javascript/)
* [For Loop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)
* [While Loop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/while)
* [Do-While Loop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/do...while)
