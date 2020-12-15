# CSS Overflow

https://www.w3.org/TR/css-overflow/


**overflow**   
: 박스의 콘텐츠가 박스를 벗어 날 경우    

- ink overflow
- scrollable overflow


속성 | 설명
---|---
overflow    | overflow-* 속성 축약
overflow-x  | 수평 방향으로 오버플로우 될 경우 처리 방법 지정
overflow-y  | 수직 방향으로 오버플로우 될 경우 처리 방법 지정
overflow-inline |
overflow-block  |
text-overflow   |
block-ellipsis  |
line-clamp      |
max-lines       |
continue        |


```css
E {overflow:overflow-x overflow-y;}
E {overflow:visible | hidden | clip | scroll | auto;}
/*
- hidden : 오버플로우된 콘텐츠를 숨기며 스크립트를 통해 스크롤 박스가 될 수 있음
- clip : 오버플로우된 콘텐츠를 숨기며 스크립트를 통해 스크롤 박스가 될 수 없음
- scroll : 오버플로우 여부와 상관없이 스크롤 박스가 됨


E {overflow:clip;}
E {overflow-clip-margin:length;}
*/


E {text-overflow:clip | ellipsis;}


E {block-ellipsis:none | auto | string;}


E {line-clamp:none | integer;}


E {max-lines:none | integer;}


E {continue:auto | discard;}
```



[top](#)
