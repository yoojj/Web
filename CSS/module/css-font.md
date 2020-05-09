# CSS Font
https://www.w3.org/TR/css-fonts/

- @font-face
- @font-feature-values


속성 | 설명
---|---
font-family      | 글자 글꼴 지정
font-weight      | 글자 굵기나 가중치 지정  
font-stretch     | 글자 폭 설정  
font-style       | 글자 스타일 지정
font-size        | 글자 크기 지정
font-size-adjust |
font-synthesis   |
font-variant     |
font-kerning     |
font-optical-sizing   |
font-feature-settings |


```css
* {font:font-style font-variant font-weight font-stretch font-size line-height font-family;}


* {font-family:"family name", sans-serif;}


* {font-weight:normal | bold | number;}
/*
100 - Thin (Hairline)
200 - Extra Light (Ultra Light)
300 - Light
400 - Normal
500 - Medium
600 - Semi Bold (Demi Bold)
700 - Bold
800 - Extra Bold (Ultra Bold)
900 - Black (Heavy)
*/

* {font-weight:lighter | bolder;}
/* 부모 요소보다 얅거나 굵게 */


* {font-stretch:50% ~ 200% | keyword;}
/*
ultra-condensed 50%
extra-condensed 62.5%
condensed       75%
semi-condensed  87.5%
normal          100%
semi-expanded   112.5%
expanded        125%
extra-expanded  150%
ultra-expanded  200%
*/


* {font-style:normal | italic | oblique<-90deg ~ 90deg>;}
* {font-style:oblique 50deg;}


* {font-size: 100% | 1em | 1rem | 16px;}

* {font-size:xx-small | x-small | small | medium | large | x-large | xx-large | xxx-large;}
/* absolute-size */

* {font-size:larger | smaller;}
/* relative-size */
```



[top](#)
