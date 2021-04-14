# Promises

## Resources

[Promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)

[Async Await](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Async_await)

Promises are javascript objects that symbolize asynchronous operations.
During an asynchronous operation one of two events can happen:

- Success: The promise gets resolved with a value
- Error: The promise gets rejected with an error object

For both of these events you can add a callback to be executed when the event
takes place.

```js
const promise = prompt("What's your name?');

// Add an event listener for the resolved case
promise.then((result) => {
  console.log("The promise resolved and returned the value: " + result);
}).catch((error) => {
  console.error(
    "The promise got rejected and this error was returned: " + error
  );
}
```

**`.then` returns another promise**
It will resolve with the return value of
the _then handler_ or be rejected if an error gets thrown.

It's important that the `.catch` is **chained** after the `.then`. This way it will
also be
called when something goes wrong in the _then-handler_.

## Async Await - Syntactic sugar for promises

Promise Version

```js
const askForNameAndGreet = function() {
  prompt("What's your name?")
  .then(response) {
    console.log("Hello " + response + "!")
  }
}
```

Async Version

```js
const askForNameAndGreet = async function () {
  const response = await prompt("What's your name?");
  console.log("Hello " + response + "!");
};
```

### !! An async function as well as a call to then always return a promise !!
