# textarea
: 여러 줄 텍스트를 입력할 수 있는 입력 필드를 지원하는 태그


속성 | 설명
---|---
autocomplete | 양식 입력시 자동 완성 기능 사용 여부 지정
cols         | 한 줄에 표시될 문자 수 지정
dirname      | 입력된 텍스트의 방향성 명시
disabled     | 요소의 비활성화 여부 지정 (불리언 속성)
form         | 요소와 연결될 form 태그 지정  
maxlength    | 입력 가능한 최대 문자 수 지정
minlength    | 입력해야 할 최소 문자 수 지정
name         | 요소 이름 지정
placeholder  | 입력할 텍스트에 대한 도움말이나 힌트 명시
readonly     | 읽기 전용 여부 지정 (불리언 속성)
rows         | 표시될 줄 수 지정  
wrap         | 텍스트 전달시 줄바꿈 여부 지정



```html
<style>
/* 크기 조정 비활성화 */
textarea {resize:none;}
</style>


<textarea rows="10" cols="25">입력</textarea>
<!-- 기본 값은 rows=2 cols=20 -->

<label for="text">입력하세요.</label>
<textarea id="text" rows="10" cols="25">입력</textarea>


<textarea wrap="off">입력</textarea>
<textarea wrap="soft">입력</textarea>
<textarea wrap="hard" rows="10" cols="25">입력</textarea>
<!--
- soft : 입력된 데이터의 줄바꿈 처리를 하지 않음
- hard : cols 속성을 기준으로 줄바꿈 처리  
-->
```



[top](#)
