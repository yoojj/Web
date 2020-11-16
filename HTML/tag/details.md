# details
: 아코디언, 토글같은 기능을 위한 태그    
! ie에서 사용시 details-polyfill 필요    

https://html.spec.whatwg.org/multipage/interactive-elements.html#the-details-element



**자식 요소**
- summary : 요소에 대한 요약, 레이블


```html
<details>
    <summary></summary>
</details>


<!-- open 속성 사용시 콘텐츠가 바로 표시됨 -->
<details open>
    <summary></summary>
</details>



<details>
    <summary>click</summary>
    <p>contents</p>
</details>

<style>
details {width:500px;border:1px solid #333;}
summary {color:red;}
details[open] summary::-webkit-details-marker {background:green;}
</style>
```



[top](#)
