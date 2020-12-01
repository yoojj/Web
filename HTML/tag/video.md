# video
: 동영상 삽입을 위한 엘리먼트         


[모두를 위한 비디오 : 크록 케이먼]     
http://camendesign.com/code/video_for_everybody     


**포함 요소**
- source
- [track](./track.md)


속성 | 설명
---|---
src      | 비디오 경로 지정  
controls | 비디오 제어를 위한 패널 표시 여부 지정 (불리언 속성)
autoplay | 비디오 자동 재생 여부 지정 (불리언 속성)
loop     | 비디오 반복 재생 여부 지정 (불리언 속성)
muted    | 비디오 음소거 여부 지정 (불리언 속성)
width, height | 비디오 너비 및 높이 지정
poster   | 비디오 재생전 표시할 이미지 지정  
preload  | 비디오 리소스 로드에 대한 힌트 지정
playsinline | (불리언 속성)
crossorigin | crossorigin 요청 처리 방식 지정


```html
<video src="경로/파일.확장자" controls>
    <p>Your browser does not support the <code>video</code> element.</p>
</video>


<!-- 모든 브라우저 지원을 위해 source 태그 사용 -->
<video controls>
    <!-- type 명시는 선택 사항 -->
    <source src="경로/파일.mp4" type="audio/mp4">
    <source src="경로/파일.webm" type="audio/webm">
    <source src="경로/파일.ogg" type="audio/ogg">
    <p>Your browser does not support the <code>video</code> element </p>
</video>
```


**video format**  

포맷 | MIME 타입 | 특징
---|---|---
mp4  | video/mp4  | 대부분 브라우저에서 지원  
ogg  | video/ogg  | IE 미지원, 사파리 미지원  
webm | video/webm | 상위 버전 브라우저에서 지원  


**Media Source API**    
https://github.com/yoojj/Web/blob/master/WebAPI/api-media-source.md



[top](#)
