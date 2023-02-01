# js-advanced-concepts-ZTM
Personal journal (and codes) of my learning journey through ZTM js advanced concepts

## Section 3

### Execution Context

Everything we run is a part of a execution context (a function that is running)

Global EC give us global object, this, ...

this => in a browser, this === window (global object, inside node is global instead of window)

The global EC (and probably all other ECs) has 2 phases, creation and execution (where the code runs).
### Lexical Environment

A place where we write the code, the same space that execution context creates. The EC tells us witch LE is running (scope)

### Hoisting