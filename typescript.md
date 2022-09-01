# 🔢 Typescript

## What Is It?

Typescript is a superset of the Javascript programming language. It lets you write code that's closer to C# but then compiles down to basic Javascript for full browser compatibility.

{% embed url="https://youtu.be/zQnBQ4tB3ZA" %}

## What Are The Benefits?

* Intellisense highlighting and documentation for functions and variables in code editors
* Automatic error checking while coding
* Type definitions for variables and callbacks for functions
* Compiles down to regular JS, so its backwards compatible

## Installation Instructions

* Open or create a new Visual Studio Code project.
* Open a terminal window _(Terminal->New Terminal)_ and install it into your project as a developer dependency using the pnpm command below

```
pnpm install --save-dev typescript
```

* Open your **package.json** file at the root of your project and make sure`"types": "./dist/main.d.ts",`is in your package, as shown in the example below. This will let other scripts that import your code know where your variable and function type definitions file for your public code is kept at.
* Double check that `"typescript": "^4.5.4",`or above has been added to your `devDependencies`. This ensures that pnpm successfully added Typescript as a dependency that will not be included in your build.

```
{
  "name": "example-project",
  "private": true,
  "version": "1.0.0",
  "types": "./dist/main.d.ts",
  "files": [
    "dist"
  ],
  "main": "./dist/main.umd.js",
  "module": "./dist/main.es.js",
  "exports": {
    ".": {
      "require": "./dist/main.umd.js",
      "import": "./dist/main.es.js"
    }
  },
  "scripts": {
    "dev": "vite",
    "build": "vite build && tsc",
    "preview": "vite preview"
  },
  "devDependencies": {
    "typescript": "^4.5.4",
    "vite": "^2.9.14"
  }
}

```

* Make sure you have a **tsconfig.json** file at the root of your project. By default you can use the settings for this file shown below

```
{
  "compilerOptions": {
    "target": "ESNext",
    "useDefineForClassFields": true,
    "module": "ESNext",
    "lib": ["ESNext", "DOM"],
    "moduleResolution": "Node",
    "strict": true,
    "sourceMap": true,
    "resolveJsonModule": true,
    "isolatedModules": false,
    "esModuleInterop": true,
    "noEmit": false,
    "noUnusedLocals": true,
    "noUnusedParameters": true,
    "noImplicitReturns": true,
    "skipLibCheck": true,
    "declaration": true,
    "declarationMap": true,
    "emitDeclarationOnly": true,
    "outDir": "./dist"
  },
  "include": ["lib"]
}
```

## Usage

* Replace your Javascript files (.js) with Typescript files (.ts)
* Add type definitions and comments to your scripts as needed.
* When making a build with your bundler tool, your TS code will be exported as Javascript

```
//Vanilla-JS works as expected
export let jsVariable = "sup";

export function JSFunction()
{
    console.log( "JS code works as expected in a Typescript file" );
}

//Typescript code is very similar
/**
* When importing your code into another script, your comments will appear.
**/
export let tsVariable : string = "sup";

/**
* Comments also work as expected for functions in Typescript
**/
export function TSFunction() : null
{
    console.log( "TS functions can optionally include info about the return value" );
}
```
