# XMLHttpRequest API       
https://xhr.spec.whatwg.org/


속성 | 설명
---|---
XMLHttpRequest.onreadystatechange	| readyState가 변경될 때마다 실행할 핸들러 지정
XMLHttpRequest.readyState           | 객체 상태에 대한 값 반환  
XMLHttpRequest.response             | 요청 결과 반환
XMLHttpRequest.responseXML          | 요청 결과 반환
XMLHttpRequest.responseText         | 요청 결과를 문자열 형태로 반환
XMLHttpRequest.responseType         | HTTP 응답 타입 반환
XMLHttpRequest.responseURL          | HTTP 응답 URL 반환
XMLHttpRequest.status               | HTTP 응답 코드 반환
XMLHttpRequest.statusText           | HTTP 응답 문자열 반환


- XMLHttpRequest.abort()
- XMLHttpRequest.getAllResponseHeaders()
- XMLHttpRequest.getResponseHeader()
- XMLHttpRequest.open()
- XMLHttpRequest.overrideMimeType()
- XMLHttpRequest.send()
- XMLHttpRequest.setRequestHeader()


```js
// 1. 객체 생성
var xhr = new XMLHttpRequest();


// readyState가 변경되면 onreadystatechange 이벤트 발생
// readyState가 총 5번 변경되므로 onreadystatechange 이벤트도 5번 발생

// xhr.onreadystatechange = function(){}
// xhr.onload = function() {}
xhr.onload = function() {
    if(this.readyState === XMLHttpRequest.DONE && this.status === 200){

    } else {
        console.log ( "Error!");
    }
}

xhr.setRequestHeader('Content-type', 'application/json');
xhr.open('POST', url, true);
xhr.send();
```



## XMLHttpRequest.readyState
: 객체의 상태에 따라 0 ~ 4의 값을 저장

- 0 : 요청이 초기화되지 않음
- 1 : 서버와 연결
- 2 : 요청 수신
- 3 : 요청 처리중
- 4 : 요청이 처리되고 응답 준비중



[top](#)
