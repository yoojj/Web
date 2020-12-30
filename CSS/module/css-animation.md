# CSS Animation

https://www.w3.org/TR/css-animations/   
https://www.w3.org/TR/web-animations/


**at rule**
- @keyframes : 키 프레임 제어


속성 | 설명
---|---
animation | animation-* 속성 축약
animation-name     | 프레임 제어를 위한 식별자 지정  
animation-duration | 애니메이션 시간 지정
animation-timing-function | 프레임이 진행되는 방법 지정
animation-iteration-count | 애니메이션 반복 횟수 지정
animation-direction  | 애니메이션이 반복될 경우 재생될 방향 지정
animation-play-state | 애니메이션의 재생이나 정지 상태 지정
animation-delay      | 애니메이션이 시작될 시간 지정
animation-fill-mode  | 애니메이션 시작 전이나 후에 적용될 값 지정  


**프레임**  
: 애니메이션을 구성하는 정지 장면    
: 애니메이션이란 프레임을 연속적으로 보여주는 것    


**키 프레임 애니메이션**  
: 애니메이션 중에서 몇 개 프레임을 선택해 키를 부여해 이를 제어하고   
&nbsp; 나머지 프레임은 자동으로 동작하는 방식의 애니메이션   


```css
E {animation:duration function count direction fill-mode play-state name;}


E {animation-name:none | custom-ident;}
/*
none
: 애니메이션 없음

string
: @keyframes이 없으면 애니메이션이 시작되지 않음
: 요소의 display 속성이 none이면 애니메이션이 적용되지 않음


E {animation-name:example;}
F {animation-name:example;}

@keyframes example {
    키 프레임을 백분률로 지정
    0% {}
    50% {}
    100% {}

    from { 0%와 동일 }
    to { 100%와 동일 }
}
*/


E {animation-duration:time;}


E {animation-timing-function:<timing-function>;}
/*
timing-function
https://github.com/yoojj/Web/blob/master/CSS/module/css-easing.md

- ease
- ease-out
- cubic-bezier()
- ...


E {
    animation-name:example;
    animation-timing-function:ease;
}

@keyframes example {
    from {
        animation-timing-function:ease;
    }
    to {
        animation-timing-function:ease;
    }
}
*/


E {animation-iteration-count:infinite | number;}


E {animation-direction:normal | reverse | alternate | alternate-reverse;}
/*
- alternate : 홀수 번째는 순방향으로 짝수 번째는 역방향으로 진행
- alternate-reverse : 홀수 번째는 역방향으로 짝수 번째는 순방향으로 진행

E {
    animation-iteration-count:3;
    animation-direction:alternate;
}
*/


E {animation-play-state:running | paused;}
/*
E.style.animationPlayState = 'running';
E.style.animationPlayState = 'paused';
*/


E {animation-delay:time;}


E {animation-fill-mode:none | forwards | backwards | both;}
/*
both = forwards + backwards
*/
```



[top](#)
