# Web Component
: UI를 구성하는 코드나 기능을 재사용 목적으로 캡슐화    
: 웹 애플리케이션에서 사용하기 위해 새로 정의한 커스텀 엘리먼트   
: 컴포넌트끼리 결합이 가능해야하며 컴포넌트의 확장성을 고려하여 정의   
! v0은 구글에서 제안한 사양이며 v1이 표준 사양   


- [HTML Template](#html-template)
- [Shadow DOM](#shadow-dom)
- [Custom Element](#custom-element)
- [<s>HTML Import</s>](html-import)


**구현**
- Polymer
- X-Tags
- Bosonic
- React
- ...


**웹 컴포넌트 공유**  
https://www.webcomponents.org/    



## HTML Template
: 동일하게 반복되는 마크업을 템플릿 태그안에 기술하고 이를 재사용     
: JS로 호출하기 전까지 템플릿 태그 안에 존재하는 엘리먼트와 스타일은 렌더링되지 않음


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
https://www.w3.org/TR/shadow-dom/


**shadow tree**  
: 독립된 범위가 지정된 DOM의 하위 tree 지칭  


**shadow host**  
: shadow tree에 연결된 요소


```html
<!-- createShadowRoot() 예전 방식 -->
<div id="box"></div>

<script>
var box = document.querySelector('#box');
var shadow = box.createShadowRoot({mode: 'open'});
shadow.innerHTML = '<h1>shadow dom</h1>';
</script>


<!-- attachShadow() -->
<div id="box"></div>

<script>
var box = document.querySelector('#box');
var shadow = box.attachShadow({mode: 'open'});
shadow.innerHTML = '<h1>shadow dom</h1>';
</script>
```



## Custom Element
: html5 규격에 없는 요소를 생성하거나 기존 요소를 확장    

https://html.spec.whatwg.org/multipage/custom-elements.html#autonomous-custom-element


```html
<!-- 커스텀 엘리먼트 정의 -->
<script>
class CustomElement extends HTMLElement {
    constructor(){
        super();
        // Shadow DOM
        // var shadow = this.attachShadow({mode: 'open'});
    }

    get fn()
    set fn()
}

customElements.define('custom-element', CustomElement);
</script>

<!-- 태그의 충돌을 방지하기 위해 이름에 대시 사용 -->
<custom-element>
    <h1>custom element</h1>
<!-- 커스텀 엘리먼트는 void element로 정의할 수 없음 -->
</custom-element>


<!-- 기존 엘리먼트 확장 -->
<script>
class BtnElement extends HTMLButtonElement {
    constructor() {
        super();
        this.addEventListener('click', e => { });
    }
}

customElements.define('btn-custom', BtnElement, {extends:'button'});
</script>

<button is="btn-custom">click</button>
```



### Lifecycle

메소드 | 설명
---|---
constructor              | 인스턴스가 생성되거나 업데이트시 호출  
connectedCallback        | DOM에 커스텀 엘리먼트가 추가될 때 마다 호출
disconnectedCallback     | DOM에서 커스텀 엘리먼트 제거될 때 마다 호출
attributeChangedCallback | 커스텀 엘리먼트의 속성이 변경-추가-제거시 호출  
adoptedCallback          | 커스텀 엘리먼트가 새 document로 이동시 호출  


```js
class CustomElement extends HTMLElement {
    constructor() {
        super();
    }

    connectedCallback() {}

    disconnectedCallback() {}

    attributeChangedCallback(attrName, oldVal, newVal) {}
}
```



## HTML Import
: hmlt, css, js를 하나로 묶고 link 태그를 통해 사용    
: Web Components v1에서 없어짐        

```html
<link rel="import" href="custom-element.html">
<custom-element></custom-element>


<!-- import는 바로 로딩되므로 onload 속성으로 제어 -->
<script async>
function handleLoad(e) {}
function handleError(e) {}
</script>

<link rel="import" href="custom-element.html" onload="handleLoad(e)" onerror="handleError(e)">
<custom-element></custom-element>
```



[top](#)
