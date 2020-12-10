# video
: 동영상 콘텐츠 삽입을 위한 태그           


**포함 요소**
- [source](./source.md)
- [track](./track.md)


속성 | 설명
---|---
src      | 비디오 경로 지정  
controls | 비디오 제어를 위한 패널 표시 여부 지정 (불리언 속성)
autoplay | 비디오 자동 재생 여부 지정 (불리언 속성)
loop     | 비디오 반복 재생 여부 지정 (불리언 속성)
muted    | 비디오 음소거 여부 지정 (불리언 속성)
width, height | 비디오 너비와 높이 지정
poster   | 비디오 재생전 표시할 이미지 지정  
preload  | 비디오 리소스 로드에 대한 힌트 지정
playsinline | (불리언 속성)
crossorigin | crossorigin 요청 처리 방식 지정


```html
<video src="경로/파일.확장자" controls>
    <p>Your browser does not support the <code>video</code> element.</p>
</video>


<video src="경로/파일.확장자" preload="auto | metadata | none">
    <p>Your browser does not support the <code>video</code> element.</p>
</video>
<!--
- auto : 재생하지 않아도 리소스를 미리 로드함
- metadata : 리소스의 메타데이터만 로드하고 none 값과 동일
- none : 재생하기 전까지 리소스를 로드하지 않음
-->


<!-- 다중 지원을 위해 source 태그 사용 -->
<video controls>
    <!-- type 명시는 선택 사항 -->
    <source src="경로/파일.mp4" type="audio/mp4">
    <source src="경로/파일.webm" type="audio/webm">
    <source src="경로/파일.ogg" type="audio/ogg">
    <p>Your browser does not support the <code>video</code> element.</p>
</video>



<!-- 하위 브라우저 지원 -->
<video controls>
    <source src="경로/파일.확장자">

    <!--
    : IE 8 경우 플래시를 지원하므로 플래시 사용
    : video 태그를 지원하는 브라우저는 source 태그 외의 콘텐츠는 무시함  

    [모두를 위한 비디오 : 크록 케이먼]     
    http://camendesign.com/code/video_for_everybody     
    -->
    <object type="application/x-shockwave-flash" data="경로/파일.확장자">
        <param name="" value="" />
    </object>
</video>
```


**video**  

컨테이너 | 코덱 | 확장자 | MIME 타입
---|---|---|---
MPEG-4(MP4) | H.264(MPEG-4 Part 10), HEVC(H.265) | .mp4 |video/mp4
Ogg | Theora | .ogv, .ogg | video/ogg
WebM | AV1, VP8, VP9 | .webm | video/webm
Matroska(MKV) | H.264, VP8, VP9 | .mkv | video/x-matroska
MOV(Quicktime) | H.264(MPEG-4 Part 10) | .mov | video/quicktime


**container format**   
= wrapper format    
: 멀티미디어를 구성하는 데이터들과 메타데이터를 포함하는 컨테이너     


**codec**   
: 멀티미디어 데이터를 압축하거나 압축을 해제하는데 사용되는 소프트웨어       
: 멀티미디어 데이터 스트림을 인코딩(저장, 암호화, 전송)하고 디코딩하는 알고리즘 정의   


**Custom Controls**
```js
/*
<div id="customControls">
    <progress id="progress">0</progress>
    <span id="time">00:00</span>
    <button type="button" id="palyPauseBtn">play</button>
    <button type="button" id="muteBtn">mute</button>
    <button type="button" id="volupUpBtn">vol+</button>
    <button type="button" id="volumeDownBtn">vol-</button>
</div>
*/

var video = document.getElementById('video');
var progress = document.getElementById('progress');
var time = document.getElementById('time');
var palyPauseBtn = document.getElementById('palyPauseBtn');
var muteBtn = document.getElementById('muteBtn');
var volumeUpBtn = document.getElementById('volumeUpBtn');
var volumeDownBtn = document.getElementById('volumeDownBtn');

video.removeAttribute('controls');

video.addEventListener('play', function(){
    palyPauseBtn.addClass('playing');
});

video.addEventListener('pause', function(){
    palyPauseBtn.removeClass('playing');
});

video.addEventListener('volumechange', function() {
    if(video.muted){
        muteBtn.addClass('muted');
    } else {
        muteBtn.removeClass('muted');
    }
});

video.addEventListener('timeupdate', function(){
    time.innerText = video.currentTime
});

video.addEventListener('ended', function(){
    video.pause();
    video.currentTime = 0;
});

progress.addEventListener('click', function(e) {

});

palyPauseBtn.addEventListener('click', palyPause);
muteBtn.addEventListener('click', mute);
volumeBtn.addEventListener('click', volume);

function palyPause(){
    if(video.paused)
        video.play();
    else
        video.pause();
}

function mute(){
    if(video.volume == 1 || video.muted == false){
        video.volume = 0;
        video.muted = true;
    } else {
        video.volume = 1;
        video.muted = false;
    }
}
```


**HTMLMediaElement API**   
https://github.com/yoojj/Web/blob/master/WebAPI/html/api-media-el.md


**Media Source API**    
https://github.com/yoojj/Web/blob/master/WebAPI/api-media-source.md



[top](#)
