# input
: 데이터를 입력할 수 있는 입력 필드를 지원하는 태그  


**사용 요소**  
- [label](./label.md)
- [datalist](./datalist.md)


속성 | 설명
---|---
accept       | type이 file인 경우 파일 형식 명시
alt          | type이 image인 경우 대체 텍스트 명시
src          | type이 image인 경우 이미지의 url 지정
width, height| type이 image인 경우 너비와 높이 지정  
autocomplete | 양식 입력시 자동 완성 기능 사용 여부 지정
checked      | type이 checkbox, radio인 경우 값 선택 여부 지정 (불리언 속성)
dirname      | type이 text, search인 경우 입력된 텍스트의 방향성 명시  
disabled     | 요소의 비활성화 여부 지정 (불리언 속성)
form         | 요소와 연결될 form 태그 지정  
formaction   | tpye이 image, submit 인 경우 form의 action 값 재정의
formenctype  | tpye이 image, submit 인 경우 form의 nctype 값 재정의
formmethod   | tpye이 image, submit 인 경우 form의 method 값 재정의
formnovalidate | tpye이 image, submit 인 경우 form의 novalidate 값 재정의
formtarget   | tpye이 image, submit 인 경우 form의 target 값 재정의
list         | 요소와 연결될 datalist 태그 지정      
max, min     | 숫자 데이터의 최댓값과 최솟값 지정
maxlength    | 요소에 입력 가능한 최대 글자수 지정
minlength    | 요소에 입력 가능한 최소 글자수 지정
multiple     | type이 email, file인 경우 여러 값을 입력 받을지 여부 지정 (불리언 속성)
name         | 요소의 이름 지정
pattern      | type이 text, password, tel인 경우 유효성 검사를 위한 정규 표현식 지정  
placeholder  | 입력할 데이터에 대한 도움말이나 힌트 명시
readonly     | 읽기 전용 여부 지정 (불리언 속성)
required     | 필수 입력 여부 지정 (불리언 속성)
size         | type이 text, password, email, tel, search, url인 경우 요소의 너비 지정
step         | 숫자 데이터의 단계 값 지정
type         | 요소의 타입 지정  
value        | 요소의 초기 값 지정


```html
<input type="file" accept="image/*">
<input type="file" accept="audio/*, video/*">
<input type="file" accept=".doc, .docx, .xml">


<input type="image" src="이미지 경로" alt="이미지 설명">
<input type="image" src="" alt="" width="" height="">


<input type="text" name="user-name" autocomplete="on">
<input type="text" name="credit-card">
<!--
: type이 hidden, image, file, checkbox, radio, submit, button, reset 인 경우 무시됨
: form에 설정된 autocomplete 값이 우선 순위를 갖음
-->


<imput type="checkbox" cheched>
<imput type="radio" cheched>


<input type="text" name="값" dirname="값.dir">
<input type="search" name="값" dirname="값.dir">


<input type="all" disabled>
<!-- 해당 값을 서버로 전달하지 않음 -->


<form id="form"></form>
<input type="all" form="form">
<!-- 같은 문서 내에 있을 경우만 사용 가능 -->


<!-- form에 설정된 값보다 input의 속성 값이 우선 순위를 갖음 -->
<input type="image | submit" formenctype="application/x-www-form-urlencoded">
<input type="image | submit" formenctype="multipart/form-data">
<input type="image | submit" formenctype="text/plain">

<form action="/action1">
    <input type="image" src="" alt="" formaction="/action2">
    <input type="submit" formaction="/action3">
</form>

<input type="image | submit" formmethod="get | post">
<input type="image | submit" formtarget="">
<input type="image | submit" formnovalidate>


<input type="" list="datalistId">
<datalist id="datalistId">
    <option value="1">1</option>
    <option value="2">2</option>
    <option value="3">3</option>
</datalist>
<!-- type이 hidden, password, file, checkbox, radio, button 인 경우 무시됨 -->


<input type="date" min="1900-01-01" max="2020-01-01">
<input type="number" min="1" max="10">
<!-- max 값은 min과 같거나 커야 함 -->


<input type="text | password | email | tel | search | url" maxlength="524288">
<!-- 음수 값 지정시 기본 값이 적용됨 -->


<input type="email | file" multiple>
<!-- 쉼표로 구분해 여러 값 입력 -->


<input type="text | password | tel" pattern="[0-9]{8}" title="">
<!--
: JS 정규 표현식과 동일
: title 속성을 사용해 패턴에 대해 설명 추가

http://html5pattern.com
-->


<input type="text | password | email | tel | search | url" placeholder="">


<style>
input:read-only {}
textarea:read-write {}
</style>

<input type="" readonly>


<input type="" required>
<!-- type이 hidden, image, submit, button, reset 일 경우 무시됨 -->


<input type="text | password | email | tel | search | url" size="20">


<input type="hidden | text | password" value="초기 값 정의">
<input type="submit | button | reset" value="버튼 이름 정의">
<input type="image | checkbox | radio" value="요소와 연관되는 값 정의">
```


**input type**  
: html4 기준 10개 타입이 존재하며 html5에서 13개 새로운 타입 추가   

값 | 설명
---|---
button         | 정의된 기능이 없는 범용 버튼
checkbox       | 여러 선택 항목 중 하나 이상의 값 선택
color          | 색상을 선택할 수 있는 선택기 제공
date           | 날짜를 컨트롤하는 선택기 제공
datetime-local | 로컬 기준 날짜와 시간을 컨트롤하는 선택기 제공
email          | 이메일 입력 필드
file           | 파일을 선택할 수 있는 선택기 제공
hidden         | 숨겨진 입력 필드
image          | submit button을 이미지로 정의
month          | 날짜를 컨트롤하는 선택기 제공
number         | 숫자를 컨트롤하는 선택기 제공  
password       | 비밀번호 입력 필드로 입력된 값은 마스킹 처리
radio          | 여러 선택 항목 중 하나의 값 선택
range          | 범위 내의 숫자를 선택할 수 있는 선택기 제공  
reset          | 리셋 버튼
search         | 검색어 입력 필드
submit         | 양식 제출 버튼
tel            | 전화 번호 입력 필드
text           | 텍스트 입력 필드
time           | 시간을 컨트롤하는 선택기 제공
url            | url 입력 필드
week           | 날짜를 컨트롤하는 선택기 제공


```html
<input type="button">


<input type="checkbox" name="val" value="1" checked>
<input type="checkbox" name="val" value="2">
<input type="checkbox" name="val" value="3">


<input type="color" value="#000000">
<!-- 기본 색상 명시 -->

<input type="color" value="#000000" list="colors">
<details id="colors">
    <option>#333333</option>
    <option>#666666</option>
    <option>#999999</option>
</details>
<!-- details 요소로 색상 범위 지정 가능 -->

<!-- color 값을 지원하지 않을 경우 -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/spectrum/1.8.0/spectrum.js"></script>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/spectrum/1.8.0/spectrum.css">


<input type="date">
<!-- YYYY-MM-DD 형식 -->

<input type="date" min="2020-01-01" max="2022-01-01" value="2020-05-05">
<!-- 최소 및 최대 입력 날짜 지정 -->

<input type="date" step="2" value="2020-01-01">
<!-- 기본 값 기준으로 격일만 선택 가능 -->

<input type="date" step="7" value="2020-01-01">
<!-- 기본 값에 대응하는 요일만 선택 가능 -->


<style>
input[type='email']:valid {}
input[type='email']:invalid {background:red;}
</style>

<input type="email">
<!-- @ 와 . 입력에 대한 유효성 검사 실행 -->


<input type="email" multiple>


<input type="image" src="" alt="submit">


<input type="month">
<!-- YYYY-MM 형식 -->


<input type="number" min="0" max="10" step="2" value="0">


<input type="radio" name="val" value="1" checked>
<input type="radio" name="val" value="2">
<input type="radio" name="val" value="3">


<input type="range" min="0" max="10" step="2" value="0">
<input type="range" id="list">
<datalist id="list">
    <option>0</option>
    <option>2</option>
    <option>4</option>
    <option>6</option>
    <option>8</option>
    <option>10</option>
</datalist>

<style>
input[type='range'] {width:100px;height:20px;...}

/* 버튼 디자인 변경 */
input[type='range']::-moz-range-thumb {...}
input[type='range']::-webkit-slider-thumb {-webkit-appearance:none !important;...}
</style>
<!-- https://www.cssportal.com/style-input-range/ -->


<input type="search" results="3">
<!--
: 브라우저에 따라 내용을 삭제하는 버튼이나 검색 내용 목록 제공
: 현재 results 속성은 비표준으로 사파리 브라우저에서만 지원  
-->


<input type="tel" pattern="[0-9]{3}-[0-9]{4}-[0-9]{4}">
<!-- email과 url 타입과 달리 유효성 검사를 하지 않으므로 pattern 속성 사용 -->


<input type="url" pattern="(http|https|ftp)://[a-zA-Z0-9]*">
<!-- http:// 입력 유효성 검사 -->
```


**input step**

타입 | 스텝 단위 | 기본 값
---|---|---
date           | 일 | 1일
datetime       | 초 | 60초
datetime-local | 초 | 60초
month          | 월 | 1개월
number         | 1 | 1
range          | 1 | 1
time           | 초 | 60초
week           | 주 | 1주일


```html
<input type="" step="1">
<input type="" step="1.5" min="1" max="10">
<input type="" step="any">


<input type="date" step="1">
<input type="number" step="1" min="-10" max="10">
```



[top](#)
