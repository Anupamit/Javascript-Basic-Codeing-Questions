# Javascript-Basic-Codeing-Questions

## Q.1 Default Parametrs:**
```js
function add(x = 10, y = 20) {
  console.log(x + y);
}
add(10, 30); // 40
```
## Q.2 What is arrow function useing this?
```js
let person={
    name: 'Anupam',
    actions : ['hockey','football','chess'],
    printAction (){
        this.actions.forEach((action)=>{
            let str = this.name + ' like to play ' + action
            console.log(str);
        })
    }
}
    person.printAction()  
```
## Q.3  Destructing Assignment:
```js
const phone = {
  title: "iPhone",
  price: 999,
  description: "The iPhone is a smartphone developed by Apple"
};
console.log(phone.title);
// Destructing Assignment
---------------------------------------------------------------------
const { title, price, description } = {
  title: "iPhone",
  price: 999,
  description: "The iPhone is a smartphone developed by Apple"
};
console.log(title); // iPhone
console.log(price); // 999
console.log(description); // The iPhone is a smartphone developed by Apple
```

## Q.4 Expalin
var allows variables to be hoisted, meaning they can be referenced in code before they are declared. let and const will not allow this, instead throwing an error.
```js
console.log(foo); // undefined
var foo = 'foo';

console.log(baz); // ReferenceError: can't access lexical declaration 'baz' before initialization
let baz = 'baz';

console.log(bar); // ReferenceError: can't access lexical declaration 'bar' before initialization
const bar = 'bar';
```
## Q.5 Explain
Redeclaring a variable with var will not throw an error, but 'let' and 'const' will.
```js
var foo = 'foo';
var foo = 'bar';
console.log(foo); // "bar"

let baz = 'baz';
let baz = 'qux'; // Uncaught SyntaxError: Identifier 'baz' has already been declared
```
## Q.6 Explain
let and const differ in that let allows reassigning the variable's value while const does not.
```js
// This is fine.
let foo = 'foo';
foo = 'bar';

// This causes an exception.
const baz = 'baz';
baz = 'qux';
```
## Q.7 Explain
The var statement declares a function-scoped or globally-scoped variable, optionally initializing it to a value.
```js
var x = 5; // global
function someThing(y) {
  var x = 3; // local
  var z = x + y;
  console.log(z);
}
someThing(4); // 7
console.log(x); // 5
-------------------------
var x = 5; // global
function someThing(y) {
  x = 1; // still global!
  var z = x + y;
  console.log(z);
}
someThing(4) // 5
console.log(x) // 1
```
Undeclared Variables like: x = 1 is accessible in: (Block scope - Function scope - Global scope)

## Q.8 How do you swap variables using Destructuring Assignment?
```js
var x = 10, y = 20;
[x, y] = [y, x];
console.log(x); // 20
console.log(y); // 10
```
## Q.9 Explain
```js
[...'Hello']
Output: ['H', 'e', 'l', 'l', 'o']
```
 The string is an iterable type and the spread operator with in an array maps every character of an iterable to one element. Hence, each character of a string becomes an element within an Array.
