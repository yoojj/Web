# label
: 입력 양식 요소의 목적을 설명하기 위한 태그   
: 요소와 레이블은 암시적 또는 명시적으로 연결되어야 함   


**사용 요소**  
- [input](./input.md)
- [output](./output.md)
- [textarea](./textarea.md)
- [button](./button.md)
- [select](./select.md)
- meter
- progress


속성 | 설명
---|---
for  | 연결될 요소 명시


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


**aria-label**  
: 양식 요소의 목적을 설명할 문자열 지정   
: 문자열이 시각적으로 표현되지 않는 경우 사용     


**aria-labelledby**   
: 다른 요소를 양식 요소와 연결하여 레이블로 사용   


```html
<!-- label -->
<label for="searchInput">Search</label>
<input type="text" id="searchInput">


<!-- aria-label -->
<input type="text" aria-label="Search">


<!-- aria-labelledby -->
<span id="searchIabel">Search</span>
<input type="text" aria-labelledby="searchIabel">

<form id="userForm">
    <span id="nameInput">name</span>
    <input type="text" aria-labelledby="userForm nameInput">
</form>
```



[top](#)
