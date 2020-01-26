# details
: 아코디언, 토글같은 기능을 위한 엘리먼트  



```html
<details>
    <summary></summary>
</details>


<details open>
    <summary></summary>
</details>
<!-- open 속성 사용시 콘텐츠가 바로 표시됨 -->



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
