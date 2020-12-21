# source
: 미디어 리소스의 다양한 포맷을 지원하기 위한 태그   


**부모 요소**  
- [audio](./audio.md)
- [video](./video.md)
- picture


속성 | 설명
---|---
src    | 미디어 리소스의 경로 지정
type   | 미디어 리소스의 MIME 유형 지정  
srcset | 해상도 별 사용할 이미지 목록 지정
sizes  | 레이아웃 별 사용할 이미지의 크기 목록 지정  
media  | 미디어 타입 지정


ex.
```html
<video controls>
    <source src="경로/파일.mp4" type="audio/mp4">
    <source src="경로/파일.webm" type="audio/webm">
    <source src="경로/파일.ogg" type="audio/ogg">
    <p>Your browser does not support the <code>video</code> element.</p>
</video>
```



[top](#)
