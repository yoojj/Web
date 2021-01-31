# List

- [ol](#ol)
- [ul](#ul)
- [menu](#menu)
- [dl](#dl)



## ol
: 순서있는 리스트

**포함 요소**   
- li
- script
- template

속성 | 설명
---|---
type  | 마커 종류 지정
start | 리스트 시작 값 지정
reversed | 리스트를 내림차순으로 지정 (불리언 속성)


```html
<ol type="1 | a | A | i | I">
    <li>a
    <li>b
    <li>c
</ol>

<ol start="10">
    <li>a
    <li>b
    <li>c
</ol>

<ol reversed>
    <li>a
    <li>b
    <li>c
</ol>
```



## ul
: 순서없는 리스트    
: html5 기준으로 전역 속성만 지원   

**포함 요소**   
- li
- script
- template


```html
<ul>
    <li>a
    <li>b
    <li>c
</ul>
```



## menu

```html
<menu>
    <li>a
    <li>b
    <li>c
<menu>
```



## li
: 리스트의 항목을 나타내는 태그

**부모 요소**   
- ol
- ul
- menu


속성 | 설명
---|---
value | 서수값으로 부모 요소가 ol인 경우에만 사용 가능

```html
<ol>
    <li value="10">a
    <li>b
    <li>c
</ol>
```



## dl
: 정의 리스트
: 용어와 용어에 대한 설명이 있는 리스트  
: html5 기준 키/값으로 표현되는 콘텐츠를 나타내기 위한 태그    

**포함 요소**
- dt
- dd
- div
- script
- template


```html
<dl>
    <div>
        <dt>name
        <dd>vlaue
    </div>
</dl>
```



[top](#)
