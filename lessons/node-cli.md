# Creating a Command Line Tool

Steps to making a node package installable

1. Add a _hash bang_ declaration to your main index.ts file to define which binary should execute the file

```ts
#!/usr/bin/env node

// Your program:
console.log("Hello Command Line");
```

2. Add a new entry to the package.json defining the name of the command you want to create as well as the file that shall be executed

```json
{
  // ... the other keys, like name, version, scripts
  "bin": {
    "rabbit-hole": "./build/index.js"
  }
}
```

3. Now you can install the command line tool using npm or yarn by passing it the path to the repository.

```bash
sudo yarn global install $(pwd)
```
