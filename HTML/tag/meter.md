# meter
: 특정 범위의 백분률을 나타내기 위한 태그


속성 | 설명
---|---
value     | 현재 값 지정
min, max  | 범위 지정  
low, high | 범위 중 최댓값과 최솟값 지정  
optimum   | 최적 값 지정


```html
<style>
meter {
    -webkit-appearance:none;
    -moz-appearance:none;
    appearance:none;
}

::-webkit-meter-bar {}
::-webkit-meter-optimum-value {}
::-webkit-meter-suboptimum-value {}
::-webkit-meter-even-less-good-value {}

::-moz-meter-bar {}
::-moz-meter-optimum {}
::-moz-meter-sub-optimum {}
::-moz-meter-sub-sub-optimum {}
</style>


<meter min="0" max="100" value="50"></meter>
<!--
: value 값은 min과 max 사이
: 기본 값은 0이며 잘못된 값을 지정하는 경우 기본 값 적용  
-->


<meter min="0" max="1" low="10" high="90"></meter>


<meter min="0" max="100" low="10" high="90" optimum="50" value="50"></meter>
```


**meter vs progress**   
- meter - static  
- progress - dynamic



[top](#)
