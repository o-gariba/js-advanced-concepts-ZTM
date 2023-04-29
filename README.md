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