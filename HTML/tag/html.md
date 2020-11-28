# html
: 웹 문서의 루트가 되는 엘리먼트로 DTD를 제외한 모든 요소의 컨테이너   


속성 | 설명
---|---
manifest | 캐시 매니페스트 url 지정  


```html
<html manifest="cache.manifest">
<!--
: 캐시 매니페스트
: 오프라인 상태에서도 애플리케이션 사용 가능한 캐시 설정 (css, js, 이미지, 폰트 등 구성 요소들)
! 매니페스트 속성이 느리므로 최근에는 Service Worker 사용   


1. cache.manifest 파일에 리소스 지정

<code>
CACHE MANIFEST
# 주석

# 오프라인시 사용 가능 리소스
CACHE:
    *.css
    *.js
    *.jpg

# 온라인시 사용 가능 리소스
NETWORK
    *

# 요청한 리소스가 없는 경우 대체할 리소스
FALLBACK
    404.html
</code>

2. <html manifest="cache.manifest">

3. js - manifest 지원 여부 확인

4. js - manifest 변경시 갱신
    window.applicationCache.status
-->


<html xmlns="http://www.w3.org/1999/xhtml">
<!--
: 문서의 XML 네임스페이스
! XHTML에서는 필수 속성이나 html5에서는 선택 속성
-->


<html prefix="og: http://ogp.me/ns#">
<!--
: 오픈 그래프 프로토콜, 오픈 그래프 메타 데이터

<meta property="og:url" content="">
<meta property="og:type" content="">
<meta property="og:title" content="">
<meta property="og:image" content="">
<meta property="og:description" content="">
-->


<html class="no-js">
<!--
: JS 미지원이나 JS off 대응을 위해 사용
: Modernizr 라이브러리에 의해 JS가 지원되는 환경이면 class="js"로 변경
-->
```



[top](#)
