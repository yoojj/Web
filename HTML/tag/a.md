# a
: 하이퍼 링크를 정의하기 위한 태그    


속성 | 설명
---|---
href     | 하이퍼링크 지정
hreflang | 링크될 리소스의 언어 명시
type     | 링크될 리소스의 MIME 유형 명시
rel      | 현재 웹 문서와 링크될 문서 사이의 연관 관계 명시
target   | 링크될 리소스가 표시될 위치 명시
media    | 링크될 리소스의 최적화된 장치 명시
download | 링크될 리소스를 다운로드 할 경우 사용
ping     | 링크 클릭시 링크 정보를 담은 HTTP POST 요청을 보낼 url 정의
referrerpolicy | HTTP 리퍼러 정책 설정


```html
<a name="id"></a>
<a role="button"></a>
<!--
: html5 기준 href는 필수 속성이 아님  
: href 속성이 없으면 나머지 속성 사용 불가
-->


<style>
a {display:block}
</style>

<a href="">
    <section>
    </section>
</a>
<!-- 블록 요소를 감쌀수 있음 -->
```



## href

```html
<!-- mailto -->
<a href="mailto:메일@메일?cc=참조메일@메일">메일 보내기</a>
<!-- 참조 -->

<a href="mailto:메일@메일?cc=참조메일@메일&bcc=참조메일@메일">메일 보내기</a>
<!-- 숨은 참조 -->

<a href="mailto:메일@메일?&subject=메일제목">메일 보내기</a>
<!-- 메일 제목 -->

<a href="mailto:메일@메일?&body=메일%0A내용">메일 보내기</a>
<!-- 메일 내용 -->


<!-- tel -->
<!-- https://tools.ietf.org/html/rfc3966#section-8 -->
<a href="tel:+번호">전화</a>
```



## media

```html
<a href="" media="print and (resolution:250dpi)">print</a>
<!-- 250dpi 해상도로 프린트 -->
```



## download
: 링크된 리소스를 다운로드시 사용하는 속성    
: 리소스 제한이 없어 생성된 데이터 다운로드 가능  


```html
<a href="test.pdf" download>다운로드</a>
<a href="test.pdf" download="새 파일명 정의">다운로드</a>


<!-- canvas -->
<canvas width="500" height="500" id="c"></canvas>
<a href="#" id="a">다운로드</a>
<script>
(function(){
    var canvas = document.getElementById('c');
    var cxt = canvas.getContext('2d');
    var a = document.getElementById('a');

    cxt.fillStyle = 'red';
    cxt.fillRect( 50, 50, 200, 200 );

    a.href = canvas.toDataURL();
    a.download = 'red-square.png';
})();
</script>


<!-- blob -->
<a href="#" id="a">다운로드</a>
<script>
(function(){
    var data = {
        a : 1,
        b : 2,
        c : 3,
    };

    var json = JSON.stringify(data);
    var blob = new Blob([json], {type: 'octet/stream'});

    var a = document.getElementById('a');
    a.href = window.URL.createObjectURL(blob);
    a.download = 'data.json';
})();
</script>
```



## ping
: 하이퍼링크에 대한 추적, 모니터링을 위해 사용

```html
<a href="index.html" ping="http://example.com">text</a>
<a href="index.html" ping="http://example.com http://example.com">text</a>
```



[top](#)
