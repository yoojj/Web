# CSS Transition

https://www.w3.org/TR/css-transitions/


속성 | 설명
---|---
transition | transition-* 속성 축약     
transition-property | 전환되는 요소 지정  
transition-duration | 전환되는 시간 지정
transition-timing-function | 전환되는 속도를 제어하기 위한 함수 지정  
transition-delay | 전환이 시작될 시간 지정


```css
E {transition:single-property transition-duration transition-timing-function transition-delay;}


E {transition-property:none | all | custom-ident;}
/*
다중 전환
E {transition-property:property, property;}
E {transition-duration:1ms, 1s;}
*/


E {transition-duration:time;}


E {transition-timing-function:function;}
/*
function list
https://www.w3.org/TR/css-easing/

- ease
- ease-out
- cubic-bezier()
- ...
*/


E {transition-delay:time;}
/*
전환 시간보다 작은 시간을 지정하면 애니메이션 중간 부터 전환이 바로 진행됨
*/
```


**performance**   
```css
E {will-change:property;}
E > F {position:absolute | fixed;transition-property:property;}
```



[top](#)
