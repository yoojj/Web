# CSS Media Query

https://www.w3.org/TR/mediaqueries/


**at rule**  
- @media
- @import


**media type**
- all
- print
- screen


**media query keyword**
- only
- not
- and
- or


```css
@media (condition) {}

@media not (condition) {}


@media (width : length) {}
@media (min-width < value) {}
@media (max-width > value) {}

@media (height : length) {}
@media (min-height < value) {}
@media (max-height > value) {}


@media (aspect-ratio : ratio) {}


@media (orientation : portrait | landscape) {}
/*
: 화면의 방향 지정

- portrait : 세로 방향
- landscape : 가로 방향
*/


@media (resolution : length) {}
@media (min-resolution < value) {}  
@media (max-resolution > value) {}    


@media (scan : interlace | progressive) {}    


@media (grid : mq-boolen) {}


@media (update : none | slow | slow) {}  


@media (overflow-block : none | scroll | paged) {}    
@media (overflow-inlie : none | scroll) {}   


@media (color : integer) {}
@media (color-index : integer) {}


@media (monochrome : integer) {}


@media (color-gamut : srgb | p3 | rec2020) {}


@media (pointer : none | coarse | fine) {}
@media (any-pointer : none | coarse | fine) {}


@media (hover : none | hover) {}
@media (any-hover : none | hover) {}
```



[top](#)
