# CSS Font
https://www.w3.org/TR/css-fonts/


**at rule**
- [@font-face](#@font-face)


속성 | 설명
---|---
font             | font-* 속성 축약
font-family      | 글자의 글꼴 지정
font-weight      | 글자의 굵기나 가중치 지정  
font-stretch     | 글자의 폭 지정  
font-style       | 글자의 스타일 지정
font-size        | 글자의 크기 지정
font-size-adjust | 글자의 크기 조정 지정
font-synthesis   | font-synthesis-* 속성 축약
font-synthesis-weight | 글꼴을 합성 여부 지정  
font-synthesis-style  | 글꼴을 합성 여부 지정  
font-synthesis-small-caps | 글꼴을 합성 여부 지정  
font-display           |
font-kerning           |
font-variant           | font-variant-* 속성 축약
font-variant-ligatures |
font-variant-position  |
font-variant-caps      | 글자의 대소문자 처리 방법 지정
font-variant-numeric   |
font-variant-alternates|
font-variant-east-asian|
font-feature-settings  | 글꼴 기능 초기 설정 지정
font-language-override |
font-optical-sizing    |
font-variant-settings  | 글꼴 변형 초기 설정 지정
font-palette           |


```css
E {font:font-style font-variant font-weight font-stretch font-size line-height font-family;}


E {font-family:"font name", font-name, sans-serif;}
/*
- serif : 획 끝에 장식이 있는 형태
- sans-serif : 획 끝에 장식이 없는 형태
- cursive : 필기체   
- fantasy : 장식체
- monospace : 글자의 폭이 일정한 형태
- system-ui : 운영체제의 시스템 폰트  
*/


E {font-weight:normal | bold | lighter | bolder | number;}
/*
- normal = 400
- bold = 700
- lighter : 상속된 값 보다 얇게  
- bolder : 상속된 값 보다 굵게

100 - Thin
200 - Extra Light (Ultra Light)
300 - Light
400 - Normal
500 - Medium
600 - Semi Bold (Demi Bold)
700 - Bold
800 - Extra Bold (Ultra Bold)
900 - Black (Heavy)
*/


E {font-stretch:50% ~ 200% | keyword;}
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


E {font-style:normal | italic | oblique<-90deg ~ 90deg>;}
/*
oblique
: 글자의 기울어진 형태 표현
*/


E {font-size: absolute-size | relative-size | length;}
/*
absolute-size
- xx-small
- x-small
- small
- medium
- large
- x-large
- xx-large
- xxx-large

relative-size
- larger : 상위 요소의 값 보다 크게
- smaller : 상위 요소의 값 보다 작게

length
- 100%
- 16px
- 1em
- 1rem
*/


E {font-size-adjust:none | number;}
/*
: 브라우저에서는 지원하지 않는 속성  
: 모바일 기기에서 뷰포트가 변할 경우 자동으로 글자 크기를 변경함

- none : 글자의 크기를 변경하지 않음
*/


E {font-synthesis:auto | none;}


E {font-synthesis-weight:auto | none;}
/*
auto
: font-family로 지정한 글꼴이 굵은 글꼴을 지원하지 않는 경우 글꼴을 합성함
*/


E {font-synthesis-style:auto | none;}
/*
auto
: font-family로 지정한 글꼴이 기울어지는(oblique) 글꼴을 지원하지 않는 경우 글꼴을 합성함
*/


E {font-synthesis-small-caps:auto | none;}
/*
auto
: font-family로 지정한 글꼴이 작은 대문자를 지원하지 않는 경우 글꼴을 합성함
*/


E {font-variant-caps:normal | small-caps | all-small-caps;}
/*
- small-caps : 첫 단어를 제외하고 소문자 크기를 기준으로 모든 글자 대문자로 변경  
- all-small-caps : 소문자 크기를 기준으로 모든 글자를 대문자로 변경
*/
```



## @font-face

- @font-feature-values
- @font-palette-values


```css
@font-face {
    <declaration-list>
}


/* 필수 */
@font-face {
    font-family:"font-name";
    src:url("font-name.eot");
    src:local("※"),
        url("font-name.eot?#iefix") format("embedded-opentype"),
        url("font-name.woff2") format("woff2"),
        url("font-name.woff") format("woff"),
        url("font-name.ttf") format("truetype"),
        url("font-name.svg#svgFontName") format("svg");
}

/* 옵션 */
@font-face {
    font-style:<font-style-value>;
    font-weight:<font-weight-value>;
    font-stretch:<font-stretch-value>;
    unicode-range:urange;
    font-feature-settings:normal | <feature-tag-value>;
    font-variation-settings:normal | string;
    font-named-instance:auto | string;
    font-display:auto | block | swap | fallback | optional;
    font-language-override:normal | string;
    ascent-override:normal | percentage;
    descent-override:normal | percentage;
    line-gap-override:normal | percentage;
}


@font-feature-values {
    font-display:auto | block | swap | fallback | optional;
}
```

font format    
https://www.w3.org/TR/css-fonts/#font-face-src-format-types



[top](#)
