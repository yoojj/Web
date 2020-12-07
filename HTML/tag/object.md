# object
: 외부 리소스 삽입을 위한 태그  


**포함 요소**
- param


속성 | 설명
---|---
data | 리소스 url 지정
type | 리소스 MIME 타입 명시  
name | 요소 이름 지정
usemap | 이미지 맵 이름 지정  
form   | 요소와 연결될 form 태그 지정
width, height | 너비와 높이 지정


```html
<object data="example.pdf" type="application/pdf"></object>
<object data="example.swf" type="application/x-shockwave-flash"></object>


<object type="application/x-shockwave-flash">
    <param name="example" value="example.swf">
    <param name="" value="">
</object>


<object data="example.swf" type="application/x-shockwave-flash">
    <embed src="example.swf" type="application/x-shockwave-flash">
</object>
```



[top](#)
