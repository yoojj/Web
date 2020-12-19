# CSS
Cascading Style Sheets  
: 마크업 언어로 작성된 요소에 시각적 표현을 적용하기 위한 명령어 집합           
: 특정 요소를 선택하고 속성 지정       


- [CSS Level](#css-level)
    - [CSS module list](./module/)
- [CSS Load](./css-load.md)
    - [Load CSS Async](./css-load-async.md)
- [CSS Context](./css-context.md)
- [CSS Methodologies](./css-methodologies.md)
- [CSS in JS](./css-in-js.md)
- [CSS Module](./css-module.md/)    
- [CSS Preprocessor](./css-preprocessor.md)
- [CSS Framework](./css-framework.md)
- CSS Performance
    - [CSS GPU Accelerated](./css-gpu.md)
- CSS Optimization


**구성 요소**   
- 선택자
- 선언 블록
- 선언문
    - 속성
    - 속성 값


```css
@At-Rule;

/* comment */
selector {property:value;}
selector {property:value;property:value;}
selector, selector {property:value;}
```



## CSS level
: CSS는 버전이 존재하지 않고 레벨이 존재   
: CSS2 이후 빠른 표준화 진행과 브라우저 지원을 위해 CSS 사양을 모듈화하여 개별 정의      
: CSS3은 모듈화된 CSS를 지칭하고 모듈은 각각 업데이트되므로 CSS4 레벨은 존재하지 않음   


레벨 | 특징 | 스펙
---|---|---
css1   | 초기 사양으로 현재 폐기 | https://www.w3.org/TR/CSS1/
css2.x | monolithic | https://www.w3.org/TR/CSS2/
css3   | component, module | https://www.w3.org/TR/CSS/



## CSS WG
CSS working group  
: CSS 레벨 규격-명세-스펙 정의    

> 초기 초안(FPWD) > 초안(WD) > 최종 초안(LCWD) > 권고 후보(CR) > 권고안(PR) > 권고(REC)  


**영향**   
RRP, PWP, FOSI, DSSSL, PSL, CHSS, JSSS   
https://eager.io/blog/the-languages-which-almost-were-css/



[top](#)
