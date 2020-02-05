# CSS File Load
: 문서에 css 파일을 포함하는 방법

- User defined CSS
- External CSS
- Internal CSS
- Inline CSS


```html
<!--
1. User defined Style Sheet
: 브라우저에서 제공하는 기본 스타일 시트(user agent stylesheet)를 사용자가 수정 가능한 경우
-->



<head>
<link rel="stylesheet" href="base.css" media="all">
<link rel="stylesheet" href="small.css" media="(min-width:50em)">
<link rel="stylesheet" href="medium.css" media="(min-width:100em)">
<link rel="stylesheet" href="large.css" media="(min-width:150em)">
</head>

<link rel="stylesheet" href="home-header.css">
<header class="home-header"></header>
<!--
2. External Style Sheet
: 외부에 생성된 css 파일을 링크   
: css 파일 안에서 @import 구문을 사용하여 css 파일을 포함할 수 있음

@import url ("*.css");

link된 css 파일은 동시에 다운로드가 가능하여 문제가 없으나
import된 css 파일은 순차적으로 다운로드되어 문제가 생길 수 있으므로 사용 지양
-->



<style>
div {background-color:#000;}
</style>
<!-- 3. Internal(Embedded) Style Sheet -->



<div style="background-color:black;"></div>
<!-- 4. Inline Styles -->
```



## Browser default CSS

**ie 7,8,9**   
http://web.archive.org/web/20170122223926/http://www.iecss.com/


**Chrome (Blink)**    
https://cs.chromium.org/chromium/src/third_party/blink/renderer/core/html/resources/html.css
https://chromium.googlesource.com/chromium/blink/+/master/Source/core/css/html.css


**Chrome/Safari (WebKit)**  
http://trac.webkit.org/browser/trunk/Source/WebCore/css/html.css


**Firefox**    
https://dxr.mozilla.org/mozilla-central/source/layout/style/res/html.css



[top](#)
