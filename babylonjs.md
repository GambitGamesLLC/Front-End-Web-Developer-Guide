# 👾 Babylonjs

## What Is It?

Babylonjs is the leading WebGL game engine.

{% embed url="https://www.youtube.com/watch?v=opZx1e53WHo" %}

## What Are The Benefits?

* **Fast** - Significantly faster than Unity3D For web based projects
* **Lightweight** - Builds are much smaller than Unity's WebGL export
* **Typescript** - Supports Typescript out of the box
* **Iteration Speed** - Iterating on web projects is much faster than alternatives
* **Native Support** - Extensible to native platforms as a second-class citizen
* **Maturity** - Much more mature than alternative options like Unity WebGL export and Threejs
* **Open Source** - Everything is free and engine code is editable, readable, and documented
* **Community** - Features a large community online of developers

## Installation Guide

* Open Visual Studio Code
* Open the terminal, run `pnpm install @babylonjs/core`
* Open your **vite.config.js** file, and add @babylonjs/core to your external rollup dependencies so it won't be included in your build

```
rollupOptions: { external: ["@babylonjs/core"] }
```

* You may need to add other parts on the Babylonjs engine to your package, depending on what you're working on. Check out how the engine is split up into packages within the [documentation](https://doc.babylonjs.com/divingDeeper/developWithBjs/treeShaking).

## Usage Guide

We recommend reading the [official Babylonjs documentation](https://doc.babylonjs.com/). If you're already familiar with coding within other game engines like Unity3D, then you'll notice many similarities, with a few notable exceptions.

* Nodes in Babylonjs == GameObject in Unity3D
* NodeTransform in Babylonjs == Transform in Unity3D
* Nodes in Babylonjs can only represent a single component

## Inspector & Hierarchy

In cases where you need to view the Babylonjs inspector to debug your scene, you will need to add at the very least the @babylonjs/core package to the window object of the DOM.

```
import * as BABYLON from "@babylonjs/core";
window.BABYLON = {...BABYLON};

//Show the Babylonjs inspector
scene.debugLayer.show({
    embedMode: true,
    enableClose: false,
    enablePopup: true,
    globalRoot: document.getElementById("app"),
    handleResize: true,
    overlay: true,
    showExplorer: true,
    showInspector: true
});
```

## Additional Tools

* [Playground ](https://playground.babylonjs.com/)- Easily test and run Babylon engine code
* [Sandbox ](https://sandbox.babylonjs.com/)- Drag & drop 3D models for testing
* [GUI Editor](https://gui.babylonjs.com/) - Create & test 2D GUI
