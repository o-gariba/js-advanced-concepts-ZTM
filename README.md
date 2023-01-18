# js-advanced-concepts-ZTM
Personal journal (and codes) of my learning journey through ZTM js advanced concepts

**Must bring local annotation from personal notebook to here**
## JS Engine - Call Stack and Memory heap

memory heap is where memory allocation happen. Is a free store to allocate arbitrary data. Variables point for each memory space

call stack knows what should be run at every time. A stack that pile functions in order to be ran

Simple variables are stored inside call stack, complex data structure is stored inside memory heap

## Garbage collection

js is a GC language, when we finish a function js will clean the memory we will no longer use.

In low level languages we can control garbage collector. Not in js