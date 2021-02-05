# DOM
Document Object Model  
: HTML, XML, SVG, MathML 같은 마크업 언어를 위한 API    
: 마크업 문서를 구조화하는 방법과 접근하고 조작하는 방법 정의    

https://dom.spec.whatwg.org/  
http://trac.webkit.org/browser/webkit/trunk/Source/WebCore/dom   


```
마크업 문서 --> 파싱 --> 문서 객체 모델
```


- [DOM Level](#dom-level)
- [DOM Infrastructure](./dom-infrastructure.md)
- [DOM Event](./dom-event.md)
- DOM API
    - [Event](./api-dom-event.md)
    - [EvnetTarget](./api-dom-event-target.md)
    - [Node](./api-dom-node.md)
    - [Document](./api-dom-document.md)
    - [Element](./api-dom-element.md)
    - [Text](./api-dom-text.md)
    - [HTML](./html)
    - [CSS](./css/)
    - [SVG](./svg/)
- [BOM API](./bom/) 



## DOM Level

**DOM level 1**    
: 각 벤더사에서 확장되던 DOM을 W3C에서 표준화  
: Node, Element, Attr, Document 등 Core 인터페이스와 HTML 인터페이스 등을 정의     

https://www.w3.org/TR/REC-DOM-Level-1/


**DOM Level 2**   
: 다양한 환경 지원을 위해 모듈화함   
: 필수 모듈인 Core 모듈과 선택 사항인 14개 모듈 제공       
: CSS 제어를 위한 CSS 인터페이스 정의    

- Core
- Xml
- Html
- View
- Style
- Event
- ...

https://www.w3.org/TR/DOM-Level-2-Core/


**DOM Level 3**    
: Xpath, Validation 등 새로운 인터페이스를 정의해 16개의 모듈 지원   

- Load and Save
- Validation
- Xpath
- ...

https://www.w3.org/TR/DOM-Level-3-Core/


**DOM level 4**   
= DOM Living Standard   
: WHATWG에 의해 DOM 관리      
: WHATWG은 기존 사양을 유지하면서 필요시 새로운 기능을 추가     
: 일부 인터페이스와 인터페이스의 멤버가 제거됨   

https://www.w3.org/TR/dom40/   
https://dom.spec.whatwg.org/   



[top](#)
