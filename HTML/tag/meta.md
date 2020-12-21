# meta
: 웹 문서에 대한 상세 정보 및 메타 데이터를 위한 태그      
: SEO에 영향을 미침     


**Metadata**   
: 웹 문서에 대한 추가 정보 모음     
: 사용자보다 검색 엔진 같은 기계를 위한 정보    


**부모 요소**  
- [head](./head.md)
- [noscript](/script.md#noscript)


속성 | 설명
---|---
charset     | 문자 인코딩 지정
content     | http-equiv와 name 속성 값 지정
http-equiv  | HTTP 헤더 작동 방식 변경
name        | 메타데이터 이름으로 charset, http-equiv, itemprop 속성과 중복 정의 불가  
itemprop    | 마이크로 데이터를 위한 속성


**마이크로 데이터**
https://github.com/yoojj/Web/blob/master/HTML/html-microdata.md


```html
<meta charset="utf-8">
<!-- 최상단에 정의 -->



<!--
http-equiv
- content-language
- content-type
- default-style
- refresh
- x-ua-compatible
- content-security-policy
-->


<meta http-equiv="content-type" content="text/html; charset=utf-8">
<!-- charset 속성과 중복 정의하면 안됨 -->


<meta http-equiv="default-style" content="pre-style">
<!--
: 우선 적용할 스타일 시트 지정  

<link rel="stylesheet" href="example.css" title="pre-style">
-->


<meta http-equiv="refresh" content="1">
<!--
: content 값 마다 웹 문서 새로고침

<meta http-equiv="refresh" content="2; URL=https://www.example.com">
: content 값 이후 해당 경로로 이동
-->


<meta http-equiv="x-ua-compatible" content="">
<!--
: 렌더링 모드 지정
: 레이아웃 엔진과 스크립트 엔진이 지정한 브라우저 버전으로 맞춰짐

최신 표준 모드로 렌더링
<meta http-equiv="x-ua-compatible" content="ie=edge">

최신 표준 모드로 렌더링 후에 크롬이 설치되어 있다면 크롬으로 렌더링
<meta http-equiv="ua-compatible" content="ie=edge,chrome=1">

쿼크 모드
<meta http-equiv="x-ua-compatible" content="ie=5">
-->


<meta http-equiv="content-security-policy" content="지시문 옵션">
<!--
: 콘텐츠 보안 정책 정의
https://github.com/yoojj/Web/blob/master/WebStandard/csp.md
-->



<meta name="application-name" content="">
<!--
: 웹 애플리케이션 이름 정의
: 웹 애플리케이션이 아닌 경우 정의하면 안됨
-->

<meta name="author" content="">

<meta name="description" content="150 이하 문자">
<!--
: 웹 문서에 대한 설명
: 검색시 결과로 보여지거나 북마크시 설명으로 사용됨
-->

<meta name="generator" content="">

<meta name="keywords" content="a,b,c,d,e">
<!-- 웹 문서와 관련된 키워드 정의 -->

<meta name="referrer" content="옵션">
<!--
: HTTP 리퍼러 제어

옵션
- no-referrer
- no-referrer-when-downgrade
- origin
- origin-when-crossorigin
- same-origin
- strict-origin
- strict-origin-when-cross-origin
- unsafe-URL

일부 브라우저만 지원되는 옵션
- always
- default
- never


리퍼러 제거
<code>
<meta name="referrer" content="no-referrer">

<javascript>
var meta = document.createElement('meta');
meta.name = 'referrer';
meta.content = 'no-referrer';
document.getElementsByTagName('head')[0].appendChild(meta);
</javascript>
</code>
-->


<meta name="theme-color" content="">
<meta name="color-scheme" content="">
<!-- 인터페이스 컬러 변경 -->
```


**meta extensions**

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<!--
: 모바일 화면 크기 제어

- width=device-width
- height=device-height

- initial-scale=0.0~10.0
- maximum-scale=0.0~10.0 : 최대 확대 비율
- minimum-scale=0.0~10.0 : 최소 축소 비율
- user-scalable=yes/no : 기기 확대 여부 설정
-->


<meta name="format-detection" content="telephone=no, address=no, email=no">
<meta name="format-detection" content="telephone=no">
<!-- (모바일) 전화번호, 이메일 자동 링크 해제 -->


<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black">
<meta name="apple-mobile-web-app-title" content="" />
<meta name="apple-mobile-web-app-capable" content="yes" />
<!-- 아이폰, 아이패드 관련 설정 -->


<meta name="msapplication-TileColor" content="#ffffff">
<meta name="msapplication-TileImage" content="경로">
<!-- 윈도우 타일 아이콘 -->


<meta name="robots" content="명령어">
<!--
: 모든 검색 엔진 로봇에게 크롤링 방법 지시  


명령어
- index : 문서 색인, 기본 값
- noindex
- follow : 링크 follow, 기본 값
- nofollow
- none : noindex, nofollow
- noodp
- noarchive
- nosnippet
- notranslate
- noimageindex


특정 봇 선택
<meta name="googlebot" content="">
<meta name="bingbot" content="">
<meta name="slurp" content="">
-->


<meta name="revisit-after" content="1 days">
<!-- 검색 봇 재방문 시간 정의 -->

<meta name="audience" content="all">
<!-- 검색 봇, 보호자 제어 소프트웨어를 위해 연령 제어 -->


<meta name="google" content="nositelinkssearchbox">
<!-- 구글 검색시 사이트 링크 검색창 표시 제어 -->

<meta name="google" content="notranslate">
<!-- 구글 번역 제어 -->

<meta name="google-site-verification" content="verification_token">


<meta property="og:url" content="">
<meta property="og:type" content="">
<meta property="og:title" content="">
<meta property="og:image" content="">
<meta property="og:description" content="">
<!--
: 오픈 그래프 프로토콜
: 문서 링크 공유시 문서에 대한 미리보기를 위한 정보
-->


<meta name="twitter:card" content="">
<meta name="twitter:url" content="">
<meta name="twitter:site" content="@트위터아이디">
<meta name="twitter:creator" content="@트위터아이디">
<meta name="twitter:type" content="">
<meta name="twitter:title" content="">
<meta name="twitter:image" content="">
<!-- 트위터 메타태그 -->


<meta property="fb:app_id" content="페이스북아이디">
<!-- 페이스북 메타태그 -->


<meta name="ICBM" content="latitude, longitude">
<meta name="geo.position" content="latitude;longitude">
<meta name="geo.region" content="country[-state]">
<meta name="geo.placename" content="city/town">
<!--
: Geotag, GeoTagging
: 위치 정보 태그  

http://calab.kaist.ac.kr:8080/~maeng/pubs/kiss2010.pdf
-->
```



[top](#)
