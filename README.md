# Web
World Wide Web, WWW, W3      
: 인터넷으로 연결된 컴퓨터를 통해 정보 공유를 목적으로 탄생  
: [하이퍼텍스트](#hypertext)-비선형적 구조로 정보 전달    
: HTML로 작성된 웹 문서들로 구성되며 웹 문서는 브라우저를 통해 렌더링       
: 텍스트, 이미지, 음성, 영상 등 정적 및 동적 콘텐츠 제공  

> Memex -> Project Xanadu -> WWW

[정보 관리 제안서 : 팀 버너스 리]    
https://www.w3.org/History/1989/proposal.html


**웹 사이트 vs 웹 애플리케이션**

웹 사이트 | 웹 애플리케이션
---|---
정적 콘텐츠 - 웹 문서 | 사용자 상호작용 - 웹 플랫폼
인터넷 프로토콜 기반 네트워크 상에 존재하는 각각의 주소와 경로를 가진 웹 문서들이 유의미하게 묶인 구조체  | - 브라우저에서 이용 할 수 있는 응용 소프트웨어<br>- 기존 시스템들의 통합을 위해 웹 기술을 서로 다른 각종 장치와 애플리케이션 간의 소통을 위한 인터페이스로 사용


- [웹 동작 방식](./how-the-web-works.md)
- 웹 문서
    - 구조 : [HTML](./HTML/)
    - 표현 : [CSS](./CSS/)
    - 동작 & 기능
        - [ECMAScript](https://github.com/yoojj/JS)
        - [WebAssembly](./WebAssembly/)
        - [DOM](./DOM/)
        - [Web API](./WebAPI/)
    - [Web Component](./web-component.md)
- [웹 표준](./WebStandard/)
    - [W3C](./WebStandard/README.md#w3c)
    - [WHATWG](./WebStandard/README.md#whatwg)
    - [WAI-ARIA](./WebStandard/wai-aria.md)
    - [WCAG](./WebStandard/wcag.md)
    - [Web i18n](./WebStandard/web-i18n.md)
- 도구 : [Browser](./Browser/)        
- 식별자 : [URI, URL, URN](./uri-url-urn.md)  
- 프로토콜 : [HTTP](./HTTP/)
- [웹 아키텍처](./webArchitecture/)
    - [웹 서비스](./web-service.md)
- [웹 서버](./WebServer/)
- [웹 검색 엔진](./WebSearchEngine/)
- [웹 보안](./WebSecurity/)
- [웹 성능 최적화](./WebOptimization/)



웹 | 정의
---|---
웹 1.0 (1990년~) | Read-Only Web, Static Web <br> - 하이퍼텍스트 위주인 정보 전달 웹<br> - 디렉토리 검색 (정보가 카테고리로 분류)
웹 2.0 (2000년~) | Read-Write Web, Participating Web<br> - 플랫폼으로서 웹<br> - 사용자들의 참여-공유-개방 = 집단지성
웹 3.0 (진행중)   | Semantic Web<br> - 웹 플랫폼의 변화<br> - 빠른 네트워크 + 의미있는 데이터 집합<br> - 개인화, 맞춤화, 상황 인식 웹
웹 4.0           | Mobile Web<br> - 모든 장치를 실시간으로 연결  
웹 5.0           | Symbiotic Web, Emotional Web<br> - 사용자 감정을 인식  



## Hypertext
: 1960년대 철학자 테드 넬슨이 구상한 용어   
: 문서 내에 텍스트에 걸린 링크를 통해 다른 단락(표, 그림, 새 문서 등)으로 이동해 정보를 자유롭게 탐색   
: 사용자에게 통제권이 부여되어 필요에 따라 내용을 건너 뛰어 필요한 정보만 습득 가능      

**구성**  
- 노드 = 문서
- 링크 = 문서를 연결하는 통로  



### Hypermedia
: 하이퍼텍스트 확장          
: 텍스트뿐만 아니라 이미지, 미디어같은 멀티미디어에 링크를 거는 것     



[top](#)
