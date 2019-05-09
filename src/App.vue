<!--create refs for video and canvas, button to take photos, define canvas sizes, show photos using v-for-->
/* eslint-disable */
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

<script>
export default {
  name: 'app',
  data()  {
    return {
      video: {},
      canvas: {},
      captures: []
    }
  },
  mounted()  {
    this.video = this.$refs.video
    // video: ElementRef;
    if (navigator.mediaDevices && navigator.mediaDevices.getUserMedia) {
      navigator.mediaDevices
        .getUserMedia(
          { video: true }
        )
        .then(stream => {
        // this.video.src = window.URL.createObjectURL(stream)
        this.video.nativeElement.srcObject = stream;
        this.video.nativeElement.play()
      })
        .catch( err => 
          alert(`Bummer! ${err.name}.`)
        );
    }
	},
  methods:  {
    capture() {
      // this.canvas = this.$refs.canvas
      // const context = this.canvas.getContext('2d').drawImage(this.video, 0, 0, 640, 480)
      // this.captures.push(canvas.toDataURL("image/png"))
        const context = this.canvas.nativeElement.getContext("2d").drawImage(this.video.nativeElement, 0, 0, 640, 480);
        this.captures.push(this.canvas.nativeElement.toDataURL("image/png"));
        console.log('picture taken');
    }
	}
}
</script>

<style>
body {
	background-color: #f0f0f0;
}
#app {
	text-align: center;
	color: #2c3e50;
	margin-top: 60px;
}
#video {
	background-color: #000000;
}
#canvas {
	display: none;
}
li {
	display: inline;
	padding: 5px;
}
</style>
