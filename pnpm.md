# 🚀 PNPM

## What Is It?

PNPM (Performant Node Package Manager) is an alternative to the popular NPM (Node Package Manager). It replaces all uses of NPM commands with PNPM commands that take less disk space and are not as buggy as basic NPM.

{% embed url="https://www.youtube.com/watch?t=2s&v=hiTmX2dW84E" %}

## What Are The Benefits?

* **Space Savings** - Exponentially lowers file size used on your hard disk for packages
* **Less Bugs** - We've seen NPM bugs cause hard drives to fill up with recursive packages
* **Faster** - All commands in general just run must faster than NPM
* **Drop-In Replacement** - There's no good reason to not just replace NPM commands with PNPM

## Windows PowerShell Privileges

To enable windows PowerShell to install PNPM,, there's an additional step we may need to do.

* On Windows PC's, press the windows key
* Type 'PowerShell'
* Right click the PowerShell icon and choose open as administrator
* Type the following command and press enter
  * `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine`
* Press 'Y' when prompted.

## Installation Instructions

* Make sure you have NPM installed already
* In a Visual Studio Code terminal, run the `npm install -g pnpm` command to install PNPM globally so it will be available regardless of directory or what project is open
* If your using private github repositories, follow the instructions at the bottom

## Usage Instructions

* Simply replace all use cases of NPM commands with PNPM commands
* EX: `pnpm install @babylonjs/core`

## Cache Cleaning

After updating a package with PNPM, you may encounter a scenario where Vite is still using an outdated version of that package when you run the `pnpm run dev` command and test your projects that use said package.&#x20;

This is because Vite makes a copy of your global PNPM packages when testing and it will need to be wiped before your changes can be pulled in.

To clear this cache, inside your project delete the `node_modules/vite` folder in your project hierarchy. It will be recreated the next time you run the `pnpm run dev` and copy your latest global packages.

## Private GitHub Repositories

The commands for accessing private GitHub repositories is the same as with standard NPM.

However accessing private GitHub repositories does not work out of the box for PNPM. In standard NPM you can authenticate using an automatic web browser popup that has you sign into your GitHub account.

We can get around this by creating an SSH key from our machine and uploading it to our GitHub organization so they can handshake. Follow the video below to setup your local machine accordingly.

{% embed url="https://youtu.be/JuQhNFYMFcE" %}
