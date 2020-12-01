# audio
: 사운드 콘텐츠를 위한 엘리먼트        
: 브라우저에 코덱을 내장시켜 사운드 재생       
: mp3, ogg, wav 등 형식을 지원하며 브라우저 별 지원 코덱이 다름   


**포함 요소**
- source
- [track](./track.md)


속성 | 설명
---|---
src      | 오디오 경로 지정
controls | 오디오 제어를 위한 패널 표시 여부 지정 (불리언 속성)
autoplay | 오디오 자동 재생 여부 지정 (불리언 속성)
loop     | 오디오 반복 재생 여부 지정 (불리언 속성)
muted    | 오디오 음소거 여부 지정 (불리언 속성)
preload  | 리소스 로드 여부 지정  
crossorigin | crossorigin 요청 처리 방식 지정


```html
<audio src="경로/파일.확장자" controls>
    <p>Your browser does not support the <code>audio</code> element.</p>
</audio>


<!-- 모든 브라우저 지원을 위해 source 태그 사용 -->
<audio controls>
    <!-- type 명시는 선택 사항 -->
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


<audio src="경로/파일.확장자" preload="auto | metadata | none">
    <p>Your browser does not support the <code>audio</code> element.</p>
</audio>
<!--
- auto : 재생하지 않아도 오디오 리소스를 미리 로드함
- metadata : 오디오의 메타데이터만 가져옴  
- none : 오디오 리소스를 미리 로드하지 않음
-->
```


**audio format**

포맷 | MIME 타입 | 특징
---|---|---
mp3  | audio/mp3  | 대부분 브라우저에서 지원  
wav  | audio/wav  | IE 미지원
ogg  | audio/ogg  | IE 미지원, 사파리 미지원  
webm | audio/webm | 상위 버전 브라우저에서 지원  


**Audio API**   
https://github.com/yoojj/Web/blob/master/WebAPI/api-audio.md



[top](#)
