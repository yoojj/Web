# button
: input과 동일한 역할을 하며 input과 달리 버튼 디자인을


속성 | 설명
---|---
disabled     | 요소 비활성화 여부 지정 (불리언 속성)
form         | 요소와 연결될 form 태그 지정  
formaction   | form의 action 값 재정의
formenctype  | form의 nctype 값 재정의
formmethod   | form의 method 값 재정의
formnovalidate | form의 novalidate 값 재정의
formtarget   | form의 target 값 재정의
name         | 요소 이름 정의  
type         | 요소 타입 지정  
value        | 요소와 관련된 값 지정   


```html
<button type="submit | reset | button">btn</button>
<!--
: 브라우저 별 type 기본 값이 다르므로 명시하는 편이 좋음  
: submit, reset은 input tpye의 submit, reset과 동일한 기능

- submit : 양식 제출
- reset : 양식 리셋
- button : 특별한 기능 없음
-->
```


**button vs input**  
```html
<style>
button::after {display:inline;content:"after";}
input::after {display:inline;content:"not work";}
</style>

<button type="submit">
    <img src="" alt="button">
</button>

<input type="submit">
```


## aria

```html
<label for="btn">
    <button type="button" id="btn">btn</button>
</label>


<!-- aria-label -->
<button type="button" aria-label="btn"></button>


<!-- aria-labelledby -->
<span id="btn">btn</span>
<button type="button" aria-labelledby="btn"></button>
```



[top](#)
