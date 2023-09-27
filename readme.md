# JavaScript Notes

## Preprocessors
A JavaScript preprocessor is a tool that transforms your JavaScript code into a compatible and optimized version for the browser. It allows you to write code in a different language, such as TypeScript, CoffeeScript, or Babel, and then compile it into plain JavaScript. With a JavaScript preprocessor, you can use features that are not supported by all browsers, such as classes, modules, arrow functions, and more. These features can help you write cleaner, safer, and more expressive code.
gulp - grunt - node scripts - babel

## "this" keyword
'use strict'
this refers to the context where the function is being executed.
this ==== current execution context
this ==== current execution context
in non-strict mode, this is always a referece to an object. In strict mode, it can be any value.

> Description 

The value of this depends on in which context it appears: function, class, or global

this === context execution 

### Function context
Inside a function, the value of this depends on how the function is called. Think about this as a hidden parameter of a funcion — just like the parameters declared in the function definition, this is a binding that the language creates for you when the function boby is evaluated.
```js
function getThis() {
    return this;
}

const obj1 = { name: 'obj1'}
const obj2 = { name: 'obj2'}

obj1.getThis = getThis;
obj2.getThis = getThis;

console.log(obj1.getThis()) // { name: 'obj1', getThis: [Function: getThis]}
console.log(obj2.getThis()) // { name: 'obj2', getThis: [Function: getThis]}

```
## Hosting
JavaScript Hoisting refers to the process whereby the interpreter appears to move the declaration of functions, variables, classes, or imports to the top of their scope, prior to execution of the code.
```js
console.log(a)
var a = 2

// this happen
var a = undefined // just for initialization 
console.log(a) // -> undefined
a = 2
```

## Scope
global Scope
```js
var a = 'a'
```
function scope
```js
function fn () {
    const a = 'a'  
    console.log(a) // -> a
}
console.log(a) // -> Error execution
```
block scope
```js
function getScope() {
    if (true) {
        const a = 'a'
        var b = 'b'
        console.log(a);
    }

    console.log(a) // -> error
    console.log(b) // -> b -> function scope
}
```

