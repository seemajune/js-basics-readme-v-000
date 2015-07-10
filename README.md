# Intro to JavaScript

JavaScript is the de facto language of the internet.  It's a tool that once mastered will allow you to interact with your users via your app in fun and interesting ways.  It is a dynamically typed, prototypical, functional programming language.  What that exactly means will come more apparent in class and through exposure to the language.  But here are the basics.

## Overview

* Syntax Basics
  * Variable Declaration
  * Whitespace
* Truthy and Falsely Values
* Return Values
* Operators
  * Basic
  * Operations on Numbers & Strings
  * Logical Operators

## Syntax Basics

Welcome to JavaScript! First thing first, let's get the absolute basics down before you do anything else.

#### Variable Declaration

To make a variable called `greeting` and set it equal to the string `"hello world"` in Ruby, we could just write:

```ruby
greeting = "hello world";
```

In JavaScript, to declare a local variable (which is almost always what you want to do), you add the keyword `var` before the variable name, like so:

```javascript
var greeting = 'hello world';
```

#### Whitespace

As with Ruby, JavaScript gives whitespace no meaning outside of quotation marks.

```javascript
var greeting =         "hello world";

greeting == "hello world" // Returns true
```

As in Ruby, tabs enhance readability, but have no special meaning.

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

## Truthy and Falsely Values

We make a lot of assumptions when we write computer programs. In order to make the right assumtions, we need to understand what values in our program evaluate to `truthy` values and which evaluate to `falsely` values.

Values that evaluate to `true`:

```javascript
'all strings';  

'all number strings'; // for example '0', '5', '0.2', '-3.14'  

[]; // an empty array  

{}; // an empty object  

1; // any non-zero number
```

Values that evaluate to 'false':
  
```javascript
0; // the number zero  

'';  // an empty string  

NaN;  

null; 

undefined;
```
  
## Return Values

Unless you use the `return` keyword or call a function that explicitly returns a value, the implicit return value in JavaScript is  `undefined`.

> Undefined represents the absence of a primitive value

Other special return values in JavaScript are `null`

> Null represents the absence of an object

and `NaN`

> NaN represents an error from the improper use of a math operator.

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

console.log(foo + bar);  // 12. uh oh, to read more about this behavior, see Intro to Strings
```
  
### Logical Operators

Operators are the same in JS as in other programming languages.

- The Or (`||`) Operator
  * returns value of first truthy operand it encounters
  * if both operands are falsely, returns value of last operand
    
```javascript
var bar = 0;
var foo = 1;
var moo = 2;

bar || foo; // returns 1
foo || moo; // returns 1
```

- The And (`&&`) Operator
  * returns first falsely operand it encounters
  * if both operands are truthy, returns value of last operand
   
```javascript
var bar = 0;
var foo = 1;
var moo = 2;

bar && foo; // returns 0
foo && moo; // returns 2
```
   
## Resources

* [String Constructor](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)
* [Number Constructor](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)
* [Arithmetic Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators)
* [Undefined, Null, NaN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference)
* [Truth and Equality in JavaScript](https://javascriptweblog.wordpress.com/2011/02/07/truth-equality-and-javascript/)
* [For Loop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)
* [While Loop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/while)
* [Do-While Loop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/do...while)
