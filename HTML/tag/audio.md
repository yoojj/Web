# audio
≒ [video](./video.md)      
: 오디오 재생을 위해 사용하는 태그  
: 브라우저에 코덱을 내장시켜 문서에서 오디오 재생       
: mp3, ogg, wav 등 오디오 형식을 지원하며 브라우저 별 지원 코덱이 다름   


**포함 요소**
- source
- [track](./track.md)


속성 | 설명
---|---
autoplay | 오디오 자동 재생 여부
controls | 오디오 제어를 위한 패널 표시
crossorigin |
loop     | 오디오 반복 재생 여부
muted    | 오디오 음소거 여부  
preload  | 문서 로드시 오디오 파일도 함께 다운로드 
src      | 오디오 경로
volume   | 오디오 재생 볼륨 설정 (0.0 ~ 1.0)


```html
<audio src="경로/파일.확장자" controls>
    <p>Your browser does not support the <code>audio</code> element.</p>
</audio>


<!-- 모든 브라우저 지원시 source 태그 사용 -->
<audio controls>
    <!-- tpye 명시는 선택 사항 -->
    <source src="경로/파일.mp3" type="audio/mp3">
    <source src="경로/파일.ogg" type="audio/ogg">
    <source src="경로/파일.wav" type="audio/wav">
    <p>Your browser does not support the <code>audio</code> element.</p>
</audio>


<!-- 속성 적용 -->
<audio src="경로/파일.확장자" controls loop autoplay>    
    <p>Your browser does not support the <code>audio</code> element.</p>
</audio>


<!-- 하위 브라우저 지원 -->
<audio controls>
    <source src="경로/파일.확장자">
    <source src="경로/파일.확장자">
    <source src="경로/파일.확장자">

    <!-- object 사용 -->
    <object type="application/x-shockwave-flash" data="경로/파일.확장자">
        <param name="" value="" />
    </object>
</audio>
```



## html5 audio format


포맷 | MIME 타입 | 특징
---|---|---
mp3  | audio/mp3  | 대부분 브라우저에서 지원  
wav  | audio/wav  | IE 미지원
ogg  | audio/ogg  | IE 미지원, 사파리 미지원  
webm | audio/webm | 상위 버전 브라우저에서 지원  




[top](#)
