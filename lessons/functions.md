## 4 - Functions

### 4.1 - Calling a Function: Call Operator `()`

The values we pass inside the parenthesis in a function call, are called
**arguments**

```js
alert("Hello");
// Read: We call the function alert with the string "Hello" as an argument.
// or: We call alert with the argument "Hello"
// or: We show an alert window with the message "Hello"

user.login();
// Read: We call the login method on user without any arguments
// or: We trigger a login for the user.

parseInt("101", 2);
// Read: We call the function parseInt and pass it the string "101" and the number 2 as arguments
// or: We parse the string "101" as a binary integer

console.log(user);
// Read: We call console log and pass in user as an argument
// or: We log the user to the console
```

### 4.2 - Creating a function

```js
const add = function (a, b) {
  return a + b;
};
// Read We bind add to a new function which has two parameters, called a and b.
// or: We define a new function called add with two parameters a and b
```

#### Parameters and Arguments

**Parameters**: The unbound identifiers specified in a function definition, which are
placeholders to be filled with actual values later when some will call the
function.
**Arguments**: The input values provided by someone who wants to call the function to
be passed into the function.

The parameters will be bound to the arguments inside the function body.

#### Return

Inside a function we can use the `return` keyword to finish the function
execution and return an output value to the caller.

```js
return 5;
// Read: We finish the function by returning the value 5
// or: We return 5 from the function
```

#### Declaration notation

Syntactic sugar for creating a binding for a new function.

```js
function add(a, b) {
  console.log(`Adding ${a} and ${b}`);
  return a + b;
}
// Read as above
```

#### Arrow functions

In ES6 a new shorter syntax for function literals was introduced using the `=>`
symbol

```js
const add = (a, b) => {
  return a + b;
};

// If the function body only contains a single return statement, you can also write:
const add = (a, b) => a + b;
```

#### Functions as Values

Functions can not only be used when creating a new binding, but can appear
wherever any other expression can appear

```js
let log = console.log;

if (noLogging) {
  // Here we are reassigning our global log function to do nothing
  log = () => {
    /* Do nothing */
  };
}
```

Very often functions are passed as arguments to other functions to be called
back later when the function is finished. These functions are called
**callback** functions.

```js
preheatOven(200, () => {
  bakeCake();
});
```
