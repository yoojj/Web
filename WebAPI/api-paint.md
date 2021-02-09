# CSS Paint API  
: 스타일 시트의 이미지 속성을 JS을 통해 동적으로 정의하는 방법 지원  

https://www.w3.org/TR/css-paint-api/


ex.
```html
<!-- index.html -->
<div class="box"></div>

<style>
.box {width:50%;height:50%;background-image:paint(example)}
</style>

<script>
CSS.paintWorklet.addModule('circle.js');
</script>


<!-- circle.js -->
<script>
var CirclePainter = class {
    paint(context, geometry, properties) {
        var centerX = geometry.width / 2;
        var centerY = geometry.height / 2;
        var radius  = 50;
        context.arc(centerX, centerY, radius, 0, Math.PI * 2);
        context.fillStyle = 'yellow';
        context.fill();
    }
}

registerPaint('example', CirclePainter);
</script>
```



# PaintWorkletGlobalScope

```webidl
[Global=(Worklet,PaintWorklet),Exposed=PaintWorklet]
interface PaintWorkletGlobalScope : WorkletGlobalScope {
    void registerPaint(DOMString name, VoidFunction paintCtor);
    readonly attribute unrestricted double devicePixelRatio;
};

dictionary PaintRenderingContext2DSettings {
    boolean alpha = true;
};


/*
partial namespace CSS {
    [SameObject] readonly attribute Worklet paintWorklet;
};
*/
```



# PaintRenderingContext2D

```webidl
[Exposed=PaintWorklet]
interface PaintRenderingContext2D {};

PaintRenderingContext2D includes CanvasState;
PaintRenderingContext2D includes CanvasTransform;
PaintRenderingContext2D includes CanvasCompositing;
PaintRenderingContext2D includes CanvasImageSmoothing;
PaintRenderingContext2D includes CanvasFillStrokeStyles;
PaintRenderingContext2D includes CanvasShadowStyles;
PaintRenderingContext2D includes CanvasRect;
PaintRenderingContext2D includes CanvasDrawPath;
PaintRenderingContext2D includes CanvasDrawImage;
PaintRenderingContext2D includes CanvasPathDrawingStyles;
PaintRenderingContext2D includes CanvasPath;
```



# PaintSize

```webidl
[Exposed=PaintWorklet]
interface PaintSize {
    readonly attribute double width;
    readonly attribute double height;
};
```



[top](#)
