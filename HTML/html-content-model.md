# HTML Content Model
https://html.spec.whatwg.org/#content-models  

: html5부터 도입된 카테고리 개념에 따라 엘리먼트를 분류하는 방법          
: 하나의 요소가 하나의 카테고리에 한정되지 않으며 카테고리에 속하지 않는 요소도 존재   

! html4, xhtml에서 요소는 [블록 요소와 인라인 요소](./html-element.md#block-and-inline-element)로 분류  


**카테고리**  
- [Metadata Content](#metadata-content)
- [Flow content](#flow-content)
- [Sectioning Content](#sectioning-content)
- [Heading Content](#heading-content)
- [Phrasing Content](#phrasing-content)
- [Embedded Content](#embedded-content)
- [Interactive Content](#interactive-content)



## Metadata Content  
: 문서에 대한 정보 설정 및 문서와 문서의 관계를 정의하는 요소들    

- base
- link
- meta
- noscript
- script
- style
- template  
- title




## Flow content  
: 콘텐츠를 포함하는 요소로 body 내의 대부분 요소들  

- a
- abbr
- address
- area -- map 요소의 자식일 경우
- article
- aside
- audio
- b
- ...



## Sectioning Content  
: 문서를 좀 더 명확하게 구조화하기 위해 범위-아웃 라인을 정의하는 요소들  

**아웃 라인**
: 섹션 계층 구조

- article
- aside
- nav
- section



## Heading Content  
: 각 세션의 머리말-표제를 정의하는 요소들

- h1 ~ h6
- hgroup(not w3)



## Phrasing Content  
: 텍스트를 정의하는 요소들

- a
- abbr
- area -- map 요소의 자식일 경우
- audio
- b
- ...



## Embedded Content  
: 미디어, 그래픽 등의 외부 자원-콘텐츠 삽입을 정의하는 요소들  

- audio
- canvas
- embed
- iframe
- img
- math
- object
- picture
- svg
- video



## Interactive Content  
: 사용자와 상호 작용을 위해 정의하는 요소들  

- a -- href 속성이 존재하는 경우
- audio -- controls 속성이 존재하는 경우
- button
- details
- embed
- iframe
- img -- usemap 속성이 존재하는 경우
- input -- type 속성에서 hidden 값이 아닌 경우
- label
- object -- usemap 속성이 존재하는 경우
- select
- textarea
- video -- controls 속성이 존재하는 경우



[top](#)
