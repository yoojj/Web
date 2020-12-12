# CSS Text Decor

https://www.w3.org/TR/css-text-decor/  
https://drafts.csswg.org/css-text-decor/     


속성 | 설명
---|---
text-decoration       | text-decoration-* 속성 축약
text-decoration-line  | 텍스트에 선 장식 지정
text-decoration-style | 선 장식의 스타일 지정
text-decoration-color | 선 장식의 색 지정
text-underline-position | 밑줄의 위치 지정
text-emphasis           | text-emphasis-* 속성 축약  
text-emphasis-style     | 텍스트에 강조 표현 방법 지정  
text-emphasis-color     | 강조 장식의 스타일 지정  
text-emphasis-position  | 강조 장식의 위치 지정  
text-shadow | 텍스트에 그림자 효과 지정  


```css
E {text-decoration:text-decoration-line text-decoration-style text-decoration-color;}


E {text-decoration-line:none | underline | overline | line-through | blink;}
/*
blink : 유저 에이전트에 따라 텍스트가 깜박거리는 효과  
*/


E {text-decoration-style:solid | double | dotted | dashed | wavy;}


E {text-underline-position:auto | under | left | right;}


E {text-emphasis:text-emphasis-style text-emphasis-color;}


E {text-emphasis-style:none | filled | open | dot | circle | double-circle | triangle | sesame | string;}
/*
- •  filled circle
- ◦  open open
- ◉  filled double-circle
- ◎  open double-open
*/


E {text-emphasis-color:color;}


E {text-emphasis-position:over | under | left | right;}


E {text-shadow:none | color;}
E {text-shadow:top left blur color;}
E {text-shadow:1px 1px 1px rgb(0 0 0 .5);}
```



[top](#)
