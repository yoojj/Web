# CSS Scrollbar

https://www.w3.org/TR/css-scrollbars/


속성 | 설명
---|---
scrollbar-color  | 스크롤바 색 지정
scrollbar-width  | 스크롤바 너비 지정


```css
E {scrollbar-color:auto | dark | light | color;}


E {scrollbar-width:auto | thin | none | length;}
/*
- thin : auto보다 얇은 너비 지정
- none : 시각적으로 스크롤바를 숨김 (스크롤 기능은 유지됨)
*/
```


**비표준**
```css
::-webkit-scrollbar {}
::-webkit-scrollbar-button {}
::-webkit-scrollbar-corner {}
::-webkit-scrollbar-track {}
::-webkit-scrollbar-thumb {}

/* ie */
E {
    scrollbar-base-color:color;
    scrollbar-face-color:color;
    scrollbar-track-color:color;
    scrollbar-arrow-color:color;
    scrollbar-shadow-color:color;
    scrollbar-dark-shadow-color:color;
    scrollbar-highlight-color:color;
}
```



[top](#)
