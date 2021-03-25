# picture
: 디스플레이 별 다른 이미지를 제공하기 위한 태그   


**포함 요소**
- [img](./img.md)
- [source](./source.md)


ex.
```html
<picture>
    <source srcset="example.jpg 400w, example@2x.jpg 800w"
            sizes="(min-width:1200px) 800px, (min-width:600px) 400px,100vw">
    <img src="example.jpg" alt="">
</picture>
```



[top](#)
