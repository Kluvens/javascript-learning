# Typescript
What is typescript: It is just an extension of JavaScript with type checking. So every javascript program also works for typescript.

In typescript, we see errors not in runtime. Typescript helps us to work with entities.

Benefits of typescript:
- static typing
- code completion
- refactoring
- shorthand notations

typescript files are run by ```npx ts-node file.ts```

Javascript types:
- number
- string
- boolean
- null
- undefined
- object

Typescript adds more types:
- any
- unknown
- never
- enum
- tuple

``` typescript
console.log("Hello World");

let age: number = 20;
let course: string = 'typescript';
let is_bool: boolean = true;
let level; // has any type

// array
let a_numbers: number[] = [1, 2, 3];

// tuple
let user: [number, string] = [1, 'Justin'];

// enum
const enum Size {Small = 1, Medium = 2, Large = 3};
let mySize: Size = Size.Medium;
console.log(mySize);

// functions
function calculateTax(income: number): number {
    return income * 1.2;
}

// add question mark to make parameter optional
// || to give possible default value
function newCal(income: number, taxYear?: number): number {
    if ((taxYear || 2022) < 2023) {
        return income * 1.2;
    }
    return income * 1.3;
}

console.log(newCal(1000))

// objects
// if we add readonly before id, then it cannot be changed
let employee: {
    id: number,
    name: string,
    retire: (date: Date) => void
} = {
    id: 1, 
    name: 'Justin',
    retire: (date: Date) => {
        console.log(date);
    }
};
```
