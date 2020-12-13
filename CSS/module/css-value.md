# CSS Value

https://www.w3.org/TR/css-values/


- [string data type](#string-data-type)
- [numeric data type](#numeric-data-type)
- color
- image
- [position](#position)
- [function](#function)



## string data type


**pre-defined keyword**   
: 속성에 따라 미리 정의된 키워드

ex.
```css
E {text-align:center;}
```


**wide keyword**  
: 모든 속성 값으로 사용 가능한 키워드   

- initial
- inherit
- unset


**author-defined identifiers**   
: 일부 속성은 사용자가 정의한 식별자를 값으로 사용 가능   
: 사용자가 정의한 식별자는 대소문자를 구별함  

- custom-ident : 정의된 식별자를 식별자로 사용 불가
- dashed-ident : 정의된 식별자를 식별자로 사용 가능

ex.
```css
:root {
    --red-color:red;
}
```


**string**  
: 따옴표로 둘러쌓인 텍스트   

ex.
```css
E {font-family:"";}
::after {content:"";}
E[attr = ""] {}
```


**url**   

ex.
```css
@import url();
@namespace url();

E {background:src();}
E {background:url();}
```



## numeric data type


```css
/* integer */
E {line-height:1;}

/* number */
E {line-height:1.5;}

/* length */
E {line-height:1.5;}

/* percentage */
E {margin:10%;}

/* dimensions */
E {margin:10px;}

/* ratio */
E {margin:3/2;}
```


단위 | 설명
---|---
cm | 센티미터
mm | 밀리미터 (1/10cm)
q  | 쿼터 밀리미터 (1/4mm)
in | 인치 (2.54cm, 96px)
pc | 파이카 (1/6in)
pt | 포인트 (1/72in)
px | 픽셀 (1/96in)


**폰트 단위**

단위 | 설명
---|---
em  | 텍스트 크기
ex  | 텍스트 높이
cap | 텍스트 캡 높이  
ch  |
ic  |
rem |
lh  |
rlh |


**뷰포트 단위**

단위 | 설명
---|---
vw  |
vh  |
vi  |
vb  |
vmin|
vmax|


**시간 단위**

단위 | 설명
---|---
s  | 초
ms | 밀리초


**각도 단위**

단위 | 설명
---|---
deg  | 디그리
grad | 그레이드
rad  | 라디안
turn | 턴  

ex. 90deg = 100grad = 1.57rad = 0.25turn



## position

- top
- center
- bottom
- left
- right

ex.
```css
E {top:0;left:0;}
```


## function

- url()
- rgb()
- calc()
- mod()
- ...



[top](#)
