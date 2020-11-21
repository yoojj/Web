# Browser
: 웹 서버에 HTTP 요청을 하는 프로그램    
: 웹 문서(html, css, js 등), 이미지, 비디오 등을 표시  


**종류**   
- [Text-base Browser](./browser-text-base.md)
- [Headless Browser](./browser-headless.md)
- [Mobile Browser](./browser-mobile.md)
- [Cross-platform Browser](./browser-cross-platform.md)



**최초 브라우저**
![최초 브라우저 이미지](https://www.w3.org/MarkUp/tims_editor | width=500)




## 브라우저 구성 요소

- [User Interface](./UI.md)
- Browser Engine
- [Layout(Rendering) Engine](./Layout-Engine/)
    - HTML Parser
    - CSS Parser
- [JavaScript Engine](./JavaScript-Engine/)
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
