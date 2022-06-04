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
  return p1 * p2;   // The function returns the product of p1 and p2
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
