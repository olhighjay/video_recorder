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
  methods: {
    async startCamVideo() {
      this.downloadable = false;
      this.recorded = false;
      this.readyToPlay = false;
      this.loading = false;
      let vidRecordOptions = {
          video: { 
              facingMode: "user", 
          } 
      };
      if(this.recordAudio) {
        vidRecordOptions.audio = { 
          echoCancellation: true,
          noiseSuppression: true
        };
      }
      let mediaStreamObj = null;

      try{
        // Request access to use the mic and video
        mediaStreamObj = await navigator.mediaDevices.getUserMedia(vidRecordOptions)
      
        this.cameraMode = true;
        this.currentStream = "camR";
        await this.updatePermit();
         //connect the media stream to the first video element
          let myVideo = document.getElementById('my-video-feedback');
          // create a video url from the callback response object
          if ("srcObject" in myVideo) {
              myVideo.srcObject = mediaStreamObj;
          } else {
              //old version
              myVideo.src = this.downloadLink = window.URL.createObjectURL(mediaStreamObj);
          }
           //show in the video element what is being captured by device's camera
          myVideo.onloadedmetadata = function(ev) {
            ev;
              // automatically start playing what is being captured by device's camera
              myVideo.play();
          };
          await this.updateMyStream(mediaStreamObj);
          await this.recordCamVideo();
      }
      catch(err) {
        err;
      }
    },
    updatePermit(){
      this.myPermissionAccepted = true;
    },
    async updateVideoTwo(){
      // this.recordedVideo = await document.getElementById('my-recorded-video');
    },
    async updateMyStream(mStream) {
      this.myStream = await mStream;
    },
    recordCamVideo() {
          // Initiate video recording
          let mediaRecorder = new MediaRecorder(this.myStream);
          this.mediaVideoRec = mediaRecorder;
          mediaRecorder.start();
    },
    async stopAndSaveRecordingCamVideo(vidRecorder) {
      let vidSave = document.getElementById('my-recorded-video');
      let chunks = [];
      await vidRecorder.stop();
      vidRecorder.ondataavailable = await function(ev) {
        chunks.push(ev.data);
      };
      vidRecorder.onstop = (ev)=>{
          ev
          let blob = new Blob(chunks, { 'type' : 'video/mp4;' });
          chunks = [];
          let videoURL = this.downloadLink = window.URL.createObjectURL(blob);
          vidSave.src = videoURL;
      }
      this.cameraMode = false;
      this.recorded = true;
      this.readyToPlay = true;
      this.currentStream = null;
      this.downloadable = true;
    },
    async startScreenRecording() {
      // await this.updateVideoTwo();
      let vidTwo = document.getElementById('my-recorded-video');
      vidTwo;
      this.readyToPlay = false;
      this.downloadable = false;
      await this.setupStream();
      let mixedStream;
      if(this.stream) {
        if (this.stream && this.audio) {
          mixedStream = new MediaStream([...this.stream.getTracks(), ...this.audio.getTracks()]);
        } else {
          mixedStream = new MediaStream(this.stream.getTracks());
        }
        this.recorder = await new MediaRecorder(mixedStream);
        this.recorder.ondataavailable = this.handleDataAvailable;
        this.recorder.onstop = this.handleStop;
        await this.recorder.start(1000);
      } else {
        console.warn('No stream available.');
      }
    },
    async setupStream () {
      try {
        this.stream = await navigator.mediaDevices.getDisplayMedia({
          video: { mediaSource: "screen" },
        });

        if(this.stream) {
          await this.updatePermit();
          this.loading = true;
          this.currentStream = "scnR";
        }

        if(this.recordAudio) {
          this.audio = await navigator.mediaDevices.getUserMedia({
            audio: {
              echoCancellation: true,
              noiseSuppression: true,
              sampleRate: 44100,
            },
          });
        }

      } catch (err) {
        console.error(err)
      }
    },
    async handleDataAvailable (e) {
      await this.chunks.push(e.data);
    },
    async handleStop (e) {
      e;
      let vidTwo = document.getElementById('my-recorded-video')
      const blob = new Blob(this.chunks, { 'type' : 'video/mp4' });
      this.chunks = [];

      // downloadButton.href = URL.createObjectURL(blob);
      // downloadButton.download = 'video.mp4';
      // downloadButton.disabled = false;

      vidTwo.src = this.downloadLink = URL.createObjectURL(blob);
      vidTwo.load();
      vidTwo.onloadeddata = function() {
        // const rc = document.querySelector(".recorded-video-wrap");
        // rc.classList.remove("hidden");
        // rc.scrollIntoView({ behavior: "smooth", block: "start" });

        vidTwo.play();
      }

      this.stream.getTracks().forEach((track) => track.stop());
      this.audio ? this.audio.getTracks().forEach((track) => track.stop()) : '';
    },
    async stopScreenRecording () {
      await this.recorder.stop();
      this.loading = false;
      this.recorded = true;
      this.downloadable = true;
      this.readyToPlay = true;
      this.currentStream = null;
    }

  }
}
</script>