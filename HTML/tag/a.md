# a
: 하이퍼 링크를 정의하는 엘리먼트   
: 다른 url, 다른 문서, 문서 내 특정 위치, 이메일, 전화 등에 사용  


속성 | 설명
---|---
[href](#href) | 목적지 정의
hreflang | 링크된 리소스의 언어 명시
target   | 링크된 리소스가 표시될 위치 명시, [속성 값](../html-attribute.md#target-attributes)
[download](#download) | 링크된 리소스 다운로드시 사용
[ping](#ping) | 링크 클릭시 링크 정보를 담은 HTTP POST 요청을 보낼 url 정의
referrerpolicy | HTTP 리퍼러 정책 설정, [속성 값](../html-attribute.md#referrer-attributes)
rel      | 현재 문서와 링크된 문서 사이의 연관 관계 명시, [속성 값](../html-attribute.md#rel-attributes)
[media](#media)| 링크된 리소스의 최적화된 장치 명시, [속성 값](../html-attribute.md#media-attributes)
type     | 링크된 리소스의 MIME 유형 명시

! html5 기준 href 속성 필수 아님
! href 속성이 없으면 나머지 속성 사용 불가



## href

```html
<a href="mailto:메일@메일?cc=참조메일@메일">메일 보내기</a>
<!-- 참조 -->

<a href="mailto:메일@메일?cc=참조메일@메일&bcc=참조메일@메일">메일 보내기</a>
<!-- 숨은 참조 -->

<a href="mailto:메일@메일?&subject=메일제목">메일 보내기</a>
<!-- 메일 제목 -->

<a href="mailto:메일@메일?&body=메일%0A내용">메일 보내기</a>
<!-- 메일 내용 -->
```



## download
: 링크된 리소스를 다운로드시 사용하는 속성    
: 리소스 제한이 없어 생성된 데이터 다운로드 가능  


```html
<a href="test.pdf" download>다운로드</a>
<a href="test.pdf" download="새 파일명 정의">다운로드</a>


<!-- canvas -->
<canvas id="c" width="500" height="500"></canvas>
<a href="#" id="a">다운로드</a>
<script>
(function(){
    const canvas = document.getElementById('c');
    const cxt = canvas.getContext('2d');
    const a = document.getElementById('a');

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
    const data = {
        a : 1,
        b : 2,
        c : 3,
    };

    const json = JSON.stringify(data);
    const blob = new Blob([json], {type: 'octet/stream'});

    const a = document.getElementById('a');
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



## media

```html
<a href="" media="print and (resolution:250dpi)">print</a>
<!-- 250dpi 해상도로 프린트 -->
```
