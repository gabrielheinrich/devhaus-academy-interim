# Error Handling

Almost every execution can fail.

Error handling is the art of communicating to the caller of a function, that the function failed to produce the desired outcome.

The simplest form of communication would be to just signify to the caller whether an error occured or not.

A more sophisticated error handling scheme however passes more information about the specific error that happened back to the calling context, e.g. an error code, error message, a stack trace, etc... so the caller can respond to the error in a more informed manner.

#### Return Values

In many older programming languages return values are used to signal errors.
For example a function can return true if the operation succeded or false otherwise.
The caller than has to check the return value

```js
if (thisMightFail()) {
  console.log("Success!!!");
} else {
  console.log("An error occured");
}
```

If a meaningful return value is expected, a function can return null to signal an error.

```js
const result = fetchSomeResult();
if (!result) {
  console.log("It worked!!!");
} else {
  console.log("Failed, result is null");
}
```

#### Benefits

- No extra
- Performent
- Predictable

#### Problems

- Caller has to remember to check the return value
- No consistent interface, (i.e. returning boolean, null, error object, etc...)
- Almost every function call can fail because of nested errors and has to pass them to the caller

### Exceptions to the rescue

Exceptions are an alternative to return values.
They open up a second channel to propagate values to the enclosing execution context.

We say that a function 'throws an exception' when an error is recognized.

```js
const divide = (a, b) => {
  if (b == 0) {
    throw new Error("You are dividing by zero");
  }
  return a / b;
};
```

If the Javascript interpreter reaches a throw statement the expression after the throw keyword is evaluated and 'thrown as an exception'
This means that the execution is interrupted immediately and doesn't follow its normal flow.
Instead the closest **catch** block up the call chain is found and execution resumes there.

Reminder: The call chain is the stack of function calls that are currently active.

#### try catch

A catch block can be created like this

```js
try {
  thisMightFail();
  orThisMightFail();
} catch (error) {
  // error is an arbitrary name you may choose. It will be bound to the caught exception
  console.log("It did fail indeed");
  console.log("And this is the value that was thrown:", error);
}
```

### Benefits of Exceptions

- Return values can be used exclusively for propagating succesfull results
- Uniform interface
- Nesting
  - A function which calls functions that might fail will automatically forward those errors to the caller without any extra code

### finally

Sometimes it's necessary to to some housekeeping work after an operation has finished, no matter whether it completed successfully or not.
This leads to code duplication:

```js
let connection = null;
try {
  connection = openConnection();
  sendSomeData(connection, {
    /***/
  });
  closeConnection(connection);
} catch (error) {
  console.log("Sending didn't work");
  closeConnection(connection);
}
```

This code duplication can be removed, by adding a finally block. A finally block will be executed no matter how the try catch block will be excited. Even in the case of a return.

```js
let connection = null;
try {
  connection = openConnection();
  sendSomeData(connection, {
    /***/
  });
} catch (error) {
  console.log("Sending didn't work");
} finally {
  closeConnection(connection);
}
```

### Error Object

In Javascript there's a constructor function called `Error` which is the standard interface for exception values.

```js
const error = new Error("Something went wrong");

// Error object properties
error.name; // "Error" could also be reset to something else
error.message; // "Something went wrong"
```

There are multiple subclasses that you might encounter. Most of them are exclusively used by the Javascript Interpreter, e.g. `SyntaxError` or `EvalError`

Here are two examples of errors you might use.

```js
new TypeError(); // When a value is not of the required type
new RangeError(); // When a value is outside an expected range
```

[Full MDN Error Reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error)

### Errors vs Bugs

There's a distinction between errors and bugs

**Bug**: Some unexpected faulty program behaviour, outside the specification of the program

**Error**: A runtime condition, which doesn't allow for the intended flow of the program to continue, which is followed by an alternative execution flow, potentially including user feedback

#### Examples

**Bug**: A typo in a variable name leads to a reference error

**Error**: The user typed a wrong password and can't be authenticated

#### A simpler explanation

**Error**: Error made by the user or hardware / system failure (think no memory left)

**Bug**: Error made by the programmer
