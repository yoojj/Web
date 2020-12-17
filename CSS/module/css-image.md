# CSS Image

https://www.w3.org/TR/css-images/  
https://drafts.csswg.org/css-images-4/  


**image type**      
: 이미지 참조 함수를 통해 로드된 이미지     
: 색으로 표현된 단색 이미지 (color image)      
: 그라디언트 함수를 사용해 동적으로 생성된 이미지      
: element() 함수를 사용해 요소를 이미지로 변환한 경우   

ex.
```css
E {background:url()};
E {list-style-image:url()};
E {cursor:url()};

#id {}
E {background:element(#id)};
```



## image

**image references**
- url()
- image()


**image fallback**  
: 이미지가 표현되지 않을 경우 단색 이미지로 대체  

```css
E {background:color url();}
E {background:color image();}
E {background:color linear-gradient();}
```

속성 | 설명
---|---
image-orientation |
image-rendering   | 이미지 크기 변경 방식에 대한 힌트 지정
image-resolution  | 이미지 해상도를 다시 지정   
object-fit        |
object-position   |


```css
E {image-rendering:auto | smooth | high-quality | crisp-edges | pixelated;}


E {image-resolution:<resolution> | from-image | snap;}
/*
resolution
- dpi : 인치당 도트수
- dpcm : 센치미터당 도트수
- dppx : px 단위당 도트수
*/
```



## gradient
: 한 색에서 다른 색으로 부드럽게 전환하며 표현된 이미지    
: 두 가지 이상의 색 사용   

- linear-gradient()
- radial-gradient()
- conic-gradient()


```css
E {background:linear-gradient(angle | to <side-or-corner>, color-list);}
/*
선형 그라디언트

- top     = 0deg
- right   = 90deg
- bottom  = 180deg
- left    = 270deg
- top right    = 45deg
- bottom right = 135deg
- bottom left  = 225deg
- top left     = 315deg  

E {background:linear-gradient(color, color);}
E {background:linear-gradient(0deg, color, color);}
E {background:linear-gradient(to top, color, color);}
*/


E {background:radial-gradient(shape | size | postion | color-list);}
/*
원형 그라디언트

shape : 원형 모양 지정
- circle
- ellipse

size
- closest-side
- closest-corner
- farthest-side
- farthest-corner

E {background:radial-gradient(color, color);}
E {background:radial-gradient(circle at center, color, color);}
E {background:radial-gradient(ellipse at 100%, color, color);}
*/


E {background:conic-gradient();}
/*
원추형 그라디언트
*/
```



[top](#)
