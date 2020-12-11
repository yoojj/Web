# CSS Color
: 텍스트 콘텐츠의 전경색(foreground color)과 불투명도(opacity) 지정을 위한 속성들      

https://www.w3.org/TR/css-color/   
https://www.w3.org/TR/css-color-5/


**at rule**
- @color-profile


속성 | 설명
---|---
color   | 텍스트 콘텐츠의 전경색 지정  
opacity | 텍스트 콘텐츠의 불투명도 지정  


```css
/* color keyword */
E {color:transparent | currentcolor | inherit;}
/*
! current-color는 SVG에서 사용하는 속성
*/


/* named color (https://www.w3.org/TR/css-color/#named-colors) */
E {color:red;}


/* hex color */
E {color:#ff0000;}


/* color-function : RGB */
E {color:rgb(255 0 0 .5);color:rgb(100% 0% 0% .5);}
E {color:rgba(255 0 0 .5);}


/* color-function : HSL */
E {color:hsl(0 100% 50% .5);}
E {color:hsla(0 100% 50% .5);}


/* color-function : HWB */
E {color:hwb(0 0% 0%);}


/* color-function : LCH */
E {color:lch();}


/* color-function : color() */
E {color:color(display-p3 1 0 0);}

@color-profile --example {src:url('');}
E {color:color(example 0 0 0);}
```


**Hexadecimal**   
: 16 진수 색상 표기법   
: 3, 4, 6, 8자리 숫자로 색상을 표현     

```css
E {color:#RRGGBB;}
E {color:#RGB;}

/* alpha */
E {color:#RRGGBBCC;}
E {color:#RGBC;}
```


**RGB**   
- rgb(red green blue)
- rgba(red green blue alpha)


**HSL**    
: 색상의 채도나 명도 변경 가능   
: 색상 = 0 ~ 359도로 표현 (0이면 빨강색, 120이면 초록색, 240이면 파란색)     
: 채도 = 0 ~ 100% (100%면 실제 색상, 0%면 회색)  
: 명도 = 0 ~ 100% (50%면 실제 색상, 0%면 검은색, 100%면 흰색)

- hsl(hue saturation lightness / alpha)
- hsla(hue saturation lightness alpha)


**HWB**
- hwb(hue whiteness blackness)


**LCH**
- lch(lightness chroma hue)

https://css.land/lch/



[top](#)
