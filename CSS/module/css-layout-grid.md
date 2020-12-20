# CSS Grid Layout

https://www.w3.org/TR/css-grid/   


속성 | 설명
---|---
grid   | grid-template-*, grid-auto-* 속성 축약
grid-template-columns |
grid-template-rows    |
grid-template-areas   |
grid-template     |
grid-auto-columns |
grid-auto-rows    |
grid-auto-flow    |
grid-row          | grid-row-* 속성 축약
grid-column       | grid-column-* 속성 축약
grid-row-start    |
grid-row-end      |
grid-column-start |
grid-column-end   |
grid-area         |


**grid container**   
: display이 속성이 grid 또는 inline-grid인 박스   


**grid item**   
: 그리드 컨테이너의 자식   
: 일부 속성이 적용되지 않음 (float, clear, vertical-align, ::first-line, ::first-letter)


```css
E {display:grid | inline-grid;}


E {grid-template-columns:none | <track-list> | <auto-track-list> | subgrid;}


E {grid-template-rows:none | <track-list> | <auto-track-list> | subgrid;}


E {grid-template-areas:none | string;}


E {grid-template:;}


E {grid-auto-columns, grid-auto-rows}


E > F {
    grid-row:grid-row-start grid-row-end;
    grid-column:grid-column-start grid-column-end;
}


E > F {
    grid-row-start:<grid-line>;
    grid-row-end:<grid-line>;
    grid-column-start:<grid-line>;
    grid-column-end:<grid-line>;
}


E > F {grid-area:<grid-line>;}
```



[top](#)
