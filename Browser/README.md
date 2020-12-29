# Browser
: 웹 서버에 HTTP 요청을 하는 프로그램    
: 응답 받은 리소스(웹문서, 이미지, 비디오 등)를 렌더링   


- [브라우저 구성 요소](#브라우저-구성-요소)
- 브라우저 분류   
    - [Headless Browser](./headless-browser.md)
    - [Text-based Browser](./text-based-browser.md)
    - Lightweight Browser
    - Mobile Browser, Micro Browser : 모바일 장치에 특화된 브라우저  
    - Cross-platform Browser : 여러 운영 체제용으로 개발된 브라우저  
    - Specialty Browser : 특수 기능을 제공하는 브라우저  



**초기 브라우저 특징**

브라우저 | 특징
---|---
WorldWideWeb(Nexus)    | 최초 CLI 브라우저로 특정 운영체제에서만 동작  
Line Mode Browser(LMB) | 크로스 플랫폼을 위한 CLI 브라우저
Lynx    | 텍스트 기반 브라우저   
Erwise  | 최초 GUI 기반 브라우저
Mosaic  | 웹 문서에 이미지 삽입 지원   
Arena   | HTML table과 CSS1을 지원한 브라우저
Netscape Navigator | 서버에서 받은 데이터를 캐시에 저장하고 이를 재사용, JavaScript를 포함  
Internet Explorer  | Windows OS에 브라우저를 포함, HTML 포맷 확장


**최초 브라우저**
![최초 브라우저 이미지](https://www.w3.org/MarkUp/tims_editor)



## 브라우저 구성 요소

- User Interface
- Browser Engine
- Layout Engine, Rendering Engine
    - HTML Parser
    - CSS Parser
- JavaScript Engine
- UI Backend
- Data Persistence


```
                                                네트워킹                           
사용자 인터페이스 --> 브라우저 엔진 --> 렌더링 엔진 --> 자바스크립트 해석기
                       |                        UI 백엔드
                   자료 저장소
```


구성 요소 | 설명
---|---
User Interface    | 브라우저에서 창을 제외한 주소 표시줄, 버튼 등 모든 부분
Browser Engine    | 사용자 인터페이스와 렌더링 엔진 사이의 동작 제어
Layout Engine     | 사용자 인터페이스에서 요청한 콘텐츠를 파싱하여 화면에 표시
JavaScript Engine | JS 코드를 파싱하고 실행  
UI Backend        | 선택 상자, 입력 상자같은 위젯을 그리는데 사용   
Data Persistence  | 쿠키 포함 모든 종류의 자원을 하드 디스크에 저장



[top](#)
