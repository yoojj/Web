# Web Component
https://www.webcomponents.org/  

: UI를 구성하는 코드나 기능을 재사용 목적으로 캡슐화    
: 웹 애플리케이션에서 사용하기 위해 새로 정의한 커스텀 엘리먼트   
: 컴포넌트끼리 결합이 가능해야하며 컴포넌트의 확장성을 고려하여 정의  

[+ Component Architecture](https://github.com/yoojj/CS/blob/master/Software/Architecture/architectural-style/component-based.md)


**구성 요소**
- [HTML Template](#html-template)
- [Shadow DOM](#shadow-dom)
- [Custom Element](#custom-element)
- [HTML Import](html-import)


**구현**
- Polymer (구글)
- X-Tags (파이어폭스)
- Bosonic
- React
- ...



## HTML Template
: 동일하게 반복되는 마크업 구조를 템플릿 태그안에 기술하여 재사용  
: JS로 호출-사용하기 전까지 템플릿 태그 안에 존재하는 엘리먼트와 스타일은 렌더링되지 않음


```html
<!-- 템플릿 작성 -->
<template id="someTemplate">
    <!-- 템플릿 안에 있는 엘리먼트들은 렌더링되지 않음 - document fragment -->
    <div></div>

    <!-- 리소스 내려받지 않음 -->
    <img src="">
</template>


<!-- 템플릿 사용 -->
<script>
var template = document.querySelector('#someTemplate');
template.content.querySelector('img').src = '';
document.body.appendChild(template.content.cloneNode(true));
</script>
```



## Shadow DOM
http://w3c.github.io/webcomponents/spec/shadow/


**shadow tree**  
: 독립된 범위가 지정된 DOM의 하위 tree 지칭  


**shadow host**  
: shadow tree에 연결된 요소


```html
<!-- createShadowRoot : 예전 방식 -->
<div id="box"></div>

<script>
const box = document.querySelector('#box');
const shadow = box.createShadowRoot({mode: 'open'});
shadow.innerHTML = '<h1>shadow dom</h1>';
</script>


<!-- attachShadow -->
<div id="box"></div>

<script>
var box = document.querySelector('#box');
var shadow = box.attachShadow({mode: 'open'});
shadow.innerHTML = '<h1>shadow dom</h1>';
</script>
```



## Custom Element
: html5 규격에 없는 요소를 생성하거나 기존 요소 확장  

https://html.spec.whatwg.org/multipage/custom-elements.html#autonomous-custom-element


```html
<!-- 커스텀 엘리먼트 정의 -->
<script>
class SomeElement extends HTMLElement {
    constructor(){
        super();
        // Shadow DOM
        // const shadow = this.attachShadow({mode: 'open'});
    }
}

customElements.define('box-custom', SomeElement);
</script>

<!-- 요소 충돌 방지를 위해 이름에 대시 기호 사용 -->
<box-custom>
    <h1>custom element</h1>
</box-custom>


<!-- 엘리먼트 확장 -->
<script>
class BtnElement extends HTMLButtonElement { .. }
customElements.define('btn-custom', BtnElement, {extends:'button'});
</script>

<button is="btn-custom">click</button>
```



### Life cycle

메소드 | 설명
---|---
connectedCallback        | document에 커스텀 엘리먼트 추가-연결 마다 호출
disconnectedCallback     | document에서 커스텀 엘리먼트 제거-연결 해제시 호출
adoptedCallback          | 커스텀 엘리먼트가 새 document로 이동시 호출  
attributeChangedCallback | 커스텀 엘리먼트의 속성 변경-추가-제거시 호출  



## HTML Import
: hmlt, css, js를 하나로 묶고 link를 통해 사용  

```html
<link rel="import" href="custom-element.html">
<custom-element></custom-element>


<!-- import는 바로 로딩되어 onload 속성으로 제어 -->
<script async>
function handleLoad(e) {}
function handleError(e) {}
</script>

<link rel="import" href="custom-element.html" onload="handleLoad(e)" onerror="handleError(e)">
<custom-element></custom-element>
```



[top](#)
