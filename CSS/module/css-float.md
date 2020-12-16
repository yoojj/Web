# CSS Float

https://www.w3.org/TR/css-page-floats/


속성 | 설명
---|---
float-reference | float되는 기준 지정
float | 배치되는 방법 지정
clear | float된 콘텐츠의 쌓임 방지를 위한 방법 지정
float-defer  | float 지연 방법 지정
float-offset | float된 콘텐츠의 오프셋 지정


```css
E {float-reference:inline | column | region | page;}


E {float:block-start | block-end | inline-start | inline-end |
   snap-block | snap-inline | left | right | top | bottom | none;}
/*
block-start, block-end, inline-start, inline-end
https://drafts.csswg.org/css-logical/#directional-keywords
*/


E {clear:inline-start | inline-end | block-start | block-end |
   left | right | top | bottom | none;}


E {float-defer:integer | last | none;}


E {float-offset:length | percentage;}
E {float-offset:x;}
E {float-offset:x y;}
```



[top](#)
