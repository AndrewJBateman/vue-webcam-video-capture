<!--create refs for video and canvas, button to take photos, define canvas sizes, show photos using v-for-->
/* eslint-disable */
<template>
  <div id="app">
    <div>
      <video ref="video" id="video" width="640" height="480" autoplay></video>
    </div>
    <div>
      <button id="snap" @click="capture()">Snap Photo</button>
    </div>
    <canvas ref="canvas" id="canvas" width="640" height="480"></canvas>
    <ul>
      <li v-for="(c, idx) in captures" :key="idx">
        <img :src="c" height="50" />
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      video: {},
      canvas: {},
      captures: [],
    };
  },
  mounted() {
    this.video = this.$refs.video;
    // video: ElementRef;
    if (navigator.mediaDevices && navigator.mediaDevices.getUserMedia) {
      navigator.mediaDevices
        .getUserMedia({ video: true })
        .then((stream) => {
          // this.video.src = window.URL.createObjectURL(stream)
          this.video.srcObject = stream;
          // this.video.nativeElement.play();
        })
        .catch((err) => alert(`Bummer! ${err.name}.`));
    }
  },
  methods: {
    capture() {
      this.canvas = this.$refs.canvas;
      let context = this.canvas
        .getContext("2d")
        .drawImage(this.video, 0, 0, 640, 480);
      this.captures.push(canvas.toDataURL("image/png"));
    },
  },
};
</script>

<style>
body {
  background-color: #f0f0f0;
}
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
#video {
  border: 1px solid;
}
#canvas {
  /* display: none; */
}
li {
  display: inline;
  padding: 5px;
}
</style>
