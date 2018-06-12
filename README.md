# Javascript

* HTML Defines structure and content
* CSS Defines Look&Feel

What defines behaviour?

We need something where we can specify rules to describe actions. Like, When this happens (event) I want that to happen (Action)
We need a new specification similar to HTML and CSS to define actions based on events.
Javascript was introduced to cover this gap.

> Javascript is completed full featured programming language that it's mostly used for defining behaviour in webapps but not only for that.

To understand how can we use javascript to define behaviuor in our web apps we need to **learn to code**.

## Fundamentals of programming:

* There is nothing more complicated in Software Engineering that learning for the first time the fundamentals of coding. Then everything is uphill
* Programming is based on some basic logical and mathematical rules, but there absolutely zero mathematical knowledge required to be proficient coding.

Everything start with something we all know: the Sum

```
2 + 2 = 4
```

Generalizing that expression we get:

```
a = 2
b = a + a
```

| variable:    | a     |
| ----------   | -     |
| Expression:  | a + a |
| Result:      | b     |

How do we solve this in javascript:

```
var a = 2
b = a + a
```

Every expression defines an input (a) and produces an output (b) We call this Function and it's the building block of modern programming. We need to understand how to create functions, identify their behaviour and be comfortable using them.

```
function sum(a) {
  var b;
  b = a + a;
  return b;
}
```

The generic format is

```
function <name>(<argument list>) {
  <expressions>
  return <result>;
}
```

1. Argument can be a list: a, b, c
2. Expression is a list of expression expr1; expr2; expr3...
3. `return <result>;` Is also an expression, but it's always the last one in the function.

This define a function, in order to use the function we need to invoke it:

```
var result = sum(2);
```
This expression will be traslated by the browser into:

```
var a = 2
var b;
b = a + a;
return b;
```

We can concatenate functions as building blocks:

```
var result = sum(sum(3));
```

There are a long list of functions already available for us to use provided by the browser. Try calling the function alert passing our variable result and see what happens.

At some point learning to code is mostly learn all the functions that you have available so you know the fastest way to implement something without having to do everything by yourself.

### Types
Every variable has a type. The type is defined by the value assignated to it.
The type defines what we can do with a variable. We can look at the three main types in programming:

* **number**: There are specific types to define different types of numbers, like integers or decimals. But initially we can see all of them as numbers. We can make use the arithmetic operators with numbers:
+, -, /, \*...
* **String**: Are created by wrapping the value between ". It represents a text, The only operation we can do with Strings is + which means concatenate (not sum). Concatenate means Add one String after the other:
``"a" + "b" // = "ab"``
`"a" - "b"` Is not a valid expression
* **Boolean**: It defines a Yes/No (true/false) expression. Is a powerful way specify questions that can be answered by our code E.g:
 * Is 10 bigger than 100 = No/False,
 * Is Red a color = Yes/true.

### Complex expression:
To be able to build usable functions we need complex expressions:

#### Conditionals:
It ask a question based on a variable and depending on the response it executes one expression or another:

> Buy 3 baggetes and if there are eggs buy 12

```
var result;
if (a > 3) {
  result = a + a;
} else {
  result = 0;
}
return result;
```

Generic format:

```
if (<boolean>) {
  <true branch>
} else {
  <false branch>
}
```

Comparators are expressions that only returns true or false
mathematical comparators:
<, <=, >, >=, ==, ===

String comparators:
==, ===

* `"a" == "b" = false`
* `"3" == 3 = true`
* `"3" === 3 = False`

> Don't mistake `=` with `==` or `===` the first one is assignment i.e. Set the value of a variable, the second is a conditional expression that produces a Boolean

#### Loops
Repeat the same expression a specific number of times:

```
var c;
var i;
for(i=0; i < 5; i++) {
  c = c + "Hello ";
}
```

Generic format:

```
for(initialization; exit conditional; modifier) {
  <expressions>
}
```

* Initialization: Here we define an expression that we want to execute always before the Loop
* Exit conditional: When this conditional is true the loop finish. It's very important because if the conditional never returns true the loop will never finish and it will block our page
* Modifier: This expression is executed in every pass of the loop before the exit conditional. It should modify the variable checked in the conditional.

## HTML and Javascript Integration

At this point we should be able to create functions, combine them and create anything that we imagine. But we still don't know how to combine Javascript with HTML.

Everything is based on functions provided by the browser. The browser provides a set of functions grouped in structures called "Objects". This functions allow us to manipulate and query the HTML document.

> Objects are a new type, the same as numbers or strings. If a variable is an object we can apply a specific set of operators. In general none of the arithmetic operators are applicable in Objects. Objects has functions that can be called with the following format: `object.function(arg)`

Going to the basics of HTML, we have our most simple document:

```
<html>
<head>
 <title>Code First Girls</title>
</head>

<body>
  <input type="text" id="textInput" name="value" />
  <input type='button' id="button" name="Ok" value="Ok" />
  <p id="result" />
  <script>
  </script>
</body>

</html>
```

We can read and manipulate the HTML document using the document object provided by the browser:
* `document.querySelector(selector)` Find a particular element in the document, for example, to get the button:
```
var buttonInput = document.querySelector("#button")
```
* To functions to particular events:
```
buttonInput.onclick = function() {
  // code to be executed when the button is clicked
}
```
* To modify the content of a HTML document:
```
inputText.innerHTML = "<b>Hello</b>";
```

## jQuery
Using the functions provided by the browser sometimes gets a bit complicated because there are different functions per browser. In that case we use a library that provide generic functions that works in every browser:

```
<html>
<head>
 <title>Code First Girls</title>
 <script
  src="https://code.jquery.com/jquery-3.3.1.min.js"
  integrity="sha256-FgpCb/KJQlLNfOu91ta32o/NMZxltwRo8QtmkMRdAu8="
  crossorigin="anonymous"></script>
</head>

<body>
  <script>
  </script>
</body>

</html>
```

* https://codepen.io/dianaklee/pen/epBypZ

## Exercises

### Sum functions
* Create a sum function that receives two values and produces the sum of both

### Hello world

```
<html>
<head>
 <title>Code First Girls</title>
</head>

<body>
  <script>
  // Our javascript code goes here
  </script>
</body>
</html>
```

* Create a function that receives a name of a person and returns a greeting personalized for that person, e.g: `Hello Joe`
  * Use the document.write() function to write the greeting in the screen

### Guess game!
* Create a new file with the standard html format
* Using random function `Math.floor(Math.random() * 11);` store a secret number
* Ask the user to guess the number using a HTML input and a button
* Guide the user by telling them if the number they gave is bigger or smaller
* Count the number of tries until the user guess the secret number


### Todo list
* Ask the user for todo items using a HTML input element and a button
* Add every item into a ul, li HTML list
* If the user tick a element in the list mark the element as done
