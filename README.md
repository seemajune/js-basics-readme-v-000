# Intro to JavaScript

JavaScript is the de facto language of the internet. It's a tool that, once mastered, will allow you to interact with your users via your app in fun and interesting ways. It is a dynamically typed, prototypical, functional programming language. What that exactly means will become more apparent in lessons and through exposure to the language. But here are the basics.

## Objectives
+ Print JavaScript to the console
+ Explain proper use of semicolons
+ Explain truthy and falsely values

## Overview

* Syntax Basics
  * Variable Declaration
  * Semicolons
  * Whitespace
* Printing to the Console
* Truthy and Falsely Values



## Syntax Basics

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

From [Codecademy's blog on semicolons](https://www.codecademy.com/blog/78):

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

Will the code execute and work without the semicolon? Yes. Is the semicolon best practice? Yes. Should you use semicolons? Also yes. 

Well, this code is all fine and dandy but how do you run it? The best, possibly most powerful thing about JavaScript is that all modern browsers know how to run it. All you need to do is make sure you're reading this on either Chrome or Firefox (trust us, the developer tools of these browsers are way better than on Safari). Then open up your browser's console. That's right, just like your computer knows about running a Ruby sandbox when you type `irb`, your browser runs a JavaScript sandbox when you open up the console.

To open up your browser's console from Chrome, type `command` + `option` + `J`. From Firefox, type `command` + `option` + `K`. (If you love writing directly into your terminal, go ahead and install [Node](http://blog.teamtreehouse.com/install-node-js-npm-mac). Then type `node` in your terminal and you'll be in a JavaScript sandbox.)

From your console (or Node terminal), simply type the code above into the prompt and hit `return`. There, you've run your first JavaScript code!

Open up Chrome and on any tab (even a blank one) right click and select `Inspect` from the dropdown. From there, select the `console` tab:

![console](https://s3.amazonaws.com/learn-verified/console.png)

The white space below is your console, a sandbox where you can enter and execte any JavaScript code you want.

![Executing JavaScript in Console](https://s3.amazonaws.com/learn-verified/exectuing-js-in-console.png)


<p data-visibility='hidden'>View <a href='https://learn.co/lessons/js-basics-readme' title='Intro to JavaScript'>Intro to JavaScript</a> on Learn.co and start learning to code for free.</p>

<p data-visibility='hidden'>View <a href='https://learn.co/lessons/js-basics-readme'>Javascript Basics </a> on Learn.co and start learning to code for free.</p>
