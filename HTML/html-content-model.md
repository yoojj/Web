# HTML Content Model
https://html.spec.whatwg.org/#content-models  

: (html5부터 도입된) 카테고리 개념에 따라 엘리먼트 분류               
: 하나의 요소가 하나의 카테고리에 한정되지 않으며 카테고리에 속하지 않는 요소도 존재   
! html4에서는 [블록 요소와 인라인 요소](./html-element.md#block-and-inline-element)로 분류  


**카테고리**  
- [Metadata Content](#metadata-content)
- [Flow content](#flow-content)
- [Sectioning Content](#sectioning-content)
- [Heading Content](#heading-content)
- [Phrasing Content](#phrasing-content)
- [Embedded Content](#embedded-content)
- [Interactive Content](#interactive-content)



## Metadata Content  
: 웹 문서에 대한 정보, 기능, 리소스와의 관계를 정의하는 요소들      

- base
- link
- meta
- noscript
- script
- style
- template  
- title



## Flow content  
: 웹 문서의 콘텐츠를 포함하는 요소들    

- a
- abbr
- address
- area
- article
- aside
- audio
- ...



## Sectioning Content  
: 웹 문서를 좀 더 명확하게 구조화하기 위해 아웃 라인을 정의하는 요소들  

- article
- aside
- nav
- section


**아웃 라인**  
: 섹션 계층 구조   
: 섹션 콘텐츠 내부에 존재하는 헤딩 요소가 암묵적 섹션을 형성       
: html5 명세에서 아웃 라인 알고리즘 제공  

https://h5o.github.io/  
http://gsnedders.html5.org/outliner/  


```html
<body>
    <h1>title</h1>

    <nav>
        <h2>title</h2>
    </nav>

    <section>
        <h2>title</h2>

        <article>
            <h3>title</h3>
        </article>
    </section>
</body>
```


**+ sectioning root**  
: 섹셔닝 루트 요소 내부에 존재하는 섹셔닝 콘텐츠는 (body 제외) 아웃 라인에 영향을 미치지 않음

- blockquote
- body
- details
- fieldset
- figure
- td

```html
<body>
    <h1>h1</h1>

    <blockquote>
        <h2>h2</h2>
    </blockquote>
</body>
```



## Heading Content  
: 각 세션의 머리말를 정의하는 요소들

- h1 ~ h6
- hgroup



## Phrasing Content  
: 텍스트를 포함하는 요소들

- a
- abbr
- area
- audio
- b
- ...



## Embedded Content  
: 미디어, 그래픽 등 외부 리소스 삽입을 위한 요소들  

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
: 사용자와 상호 작용을 위한 요소들  

- a (href 속성이 존재하는 경우)
- audio (controls 속성이 존재하는 경우)
- button
- details
- embed
- iframe
- img (usemap 속성이 존재하는 경우)
- input (type 속성의 값이 hidden이 아닌 경우)
- label
- object (usemap 속성이 존재하는 경우)
- select
- textarea
- video (controls 속성이 존재하는 경우)



[top](#)
