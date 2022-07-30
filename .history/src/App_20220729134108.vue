<template>
  <div>
    <navbar></navbar>
    <div id="main-flex">
      <div v-if="false" class="my-sidebar">
        <ul class="my-sidebar-items">
            <li class="sidebar-item-active"> <img src="./assets/video-player.png" alt=""> &nbsp; My Recordings</li>
            <li> <i class="fa fa-share-alt" style="color:#102346"></i> &nbsp; Requested</li>
        </ul>
      </div>
      <div v-if="false" class="my-main">
        <div class="my-main-container">
          <div><small class="breadcrumbs">Snapbyte <i class="fa fa-angle-right" style="font-weight:200"></i> My Recordings</small></div>
          <div class="subheading-tab">
            <div> <span class="my-recordings">My Recordings </span><span class="my-recordings-count">25</span> </div>
            <div> 
              <button class="sub-heading-btn white-btn">
                <i class="fa fa-long-arrow-down" aria-hidden="true"></i>
                <i class="fa fa-long-arrow-up" aria-hidden="true"></i>
                By Date
              </button>
              <button class="sub-heading-btn white-btn">
                <i class="fa-solid fa-filter"></i>
                Add Filter
              </button>
              <button class="sub-heading-btn blue-btn">
                <i class="fa fa-video"></i>
                New Request
              </button>
              <button class="sub-heading-btn red-btn">
                <span class="rec">REC</span>
                Start Recording
              </button>
            </div>
          </div>
          
          <empty-recorded></empty-recorded>
          
          <data-table v-if="true"></data-table>
          <!-- Button trigger modal -->
<button type="button" class="btn btn-primary" data-toggle="modal" data-target="#recordOptions">
Launch demo modal
</button>

<!-- Modal -->
<div class="modal fade" id="recordOptions" tabindex="-1" role="dialog" aria-labelledby="recordOptions" aria-hidden="true">
<div class="modal-dialog modal-dialog-centered" role="document">
  <div class="modal-content">
    <div class="modal-header">
      <h5 class="my-modal-title">New Recording</h5>
      <button type="button" class="close" data-dismiss="modal" aria-label="Close">
        <span aria-hidden="true"><i class="fa fa-xmark"></i></span>
      </button>
    </div>
    <div class="modal-body">
      <p class="save-in">Save the recording in</p>
      <div>
        <select class="save-option">
          <Option value="" key="">Select a project</Option>
          <Option value="" key="">Project 1</Option>
          <Option value="" key="">Project 2</Option>
          <Option value="" key="">Project 3</Option>
          <Option value="" key="">Project 4</Option>
        </select>
      </div>
      <div style="margin-top: 35px;">
        <div class="record">
          <div class="record-name">Record screen</div>
          <div class="record-switch">
            <label class="switch">
              <input type="checkbox">
              <span class="slider round"></span>
            </label>
          </div>
        </div>
        <div class="record">
          <div class="record-name">Record camera</div>
          <div class="record-switch">
            <label class="switch">
              <input type="checkbox">
              <span class="slider round"></span>
            </label>
          </div>
        </div>
        <div class="record">
          <div class="record-name">Record mic</div>
          <div class="record-switch">
            <label class="switch">
              <input type="checkbox">
              <span class="slider round"></span>
            </label>
          </div>
        </div>
      </div>
    </div>
    <div class="text-center">
      <button type="button" class="start-recording-btn">Start Recording</button>
    </div>
  </div>
</div>
</div>
        </div>
      </div>
    </div>
    <div class="record-page">
      <div class="view-frame-wrapper">
        <div class="d-flex mb-2">
          <div class="live-icon-wrapper">
            <div class="live-icon" ></div>
          </div>
          <div class="ml-2">Live Preview</div>
        </div>
        <div class="view-frame">
          <div  style="height:100%">
            <video v-if="recorded" controls muted id="my-video-feedback" class=" bg-black w-full h-auto"></video>
            <video v-else id="my-recorded-video" controls class="recorded-video bg-black w-full h-auto"></video>
          </div>
        </div>
        <div class="text-center start-recording-wrapper">
          <button class="start-recording">Start recording</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Navbar from './layouts/Navbar.vue'
import DataTable from '@/components/DataTable'
import EmptyRecorded from '@/components/EmptyRecorded'

export default {
  name: 'App',
  components: {
    Navbar,
    DataTable,
    EmptyRecorded
  },
  data() {
    return {
      recorded: true,
      myPermissionAccepted: true
    }
  },
  methods: {
    async recordVideo() {
      let vidRecordOptions = { 
          audio: { 
              echoCancellation: true,
              noiseSuppression: true, 
          },
          video: { 
              facingMode: "user", 
          } 
      };
console.log(navigator.mediaDevices.getUserMedia(vidRecordOptions));
    try {
  // // Request access to use the mic and video
      await navigator.mediaDevices.getUserMedia(vidRecordOptions)
      this.processCamVideo();
    }catch(err){
          console.log("See am here"); 
        console.log(err.name, err.message);
          return err
    }
  


    },
     processCamVideo(mediaStreamObj) {
//     //connect the media stream to the first video element
    let myVideo = document.getElementById('my-video-feedback');
//     // create a video url from the callback response object
    if ("srcObject" in myVideo) {
        myVideo.srcObject = mediaStreamObj;
    } else {
        //old version
        myVideo.src = window.URL.createObjectURL(mediaStreamObj);
    }
//     //show in the video element what is being captured by device's camera
    myVideo.onloadedmetadata = function(ev) {
      ev;
        // automatically start playing what is being captured by device's camera
        myVideo.play();
    };

//     //add listeners for saving video/audio
//     let start = document.getElementById('btnStart');
//     let stop = document.getElementById('btnStop');

    // let vidSave = document.getElementById('vid2');

//     // Initiate video recording
    let mediaRecorder = new MediaRecorder(mediaStreamObj);
    // let chunks = [];
    mediaRecorder.start();
    // setTimeout(() => {
    //     mediaRecorder.stop();
    //     mediaRecorder.ondataavailable = function(ev) {
    //                 chunks.push(ev.data);
    //             };
    //             mediaRecorder.onstop = (ev)=>{
    //               ev
    //                         let blob = new Blob(chunks, { 'type' : 'video/mp4;' });
    //                         chunks = [];
    //                         let videoURL = window.URL.createObjectURL(blob);
    //                         vidSave.src = videoURL;
    //                     }
    // }, 8000);
}
  },
  created() {
    this.recordVideo();
  }
}
</script>


<style>
 @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;700&display=swap');

#main-flex {
  display: flex;
  width: 100%;
}

.record-page {
  background: transparent linear-gradient(117deg, #0dacd85d 0%, #eafaff5d 0%, #d3f5fe65 100%) 0% 0% no-repeat padding-box;
  width: 100%;
  padding: 81px 20%;
}
.view-frame-wrapper {
  margin: 0 auto;
  max-width: 965px;
}
.view-frame {
  height: 518px;
  background: #21455E 0% 0% no-repeat padding-box;
  border-radius: 8px;
}
.live-icon-wrapper {
  border: 2px solid red; 
  border-radius: 50%; 
  height:20px;
  width:20px;
}
.live-icon {
  background-color:red; 
  border-radius: 50%; 
  height:12px; 
  width:12px; 
  margin: 10% auto;
}
.start-recording-wrapper {
  margin-top: 50px;
}
.start-recording {
  padding: 5px 30px;
  background: #0DABD8 0% 0% no-repeat padding-box;
  border-radius: 32px;
  border: none;
  color: #fff;
}



.my-sidebar {
  flex: 0 0 240px;
  /* width: 20%; */
  /* height: 100%; */
  background-color: #ebf2f656;
  border-right: 2px solid #21455e54;
  /* border-right: 2px solid #21455E; */
  /* width:250px; */
}
.my-sidebar-items {
  list-style: none;
  padding: 20px 0;
}
.my-sidebar-items>li {
  margin : 10px 12px 10px 18px;
  padding: 7px 20px ;
}
.sidebar-item-active {
  background-color: #E2E5ED;
  border: 2px solid #0DABD838;
  border-radius: 10px;
}





.my-main {
  flex: 1;
  flex-wrap: wrap;
}
.my-main-container {
  padding: 1.5% 8.5%;
}
.subheading-tab {
  display: flex;
  justify-content: space-between;
}
.sub-heading-btn {
  padding: 3px 15px;
  border-radius: 20px;
  margin-left: 15px;
  font-size: 14px;
}
.white-btn {
  border: 1px solid #E2E5ED;
  background-color: white;
  color: #637C8E;
}
.blue-btn {
  border: none;
  background-color: #0DABD8;
  color: #fff;
}
.red-btn {
  border: none;
  background-color: #EF5350;
  color: #fff;
}
.my-recordings, .my-recordings-count {
  font-size: 24px;
  color: #000
}
.my-recordings {
  color: #000
}
.my-recordings-count {
  color: #637C8E;
  font-weight: 600;
}
.breadcrumbs {
  color:#637C8E;
}
.rec {
  color:#000; 
  background-color:#fff; 
  border-radius:50%; 
  padding:3px 1px; 
  font-size:10px;
}



.save-option {
  width:100%; 
  background: #F8FAFB 0% 0% no-repeat padding-box;
  border: 1px solid #E2E5ED;
  border-radius: 8px; 
  padding:8px 20px;
}
.modal-dialog {
  max-width: 400px !important;
}
.modal-content {
  padding-bottom: 30px !important;
}
.modal-body {
  padding:30px !important;
}
.my-modal-title {
  color:#000; 
  font-size: 22px; 
  padding-left: 14px;
}
.record {
  margin-top: 15px;
  display: flex;
  justify-content: space-between;
}
.record-name {
  color: #21455E;
  font-size: 18px;
}
.save-in {
  color:black; 
  font-size:16px;
}
.start-recording-btn {
  background: #0DABD8 0% 0% no-repeat padding-box;
  border-radius: 28px; 
  font-size:18px; 
  padding:5px 55px; 
  border: none; 
  color:#fff;
}


.switch {
  position: relative;
  top: 10px;
  display: inline-block;
  width: 50px;
  height: 13px;
}

.switch input { 
  opacity: 0;
  width: 0;
  height: 0;
}

.slider {
  position: absolute;
  cursor: pointer;
  top: -10px;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #ccc;
  -webkit-transition: .4s;
  transition: .4s;
}

.slider:before {
  position: absolute;
  content: "";
  height: 15px;
  width: 15px;
  left: 4px;
  bottom: 4px;
  background-color: white;
  -webkit-transition: .4s;
  transition: .4s;
}

input:checked + .slider {
  background-color: #1bd85a;
}

input:focus + .slider {
  box-shadow: 0 0 1px #1bd85a;
}

input:checked + .slider:before {
  -webkit-transform: translateX(26px);
  -ms-transform: translateX(26px);
  transform: translateX(26px);
}

/* Rounded sliders */
.slider.round {
  border-radius: 34px;
}

.slider.round:before {
  border-radius: 50%;
}


button:hover {
  cursor: pointer;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  font: normal normal normal 14px/26px Poppins;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
   /* text-align: center; */
   font-size: 16px;
  color: #707070;
  border-bottom: solid 2px #E2E5ED;
  overflow: hidden;
  /* margin-top: 60px;  */
}

#my-video-feedback::-webkit-media-controls-volume-slider {
        display: none;
}
#my-video-feedback::-webkit-media-controls-mute-button {
        display: none;
}
#my-video-feedback, #my-recorded-video {
  width:100%; 
  height:100%;
}


</style>
