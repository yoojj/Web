# label
: UI 관련 요소의 레이블을 위한 엘리먼트   


**사용 요소**  
- button
- [input](./input.md)
- meter
- [output](#output)
- progress
- [select](#select)
- [textarea](#textarea)


속성 | 설명
---|---
for  | 연결될 요소  
form | 레이블이 속한 양식 명시



```html
<!-- 암시적 연결 -->
<label>
    <input type="text" id="name">
</label>


<!-- 명시적 연결 -->
<label for="name">이름</name>
<input type="text" id="name">
```



[top](#)
