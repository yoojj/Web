# iframe
: 웹 문서 내에 다른 웹 문서를 포함하기 위해 사용하는 태그   


속성 | 설명
---|---
src             | 포함할 리소스 url 지정
srcdoc          | 포함할 인라인 html 삽입   
name            | 아이프레임 이름 지정
width, height   | 너비와 높이 지정
loading         | 리소스 로드 방법 지정
sandbox         | 리소스 제한 설정 지정
allow           | 리소스 권한 정책 지정
allowfullscreen | 리소스 사용 허용 여부 지정
referrerpolicy  | HTTP 리퍼러 정책 설정  


```html
<iframe src=""></iframe>

<iframe src="data:text/html,<p>text</p>"></iframe>
<iframe srcdoc="<p>text</p>"></iframe>
<!--
: srcdoc 속성을 지원할 경우 src 속성 재정의  
: srcdoc 속성을 지원하지 않을 경우 src 속성을 사용    
-->


<iframe src="" loading="eager | lazy"></iframe>
<!--
- auto : 브라우저 설정에 따름  
- eager : 아이프레임 즉시 로드
- lazy : 뷰포트에 도달하기 전까지 아이프레임 로드 연기

크롬 기준 아래에 해당하는 경우 아이프레임이 숨겨진 것으로 간주하여 지연 로드하지 않음  
- 아이프레임 너비와 높이가 4px 이하
- 아이프레임 위치 -x -y
- visibility:hidden
- display:none
-->


<iframe src="url" sandbox=""></iframe>
<!--
- allow-downloads
- allow-forms : form 전송 가능  
- allow-modals
- allow-orientation-lock
- allow-pointer-lock : Pointer Lock API 사용 가능   
- allow-popups : 팝업 허용
- allow-popups-to-escape-sandbox
- allow-presentation             
- allow-same-origin : 리소스 도메인을 같은 도메인으로 간주       
- allow-scripts : 스크립트 실행 가능           
- allow-storage-access-by-user-activation
- allow-top-navigation           
- allow-top-navigation-by-user-activation
-->
```



[top](#)
