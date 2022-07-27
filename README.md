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

## Q.10 Explain
```js
function mul (x) {
  return function (y) { // anonymous function
    return function (z) { // anonymous function
      return x * y * z;
    };
  };
}
console.log(mul(2)(3)(4)); // output : 24
console.log(mul(4)(3)(4)); // output : 48
```
## Q.11 How can we empty the array above?
```js
var arrayList = ['a', 'b', 'c', 'd', 'e', 'f']; // Created array
var anotherArrayList = arrayList;  // Referenced arrayList by another variable
arrayList = []; // Empty the array
console.log(anotherArrayList); // Output ['a', 'b', 'c', 'd', 'e', 'f']

var arrayList = ['a', 'b', 'c', 'd', 'e', 'f']; // Created array
var anotherArrayList = arrayList;  // Referenced arrayList by another variable
arrayList.length = 0; // Empty the array by setting length to 0
console.log(anotherArrayList); // Output []

var arrayList = ['a', 'b', 'c', 'd', 'e', 'f']; // Created array
var anotherArrayList = arrayList;  // Referenced arrayList by another variable
arrayList.splice(0, arrayList.length); // Empty the array by setting length to 0
console.log(anotherArrayList); // Output []
```
## Q.12 Explain
```js
var output = (function(x) {
  delete x;
  return x;
})(0);

console.log(output);//0
```
The code above will output 0 as output. delete operator is used to delete a property from an object. Here x is not an object, it's a local variable. delete operator doesn't affect local variables.

## Q.13 Explain
```js
var x = 1;
var output = (function() {
  delete x;
  return x;
})();

console.log(output);
```
The code above will output 1 as output. delete operator is used to delete a property from an object. Here x is not an object it's global variable of type number.

## Q.14 Explain
```js
var x = { foo : 1};
var output = (function() {
  delete x.foo;
  return x.foo;
})();

console.log(output);  //Undefine
```
The code above will output undefined as output. delete operator is used to delete a property from an object. Here x is an object which has foo as a property and from a self-invoking function, we are deleting the foo property of object x and after deletion, we are trying to reference deleted property foo which result undefined.

## Q.15 Explain
```js
var Employee = {
  company: 'xyz'
}
var emp1 = Object.create(Employee);
delete emp1.company
console.log(emp1.company); //xyz
```
The code above will output `xyz` as output. Here `emp1` object got company as **prototype** property. delete operator doesn't delete prototype property.
## Q.16 Explain
```js
var trees = ["redwood", "bay", "cedar", "oak", "maple"];
delete trees[3];
console.log(trees) //[ 'redwood', 'bay', 'cedar', <1 empty item>, 'maple' ]
```
this is just way of displaying an uninitialized index of an array in chrome.
## Q.17 Explain
```js
var trees = ["xyz", "xxxx", "test", "ryan", "apple"];
delete trees[3];
console.log(trees.length);
```
## Q.18 Explain
```js
var bar = true;
console.log(bar + 0);   //1+0=1
console.log(bar + "xyz");  //true+xyz=truexyz  (Concatenation)
console.log(bar + true);  //1+1=2
console.log(bar + false);  //1+0=1
```
## Q.19 Explain
```js
var z = 1, y = z = typeof y;
console.log(y); //Undefine
```
## Q.20 Explain
```js
var foo = function bar() { return 12; };
typeof bar();  //Reference Error
```
## Q.21 Explain
```js
var foo = function() {
  console.log("Hi I am inside Foo")
}
foo() //run-time and is called a function expression,

function bar () {
  console.log("Hi I am inside bar");
}
bar() //parse time and is called a function statement.
```
## Q.22 Explain
```js
bar();
(function abc(){console.log('something')})();
function bar(){console.log('bar got called')};
// bar got called
// something
```
Since the function is called first and defined during parse time the JS engine will try to find any possible parse time definitions and start the execution loop which will mean function is called first even if the definition is post another function.
## Q.23 Explain
```js
var counterArray = {
  A : 3,
  B : 4
};
counterArray["C"] = 1;
console.log(Object.keys(counterArray).length); //3
```
## Q.24 Difference between Function, Method and Constructor calls in JavaScript.
```js
function helloWorld(name) {
  return "hello world, " + name;
}
// Normal Function
helloWorld("JS Geeks"); // "hello world JS Geeks"

var obj = {
  helloWorld : function() {
    return "hello world, " + this.name;
  },
  name: 'John Carter'
}
//Method
obj.helloWorld(); // // "hello world John Carter"

var obj2 = {
  helloWorld : obj.helloWorld,
  name: 'John Doe'
}

obj2.helloWorld(); // "hello world John Doe"

function Employee(name, age) {
  this.name = name;
  this.age = age;
}
// Constructor
var emp1 = new Employee('John Doe', 28);
emp1.name; // "John Doe"
emp1.age; // 28
```
## Q.26 Example of IIFE  (Immediately Invoked Function Expression)?
```js
(function() {
  console.log("Hi, I'm IIFE!");
})(); //Hi, I'm IIFE!

var result = (function myIIFEFunc(param1) {
  console.log("Hi, I'm IIFE, " + param1);
  return 1;
})("Yuri");
// Hi, I'm IIFE, Yuri!
// result variable will contain 1
```
 the two () braces, this is how we run the function we just declared.
 ```js
 ~function(){console.log("hi I'm IIFE")}()
!function(){console.log("hi I'm IIFE")}()
+function(){console.log("hi I'm IIFE")}()
-function(){console.log("hi I'm IIFE")}()
(function(){console.log("hi I'm IIFE")}());
var i = function(){console.log("hi I'm IIFE")}();
true && function(){ console.log("hi I'm IIFE") }();
0, function(){ console.log("hi I'm IIFE") }();
new function(){ console.log("hi I'm IIFE") }
new function(){ console.log("hi I'm IIFE") }()
```
 
## Q.27 Fix this and print 01234?
```js
var arr = [10, 32, 65, 2];
for (var i = 0; i < arr.length; i++) {
  setTimeout(function() {
    console.log('The index of this number is: ' + i);
  }, 3000);
}
//For ES6, you can just replace var i with let i that print all iteration correctly
//The index of this number is: 4
//The index of this number is: 4
//The index of this number is: 4
//The index of this number is: 4
var arr = [10, 32, 65, 2];
for (var i = 0; i < arr.length; i++) {
  setTimeout(function(i) {
    return function () {
      console.log('The index of this number is: ' + i)
    };
  }(i), 3000);
}
The index of this number is: 0
The index of this number is: 1
The index of this number is: 2
The index of this number is: 3

var arr = [10, 32, 65, 2];
arr.forEach(function(ele, i) {
  setTimeout(function() {
    console.log('The index of this number is: ' + i);
  }, 3000);
})
```
## Q.28 Write code for merge two JavaScript Object dynamically?
```js
var person = {
	name : 'John',
	age  : 24
}

var address = {
	addressLine1 : 'Some Location x',
	addressLine2 : 'Some Location y',
	city : 'NewYork'
} 
let merge = Object.assign(person, address);
console.log(merge);
```
**Passing values by reference vs by value**
## Q.29 Explain?
```js
var strA = "hi there";
var strB = strA;
strB="bye there!";
console.log (strA)
// The output will be 'hi there' because we're dealing with strings here. Strings are passed by value, that is, copied.
```
## Q.30 Explain?
```js
var objA = {prop1: 42};
var objB = objA; 
objB.prop1 = 90;
console.log(objA) 
//objA and objB point to the same object in memory.
```
## Q.31 Explain?
```js
var objA = {prop1: 42};
var objB = objA;
objB = {};
console.log(objA)
// {prop1: 42}
```
## Q.32 Explain?
```js
var arrA = [0,1,2,3,4,5];
var arrB = arrA;
arrB[0]=42;
console.log(arrA)
//[42,1,2,3,4,5].
```
## Q.33 Explain?
```js
var arrA = [0,1,2,3,4,5];
var arrB = arrA.slice();
arrB[0]=42;
console.log(arrA)
//[0,1,2,3,4,5]
```
The slice function copies all the elements of the array returning the new array
## Q.34 Explain?
```
var arrA = [{prop1: "value of array A!!"},  {someProp: "also value of array A!"}, 3,4,5];
var arrB = arrA;
arrB[0].prop1=42;
console.log(arrA);
// [{prop1: 42}, {someProp: "also value of array A!"}, 3,4,5].
```



























