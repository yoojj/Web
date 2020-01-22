# HTML Element
: 태그, 속성, 콘텐츠같은 요소들로 구성된 집합체    
: 여러 엘리먼트를 사용하여 문서를 구성   
: 한 엘리먼트 안에 다른 엘리먼트를 포함하는 중첩 사용 가능    


**구성 요소**      
- tag : 요소의 시작과 끝 구분  
    - 꺽쇠 기호
    - 요소 이름
    - 요소 속성
- content
    - 텍스트
    - 공백
    - 중첩 요소


```html
<singleton-tag attribute="value">


<opening-tag attribute="value">텍스트</closing-tag>


<tag>
    <tag attribute="value">텍스트</tag>
</tag>
```


**tag vs element**

```html
<!-- 시작 태그와 종료 태그 -->
<h1></h1>

<!-- 요소 -->
<h1>내용</h1>
```


**엘리먼트 분류**   
- [void element](#void-element)
- [hidden element](#hidden-element)
- [semantic element](#semantic-element)
- [block and inline element](#block-and-inline-element)
- [optional tag](#optional-tag)

! 공식 문서 분류  
void elements, template element, raw text elements, escapable raw text elements, foreign elements, normal elements



## void element
= singleton tag, self-closing tag, empty tag   
: 종료 태그가 존재하지 않는 단일 태그  
: 단일 태그는 종료 태그가 없으므로 내용-콘텐츠를 갖고 있지 않음  

- area
- base
- br
- col
- command
- embed
- hr
- img
- input
- keygen
- link
- meta
- param
- source
- track
- wbr



## hidden element
: 시각적으로 표시되지 않는-렌더링되지 않는 엘리먼트   

- area
- base
- head
- link
- meta
- ...


```html
<style>
/* CSS를 재정의하여 표시할 수 있음 */
[hidden], head, link, meta, style, script {
    display: block;
    visibility:visible;
}
</style>
```



## semantic element
: 문서의 정보를 의미있게 표현하는 엘리먼트      
: 태그 자체로 브라우저나 사용자에게 콘텐츠에 대한 의미를 알릴 수 있음  

**구분**    
- 구조적 태그
- 텍스트 관련 태그
- 미디어 관련 태그


### 구조적 태그
: 문서의 구조나 정보를 그룹화하기 위한 태그

- header
- footer
- main
- nav
- section
- article
- aside



### 텍스트 관련 태그
: 텍스트의 의미나 목적을 나타내기 위한 태그  
: 텍스트의 시각적인 변화에 영향주는 태그 존재    

- h1 ~ h6
- details
- strong
- em
- mark
- cite
- q
- blockquote
- time
- code
- ...


### 미디어 관련 태그
: 미디어 유형을 위한 태그  

- audio
- video
- picture
- track



## block and inline element
: html4 기준으로 엘리먼트를 분류하는 방법   
: html5 기준으로 [콘텐츠 모델](./html-content-model.md)을 통해 엘리먼트 분류   


**block element**     
: (부모 요소의 전체 공간) 전체 너비를 차지하는 엘리먼트    
: 전체 너비를 차지하므로 새 줄에서 시작    
: 하위 요소로 블록 엘리먼트와 인라인 엘리먼트 전부 포함 가능   


**inline element**  
: 라인에서 시작하여 콘텐츠만큼 너비를 차지하는 엘리먼트   
: 하위 요소로 인라인 엘리먼트만 포함 가능   



## optional tag
: 파일 크기, 가독성 등을 위해 일부 시작 태그와 종료 태그를 생략하는 태그     
: 속성을 갖고 있는 시작 태그는 생략 불가  

https://html.spec.whatwg.org/multipage/syntax.html#optional-tags


```html
<ul>
    <li>1
    <li>2
    <li>3
</ul>
```



[top](#)
