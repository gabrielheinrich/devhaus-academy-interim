## 1 - Bindings
Declare variables, not war.

[Exercises](https://github.com/valeriakori/variables-exercises)

Variables are reusable chunks of data. They can be accessed by their identifier. The identifier should have a descriptive name. We can picture this like a box that we label and put something (value) in it.

```js
// Creating a variable is called "declaring"
let degreeInCelsius = 20;
// Read: We create a new binding between the identifier degreeInCelsius 
// and the number 20.
// or: Let degreeInCelsius be 20
// or: We declare a new variable called degreeCelsius
// or: We bind degreeInCelsius to the value 20
// or: We define degreeInCelsius as 20

degreeCelsius = 25;
// Read: We reassign the variable degreeCelsius 
// the new value 25

const degreeInFarenheit = 20;
// Read: We create a new constant binding between ...
```

---

### Old style bindings

Before the ES6 Standard introduced `let` and `const` to the language, the only way to create bindings was by using the keyword `var`. 
This older way of creating bindings has some weaknesses and is rarely used in modern code, but is still supported for backwards compatibility.

```js
// Old School JavaScript
var degreeInCelsius = 20;

// New JavaScript
let degreeInCelsius = 20;
```

### const

Variables declared with const are constants. They cannot be reassigned, i.e. give a new value. Use them for data that you know will not be changed.

```js
const myName = 'Valeria'

// at some point later in the code I decide to do this
myName = 'Anna'
// Uncaught TypeError: invalid assignment to const 'myName'

const myName = 'Anna'
// Uncaught SyntaxError: redeclaration of const myName
```

### let

Variables declared with let can be reassigned, i.e. give a new value. They cannot be redeclared. Use them for data that might change. We can picture this as removing the previous value from the labeled box, throwing it out and putting a new value in.

```js
let myName = 'Valeria'

// at some point later in the code I decide to do this
myName = 'Anna'
// This is ok

let myName = 'Anna Valeria'
// Uncaught SyntaxError: redeclaration of let myName
```
---

### Rules for identifiers in Javascript

- Constructed from `A-Z`, `a-z`, `0-9`, `_` and `$`
- But may not start with a digit, i.e. `2ndName` is not a valid identifier
- Can not be a keyword, like `const let var function return break continue true false null undefined ...`
- Use camelCase by default
- Sometimes ALL_UPPERCASE is used for constants and PascalCase for constructors
  (functions which construct new objects)

---

### Typing variables

To make our variables real TypeScript variables we need to assign a type to the variable when we declare it.

```js
// Boolean
let isSunny: boolean = true;

// Number
const bitsInAByte: number  = 8;

// String
const zoomRoomId: string = "8611564454";

// Arrays
let fruits: string[] = ['apples', 'oranges', 'tomatoes']

// Arrays alternative
let fruits: Array<string> = ['apples', 'oranges', 'tomatoes']

```

---

### Escaping Strings

If we use "" (double quotes) or '' (single quotes) to wrap our strings we have trouble adding formatting in the form of line breaks tabs or even having quotes in our string. We can achieve that using the \ (backslash) character to **escape** characters.

**Using Quotes**
```js
console.log("The man whispered, \"please speak to me.\"")
```
> **Logs:** The man whispered, "please speak to me."

**Line Breaks** 
```js
console.log("Programming Haiku:\nwhat is with this code?\noh my, looks like I wrote it\nwhat was I thinking?")
```
> **Logs:** 

Programming Haiku:

what is with this code?

oh my, looks like I wrote it

what was I thinking?

**Overview**

|Code|Character|
| ------ | -------:|
|\\ |	\ (backslash) |
|\" |	'' (double quote) |
|\' |	' (single quote) |
|\n |	newline |
|\t |	tab |

---

### Operators

We don't have to use a literal value to define the value of a variable. 

#### Assigning a variable to another variable

```js
let message = "Hello"

let greeting = "Hey"

message = greeting

// both output "Hey"
console.log(message)
console.log(greeting)
```

#### Concatenate Strings

We can add multiple strings together by **concatenating** them together using the **+** operator.

```js
let message = "Hello"

let myName = "Mike"

let greeting = message + " " + myName + "!"

// outputs "Hello Mike!"
console.log(greeting)
```

A quirk of JavaScript is that concatenating strings and numbers results in a string.

```js
let amountOfApples = 5

let myName = "Ferdinand"

let sentence = myName + " has " + amountOfApples + "apples."

// outputs "Ferdinand has 5 apples."
console.log(sentence)
```

A modern way of bunching strings into a cohesive text is called **Template Literals** using the `` (backticks) character. We wrap the variables in {} (curly brakets) and append a $ (dollar sign)

```js
let amountOfApples = 5

let myName = "Ferdinand"

let sentence = `${myName} has ${amountOfApples} apples.`

// outputs "Ferdinand has 5 apples."
console.log(sentence)
```

#### Arithmetic Operators

```js
1 + 1; // => 2
// Read: 1 plus 1

8 - 1; // => 7
// Read: 8 minus 1

10 * 2; // => 20
// Read: 10 times 2

10 / 3; // => 3.3333333333333335
// Read: Divide 10 by 3 (floating-point!)

10 % 3; // => 1
// Read: 10 modulo 3 (Remainder after integer division)

2 ** 10; // => 1024
// Read: 2 to the power of 10
```
#### Reassignment

```js
x = 24;
// Read: We assign the value 24 to x.
// or: We set x to 24.
```

##### Compound reassignment

```js
x += 2;
// Read: We add 2 to x;
// Syntactic sugar for x = x + 2;

// For most operators there exists a compound version
x -= 2;
x *= 2;
x /= 2;
x %= 2;
x &&= true;
// ...
```

#### Lookup Operator

```js
// Array
const fruits = ["apple", "banana", "orange"];

fruits[0]; // "apple"
// Read: fruits at index 0

fruits[1]; // "banana"
// Read: fruits at index 1

// Object
const player1 = {
  name: "Rick",
  score: 256,
};

player1["score"]; // 256
// Read: We lookup the key score in the object player1
// Or: The score of player1

player1.score; // 256
// Syntactic sugar for player1["score"]

// Deep nesting is very common
document.body.children.length;
// Read: document dot body dot children dot length
// Or: document body children length

// length is a property of arrays
fruits.length; // 3
```

### Process Variables

What if we don't want to hard code a variable but let the user decide an input? When running a programm from the command line the user can provide arguments wich we can use in our code.

`node programm.js Tina`

```js
console.log(process.argv[0])
// logs: /usr/local/bin/node
// absolute pathname of the executable that started the Node.js process

console.log(process.argv[1])
// logs: /home/user/Developer/variables-exercises/index.js
// i.e. location of the executed file

console.log("Hello " + process.argv[2])
// logs: Hello Tina
// the actual parameter provided through the command line
```

The users variables are available starting from the index 2. A good documentation let's the user know how many parameters are expected
