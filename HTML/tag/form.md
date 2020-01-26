# form
: 사용자로부터 데이터를 받아 서버로 전달하기 위한 입력 양식 엘리먼트    
: 하나 이상 입력 요소를 담고 있는 컨테이너


**포함 요소**
- fieldset
- legend
- [label](./output.md)
- [input](./input.md)
- [output](./output.md)
- [textarea](./textarea.md)
- button
- [select](./select.md)
- datalist
- [option](./option.md)
- [optgroup](./option.md#optgroup)



속성 | 설명
---|---
accept-charset | 문자 인코딩 지정
action         | 입력된 양식을 보낼 서버의 url
autocomplete   | 양식 입력시 자동 완성 기능 사용 여부 지정
enctype        | 리소스의 MIME 유형 명시, [속성 값](../html-attribute.md#media)
method         | 입력된 양식을 제출하는 방법 지정
name           | 식별을 위한 폼 이름 지정  
novalidate     | 입력된 데이터 유효성을 수행하지 않도록 지정
target         | 데이터 전달 후 응답이 열릴 위치 지정, [속성 값](../html-attribute.md#target)



```html
<form>
    <fieldset>
        <legend>그룹 설명</legend>
    </fieldset>
</form>
<!--
양식이 많을 경우 fieldset 요소를 사용해 구분-그룹화  
-->


<form accept-charset="UTF-8 ISO-8859-1 EUC-KR"></form>
<!--
: accept-charset 속성의 기본 값은 예약 문자열 UNKNOWN
: 여러 인코딩을 정의할 경우 나열된 순서대로 사용  
-->


<form autocomplete="on"></form>
<form autocomplete="off">
    <input type="text" name="user-name" autocomplete="on">
    <input type="text" name="credit-card">
</form>    
<!--
: 사용자 개인 정보에 문제되는 필드는 off 값을 사용해 캐시에 저장되지 않게 처리

- on : 기본값, 이전에 입력한 값을 기반으로 자동 완성 지원  
- off : form 전체에 자동 완성 기능을 지원하지 않음


chrome://settings/autofill
-->


<form enctype="application/x-www-form-urlencoded" method="post"></form>
<form enctype="multipart/form-data" method="post"></form>
<form enctype="text/plain" method="post"></form>
<!--
- application/x-www-form-urlencoded : 기본 값, 모든 문자가 인코딩됨
- multipart/form-data : 이미지, 파일 등과 데이터
- text/plain : 읽을 수 있는 문자열 데이터  
-->


<form method="get"></form>
<form method="post"></form>
<!--
-->



<dialog open>
    <form method="dialog"></form>
</dialog>
<!-- 양식이 제출될 때 대화 상자 close -->


<form novalidate></form>
```



[top](#)
