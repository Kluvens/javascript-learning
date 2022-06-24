# javascript-learning

Javascript uses ```console.log()``` to print. e.g.
``` javascript
const years = 5;
console.log(years);
```

## Comments
In javascript, single line comments start with ```//```. While multi-line comments start with ```/*``` and end with ```/*```.

## Variables
Variables are containers for storing data.

Javascript variables are declared via ```var```, ```let``` and ```const```. Where ```var``` can work for older version of JavaScript, ```const``` works from 2015 and the value of the variable cannot change, ```let``` works from 2015 and the value of the variable cannot change.

All JavaScript **variables** must be identified with **unique names**. These unique names are called **identifiers**.

JavaScript can add strings and numbers: ```let x = "5" + 2 + 3;``` will get ```523```.

Describing nothing(```undefined``` and ```null`` are equal in value but differenet in type):
``` javascript
const notexist = undefined
const existbutnothing = null
```

## Operators
Javascript operators are very similar to other programming languages.
Things to notice:
- ```===``` - equal value and equal type
- ```!===``` - not equal value or not equal type
- ```?``` - ternary operator
- ```&&``` - logical and
- ```||``` - logical or
- ```!``` - logical not
- ```typeof``` - returns the type of a variable
- ```instanceof``` - returns true if an object is an instance of an object type

## Functions
A JavaScript function is a block of code designed to perform a particular task. e.g.
``` javascript
function myFunction(p1, p2) {
  if (p1 > p2) {
    return p2;
  } else {
    return p1;
  }
}
```

Variables declared within a JavaScript function, become LOCAL to the function.
``` javascript
function myFunction() {
  let carName = "Volvo";
  // code here CAN use carName
}
```

## If .. else statement
```
if (number > 10) {
  console.log("Bigger than 10");
} else if (number < 2) {
  console.log("number is less than 2");
} else {
  console.log("number is between 2 and 9");
}
```

## Switch statement
```
switch (new Date().getDay()) {
  case 0:
    day = "Sunday";
    break;
  case 1:
    day = "Monday";
    break;
  case 2:
     day = "Tuesday";
    break;
  case 3:
    day = "Wednesday";
    break;
  case 4:
    day = "Thursday";
    break;
  case 5:
    day = "Friday";
    break;
  case 6:
    day = "Saturday";
  default:
    text = "Not a day in a week";
}
```

## While loop
```
let i = 0;
while (i < 0) {
  console.log("Hello there");
  i += 1;
}
```

## For loop
```
for (let i = 0; i < 5; i++) {
  console.log("Hello there" + i);
}
```

## For in loop
The JavaScript ```for in``` statement loops through the properties(keys) of an Object. If loop through an array, it refers to the index.
```
const person = {fname:"John", lname:"Doe", age:25};

let text = "";
for (let x in person) {
  text += person[x];
}
```

## For of loop
The JavaScript ```for of``` statement loops through the values of an iterable object.
```
const cars = ["BMW", "Volvo", "Mini"];

let text = "";
for (let x of cars) {
  text += x;
}
```

## Objects
Objects are variables too. But objects can contain many values. The values are written as **name:value** pairs (name and value separated by a colon). Javascript objects cannot be compared.
```
const car = {type:"Fiat", model:"500", color:"white"};
```

Accessing object properties in two ways: ```objectName.propertyName``` or ```objectName["propertyName"]```

Objects can also have methods. Methods are actions that can be performed on objects. Methods are stored in properties as function definitions. In javascript, the ```this``` keyword refers to an object.
```
const person = {
  firstName: "John",
  lastName : "Doe",
  id       : 5566,
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
};
```

Accessing an object method via ```objectName.methodName()```

## Collections
### Sequential collections
in sequential collections values are referenced by their integer index(key) that represents their location in an order.

In javascript, sequential collections are represented by an array. And arrays are used for both C-style arrays and C-style linked lists.

### Arrays
Arrays are mutable ordered structures of the same type.

``` javascript
const names = ['hayden', 'jake', 'justin']
// this can also be done
// const names = new Array('hayden', 'jake', 'justin');

// get the array
console.log(`1 ${names}`);

// get an item of an array
console.log(`2 ${names[0]}`);

// reassign value to the array
names[1] = "Jake"

// append to the array
names.push('Rani');

// check if an item is in the array
console.log(names.includes('hayden'));

// returns the number of elements
console.log(names.length);

// sort the array
console.log(names.sort());

// join() method also joins all array elements into a string
console.log(names.join(" * "));

// remove the last element from an array
names.pop();

// shift() method removes the first array element and shifts all other elements to a lower index.
names.shift();

// unshift() method adds a new element to the first place of an array, and unshifts order elements
names.unshift('nick');

// array elements can be deleted using the operator delete
// but using delete leaves undefined holes in the array
delete names[0];

// concat() method creates a new array by merging existing arrays
const myNames = names.concat(['more', 'names']);

// the splice() method adds new items to an array
names.splice(2, 0, "OK", "Kiwi");
// the first parameter defines the position where new elements should be added
// the second parameter defines how many elements should be removed
// the rest of the parameters ("ok", "kiwi") define the new elements to be added
// splice() can be used to remove elements
names.splice(0, 1);

// slice() method slices out a piece of an array into a new array
const newNames = names.slice(1, 3);

// javascript automatically converts an array to a comma separated string when a primitive value is expected.
console.log(names.toString());

// reverse the string
names.reverse();

// by default, sort() sorts values as strings
const points = [40, 100, 1, 5, 25, 10];
points.sort(function(a, b){return a - b});
// this is the right way to sort numbers

// the right way to sort numbers by descending order
const points = [40, 100, 1, 5, 25, 10];
points.sort(function(a, b){return b - a});

// get the maximum of an array
Math.max.apply(null, points);

// get the minimum of an array
Math.min.apply(null, points);

// The foreach() method calls a function once for each array element
const numbers = [45, 4, 9, 16, 25];
let txt = "";
numbers.forEach(myFunction);

function myFunction(value, index, array) {
  console.log(value, index, array);
}

// The map() method creates a new array by performing a function on each array element
const numbers1 = [45, 4, 9, 16, 25];
const numbers2 = numbers1.map(myFunction);

function myFunction(value, index, array) {
  return value * 2;
}

// The filter() method creates a new array with array elements taht passes a test.
const numbers = [45, 4, 9, 16, 25];
const over18 = numbers.filter(myFunction);

function myFunction(value, index, array) {
  return value > 18;
}

// reduce() method runs a function on each array element to produce a single value.
const numbers = [45, 4, 9, 16, 25];
let sum = numbers.reduce(myFunction);

function myFunction(total, value, index, array) {
  console.log(total, value, index)
  return total + value;
}

// The every() method check if all array values pass a test
const numbers = [45, 4, 9, 16, 25];
let allOver18 = numbers.every(myFunction);

function myFunction(value, index, array) {
  return value > 18;
}

// The some() method checks if some array values pass a test
const numbers = [45, 4, 9, 16, 25];
let someOver18 = numbers.some(myFunction);

function myFunction(value, index, array) {
  return value > 18;
}

// The indexOf() method searches an array for an element value and returns its position
const fruits = ["Apple", "Orange", "Apple", "Mango"];
let position = fruits.indexOf("Apple") + 1;

// lastIndexOf() returns the position of the last occurence of the specified element
const fruits = ["Apple", "Orange", "Apple", "Mango"];
let position = fruits.lastIndexOf("Apple") + 1;

// find() method returns the value of the first array element that passes a test function
const numbers = [4, 9, 16, 25, 29];
let first = numbers.find(myFunction);

function myFunction(value, index, array) {
  return value > 18;
}

// findindex() method returns the index of the first array element that passes a test function
const numbers = [4, 9, 16, 25, 29];
let first = numbers.findIndex(myFunction);

function myFunction(value, index, array) {
  return value > 18;
}
```
Sort object arrays:
```
const cars = [
  {type:"Volvo", year:2016},
  {type:"Saab", year:2001},
  {type:"BMW", year:2010}
];

cars.sort(function(a, b){return a.year - b.year});
```

## Classes
use the keyword ```class``` to create a class. And always add a method named ```constructor()```
``` javascript
class Car {
  constructor(name, year) {
    this.name = name;
    this.year = year;
  }
}
```

using a class:
``` javascript
let myCar1 = new Car("Ford", 2014);
let myCar2 = new Car("Audi", 2019);
```

class methods are created with the same syntax as object methods. methods are created after constructor.
``` javascript
class Car {
  constructor(name, year) {
    this.name = name;
    this.year = year;
  }
  age() {
    let date = new Date();
    return date.getFullYear() - this.year;
  }
}
```

## Modules
JavaScript modules allow you to break up your code into separate files.
This makes it easier to maintain the code-base
JavaScript modules rely on the ```import``` and ```export``` statements

### Exports
We can label any declaration as exported by placing ```export``` before it.
``` javascript
// export an array
export let months = ['Jan', 'Feb', 'Mar','Apr', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'];

// export a constant
export const MODULES_BECAME_STANDARD_YEAR = 2015;

// export a class
export class User {
  constructor(name) {
    this.name = name;
  }
}
```

We can also export apart from declarations
``` javascript
function sayHi(user) {
  alert(`Hello, ${user}!`);
}

function sayBye(user) {
  alert(`Bye, ${user}!`);
}

export {sayHi, sayBye}; // a list of exported variables
```

### Import
``` javascript
import {sayHi, sayBye} from './say.js';

sayHi('John'); // Hello, John!
sayBye('John'); // Bye, John!
```
But if there are many things to import, we can import everything as an object.
``` javascript
import * as say from './say.js';

say.sayHi('John');
say.sayBye('John');
```

## Types
### Types and typeof
In javascript, there are 5 different data types that can contain values:
- string
- number
- boolean
- object
- function

There are 6 types of objects:
- Object
- Date
- Array
- String
- Number
- Boolean

And 2 data types that cannot contain values:
- null
- undefined

We can use ```typeof``` operator to find the data type of a javascript variable.
``` javascript
typeof "John"                 // Returns "string"
typeof 3.14                   // Returns "number"
typeof NaN                    // Returns "number"
typeof false                  // Returns "boolean"
typeof [1,2,3,4]              // Returns "object"
typeof {name:'John', age:34}  // Returns "object"
typeof new Date()             // Returns "object"
typeof function () {}         // Returns "function"
typeof myCar                  // Returns "undefined" *
typeof null                   // Returns "object"
```

### type conversion
Number methods:
- Number() - returns a number, converted from its argument
- parseFloat() - parses a string and returns a floating point number
- parseInt() - parses a string and returns an integer
- ```+``` unary + operator can be used to convert a variable to a number

``` javascript
Number("3.14")    // returns 3.14
Number(" ")       // returns 0
Number("")        // returns 0
Number("99 88")   // returns NaN

let y = "5";      // y is a string
let x = + y;      // x is a number
```

Converting numbers to strings with the global method ```string()```:
``` javascript
String(x)         // returns a string from a number variable x
String(123)       // returns a string from a number literal 123
String(100 + 23)  // returns a string from a number from an expression
```

The Number method ```toString()``` does the same:
``` javascript
x.toString()
(123).toString()
(100 + 23).toString()
```

More string methods:
- toExponential() - returns a string, with a number rounded and written using exponential notation
- toFixed() - returns a string, with a number rounded and written with a specified number of decimals
- toPrecision() - returns a string, with a number written with a specified length

Converting dates to strings:
the global method ```String()``` can convert dates to strings.
``` javascript
String(Date())  // returns "Thu Jul 17 2014 15:38:19 GMT+0200 (W. Europe Daylight Time)"
```

More Date methods:
- getDate() - get the day as a number
- getDay() - get the weekday a number
- getFullYear() - get the four digit year
- getHours() - get the hour
- getMilliseconds() - get the milliseconds
- getMinutes() - get the minutes
- getMonth() - get the month
- getSeconds() - get the seconds
- getTime() - get the time (milliseconds since January 1, 1970)

Converting booleans to numbers:
``` javascript
Number(false)     // returns 0
Number(true)      // returns 1
```

Converting booleans to strings:
``` javascript
String(false)      // returns "false"
String(true)       // returns "true"
```

## Arrow function
``` javascript
// before
hello = function() {
  return "Hello World!";
}

// with arrow function
hello = () => {
  return "Hello World!";
}

// arrow function with parameters
hello = (val) => "Hello " + val;

// arrow function without parentheses(when having only one parameter)
hello = val => "Hello " + val;

## Spread syntax
The spread syntax is commonly used to make shallow copies of JS objects. Using this operator makes the code concise and enhances its readability.

The spread syntax is denoted by three dots.
``` javascript
let array = [...value]
```

Examples:
1. Copying an array
``` javascript
let array1 = ['h', 'e', 'l', 'l', 'o'];
let array2 = [...array1];
console.log(array2);
['h', 'e', 'l', 'l', 'o'] // output
```
2. Inserting the elements of one array into another
``` javascript
let desserts = ['cake', 'cookie', 'donut'];
let desserts1 = ['icecream', 'flan', 'frozen yoghurt', ...desserts];
console.log(desserts);
//Appending baked_desserts after flan
let desserts2 = ['icecream', 'flan', ...desserts, 'frozen yoghurt'];
console.log(desserts2);
// output
[ 'cake', 'cookie', 'donut' ]
[ 'icecream', 'flan', 'cake', 'cookie', 'donut', 'frozen yoghurt' ]
```
3. Array to arguments
``` javascript
function multiply(number1, number2, number3) {
  console.log(number1 * number2 * number3);
}
let numbers = [1,2,3];
multiply(...numbers);
```
