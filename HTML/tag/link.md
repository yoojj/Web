# link
: 문서와 외부 리소스 연결하고 관계를 명시      


**부모 요소**  
- [head](./head.md)
- noscript


```html
<link href="">
<!-- 링크될 리소스 위치 명시 -->


<link href="" type="">
<link href="" as="">
<!-- 링크될 리소스 타입 명시 -->


<link href="" hreflang="">
<!-- 링크될 리소스 언어 명시 -->


<link href="" crossorigin>
<!-- crossorigin 요청 처리 방식 지정 -->


<link rel="" href="" type="">
<!--
: 문서와 링크될 리소스 간의 관계 명시

- stylesheet
- alternate
- icon
- preconnect
- preload
- prefetch
- prerender
- dns-prefetch
- pingback
- canonical
- external
- help
- next
- prev
- search
- bookmark
- manifest
- author
- license
-->

<link rel="stylesheet" href="example.css">
<link rel="alternate stylesheet" href="basic.css" title="Basic">
<!-- 대체 스타일 시트 -->

<link rel="alternate" media="only screen and (width:640px)" href="http://m.example.com/">
<link rel="alternate" hreflang="en" href="https://www.example.com/">


<link rel="preconnect" href="//example.com">
<!-- DNS lookup, Redirection 등 커넥션 연결 -->


<link rel="preload" href="" as="">
<!-- 리소스 로드 우선 순위를 지정 -->


<link rel="prefetch" href="" as="">
<!-- 특정 리소스를 미리 로드해 캐시에 저장 -->


<link rel="dns-prefetch" href="//example.com">
<!--
: preconnect 중 DNS lookup만 적용
<meta http-equiv="x-dns-prefetch-control" content="on">
-->


<link rel="manifest" href="example.manifest">
<!-- https://w3c.github.io/manifest/ -->


<link rel="author" href="humans.txt">
<!-- http://humanstxt.org/humans.txt -->
```


**프리 패치 & 프리 랜더링**   
: 레이턴시 극복  
: 링크될 리소스의 로드 속도를 빠르게 하기 위해 사용      
: 프리 패치를 적용해도 브라우저가 상황에 따라 이를 무시할 수 있음  
: 링크 프리패치 요청이 HTTP/2.0 에서는 효과가 거의 없음



[top](#)
