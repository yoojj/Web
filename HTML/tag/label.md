# label
: UI 관련 요소의 목적을 설명하기 위한 태그   
: 요소와 레이블은 암시적 또는 명시적으로 연결되어 있어야 함   


**사용 요소**  
- [button](./button.md)
- [input](./input.md)
- [output](./output.md)
- [select](./select.md)
- [textarea](./textarea.md)
- meter
- progress


속성 | 설명
---|---
for  | 연결될 요소  
form | 레이블이 속한 form 명시



```html
<!-- 명시적 연결 -->
<label for="name">이름</name>
<input type="text" id="name">


<!-- 암시적 연결 -->
<label>
    이름
    <input type="text" id="name">
</label>
```



## aria

```html
<!-- label -->
<label for="search">Search</label>
<input type="text" id="search">
<button type="submit">Search</button>


<!-- aria-label -->
<input type="text" aria-label="Search">
<button type="submit">Search</button>


<!-- aria-labelledby -->
<input type="text" aria-labelledby="search-button">
<button id="search-button" type="submit">Search</button>
```



[top](#)
