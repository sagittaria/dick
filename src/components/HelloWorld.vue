<template>
  <div style="display: flex;">
    <div class="left" style="border: 1px solid red;width:50%;">
      <video-player
        class="video-player-box"
        ref="videoPlayer"
        :options="options"/>
    </div>
    <div class="right" style="border: 1px solid blue;width:10%;">
      <el-input rows="6" type="textarea" v-model="text"></el-input>
    </div>
  </div>
</template>

<script>
import 'video.js/dist/video-js.css'
import {videoPlayer} from 'vue-video-player'
import 'videojs-flash'
export default {
  name: 'HelloWorld',
  components: {videoPlayer},
  data() {
    return {
      text: '',
      options: {
        autoplay: true,
        muted: true,
        language: 'en',
        playbackRates: [0.5, 1.0, 1.5, 2.0],
        techOrder: ['html5', 'flash'],
        sources: [
          {type: 'rtmp/flv', src: 'rtmp://172.16.52.154:9911/live/1scr-sub'}
        ]
      },
    }
  }
}
</script>

<style>
.video-player-box .video-js{
  height: 500px;
  width: 95%;
}
</style>
