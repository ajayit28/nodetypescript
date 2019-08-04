# TypeScript with NodeJS

## What is typescript?

* Typescript is superset of javascript.
* Compiles to plain javascript (Using tsc)
* Easily integrated to javascript projects
* Designed for development of large applications

## What typescript is offer?

* Static Type Checking
* Class Based Objects
* Modularity
* ES6 features
* Syntax closer to Higher level langulage like Java

## Installation

```
 npm install -g typescript // Install typescript globally to access from anywhere
 tsc // Compiled the ts source code using tsc
 tsc —init // Intializing the typescript config
```

## tsconfig.json

```JSON
slint.config => 

{
  "compilerOptions": {
    /* Basic Options */
    "target": "es5",                          /* Specify ECMAScript target version: 'ES3' (default), 'ES5', 'ES2015', 'ES2016', 'ES2017', 'ES2018', 'ES2019' or 'ESNEXT'. */
    "module": "commonjs",                     /* Specify module code generation: 'none', 'commonjs', 'amd', 'system', 'umd', 'es2015', or 'ESNext'. */
  
     "outDir": "./dist",                        /* Redirect output structure to the directory. */
     "rootDir": "./src",                       /* Specify the root directory of input files. Use to control the output directory structure with --outDir. */

    /* Strict Type-Checking Options */
    "strict": true,                           /* Enable all strict type-checking options. */
 
    /* Additional Checks */

    /* Module Resolution Options */
     "moduleResolution": "node",            /* Specify module resolution strategy: 'node' (Node.js) or 'classic' (TypeScript pre-1.6). */
    
    "esModuleInterop": true                   /* Enables emit interoperability between CommonJS and ES Modules via creation of namespace objects for all imports. Implies 'allowSyntheticDefaultImports'. */ 
  }
}
```

## Installing dependenies

```
npm i express —save

npm i -D typescript ts-node nodemon @types/node @types/express

```



## src/app.ts

```typescript
import express, { Application, Request, Response, NextFunction} from 'express';

const app : Application = express()

const add = (a: number, b: number) : number => {
  return a + b
}


app.get("/", (req : Request, res: Response, next: NextFunction) => {
  console.log(add(10, 20))
  res.send("Hello")
})

app.listen(5000, () => {
  console.log("Server listening on 5000 port");
  
})
```


## NPM Scripts

```
"scripts": {
    "start": "node dist/app.js",
    "dev": "nodemon src/app.ts",
    "build": "tsc -p ."
  }
```


