# javascript-learning

Javascript uses ```console.log()``` to print. e.g.
```
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

Describing nothing:
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
```
function myFunction(p1, p2) {
  if (p1 > p2) {
    return p2;
  } else {
    return p1;
  }
}
```

Variables declared within a JavaScript function, become LOCAL to the function.
```
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
```
