# ⚡ Vite

## What Is It?

Vite is a web asset build tool, that takes the files for your web app or package and generates a build folder that is more optimized and easily shared as a package.

{% embed url="https://youtu.be/KCrXgy8qtjM" %}

## What Are The Benefits?

* **Tree Shaking** - Optimizes builds to contain only what your 'import' statements require
* **Local Testing** - Provides a local server so you can test your code as if it's on a server
* **Hot Module Replacement** - Speeds up testing by swapping only what's changed in your code.

## Installation Guide

* Open Visual Studio Code
* Open a new terminal window, and run the `pnpm install vite` command

## Primary Commands

```
//Test your project locally
pnpm run dev

//Build your project to the /dist folder
pnpm run build
```

## Project Creation Guide

* Open Visual Studio Code and start a new terminal window
* Use the `cd` command to move to the folder you want to create your project within.
  * Typically this is in `Documents->Github->CompanyName`
* Run the `pnpm create vite` to create a new blank project
* Name your project appropriately within the terminal prompt
* Choose your UI framework
  * Choose _`svelte -> svelte-ts`_ when making a UI library package or App
  * Use _`vanilla -> vanilla-ts`_ when making a non-UI library package

## Typescript Preparation

Modify the `tsconfig.json` file that was automatically created with your Vite project

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

## Setup Project As Library

Most of the time, you'll be working on a specific package, but Vite creates new projects under the assumption that you're creating the main app that imports those packages. Here's how you change that.

* Follow the steps above to install and create a project
* Next you'll be modifying a few of the default files that Vite created. This will be different if you're creating a Svelte based UI package vs a regular package
* If you are creating a UI package using Svelte, use the following `package.json` file as a guide

```
{
  "name": "typescript-svelte-vite-library-project",
  "private": true,
  "version": "1.0.0",
  "type": "module",
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
    "preview": "vite preview",
    "check": "svelte-check --tsconfig ./tsconfig.json"
  },
  "devDependencies": {
    "@sveltejs/vite-plugin-svelte": "^1.0.1",
    "@tsconfig/svelte": "^3.0.0",
    "svelte": "^3.49.0",
    "svelte-check": "^2.8.0",
    "svelte-preprocess": "^4.10.7",
    "tslib": "^2.4.0",
    "typescript": "^4.6.4",
    "vite": "^3.0.7"
  }
}
```

* If you are creating a non-UI package, modify `package.json` using the guide below

```
{
  "name": "typescript-vite-library-template",
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

* Modify `vite.config.js` using the guide below if you are creating a Svelte UI package

```
// vite.config.js
const path = require('path')
const { defineConfig } = require('vite')
import { svelte } from '@sveltejs/vite-plugin-svelte'

module.exports = defineConfig({
  plugins: [svelte()],
  build: {
    lib: {
      entry: path.resolve(__dirname, 'lib/main.ts'),
      name: 'main',
      fileName: (format) => `main.${format}.js`,
      formats:['es']
    },
    rollupOptions: {
      external: [""]
    }
  }
})
```

* Alternatively modify `vite.config.js` following the guide below if this is a non-UI package

```
// vite.config.js
const path = require('path')
const { defineConfig } = require('vite')

module.exports = defineConfig({
  build: {
    lib: {
      entry: path.resolve(__dirname, 'lib/main.ts'),
      name: 'main',
      fileName: (format) => `main.${format}.js`,
      formats:['es']
    },
    rollupOptions: {
      external: [""]
    }
  }
})
```

## Coding Sample

The entry point for your code is the `index.html` file at the root of your project folder

Either modify or create `index.html` and modify it to match the following

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <link rel="icon" type="image/svg+xml" href="favicon.svg" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>typescript-library-template</title>
  </head>
  <body>
    <div id="app"></div>
    <script type="module" src="./test.js"></script>
  </body>
</html>
```

You can see above that we're loading a Javascript file that accepts ESM loading at your folder root.

Create `test.js` in your project root, which will be used to test your code locally.

Add the following code to `test.js`

```
//Put the code you want to test when `pnpm run dev` is called in this file
import * as module from "./lib/main.ts";

async function Run()
{
    try 
    {
        module.Message("test successfull");
    } 
    catch (error) 
    {
        console.error(error);
    }
}

Run();
```

Within your project root, create or open the `lib` folder, where your primary files will exist

Inside of the `lib` folder, create a new file called `main.ts`

Add the following code to `main.ts`

```
/**
 * Logs a message to the console
 * @param sayThis The message you want logged to the console
 */
//--------------------------------------------------//
export function Message( sayThis: string ) : void
//--------------------------------------------------//
{
    console.log( sayThis );

} //END Message
```

Open a new terminal window and use the command below to test your code

```
pnpm run dev
```

Click the link that is generated at your local port to open `index.html` in your web browser. Any changes you make to your code will appear instantly.
