# audio
: 사운드 콘텐츠 삽입을 위한 태그         


**포함 요소**
- [source](./source.md)
- [track](./track.md)


속성 | 설명
---|---
src      | 오디오 경로 지정
controls | 오디오 제어를 위한 패널 표시 여부 지정 (불리언 속성)
autoplay | 오디오 자동 재생 여부 지정 (불리언 속성)
loop     | 오디오 반복 재생 여부 지정 (불리언 속성)
muted    | 오디오 음소거 여부 지정 (불리언 속성)
preload  | 오디오 리소스 로드에 대한 힌트 지정
crossorigin | crossorigin 요청 처리 방식 지정


```html
<audio src="경로/파일.확장자" controls>
    <p>Your browser does not support the <code>audio</code> element.</p>
</audio>


<audio src="경로/파일.확장자" preload="auto | metadata | none">
    <p>Your browser does not support the <code>audio</code> element.</p>
</audio>
<!--
- auto : 재생하지 않아도 리소스를 미리 로드함
- metadata : 리소스의 메타데이터만 로드하고 none 값과 동일   
- none : 재생하기 전까지 리소스를 로드하지 않음
-->


<!-- 다중 지원을 위해 source 태그 사용 -->
<audio controls>
    <!-- type 명시는 선택 사항 -->
    <source src="경로/파일.mp3" type="audio/mp3">
    <source src="경로/파일.ogg" type="audio/ogg">
    <source src="경로/파일.wav" type="audio/wav">
    <p>Your browser does not support the <code>audio</code> element.</p>
</audio>


<!-- 하위 브라우저 지원 -->
<audio controls>
    <source src="경로/파일.확장자">

    <!-- IE 8 경우 플래시를 지원하므로 플래시 사용 -->
    <object type="application/x-shockwave-flash" data="경로/파일.확장자">
        <param name="" value="" />
    </object>
</audio>
```


**HTMLAudioElement API**    
https://github.com/yoojj/Web/blob/master/WebAPI/html/api-audio-el.md


**Audio API**   
https://github.com/yoojj/Web/blob/master/WebAPI/api-audio.md



[top](#)
