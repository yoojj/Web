# CSS Content

https://www.w3.org/TR/css-content/


속성 | 설명
---|---
content | 가상 엘리먼트를 통해 렌더링 될 콘텐츠 지정
quotes  | 텍스트에 인용 부호 지정  
bookmark-level | 북마크 생성 여부 지정
bookmark-label |
bookmark-state |


**function**
- leader()
- target-counter()
- target-counters()
- target-text()
- string()
- content()


```css
::before,
::after,
::marker {content:none | normal | content-list | string | counter;}
/*
content-list
: 텍스트, 이미지, 이모지 등의 한 개 이상의 콘텐츠 목록

E {content:none | normal;}
E::before {content:contents;}
*/


E {quotes:none | auto | string;}
/*
- open-quote
- close-quote
- no-open-quote
- no-close-quote

q {quotes:"start:" ":end";}

q::after {content:open-quote;}
q::after {content:no-close-quote;}
*/


E {bookmark-level:none | length;}
```



[top](#)
