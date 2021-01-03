# link
: 웹 문서와 외부 리소스 연결하고 관계를 명시      


**부모 요소**  
- [head](./head.md)
- [noscript](/script.md#noscript)


속성 | 설명
---|---
href  | 하이퍼 링크나 링크될 리소스의 위치 명시
type  | 링크될 리소스 MIME 타입 명시
hreflang | 링크될 리소스의 언어 명시
disabled | 링크 비활성화 여부 지정  
rel   | 웹 문서와 링크될 리소스 간의 관계 명시
media | 리소스가 적용될 미디어 명시
as    | rel 값이 preload나 modulepreload인 경우 타입 명시  
color | rel 값이 mask-icon인 경우 색상 명시  
sizes | rel 값이 icon인 경우 아이콘 사이즈 명시
imagesrcset | rel 값이 preload인 경우 사용할 이미지 명시   
imagesizes  | rel 값이 preload인 경우 사용할 이미지 명시   
integrity   | 하위 리소스 무결성 확인을 위한 해시 값 지정  
crossorigin | crossorigin 요청 처리 방식 지정
referrerpolicy | HTTP 리퍼러 정책 설정


```html
<link itemprop="url" href="">
<link itemprop="embedURL" href="">


<link rel="alternate stylesheet" href="basic.css" title="Basic Style">
<!--
: 대체 스타일 시트 정의
: 전역 속성인 title 의미 변경    
-->


<link rel="alternate" media="only screen and (width:640px)" href="http://m.example.com/">
<link rel="alternate" hreflang="en" href="https://www.example.com/">


<link rel="author" href="humans.txt">
<!-- http://humanstxt.org/humans.txt -->

<link rel="author license" href="/about">


<link rel="canonical" href="https://www.example.com/">
<!--
: 검색 엔진 최적화를 위한 캐노니컬 태그
: 웹 문서에 여러 url이 존재하는 경우 기준이 되는 url 지정  

http://example.com
http://example.com/
https://example.com/
-->


<link rel="manifest" href="manifest.webmanifest">
<!--
: 웹 앱의 정보를 json으로 제공해 오프라인에서도 동작하도록 지원

{
  "lang": "",
  "name": "",
  "description": "",
  "icons": [{
    "src": "icon.png",
    "sizes": "192x192"
  }]
}
-->


<link rel="icon" type="image/png" href="avicon.png">
<link rel="shortcut icon" href="favicon.ico">
<link rel="apple-touch-icon-precomposed" href="favicon.ico" sizes="152x152">


<link rel="preconnect" href="//example.com">
<!-- DNS lookup, Redirection 등 커넥션 연결 -->


<link rel="preload" href="example.css" as="style">
<link rel="preload" href="font.woff" as="font">
<!-- 리소스 로드 우선 순위 설정 -->


<link rel="prefetch" href="" as="">
<!--
: 나중에 필요할 수 있는 리소스를 미리 로드하고 이를 캐시에 저장
: meta 태그와 HTTP 헤더를 통해서도 설정 가능

<meta http-equiv="link" content="리소스; rel=prefetch">
Link: <리소스>; rel=prefetch
-->


<link rel="dns-prefetch" href="//example.com">
<!-- preconnect 중 DNS lookup만 적용 -->


<link rel="prerender" href="">


<link rel="stylesheet" href="example.css">
```


**+ Resource Hints**    
https://github.com/yoojj/Web/blob/master/WebOptimization/resource-hints.md



[top](#)
