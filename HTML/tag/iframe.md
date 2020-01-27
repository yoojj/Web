# iframe
: 문서 내에 다른 문서를 포함하기 위해 사용하는 태그   
: html4에서 지원하던 속성은 html5에서 거의 지원하지 않음        


속성 | 설명
---|---
allow      |
allowfullscreen      |
allowpaymentrequest  |
importance | 리소스 다운로드 우선 순위 명시
loading    | 아이프레임 로드 방법 명시
name       | 아이프레임 이름 지정
referrerpolicy | HTTP 리퍼러 정책 설정, [속성 값](../html-attribute.md#referrer-attributes)   
sandbox    | 리소스에 대한 제한 설정  
src        | 포함할 리소스 url
srcdoc     | inline html 삽입
width, height  | 너비 및 높이 지정



```html
<iframe src="url" importance="auto"></iframe>
<iframe src="url" importance="high"></iframe>
<iframe src="url" importance="low"></iframe>


<iframe src="url" loading="lazy"></iframe>
<!--
- auto : 브라우저 설정에 따름  
- eager : 아이프레임 즉시 로드
- lazy : 뷰포트에 도달하기 전까지 아이프레임 로드 연기

크롬 기준 아래에 해당하는 경우 아이프레임이 숨겨진 것으로 간주하여 지연 로드하지 않음  
- 아이프레임 너비와 높이가 4px 이하
- display:none | visibility:hidden
- 아이프레임 위치 -x -y
-->


<iframe src="url" sandbox></iframe>
<!--
아래와 같은 제한 사항 설정됨
- form 전송 불가
- JS 실행 차단
- 플러그인, API 비활성화
- ...
-->

<iframe src="url" sandbox="값"></iframe>
<!--
- allow-forms : form 전송 가능  
- allow-modals
- allow-orientation-lock
- allow-pointer-lock :  Pointer Lock API 사용 가능   
- allow-popups : 팝업 허용
- allow-popups-to-escape-sandbox
- allow-presentation             
- allow-same-origin : 리소스 도메인을 같은 도메인으로 간주       
- allow-scripts : JS 실행 가능           
- allow-storage-access-by-user-activation
- allow-top-navigation           
- allow-top-navigation-by-user-activation
-->


<iframe srcdoc="<p>srcdoc</p>" src=""></iframe>
<!--
: srcdoc 속성을 지원할 경우 src 속성 재정의  
: srcdoc 속성을 지원하지 않을 경우 src 속성을 사용    
-->
```



[top](#)
