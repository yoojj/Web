# output
: 계산 결과나 사용자 행동 결과 등을 나타내기 위한 엘리먼트   


속성 | 설명
---|---
for  | 계산을 위한 값을 갖고 있는 요소 연결  
form | 요소가 포함될 form 명시  
name | 요소의 이름 지정



```html
<form oninput="o.value=a.valueAsNumber+b.valueAsNumber">
    <input type="range" name="a" value="50"> 50 +
    <input type="number" name="b" value="50"> =
    <output name="o" for="a b"></output>
</form>
```



[top](#)
