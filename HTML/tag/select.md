# select
: 드롭 다운 리스트 UI를 제공하는 태그  


**포함 요소**  
- [option](./option.md)
- [optgroup](./option.md#optgroup)


속성 | 설명
---|---
autofocus | 문서 로드시 요소에 선택 포커스
disabled  | 요소 비활성화
form      | 요소가 포함될 form 명시
multiple  | 여러 옵션 선택시 정의
name      | 요소 이름
required  | 필수 선택인 경우 지정
size      | 보여질 옵션 수 정의



```html
<select size="3"></select>


<select>
    <option value="1" selected>1</option>
    <option value="2">2</option>
    <option value="3">3</option>
</select>


<select>
    <optgroup label="a">
        <option value="1">1</option>
    </optgroup>
    <optgroup label="b">
        <option value="1">1</option>
    </optgroup>
</select>
```



[top](#)
