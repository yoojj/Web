# time
: 시간, 날짜, 기간을 위한 엘리먼트   



```html
<time datetime=""></time>
<!-- datetime 속성 값은 기계가 읽을 수 있는 형식 사용 -->

<time datetime="yyyy"></time>
<time datetime="yyyy-mm"></time>
<time datetime="yyyy-mm-dd"></time>
<time datetime="mm-dd"></time>

<time datetime="hh:mm"></time>
<time datetime="hh:mm:ss"></time>


<time datetime="2020-01-01T12:00"></time>
<time datetime="2020-01-01 12:00"></time>
<!-- 날짜와 시간 구분 -->


<time datetime="P3D">3일</time>
<time datetime="PT30">30분</time>
<time datetime="PT3H30M">3시 30분</time>
<time datetime="PT23H 3M 1.234S">23시간 3분 1초 234밀리초</time>
<!--
접두사
- P (period) : 기간
- D (days) : 날짜
- H (hours) : 시간
- M (minutes) : 분
- S (seconds) : 초
-->
```


[top](#)
