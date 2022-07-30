<template>
    <div class="record-page">
      <div class="view-frame-wrapper">
        <div v-if="recordVideo && currentStream === 'camR'" class="d-flex mb-2">
          <div class="live-icon-wrapper">
            <div class="live-icon" ></div>
          </div>
          <div class="ml-2">Live Preview</div>
        </div>
        <div class="view-frame">
          <div v-if="loading && !cameraMode" class="d-flex justify-content-center" style="padding-top:30%">
            <h3 class="text-light">Screen is recording..</h3> &nbsp;&nbsp; <def-loader></def-loader>
          </div>
          <div v-if="myPermissionAccepted" style="height:100%">
          <!-- <div v-if="true" style="height:100%"> -->
            <video v-if="!recorded && cameraMode" muted id="my-video-feedback" class=" bg-black w-full h-auto"></video>
            <video v-show="recorded && readyToPlay" id="my-recorded-video" controls class="recorded-video bg-black w-full h-auto"></video>
          </div>
        </div>
        <div class="text-center start-recording-wrapper">
          <!-- <button @click="startScreenRecording" class="start-recording">Start recording</button> -->
          <button v-if="recordVideo && (!currentStream || (currentStream != 'camR'&& currentStream != 'scnR'))" @click="startCamVideo" class="start-recording">Record Camera</button>
          <button v-if="recordVideo && currentStream === 'camR'" @click="stopAndSaveRecordingCamVideo(mediaVideoRec)" class="red-btn start-recording">Stop recording</button>

          <button v-if="recordScreen && (!currentStream || (currentStream != 'scnR' && currentStream != 'camR'))" @click="startScreenRecording" class="start-recording ml-2">Record Screen</button>
          <button v-if="recordScreen && currentStream === 'scnR'" @click="stopScreenRecording" class="red-btn start-recording">Stop recording</button>
          <a v-if="downloadable" :href="downloadLink" download="video.mp4" class="my-btn start-recording ml-2">Download</a>
        </div>
      </div>
    </div>
</template>

<script>
import DefLoader from '@/components/DefLoader'
export default {
    name: 'RecordPage',
    components: {
        DefLoader
    },
    props: [ 'recordAudio', 'recordVideo', 'recordScreen'],
    data() {   
    return {
      recorded: false,
      cameraMode: false,
      readyToPlay: false,
      loading: false,
      downloadable: false,
      myPermissionAccepted: false,
      myStream: null,
      mediaVideoRec: null,
      currentStream: null,
      downloadLink: '',

      stream: null,
      audio: null,
      mixedStream: null,
      chunks: [], 
      recorder: null,
      recordedVideo: '',
    }
  },
}
</script>