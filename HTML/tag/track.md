# track
: 외국어, 스크린리더 등을 위해 동영상에 자막, 설명, 캡션, 메타 데이터를 추가하기 위한 엘리먼트  


**부모 요소**   
- [audio](./audio.md)
- [video](./video.md)


속성 | 설명
---|---
default | 트랙 활성화
kind    | 트랙 사용 방법
label   | 트랙 제목  
src     | 트랙 파일 경로  
srclang | 트랙 텍스트 언어 명시



```html
<video src="">
    <track kind="subtitles" label="English subtitles" src="파일-en.vtt" srclang="en" default></track>
    <track kind="subtitles" label="한글 자막" src="파일-ko.vtt" srclang="ko"></track>
</video>
<!--
kind
- subtitles : 기본값, 화면 표시
- captions : 화면 표시
- descriptions
- chapters
- metadata
-->
```



## WebVTT
: 자막을 위한 파일    
: 모든 브라우저에서 지원하는 형식   

1. 한 아이템을 큐라고 지칭
2. 큐는 시작 시간과 끝 시간을 갖으며 화살표로 구분
3. 공백으로 큐 구분  


```vtt
WEBVTT

큐 옵션 railroad | manuscript
큐 시작 시간 --> 큐 끝 시간
큐 자막

00:00:01.000 --> 00:00:02.000
자막
<p>html 태그 적용</p>

00:00:02.000 --> 00:00:03.000
자막
<c.some-class>스타일 적용</c>



<style type="text/css">
    ::cue .some-class {color: red;}
</style>
```


**검사기**   
https://quuz.org/webvtt/
