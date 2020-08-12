# :zap: Vue Webcam Video Capture

* Vue app using PC webcam video data streamed via api to a html interface. For chrome only.

*** Note: to open web links in a new window use: _ctrl+click on link_**

## :page_facing_up: Table of contents

* [:zap: Vue Webcam Video Capture](#zap-vue-webcam-video-capture)
  * [:page_facing_up: Table of contents](#page_facing_up-table-of-contents)
  * [:books: General info](#books-general-info)
  * [:camera: Screenshots](#camera-screenshots)
  * [:signal_strength: Technologies](#signal_strength-technologies)
  * [:floppy_disk: Setup](#floppy_disk-setup)
  * [:computer: Code Examples](#computer-code-examples)
  * [:cool: Features](#cool-features)
  * [:clipboard: Status & To-Do List](#clipboard-status--to-do-list)
  * [:clap: Inspiration](#clap-inspiration)
  * [:envelope: Contact](#envelope-contact)

## :books: General info

* Uses the Vue javascript framework.
* webcam video data streamed via api to html interface.

## :camera: Screenshots

![Example screenshot](./img/.png).

## :signal_strength: Technologies

* [Vue framework v2.6](https://vuejs.org/)
* [Vue CLI v3](https://github.com/vuejs/vue-cli)
* [Vue DevTools extension for Chrome](https://chrome.google.com/webstore/detail/vuejs-devtools/nhdogjmejiglipccpnnnanhbledajbpd) was useful for debugging and seeing what was happening with the state when Vuex was used.

## :floppy_disk: Setup

Run `npm start` for a dev server. Navigate to `http://localhost:8080/`. The app will automatically reload if you change any of the source files.

## :computer: Code Examples

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

## :cool: Features

## :clipboard: Status & To-Do List

* Status: Not working.
* To-Do: Replace entire Vue project

## :clap: Inspiration

* [X-Team blog by Nic Raboy: HOW TO CAPTURE WEBCAM VIDEO WITH VUE.JS](https://x-team.com/blog/webcam-capture-vue/).

## :envelope: Contact

* Repo created by [ABateman](https://www.andrewbateman.org) - you are welcome to [send me a message](https://andrewbateman.org/contact)
