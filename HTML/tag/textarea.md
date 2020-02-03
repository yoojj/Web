# textarea
: 여러 줄 문자열을 입력하기 위해 사용하는 태그   


속성 | 설명
---|---
autofocus    | 문서 로드시 요소에 입력 포커스
cols         | 한 줄에 표시될 문자수 지정
dirname      | 입력된 데이터-텍스트의 방향 명시
disabled     | 요소 비활성화
form         | 요소가 포함될 form 명시
maxlength    | 입력 가능한 최대 문자수 지정
minlength    | 입력해야 하는 최소 문자수 지정
name         | 요소 이름
placeholder  | 입력할 데이터에 대한 도움말, 힌트 명시
readonly     | 읽기 전용으로 직접 값 입력 불가능
required     | 필수 입력인 경우 지정
rows         | 표시될 줄 수 지정  
spellcheck   | 철자 검사 여부 지정
wrap         | 데이터 전달시 줄바꿈 여부 지정



```html
<style>
/* textarea 크기 조정 비활성화 */
textarea {resize:none;}
</style>


<textarea></textarea>
<textarea rows="10" cols="25">입력</textarea>


<label for="text">입력하세요.</label>
<textarea id="text" rows="10" cols="25">입력</textarea>


<textarea spellcheck="default">입력</textarea>
<textarea spellcheck="true">입력</textarea>
<textarea spellcheck="false">입력</textarea>


<textarea wrap="off">입력</textarea>
<textarea wrap="soft">입력</textarea>
<textarea wrap="hard" rows="10" cols="25">입력</textarea>
<!--
- soft : 입력된 데이터의 줄바꿈 처리를 하지 않음
- hard : cols 속성을 기준으로 줄바꿈 처리  
-->
```



[top](#)
