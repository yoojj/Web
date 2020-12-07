# progress
: 작업의 진행 상태를 표현하기 위한 태그   

속성 | 설명
---|---
value | 작업 진행률  
max   | 전체 작업량


```html
<style>
progress {
    -webkit-appearance:none;
    -moz-appearance:none;
    appearance:none;
}

progress[value] {}
progress:not([value]) {}

::-webkit-progress-bar {}
::-moz-progress-bar {}

::-webkit-progress-value {}
::-moz-progress-value {}
</style>


<progress max="100"></progress>
<!-- value 속성이 없는 경우 미정 상태 --->


<progress max="100" value="50">
    <strong>50%</strong>
</progress>
```



[top](#)
