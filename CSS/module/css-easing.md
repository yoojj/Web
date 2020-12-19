# CSS Easing Function
: 움직임의 감속이나 가속 정도를 표현하는 함수   

https://www.w3.org/TR/css-easing/  
https://developer.mozilla.org/en-US/docs/Web/CSS/easing-function


- [linear easing function](#linear-easing-function)
- [cubic bezier easing function](#cubic-bezier-easing-function)
- [step easing function](#step-easing-function)


**interpolation**  
: 주어진 데이터(ex. 시간) 사이에 위치하는 속성의 값을 추측하는 것      



## linear easing function
: easing을 사용하지 않은 함수    
: 시간에 따라 속성의 값이 균일하게 증가


```
linear = cubic-bezier(0, 0, 1, 1)
```



## cubic bezier easing function

```
ease         = cubic-bezier(0.25, 0.1, 0.25, 1)
ease-in      = cubic-bezier(0.42, 0, 1, 1)
ease-out     = cubic-bezier(0, 0, 0.58, 1)
ease-in-out  = cubic-bezier(0.42, 0, 0.58, 1)

cubic-bezier(x1 , y1 , x2 , y2)
```


https://cubic-bezier.com/  
http://www.css3beziercurve.net/  



## step easing function

```
step-start  = steps(1, start)
step-end    = steps(1, end)
steps()
```



[top](#)
