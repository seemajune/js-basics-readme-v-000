# Intro to JavaScript

JavaScript is the de facto language of the internet. It's a tool that, once mastered, will allow you to interact with your users via your app in fun and interesting ways. It is a dynamically typed, prototypical, functional programming language. What that exactly means will become more apparent in class and through exposure to the language. But here are the basics.

## Overview

* Printing to the Console
* Syntax Basics
  * Variable Declaration
  * Semicolons
  * Whitespace
* Truthy and Falsely Values
* Return Values
* Operators
  * Basic
  * Operations on Numbers & Strings
  * Logical Operators

## Printing to the Console

One of the first methods you probably learned in Ruby was `puts`. JavaScript has an equivalent function called `console.log()`. Let's take the Ruby code below and turn it into JavaScript code:

```ruby
puts "JavaScript is also known as ECMAScript"
```

Well let's change that `puts` into a `console.log`:

```javascript
console.log "JavaScript is also known as ECMAScript"
```
Now we'll wrap the string in parentheses:

```javascript
console.log("JavaScript is also known as ECMAScript")
```

And the icing on the top of this printing-string cake (yum!) is to add a semicolon at the end:

```javascript
console.log("JavaScript is also known as ECMAScript");
```

Will the code execute and work without the semicolon? Yes. Is the semicolon best practice? Yes. Should you use semicolons? Also yes. We'll cover semicolons more in depth later in this readme.

Well, this code is all fine and dandy but how do you run it? The best, possibly most powerful thing about JavaScript is that all modern browsers know how to run it. All you need to do is make sure you're reading this readme on either Chrome or Firefox (trust us, the developer tools of these browsers are way better than on Safari). Then open up your browser's console. That's right, just like your computer knows about running a Ruby sandbox when you type `> irb`, your browser runs a JavaScript sandbox when you open up the console.

To open up your browser's console from Chrome, type `command` + `option` + `J`. From Firefox, type `command` + `option` + `K`. (If you love writing directly into your terminal, go ahead and install [Node](http://blog.teamtreehouse.com/install-node-js-npm-mac). Then type `node` in your terminal and you'll be in a JavaScript sandbox.)

From your console (or Node terminal), simply type the code above into the prompt and hit `return`. There, you've run your first JavaScript code!

## Syntax Basics

Now that you know how to print something, let's move onto some more basics. 

#### Variable Declaration

To make a variable called `greeting` and set it equal to the string `"hello world"` in Ruby, we could just write:

```ruby
greeting = "hello world"
```

In JavaScript, to declare a local variable (which is almost always what you want to do), you add the keyword `var` before the variable name, like so:

```javascript
var greeting = "hello world";
```
Notice that semicolons are used after variable declaration and after printing information to the console.

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

#### Semicolons

Semicolons *must* be used in some cases, *should* be used in others, and other times not at all.

**Necessary**

Semicolons must be used when two statements are on the same line (this is called statement chaining). In Ruby, you probably didn't see too much statement chaining so here's an example:

```ruby
fox = "XOF NWORB KCIUQ EHT"
fox.reverse!; fox.downcase!
# => "the quick brown fox"
```

Notice how that semicolon separates the reversal from the downcasing? JavaScript, like Ruby, also requires semicolons when executing two statements on the same line:

```javascript
var fox = "XOF NWORB KCIUQ EHT";
fox = fox.split("").reverse().join(""); fox = fox.toLowerCase();
// => "the quick brown fox"
```
Of course, there are exceptions. For instance, when we cover loops, you may notice that the `for` loop abides by this rule for the first two statements in its argument but not for the last. Not to worry, its syntax will get covered more fully later in the curriculum.

**Ideal**

From [Codecademy's blog on semicolons](http://www.codecademy.com/blog/78-your-guide-to-semicolons-in-javascript):

>As we saw above, the semicolon in JavaScript is used to separate statements. However, it can be omitted if the statement is followed by a line break (or there’s only one statement in a {block}). A statement is a piece of code that tells the computer to do something. Here are the most common types of statements:

```javascript
var i;                        // variable declaration
i = 5;                        // value assignment
i = i + 1;                    // value assignment
i++;                          // same as above
var x = 9;                    // declaration & assignment
console.log("hi");            // function call
```

> All of these statements can end with a `;` but none of them must. However, it is a good habit to terminate each statement with a `;`.

**Avoid**

Semicolons don't follow ending curly brackets. If you see this `};` in your code, you know something's up. For instance, this if statement has no ending semicolon:

```javascript
var lunchtime = true;

if (lunchtime) {
  console.log("Go get lunch!");
}
```

Also avoid putting semicolons between an ending parenthesis and a beginning curly bracket. In other words, you shouldn't write `) ; {`.

**Hints**

Should you get stuck with your semicolon usage (and don't worry, even professional JavaScript developers occasionally forget what goes where), paste your code into a JSLinter, such as [JSLint](http://www.jslint.com/) or even [JSFiddle](http://jsfiddle.net/). If you click `Lint`, you'll see a line-by-line evaluation of your semicolon usage and other syntax mistakes.

## Truthy and Falsely Values

We make a lot of assumptions when we write computer programs. In order to make the right assumptions, we need to understand what values in our program evaluate to `truthy` values and which evaluate to `falsely` values.

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

* [Codecademy - Guide to Semicolons in JavaScript](https://www.codecademy.com/blog/1707)
* [MDN - Return](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/return)
* [JavaScript We Blog - Truth and Equality in JavaScript](https://javascriptweblog.wordpress.com/2011/02/07/truth-equality-and-javascript/)

<a href='https://learn.co/lessons/js-basics-readme' data-visibility='hidden'>View this lesson on Learn.co</a>
