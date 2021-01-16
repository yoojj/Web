# DOM
Document Object Model  
: HTML, XML, SVG, MathML 같은 마크업 언어를 위한 API    
: 마크업 문서를 구조화하는 방법과 접근하고 조작하는 방법 정의    
: 문서의 구성 요소를 트리 구조로 표현하고 DOM 메소드를 통해 제어      


https://dom.spec.whatwg.org/  
http://trac.webkit.org/browser/webkit/trunk/Source/WebCore/dom   


```
마크업 문서 --> 파싱 --> 문서 객체 모델 
```



## DOM level


**DOM level 1**    
: 브라우저 별로 확장되던 DOM을 W3C에서 표준화  
: Node, Element, Attr, Document 등 Core 인터페이스와 HTML을 위한 인터페이스 정의     

https://www.w3.org/TR/REC-DOM-Level-1/


**DOM Level 2**   
: 다양한 환경 지원을 위해 모듈화함   
: 필수 모듈인 Core 모듈과 선택 사항인 14개 모듈 제공       
: Core 모듈을 확장하고 CSS를 위한 CSS 인터페이스 제공

- Core
- Xml
- Html
- View
- Style
- Event
- ...

https://www.w3.org/TR/DOM-Level-2-Core/


**DOM Level 3**    
: Xpath, Validation 등 새로운 인터페이스를 정의하여 16개의 모듈 지원   

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
