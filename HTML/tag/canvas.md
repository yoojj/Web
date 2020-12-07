# canvas
: 텍스트, 도형, 그래프 등 시각적 이미지를 즉시 렌더링하는 비트맵 영역을 지원하는 태그


속성 | 설명
---|---
width, height | 캔버스 너비와 높이 지정


```html
<canvas width="300" height="150" id="canvas-id">
    캔버스를 지원하지 않을 경우를 대비해 대체 콘텐츠 삽입
    <img src="" alt="">
</canvas>


<script>
window.onload = function() {
    var canvas = document.getElementById('canvas-id');
    var ctx = canvas.getContext('2d');
    draw(ctx);
}

function draw(ctx){
    ctx.save();

    ctx.fillStyle = 'red';
    ctx.fillRect(0, 0, 100, 100);

    ctx.restore();
}
</script>
```



[top](#)
