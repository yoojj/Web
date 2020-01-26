# video
≒ [audio](./audio.md)   
: 동영상 삽입을 위한 엘리먼트   
: video 태그를 브라우저에서 지원하지 않을 경우 플러그인 사용     


**[모두를 위한 비디오 : 크록 케이먼]**  

http://camendesign.com/code/video_for_everybody     


**포함 요소**
- source
- [track](./track.md)


속성 | 설명
---|---
autoplay | 비디오 자동 재생 여부
buffered |
controls | 비디오 제어를 위한 패널 표시
crossorigin |
loop     | 비디오 반복 재생 여부
poster   | 비디오가 재생되지 않을때 표시되는 이미지
preload  |
playsinline |
muted    | 비디오 음소거 여부  
src      | 비디오 경로
width, height | 비디오 너비 및 높이 지정



```html
<!-- 지원 여부 확인 -->
<script>
function supportsVideo(){
    return !!document.createElement('video').canPlayType;
}
</script>


<video src="경로/파일.확장자" controls>
    <p>Your browser does not support the <code>video</code> element.</p>
</video>


<!-- 모든 브라우저 지원시 source 태그 사용 -->
<video controls>
    <!-- tpye 명시는 선택 사항 -->
    <source src="경로/파일.mp4" type="audio/mp4">
    <source src="경로/파일.webm" type="audio/webm">
    <source src="경로/파일.ogg" type="audio/ogg">
    <p>Your browser does not support the <code>video</code> element </p>
</video>
```



## MSE API
Media Source Extensions   
: 적응 스트리밍을 위한 기능을 제공하는 API


```html
<script>
const video = document.getElementById('video');
const ms = new MediaSource();

const url = window.URL.createObjectURL(ms);
video.src = url;

ms.addEventListener('sourceopen', function(e) {
    ..
}, false);


// 추가
</script>
```
