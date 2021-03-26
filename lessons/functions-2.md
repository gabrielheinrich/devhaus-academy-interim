# Functions - 2

## import & export

Since it would become unhandy to continue to write all our source code in a single file, there's a feature in typescript to import other typescript files. On the other hand we can also export variables, so they can be imported into other source code files. All import statements go at the beginning of your files.

index.ts

```ts
import "./markdown.ts";
// This will just run the source code in markdown.ts

import { h1 } from "./markdown.ts";
// This will also run the source code in markdown.ts, but at the same time import the variable called h1, so you can use it inside this file

import { writeFile } from "fs";
// This will import the function writeFile from the node_module "fs"
```

markdown.ts

```ts
export const h1 = function (text: string) {
  return "# " + text;
};
```

## interface

Interfaces are a great way to define a type that describes the structure of an object in Typescript more precisely. Interfaces don't compile into any Javascript code, they are purely used by the typechecker in tsc

Syntax for an interface called Recipe

```ts
interface Recipe {
  title: string;
  ingredients: string[];
}
```

## split and join

Very often we want to convert between arrays and strings. There are two very helpful methods that make this very easy: split and join

```ts
"Hey, how are you doing?".split(" ");
// -> ["Hey," "how", "are", "you" "doing?"]

["I", "am", "very", "excited"].join("!! ");
// -> "I!! am!! very!! excited"
// Notice how there are no excalamation marks added at the end!
```

## map

Even more often we want to take an array and convert it into another array, by doing something to each element in the array. The tool of choice to do so is the array method called map. It is our first example of a function taking another function as an argument

```ts
const loud = function (text: string) {
  return text.toUpperCase() + "!";
};

const names = ["Tick", "Trick", "Track"];

const loudNames = names.map(loud);
// loudNames -> ["TICK!", "TRICK!", "TRACK!]
```

## Callbacks

We have now already seen one example for a function taking in a function as an input. A function we give to another function is called a Callback, because we give it to a function so it can _'call it later'_.
Callbacks are not only used with functions like map, where we hand in a function so it can be called multiple times. They are also very frequent, when we are asking the computer to do something, that might take a while (like writing a file) and want to run some code **after** the job is finished. Here is an example

```ts
import { writeFile } from "fs";

// This is our callback function, we set it up to use it later
const logThatYouAreDone = function () {
  console.log("Done! I finished writing the file.");
};

writeFile(
  "example.txt", // name of the file to create
  "Hello File!", // contents of the file
  { encoding: "utf-8" }, // some options, here we are only setting the encoding
  logThatYouAreDone // Here we pass in the callback function. writeFile will invoke it once it's done
);
```
