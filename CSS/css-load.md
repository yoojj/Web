# CSS Load


**종류**
- [User-defined CSS](#user-defined-css)
- [External CSS](#external-css)
- [Internal CSS](#internal-css)
- [Inline CSS](#inline-css)



## User-defined CSS
: 브라우저에서 제공하는 기본 스타일 시트(user agent stylesheet)를 사용자가 수정하거나   
&nbsp; 사용자가 정의한 CSS 파일을 브라우저의 기본 스타일 시트로 등록  


**firefox**
1. 주소창 about:config 입력
2. 검색창에 toolkit.legacyUserProfileCustomizations.stylesheets 검색하고 활성화


**chrome**
: stylish 확장 프로그램 설치



### Browser default CSS

**ie 7,8,9**   
http://web.archive.org/web/20170122223926/http://www.iecss.com/


**Chrome (Blink)**    
https://cs.chromium.org/chromium/src/third_party/blink/renderer/core/html/resources/html.css
https://chromium.googlesource.com/chromium/blink/+/master/Source/core/css/html.css


**Chrome/Safari (WebKit)**  
http://trac.webkit.org/browser/trunk/Source/WebCore/css/html.css


**Firefox**    
https://dxr.mozilla.org/mozilla-central/source/layout/style/res/html.css



## External CSS

```html
<head>
<link rel="stylesheet" href="base.css" media="all">
<link rel="stylesheet" href="small.css" media="(min-width:50em)">
<link rel="stylesheet" href="medium.css" media="(min-width:100em)">
<link rel="stylesheet" href="large.css" media="(min-width:150em)">
</head>

<link rel="stylesheet" href="home-header.css">
<header class="home-header"></header>
```



## Internal CSS
= Embedded CSS

```html
<style>
div {}
</style>

<div></div>
```



## Inline CSS
: 웹 문서의 요소에 직접 스타일 속성 지정     
: 외부 스타일 시트보다 우선 순위가 높음   
: 인라인으로 스타일 지정시 가상 클래스와 가상 엘리먼트 사용 불가   

```html
<div style=""></div>
```



[top](#)
