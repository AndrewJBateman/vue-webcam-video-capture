# Vue Webcam Video Capture

* Vue app using PC webcam video data streamed via api to a html interface. For chrome only.

*** Note: to open web links in a new window use: _ctrl+click on link_**

## Table of contents

* [General info](#general-info)
* [Screenshots](#screenshots)
* [Technologies](#technologies)
* [Setup](#setup)
* [Features](#features)
* [Status](#status)
* [Inspiration](#inspiration)
* [Contact](#contact)

## General info

* Uses the Vue javascript framework.

## Screenshots

![Example screenshot](./img/.png).

## Technologies

* [Vue framework v2.5.2](https://vuejs.org/)

* [Vue CLI v3.1.2](https://github.com/vuejs/vue-cli)

* [Vue DevTools extension for Chrome](https://chrome.google.com/webstore/detail/vuejs-devtools/nhdogjmejiglipccpnnnanhbledajbpd) was useful for debugging and seeing what was happening with the state when Vuex was used.

## Setup

Run `npm start` for a dev server. Navigate to `http://localhost:8080/`. The app will automatically reload if you change any of the source files.

## Code Examples

```html

<template>
  <div id="app">
    <div><video ref="video" id="video" width="640" height="480" autoplay></video></div>
    <div><button id="snap" v-on:click="capture()">Snap Photo</button></div>
    <canvas ref="canvas" id="canvas" width="640" height="480"></canvas>
    <ul>
      <li v-for="c in captures" :key="c.id">
      <img v-bind:src="c" height="50" />
      </li>
    </ul>
  </div>
</template>

```

## Features

## Status & To-Do List

* Status: App compiles but does not show webcam video so does not capture photos. There were cahnges to the way video is captured in chrome and the code needs to reflect this.

* To-Do: fix.

## Inspiration

* [X-Team blog by Nic Raboy: HOW TO CAPTURE WEBCAM VIDEO WITH VUE.JS](https://x-team.com/blog/webcam-capture-vue/).

## Contact

Repo created by [ABateman](https://www.andrewbateman.org) - feel free to contact me!
