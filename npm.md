# 🚚 NPM

## What Is It?

NPM (Node Package Manager) is the leading system for packaging up your code into re-usable packages.

{% embed url="https://www.youtube.com/watch?v=P3aKRdUyr0s" %}

## What Are The Benefits?

* **Reusability** - Your code can be packaged and used in other projects
* **Simplicity** - Separating your code into packages makes it easier to understand
* **Sharing Is Caring** - You can install packages from other developers to use in your projects

## Installation Instructions

* Visit [https://nodejs.org/en/download/](https://nodejs.org/en/download/)
* Download the version appropriate for your computer (normally the LTS windows installer)
* Run the installer
* Install Nodejs to its default location (to make debugging easier if needed)
* Choose to install all features to your local hard drive
* Enable the checkbox to "Automatically install the necessary tools"
* Finish running the installer

## Usage Instructions

* Open Visual Studio Code
* Within Visual Studio Code, open a new terminal window
* Use the `cd` command to change the terminal to the folder path of your project
* To install a package that will be included in your build, enter the command `npm install packageName`&#x20;
  * Within **package.json** at the root of your project, this will add `packageName` to your array of dependencies
* To install all packages that are already included in your **package.json** file in the root of your project, run `npm install`. This will install all packages listed in the `dependencies` and `devDependencies` sections of that file
* To install a package as a dependency but keep it out of your build (used for commonalities like the Babylonjs engine). Open the **vite.config.js** file of your project (only available in a Vite project) and add the package name to the `rollupOptions: { external: [""] }` string array
  * EX: `rollupOptions: { external: ["@babylonjs/core", "@babylonjs/gui"] }`
* To install a package used across all projects as a tool, run `npm -g install packageName`
* To install a package that within your project that is not a dependency and will not be in your build (aka a _devDependency_), run `npm install --save-dev packageName`
* To remove a package, run `npm remove packageName`
* To wipe all packages from your cache, run `npm cache clean –force`

## Private Github Packages

* To install a package from Github, swap out the `packageName` in the above instructions for `github:OrganizationName/PackageName`
  * EX:`github:GambitGamesLLC/Test` instead of just `Test` as the `packageName`
* Upon running the install command, you may be prompted to sign into your Github account to check for authorization.
