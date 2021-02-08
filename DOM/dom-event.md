# DOM Event     
: 객체에 이벤트를 등록하고 트리 구조를 통해 이벤트가 전달되는 시스템     

이벤트  
: 객체와 상호 작용을 하기 위한 방법  



## 이벤트 등록  


### 1. 인라인 이벤트
: 요소의 이벤트 속성에 이벤트 등록

```html
<tag onclick="(e) => {}">
```



### 2. 이벤트 핸들러
: 객체의 EventHandler 속성을 통해 이벤트 등록   
: 동일한 이벤트 속성의 이벤트를 여러개 등록할 경우 마지막으로 정의된 이벤트만 처리     

```js
var el = document.getElementById('');
el.onclick = (e) => {};
```



### 3. 이벤트 리스너   
: 객체에 이벤트를 처리하는 이벤트 리스너 등록      
: 이벤트 리스터는 EventTarget 인터페이스를 구현    

```js
var el = document.getElementById('');

el.addEventListener('click', callback, 'use-capture');
el.removeEventListener('click', callback, 'use-capture');

function callback(e) {
    // 이벤트가 발생하면 호출되는 함수 첫번째 인수로 이벤트 객체가 전달됨
    // 이벤트 객체는 Event 인터페이스를 구현한 객체  
}
```



## 이벤트 전달
: 객체에 등록한 이벤트가 객체의 트리 구조를 통해 전달  


**이벤트 버블링**    
: 하위 노드가 이벤트를 먼저 받은 다음 상위 노드에게 전달


**이벤트 캡처링**  
: 상위 노드가 이벤트를 먼저 받은 다음 하위 노드에게 전달  



[top](#)
