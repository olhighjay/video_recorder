<template>
    <div class="empty-main">
        <div>
            <img alt="Advert" class="empty-main-img" src="../assets/video-player-film.png">
        </div>
        <p class="say-hello">Say hello to the world!</p>
        <p class="hello-sub">Record your first video/audio and share it what your team, friends, 
            <br />followers and customers.
        </p>
        <div class="text-center">
        <button class="sub-heading-btn red-btn">
            <span class="rec">REC</span>
            Start Recording
        </button>
        <button class="sub-heading-btn blue-btn">
            <i class="fa fa-video"></i>
            New Request
        </button>
        </div>
    </div>
    <div class="footer">
        <div class="advert">
            <img alt="Advert" src="../assets/hqdefault.jpg">
        </div>
        <div>
        <p class="moore">Want more controls & better <br />quality recording?</p>
        <button class="sub-heading-btn blue-btn">Download the desktop recorder</button>
        </div>
    </div>
</template>

<style >
.empty-main {
    border: 1px dashed #A3BAC6; margin-top:30px;
    border-radius: 38px;
    opacity: 1; 
    padding-top:105.9px; 
    padding-bottom:68.5px;
}
.empty-main-img {
    width:203px; 
    margin: 0 auto; 
    display:block;
}
.say-hello {
    color: #000; 
    font-size: 22px; 
    text-align:center; 
    margin-top:25px;
}
.hello-sub {
    color: #637C8E; 
    font-size: 14px; 
    text-align:center;
}
.footer {
    display: flex;
    margin-top:42px; 
    margin-bottom: 140px;
}
.advert {
    flex-basis: 50%;
}
.moore {
    font-size: 26px; 
    color:#21455E; 
    margin-top:10%;
}
</style>