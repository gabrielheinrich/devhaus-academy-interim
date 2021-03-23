# Hello World Guide

## Step 1: Creating and opening a new empty repository

```bash
# Go to the Developer folder
cd ~/Developer
# Create a new git repository in a new directory called 'hello-world'
git init hello-world
# Open the directory hello-world in vs code
code -r hello-world
```

After the window reloads, open the terminal again to continue with step 2.

## Step 2: Setting up a package.json file with yarn

```bash
# This will create a new default package.json file in the current directory.
# -y stands for yes, as in say yes to all questions asked
yarn init -y
```

## Step 3: Creating our main typescript file

```bash
# First we create a new directory
mkdir src
# Then we can create a new file
touch src/index.ts
```

Next open the index.ts file and insert this hello world code snippet into the file

```ts
console.log("Hello World");
```

## Step 4: Configuring Typescript

```bash
# All typescript configuration goes in a new file called tsconfig.json, let's create it
touch tsconfig.json
```

Then insert this in the tsconfig.json file to tell typescript which files to compile and to place its output in a directory called **build**

```json
{
  "compilerOptions": {
    "outDir": "build"
  },
  "files": ["src/index.ts"]
}
```

## Step 5: Compile Typescript to Javascript

```bash
# After having setup the tsconfig.json file, this is as simple as:
tsc
```

This will create a file in the **build** directory called **index.js**

## Step 6: Run the program

```bash
node build/index.js
```

You should see **Hello World** being printed to the console.
