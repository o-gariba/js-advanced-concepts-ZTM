# js-advanced-concepts-ZTM
Personal journal (and codes) of my learning journey through ZTM js advanced concepts

## Interpreter vs Compiler

First, js worked in a interpreted way. Apparently not any more

I always looked to codes in a interpreted view, with an machine eye looking for each line individually and searching or executing smthg.ape
Compiler transform our code to smthg in between computer language, and just then it will be interpreted.

Basically all programming languages is both compiled and interpreted.

Compilers can do optimizations to our code, reducing the interpreter job

## JIT Compiler

Just in time 

runs both compiler and interpreter. It is commonly used in web browsers

## Is js an interpreted language?

Not technically. It depends on what is being implemented.

## JS Engine - Call Stack and Memory heap

memory heap is where memory allocation happen. Is a free store to allocate arbitrary data. Variables point for each memory space

call stack knows what should be run at every time. A stack that pile functions in order to be ran

Simple variables are stored inside call stack, complex data structure is stored inside memory heap

## Garbage collection

js is a GC language, when we finish a function js will clean the memory we will no longer use.

In low level languages we can control garbage collector. Not in js

## JS is a single thread language

It means it has just 1 call stack and 1 memory heap. It deals with 1 function at a time.

But it obviously is not good for a web browser engine.

JS uses WEB API methods to call asynchronous method calls (fetch, setTimeout), so the browser deals with it, not js.

## The callback queue

When js send a function to web api, the call stack still works in order. Once it's empty (all the code was read and no function need to do anything), the callback queue check if Web API send something ready to be run, if so, it pushes this function to the call stack.


---

## Section 3


### Execution Context

Everything we run is a part of a execution context (a function that is running)

Global EC give us global object, this, ...

this => in a browser, this === window (global object, inside node is global instead of window)

The global EC (and probably all other ECs) has 2 phases, creation and execution (where the code runs).
### Lexical Environment

A place where we write the code, the same space that execution context creates. The EC tells us witch LE is running (scope)

### Hoisting

???

### Scope chain

it links and grants us access to variables in global env. 

lexical scope (LS) !== dynamic scope (DS)

LS = available data and variables where the function was defined
DS = where the function is called

Lexical env === `[[scope]]`

if we search a function in our browser we see `[[scope]]` object showing its scope(s)

### Weird cases in JS

if we create a function with a variable not declared, js tries to find its declaration in global env (which will not find) and then create a declaration for us. Which is very weird. 'use strict' will throw an error (which is better).

if we have:

```js
var hey = function oou() {
  return 'hey'
}

doodle()
```

js will throw a referenceError because oou just exists inside `hey` env. This will work:

```js
var hey = function oou() {
  doodle()
  return 'hey'
}

// hey

```

### Function scope vs block scope

scope === what variables we have access to 

js have function scope (with `var` declaration)

block scope comes with ES6, with `let` and `const` declaration

### IIFE

immediately invoked function expression

```js
(function() {
  var a = 1
})();

a // erro a is not defined
```

---

## Section 9

### Memory leak

It happens when a program allocates memory with unused variables. We ran out of memory because we allocate badly.

---

## Section 3

### Context vs Scope

Scope is function based, its about witch variables have access to what.

Context is about objects. Whats the value of `this`?

---

## Section 4

### JS types

```js
typeof null //'object'
```

This is a mistake and has been chosen not to change it because legacy.

functions are objects (arrays are too). We can assure it by doing:

```js
function a() {
  return 5
}
a.hi = 'haha'

console.log(a.hi) //haha
```
