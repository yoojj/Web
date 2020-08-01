# XMLHttpRequest API       
https://xhr.spec.whatwg.org/


속성 | 설명
---|---
XMLHttpRequest.readyState           | 객체 상태 반환  
XMLHttpRequest.response             | 요청 결과 반환
XMLHttpRequest.responseXML          | 요청 결과 반환
XMLHttpRequest.responseText         | 요청 결과를 문자열 형태로 반환
XMLHttpRequest.responseType         | HTTP 응답 타입 반환
XMLHttpRequest.responseURL          | HTTP 응답 URL 반환
XMLHttpRequest.status               | HTTP 응답 코드 반환
XMLHttpRequest.statusText           | HTTP 응답 문자열 반환
XMLHttpRequest.timeout              | 요청을 종료할 시간 설정
XMLHttpRequest.upload               | 업로드 관련 객체 반환


- XMLHttpRequest.abort() : 요청 종료
- XMLHttpRequest.getAllResponseHeaders() 
- XMLHttpRequest.getResponseHeader() : 요청 헤더 반환
- XMLHttpRequest.open() : 요청 설정
- XMLHttpRequest.overrideMimeType() : MIME 타입 지정   
- XMLHttpRequest.send() : 요청 발송
- XMLHttpRequest.setRequestHeader() : 요청 헤더 설정


**이벤트 핸들러**    
- onloadstart()
- onprogress()
- onabort()
- onerror()
- onload()
- ontimeout()
- onloadend()
- onreadystatechange()


ex.

```js
// 1. 객체 생성
var xhr = new XMLHttpRequest();

// 2. 헤더 및 요청 정보 설정
xhr.setRequestHeader('Content-type', 'application/json');
xhr.open('POST', 'url', true);

// 3. 타임아웃 설정
xhr.timeout = 3000;


// readyState가 변경되면 onreadystatechange 이벤트 발생
// readyState가 총 5번 변경되므로 onreadystatechange 이벤트도 5번 발생
// xhr.onreadystatechange = function(){}
// xhr.onload = function() {}
xhr.onload = function() {
    if(this.readyState === XMLHttpRequest.DONE && this.status === 200){
        console.log(this.responseText);
    } else {
        console.log ('error');
    }
}


// 타임아웃 됐을 경우
xhr.ontimeout = function(e){
};


xhr.send();
```



## XMLHttpRequest.readyState
: XMLHttpRequest 상태 반환

값 | 상태 | 설명
---|---|---
0 | UNSENT | 객체는 생성되었으나 open() 메소드를 통해 요청이 초기화되지 않음
1 | OPENED | open() 메소드 호출
2 | HEADERS_RECEIVED | send() 메소드 호출
3 | LOADING | 요청 처리중이며 일부 데이터만 수신
4 | DONE    | 모든 요청 처리



## XMLHttpRequest.upload
: XMLHttpRequestUpload 객체 반환    
: 서버에 데이터를 업로드하는 상태 모니터링   



[top](#)
