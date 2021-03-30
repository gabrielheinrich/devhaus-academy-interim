# Loops

## while

```js
let i = 0;
while (i < 100) {
  console.log(i);
  i += 1;
}
// Read: We check whether i is less than 100.
// If that is the case we continue by logging the value of i to the console
// Then we increment i and start over, by checking again, whether i is less than 100
// As soon as i is no longer smaller than 100 the loop is over and we continue with the next statement
```

## for

A for loop is just syntactic sugar for a while loop, where we create a binding
that we want to update after each run through the loop.
This loop is equivalent to the loop above.

```js
for (let i = 0; i < 100; i += 1) {
  console.log(i);
}
```

## for of

If we want to iterate over the individual elements of an array, we can use a for
of loop. In each iteration an identifier will be bound to the currently selected element of
the array

```js
for (const element of ["apple", "orange", "banana"]) {
  console.log(element);
}
// OUTPUT:
// apple
// orange
// banana
```

## break and continue

**Inside a loop** there are two special statements allowed to abort the loop or
skip the rest of the loop body.

```js
break;
// Read: We break out of the loop and continue with the next statement after the loop body

continue;
// Read: We immediately jump to the end of the loop body to continue with the next loop iteration.
```

## Katas

- [Grasshopper Summation](https://www.codewars.com/kata/55d24f55d7dd296eb9000030)
- [Number of decimal digits](https://www.codewars.com/kata/58fa273ca6d84c158e000052)
- [Linear Search: Part 1](https://edabit.com/challenge/pEzxi4MqHGrAi7ZdA)
- [Linear Search: Part 2](https://edabit.com/challenge/z6Pxiw289JtaE2ndL)
- [Reverse an Array](https://edabit.com/challenge/kJQYTCCWSnzhXG9dn)
- [Tetris Score](https://www.codewars.com/kata/5da9af1142d7910001815d32)
- [Driving School Series #1](https://www.codewars.com/kata/58999425006ee3f97c00011f)
- [Computer problem series #1: Fill the hard disk drive](https://www.codewars.com/kata/5d49c93d089c6e000ff8428c)
- [Sum of array](https://www.codewars.com/kata/53dc54212259ed3d4f00071c)
