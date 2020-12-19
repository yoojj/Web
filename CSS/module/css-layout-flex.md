# CSS Flex Layout

https://www.w3.org/TR/css-flexbox/


속성 | 설명
---|---
flex-flow      | flex-flow, flex-wrap 속성 축약
flex-direction | 플렉스 아이템이 배치될 방향 지정
flex-wrap      | 플렉스 아이템이 플렉스 컨테이너를 벗어날 경우 배치될 방법 지정  
order          | 플렉스 아이템이 배치될 순서 지정  
flex           | flex-grow, flex-shrink, flex-basis 속성 축약
flex-grow      | 플렉스 아이템이 할당 받을 공간 정도 지정
flex-shrink    | 플렉스 아이템 크기 축소 여부 지정
flex-basis     | 플렉스 아이템 초기 크기 지정  
justify-content| 플렉스 아이템의 수평 방향 정렬 방법 지정  
align-items    | 플렉스 아이템의 수직 방향 정렬 방법 지정  
align-self     | 해당 플렉스 아이템의 수직 방향 정렬 방법 지정  
align-content  |   


**flex container**   
: display이 속성이 flex 또는 inline-flex인 박스   
: flexbox에서 부모가 되는 박스  
: 일부 속성이 적용되지 않음 (::first-line, ::first-letter)


**flex items**  
: 플렉스 컨테이너의 콘텐츠   
: flexbox에서 자식이 되는 박스  
: 일부 속성이 적용되지 않음 (float, clear, vertical-align, ::first-line, ::first-letter)


```html
<tag style="display:flex">
    <block-tag-item></block-tag-item>
    <inline-tag-item></inline-tag-item>
    text-item

    <not-item style="display:none"></not-item>
    <not-item style="display:contents"></not-item>
    <not-item style="display:absolute;"></not-item>
    <not-item style="display:fixed;"></not-item>
</tag>


<style>
E {display:flex | inline-flex;}
/*
- flex : 블록 플렉스 컨테이너 생성
- inline-flex : 인라인 플렉스 컨테이너 생성
*/


E {flex-flow:flex-direction flex-wrap;}


E {flex-direction:row | row-reverse | column | column-reverse;}
/*
- row : 쓰기 모드의 인라인 측 방향
- column : 쓰기 모드의 블록 측 방향

쓰기 모드
https://www.w3.org/TR/css-writing-modes/#writing-mode
*/


E {flex-wrap:nowrap | wrap | wrap-reverse;}
/*
- nowrap : 플렉스 아이템이 플렉스 컨테이너를 벗어나도 한 줄로 배치
- wrap : 플렉스 아이템이 플렉스 컨테이너를 벗어날 경우 여러 줄에 배치
- wrap-reverse : wrap처럼 작동하나 플렉스 아이템의 배치 순서가 반대로 됨
*/


E > F {order:length;}
/*
: 시각적 순서에만 영향을 미치며 플렉스 아이템이 아닌 경우 적용되지 않음
*/


E > F {flex:flex-grow flex-shrink flex-basis;}


E > F {flex-grow:number;}
/*
: 플렉스 컨테이너 내부에 형성된 빈 공간을 flex-grow 속성에 따라 플렉스 아이템에게 반영
: 빈 공간이 없다면 flex-grow 속성 값은 반영되지 않음

E {display:flex;width:500px;}
E > F1 {flex-grow:2;} width = (500/4)*2
E > F2 {flex-grow:1;} width = (500/4)*1
E > F3 {flex-grow:1;} width = (500/4)*1
*/


E > F {flex-shrink:number;}
/*
: 플렉스 아이템 크기가 플렉스 컨테이너를 벗어날 경우 축소 여부 지정

- 0 : 축소하지 않음
- 1 : 축소
*/


E > F {flex-basis:content | width;}


E {justify-content:flex-start | flex-end | center | space-between | space-around;}


E {align-items:flex-start | flex-end | center | baseline | stretch;}


E > F {align-self:auto | flex-start | flex-end | center | baseline | stretch;}


E {align-content:flex-start | flex-end | center | space-between | space-around | stretch;}
</style>
```



[top](#)
