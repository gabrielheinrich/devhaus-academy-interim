# Week 1 Typescript Review Katas

- [Grade Book](https://www.codewars.com/kata/55cbd4ba903825f7970000f5)
- [Object Debugging](https://www.codewars.com/kata/56d8ae9237123036d3001b54)
- [Template Strings](https://www.codewars.com/kata/55a14f75ceda999ced000048)
- [Student's Final Grade](https://www.codewars.com/kata/5ad0d8356165e63c140014d4)
- [Extra: Strings, strings, strings](https://www.codewars.com/kata/56d6b921c9ae3fd926000601)
  - Hint: Lookup both `typeof` and `Array.isArray`

## Questions

- When do we use an `interface` in typescript?
- What is the meaning of the type `void` in typescript?
- What is the return type of the `<=` operator?
- What do these expression evaluate to:

```ts
[1, 2, 3, 4].map(function (x: number): number {
  return x * x;
});
```

```ts
["Expr", "ssions will b", " ", "valuat", "d"].join("e");
```

```ts
"# My Title".split(" ");
```

```ts
console.log("Hello World");
```

## Git Refresher

- What's the difference between `git reset` and `git reset --hard`. What do these commands do?
- What's the difference between the branches `master` and `origin/master`
- What's the command to create a new branch with the name `my-next-feature`?
- What's the command to jump to a branch called develop?
- If you switch a branch you often get an error, that you have uncommited changes. What can you do to resolve this?
- `git pull` is a shortcut command. Which two other commands are actually running underneath (let's assume your HEAD is on the master branch)
