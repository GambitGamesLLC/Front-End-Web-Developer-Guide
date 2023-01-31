# 🖥 Tauri

## What Is It?

Tauri is a multi-platform, front-end agnostic build tool for creating platform agnostic native applications using web coding technologies.

{% embed url="https://www.youtube.com/watch?v=-X8evddpu7M" %}

## What Are The Benefits?

* **Optimization** - Compared to competitors like [Electron](https://www.electronjs.org/), Tauri is extremely performant because it uses the device's default web browser, instead of including the Chromium browser with your app.
* **Web Tech For Apps** - Provides an easy way to use your existing web based repositories and packages for application development.
* **Fast** - Communication between your web code and Rust code allows you to write intensive operations with the full power of the device when you need it.

## Before You Get Started

* The guide below assumes you have worked with [Visual Studio Code](visual-studio-code.md), [PNPM](pnpm.md) and [Vite](vite.md). We recommend checking out those specific guides and becoming familiar with those tools first before using Tauri.

## Installation Guide

* Follow the [Prerequisites guide](https://tauri.app/v1/guides/getting-started/prerequisites/) from the official Tauri documentation.
  * For PC
    * Install [Build Tools For Visual Studio 2022](https://tauri.app/v1/guides/getting-started/prerequisites/#1-microsoft-visual-studio-c-build-tools)
    * Install [WebView2](https://tauri.app/v1/guides/getting-started/prerequisites/#2-webview2) (skip if on Windows 11 or above)
    * Install [Rust](https://tauri.app/v1/guides/getting-started/prerequisites/#3-rust)
    * Restart your computer
* Copy the [Tauri + Typescript + Vite template repo](https://github.com/GambitGamesLLC/tauri-typescript-vite-template) on Github to get started with your own project.

## Primary Commands

```
//Test your project locally
pnpm tauri dev

//Build your project to the /dist folder
pnpm tauri build
```
