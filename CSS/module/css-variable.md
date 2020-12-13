# CSS Variable

https://www.w3.org/TR/css-variables/


속성 | 설명
---|--
--* | 사용자 정의 속성 지정


**function**
- var()


```css
E {--custom-property-name:value;}
/*
:root {--red-color:red;}
E {color:val(--red-color);}

사용자 정의 속성이 유효하지 않을 경우 다음 값이 적용됨
E {color:val(--custom-color), orange, yellow;}
*/
```



[top](#)
